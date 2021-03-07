---
title: Registro corporativo de dispositivos do HoloLens no endereço MAC, ambiente Wi-Fi restrito
description: Como o endereço MAC para a rede em dispositivos do HoloLens 2
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
ms.openlocfilehash: fe365248332f8e78b15ab362f169b84e48dfe594
ms.sourcegitcommit: 07ffe1bf2f45dcb2ba9d7fbe54b4773a0fb9d525
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393835"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>Registro corporativo de dispositivos do HoloLens no endereço MAC, ambiente Wi-Fi restrito

Este documento descreverá um cenário comum que identificamos em ambientes do cliente em que o Wi-Fi é restrito por endereços MAC, ou os certificados são necessários para se juntar a redes sem fio.

## <a name="example-scenario"></a>Cenário de Exemplo

Muitos clientes em ambientes seguros têm restrições em suas redes sem fio ou com fio que só permitirão que dispositivos aprovados (com base em endereços MAC) se conectem com êxito. Isso pode ser imposto por meio da filtragem de Endereço MAC em um Ponto de Acesso Sem Fio ou por meio de um servidor DHCP. Além disso, algumas redes Sem Fio podem ser protegidas com PEAP, o que exige que um certificado seja aplicado ao dispositivo antes da autenticação na rede Sem Fio.

Neste cenário, dois requisitos principais podem introduzir atrasos ou exigir intervenção manual ao ingressar dispositivos HoloLens na rede:

- O certificado PEAP sem fio deve ser aplicado ao dispositivo antes que o dispositivo ingresse na rede sem fio com êxito.
- O endereço MAC do adaptador de rede Wi-Fi do HoloLens deve ser registrado.

Os principais desafios com os requisitos acima são:

1. No momento, o Endereço MAC só pode ser identificado no aplicativo Configurações no dispositivo ou no Intune após um registro bem-sucedido.
2. Sem o endereço MAC, o dispositivo não pode se conectar à rede Wi-Fi para iniciar o registro.
3. As soluções alternativas manuais para esses desafios exigem que um técnico interaja com o dispositivo.

## <a name="solutions"></a>Soluções

Há muitas maneiras de melhorar essa situação, dependendo da infraestrutura disponível no ambiente.

| Solução | Benefícios | Requisitos |
| --- | --- | --- |
| Pacote de provisionamento com o adaptador Ethernet | Melhora a experiência do OOBE e permite uma experiência técnica mais rápida. | O adaptador e o técnico compatível com o Hub USB-C + Ethernet do HoloLens ainda precisarão interagir com o dispositivo para captura MAC e finalização OOBE |
| Piloto automático com registro do Intune na Ethernet | Esta é uma conexão de etapa única e o registro do dispositivo no ambiente do cliente. A captura MAC pode ser concluída sem a necessidade de interagir com o dispositivo | Intune habilitado para o locatário AAD do cliente e um adaptador Ethernet USB-C compatível com o HoloLens |
| Relatório automatizado de endereços MAC | Quando os dispositivos são registrados com o locatário do Intune, um script pode relatar o endereço MAC ao técnico. | Commandlets do Powershell do Intune |

## <a name="provisioning-package-with-ethernet-adaptor"></a>Pacote de provisionamento com o adaptador Ethernet

> [!NOTE] 
> Se a rede com fio também estiver sujeita a restrições MAC, em seguida, o endereço MAC do adaptador USB-C Hub + Ethernet também precisará ser pré-aprovado. O cuidado deve ser tomado com esse adaptador, pois ele permitirá o acesso à rede de outros dispositivos.

### <a name="requirements"></a>Requisitos

- Porta de rede com fio com acesso à rede do cliente
- Hub USB-C Compatível do HoloLens com adaptador Ethernet – Qualquer adaptador que n&#39ão exige drivers ou instalação de aplicativos adicionais deve ser adequado.
- Pacote de provisionamento contendo:
  - Contendo certificados e informações de rede sem fio
  - Opcionalmente, contendo informações de inscrição para a Organização&#39;s do Microsoft Azure Active Directory
  - Contendo outras configurações de provisionamento necessárias

### <a name="process"></a>Processo

O processo pode variar dependendo do nível de software do dispositivo. Se o dispositivo tiver a [Atualização do maio do 2004](hololens-release-notes.md#windows-holographic-version-2004), siga as etapas abaixo.

1. Coloque o pacote de provisionamento na raiz de um pen drive e conecte-o ao Hub.
2. Conecte o cabo Ethernet ao adaptador Hub + Ethernet.
3. Conecte o Hub USB-C ao dispositivo HoloLens.
4. Ligue o HoloLens e coloque o dispositivo.
5. Pressione o **Botão Diminuir Volume e Ligar** para aplicar o Pacote de Provisionamento.
6. O técnico agora pode seguir o OOBE e, quando concluído, abra o Aplicativo de Configurações para recuperar o Endereço MAC do dispositivo.

Se o dispositivo tiver um build do Sistema Operacional antes da [Atualização do maio do 2004](hololens-release-notes.md#windows-holographic-version-2004), siga as etapas abaixo.

1. Ligue o HoloLens e conecte o dispositivo a um computador.
2. O dispositivo deve ser exibido no computador como um dispositivo de armazenamento de arquivos.
3. Copiar o pacote de provisionamento para o dispositivo
4. Conecte o cabo Ethernet ao Hub.
5. Conecte o Hub USB-C ao dispositivo HoloLens.
6. Colocar o HoloLens
7. Pressione o botão **Diminuir Volume e Ligar** para aplicar o Pacote de Provisionamento.
8. O técnico agora pode seguir o OOBE e, quando concluído, abra o Aplicativo de Configurações para recuperar o Endereço MAC do dispositivo.

### <a name="benefits"></a>Benefícios

Isso permitirá um &quot;toque único&quot; do dispositivo para aplicar o pacote de provisionamento correto e coletar o endereço MAC do dispositivo. [Os pacotes de provisionamento podem ser criados seguindo as orientações aqui.](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="autopilot-with-intune-enrollment"></a>AutoPilot com Inscrição do Intune

### <a name="requirements"></a>Requisitos

- Porta de rede com fio com acesso à rede do cliente
- Dispositivos do HoloLens executando o Windows Holographic 2004
- Adaptador USB-C Compatível com HoloLens
- Configurar e habilitar o Intune para o Locatário do cliente
- Dispositivo registrado para o piloto automático e importado para o locatário do cliente
- Políticas do Intune definidas para o dispositivo:
   - Contendo certificados e informações de rede sem fio
   - Contendo outras configurações de provisionamento necessárias

Isso permitirá que um cliente com requisitos avançados de rede registre os dispositivos em uma abordagem adaptável e dimensionável

Os pré-requisitos adicionais serão necessários, da seguinte maneira:
1. [Habilitar o locatário da visualização AutoPilot](https://docs.microsoft.com/hololens/hololens2-autopilot)
1. Crie as políticas do HoloLens para substituir o pacote de provisionamento no Intune.
1. Criar as políticas do Intune do HoloLens.
1. Atribua os dispositivos ao grupo correto.

### <a name="process"></a>Processo

1. Conecte o cabo ethernet ao adaptador e conecte o adaptador à porta USB-C no dispositivo HoloLens 2.
2. Ligar o HoloLens.
3. O dispositivo deve se conectar automaticamente à Internet durante o OOBE por meio do adaptador Ethernet. Ele deve detectar a configuração do Autopilot e registrar-se automaticamente no Azure AD e no Intune
4. O dispositivo aplicará os Certificados Wi-Fi necessários e outras configurações conforme necessário por meio do Intune
5. Quando concluído, o técnico pode carregar o Portal do Intune (Endpoint Manager) e fazer uma pesquisa na página de propriedades do dispositivo em **Início-> Dispositivos-> DeviceName -> Hardware**
6. O endereço MAC WiFi ficará visível no Portal do Intune

![Endereço MAC por meio do Intune](images/mac-address-intune.jpg)

7. O técnico adicionará esse endereço MAC como um dispositivo permitido.

### <a name="benefits"></a>Benefícios

Isso permitirá que uma experiência de implantação &quot;Atalhada&quot; para o Técnico, com a capacidade de um dispositivo ser acessado no Microsoft Azure Active Directory e no Intune sem o técnico ter que usar o dispositivo ou interagir manualmente com o ambiente do HoloLens.

## <a name="reporting-of-mac-addresses-to-the-technician"></a>Relatórios de endereços MAC para o técnico

### <a name="requirements"></a>Requisitos

- Autorização do &quot; PowerShell do Graph do Intune &quot; em relação ao Locatário do cliente
- Instalação do Windows PowerShell do Intune Graph na máquina de técnicos.
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Acesso de leitura para os elementos de &quot;Dispositivos gerenciados&quot; do Intune. (Operadora de suporte técnico ou acima, ou uma função personalizada)

No presente, não há uma maneira &quot;simples&quot; para acionar um comando de automação baseado na Enrolment de um novo dispositivo no Intune. Portanto, esse comando fornecerá ao técnico uma maneira simples de recuperar o endereço MAC sem precisar fazer logon no portal e recuperá-lo manualmente.

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

Isso retornará o nome e o endereço MAC de todos os dispositivos do HoloLens que tiverem sido inscritos nos últimos 30 dias.

![Endereço MAC por meio do PowerShell](images/mac-address-powershell.jpg)

### <a name="process"></a>Processo

Depois que o Enrolment do Intune tiver sido concluído, o técnico executaria o script acima para recuperar o endereço MAC.
