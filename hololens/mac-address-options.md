---
title: Registro Enterprise de dispositivos HoloLens no ambiente de Wi-Fi restrito por endereço MAC
description: Como usar o endereço MAC para a rede em dispositivos HoloLens 2
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 7938a433921a096913986f5eccff953fd17f1534
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639430"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>Registro Enterprise de dispositivos HoloLens no ambiente de Wi-Fi restrito por endereço MAC

Este documento descreverá um cenário comum que identificamos nos ambientes do cliente, em que o Wi-Fi é restrito por endereços MAC ou em que é necessário ter certificados para ingressar em redes sem fio.

## <a name="example-scenario"></a>Cenário de Exemplo

Muitos clientes em ambientes seguros têm restrições nas redes sem fio ou com fio que só permitirão a conexão bem-sucedida de dispositivos aprovados (baseados em endereços MAC). Isso pode ser imposto por meio da filtragem de endereço MAC em um ponto de acesso sem fio ou por meio de um servidor DHCP. Além disso, algumas redes sem fio podem ser protegidas com o PEAP, o que exige a aplicação de um certificado ao dispositivo antes da autenticação na rede sem fio.

Neste cenário, dois requisitos principais podem introduzir atrasos ou exigir intervenção manual ao ingressar os dispositivos HoloLens na rede:

- O certificado PEAP sem fio precisa ser aplicado ao dispositivo antes que o dispositivo ingresse na rede sem fio com êxito.
- O endereço MAC do adaptador de rede Wi-Fi do HoloLens precisa ser registrado.

Os principais desafios nos requisitos acima são:

1. No momento, o endereço MAC só pode ser identificado no aplicativo Configurações do dispositivo ou no Intune após um registro bem-sucedido.

2. Sem o endereço MAC, o dispositivo não pode ingressar na rede Wi-Fi para iniciar o registro.

3. As soluções alternativas manuais para esses desafios exigem que um técnico interaja com o dispositivo.

## <a name="solutions"></a>Soluções

Há muitas maneiras de aprimorar essa situação, dependendo da infraestrutura disponível no ambiente.

| Solução | Benefícios | Requisitos |
| --- | --- | --- |
| Pacote de provisionamento com o adaptador Ethernet | Aprimora a experiência do OOBE e permite uma experiência técnica mais rápida. | O Hub USB-C compatível com o HoloLens com o adaptador Ethernet e o técnico ainda precisarão interagir com o dispositivo para a captura do MAC e a finalização do OOBE |
| Autopilot com o registro do Intune pela Ethernet | Essa é uma conexão de etapa única e indica o registro do dispositivo no ambiente do cliente. A captura do MAC pode ser concluída sem a necessidade de interagir com o dispositivo | Habilitado para o Intune para o locatário do AAD do cliente e um adaptador Ethernet USB-C compatível com o HoloLens |
| Relatório automatizado de endereços MAC | Quando os dispositivos são registrados com o locatário do Intune, um script pode relatar o endereço MAC ao técnico. | Cmdlets do PowerShell no Intune |

## <a name="provisioning-package-with-ethernet-adaptor"></a>Pacote de provisionamento com o adaptador Ethernet

> [!NOTE] 
> Se a rede com fio também estiver sujeita às restrições do MAC, o endereço MAC do Hub USB-C com o adaptador Ethernet também precisará ser pré-aprovado. Tenha cuidado com esse adaptador, pois ele permitirá o acesso à rede em outros dispositivos.

### <a name="requirements"></a>Requisitos

- Porta de rede com fio com acesso à rede do cliente
- Hub USB-C compatível com o HoloLens com adaptador Ethernet – Qualquer adaptador que não exige drivers nem a instalação de aplicativos adicionais deve ser adequado.
- Pacote de provisionamento contendo:
  - Certificados e informações da rede sem fio
  - Opcionalmente, informações de registro do Azure AD da organização
  - Outras configurações de provisionamento necessárias

### <a name="process"></a>Processar

O processo pode variar dependendo do nível de software do dispositivo. Se o dispositivo tiver a [atualização de maio de 2004](hololens-release-notes.md#windows-holographic-version-2004), siga as etapas abaixo.

1. Coloque o pacote de provisionamento na raiz de um pen drive e conecte-o ao Hub.
2. Conecte o cabo Ethernet ao Hub e ao adaptador Ethernet.
3. Conecte o Hub USB-C ao dispositivo HoloLens.
4. Ligue o HoloLens e o dispositivo.
5. Pressione o **botão Abaixar Volume e Energia** para aplicar o pacote de provisionamento.
6. O técnico já pode seguir o OOBE e, quando ele terminar, abra o Aplicativo Configurações para recuperar o endereço MAC do dispositivo.

Se o dispositivo tiver um build do sistema operacional anterior à [atualização de maio de 2004](hololens-release-notes.md#windows-holographic-version-2004), siga as etapas abaixo.

1. Ligue o HoloLens e conecte o dispositivo a um computador.
2. O dispositivo deve ser exibido no computador como um dispositivo de armazenamento de arquivos.
3. Copie o pacote de provisionamento para o dispositivo
4. Conecte o cabo Ethernet ao hub.
5. Conecte o Hub USB-C ao dispositivo HoloLens.
6. Ligue o HoloLens
7. Pressione o **botão Abaixar Volume e Energia** para aplicar o pacote de provisionamento.
8. O técnico já pode seguir o OOBE e, quando ele terminar, abra o Aplicativo Configurações para recuperar o endereço MAC do dispositivo.

### <a name="benefits"></a>Benefícios

Isso permitirá um "Toque único" do dispositivo para aplicar o pacote de provisionamento correto e coletar o endereço MAC do dispositivo. [Os pacotes de provisionamento podem ser criados seguindo as diretrizes descritas aqui.](hololens-provisioning.md)

## <a name="autopilot-with-intune-enrollment"></a>Autopilot com o registro do Intune

### <a name="requirements"></a>Requisitos

- Porta de rede com fio com acesso à rede do cliente
- Dispositivos HoloLens que executam o Windows Holographic 2004
- Adaptador Ethernet USB-C compatível com o HoloLens
- Intune configurado e habilitado para o locatário do cliente
- Dispositivo registrado para o Autopilot e importado para o locatário do cliente
- Políticas do Intune definidas para o dispositivo:
   - Certificados e informações da rede sem fio
   - Outras configurações de provisionamento necessárias

Isso permitirá que um cliente com requisitos avançados de rede registre os dispositivos em uma abordagem escalonável e sem interferência

Os pré-requisitos adicionais serão necessários, conforme descrito abaixo:
1. [Habilitar o locatário para a versão prévia do Autopilot](hololens2-autopilot.md).
1. Criar as políticas do HoloLens para substituir o pacote de provisionamento no Intune.
1. Criar as políticas do Intune para o HoloLens.
1. Atribuir os dispositivos ao grupo correto.

### <a name="process"></a>Processar

1. Conecte o cabo Ethernet ao adaptador e o adaptador à porta USB-C no dispositivo HoloLens 2.

2. Ligue o HoloLens.

3. O dispositivo se conectará automaticamente à Internet durante o OOBE por meio do adaptador Ethernet. Ele detectará a configuração do Autopilot e será registrado automaticamente no Azure AD e no Intune.

4. O dispositivo aplicará os certificados Wi-Fi necessários e outras configurações conforme necessário por meio do Intune.

5. Quando concluído, o técnico pode carregar o Portal do Intune (Endpoint Manager) e fazer uma pesquisa na página de propriedades do dispositivo em **Página Inicial -> Dispositivos -> NomeDoDispositivo -> Hardware**.

6. O endereço MAC do Wi-Fi estará visível no Portal do Intune.

   ![Endereço MAC por meio do Intune](images/mac-address-intune.jpg)

7. O técnico adicionará esse endereço MAC como um dispositivo permitido.

### <a name="benefits"></a>Benefícios

Isso permitirá uma experiência de implantação "sem contato" para o técnico, com o dispositivo podendo ir do estado original ao registro no Azure AD e no Intune sem que o técnico precise usar o dispositivo ou interagir manualmente com o ambiente do HoloLens.

## <a name="reporting-of-mac-addresses-to-the-technician"></a>Relatório de endereços MAC para o técnico

### <a name="requirements"></a>Requisitos

- Autorização do "PowerShell do Intune Graph" no locatário do cliente
- Instalação do PowerShell do Intune Graph no computador dos técnicos.
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Acesso de leitura nos elementos dos "Dispositivos Gerenciados" do Intune. (Operador de suporte técnico ou superior ou uma função personalizada)

No momento, não há uma forma "simples" para disparar um comando de automação baseado na registro de um novo dispositivo no Intune. Portanto, esse comando fornecerá ao técnico uma forma simples de recuperar o endereço MAC sem precisar fazer logon no portal e recuperá-lo manualmente.

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

Isso retornará o nome e o endereço MAC de todos os dispositivos HoloLens que foram registrados nos últimos 30 dias.

![Endereço MAC por meio do PowerShell](images/mac-address-powershell.jpg)

### <a name="process"></a>Processar

Depois que o registro do Intune for concluído, o técnico executará o script acima para recuperar o endereço MAC.
