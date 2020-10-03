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
ms.openlocfilehash: 2b0ed266389ccc5a21117a604a6eb0abd214d4d1
ms.sourcegitcommit: 1793f53f9e1cc63ac40edc09e65bb4beb80a4575
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "11093216"
---
# Registro corporativo de dispositivos do HoloLens no endereço MAC, ambiente Wi-Fi restrito

Este documento descreverá um cenário comum que identificamos em ambientes do cliente em que o Wi-Fi é restrito por endereços MAC, ou os certificados são necessários para se juntar a redes sem fio.

## Cenário de exemplo:

Muitos clientes em ambientes seguros têm restrições em relação a redes sem fio ou com fio, que só permitirão que os dispositivos aprovados (com base nos endereços MAC) sejam conectados com êxito (com a filtragem de endereços MAC em um ponto de acesso sem fio ou em um servidor DHCP). Além disso, algumas redes sem fio podem ser protegidas com o PEAP, o que requer que um certificado seja aplicado ao dispositivo antes de poder autenticar com êxito a rede sem fio.

Dois problemas importantes podem surgir com dispositivos do HoloLens, o que pode fazer com que os atrasos e o trabalho manual se associem aos dispositivos do HoloLens à rede.

- O certificado PEAP sem fio deve ser aplicado ao dispositivo antes que o dispositivo ingresse na rede sem fio com êxito.
- O endereço MAC do adaptador de rede Wi-Fi do HoloLens deve ser registrado.

Estes são os principais desafios para isso:

1. No momento, o endereço MAC só pode ser identificado no aplicativo configurações no dispositivo ou no Intune após um registro bem-sucedido do Intune.
2. Sem o endereço MAC, o dispositivo não pode se conectar à rede Wi-Fi para iniciar o registro.
3. As soluções manuais para esses desafios exigem o envolvimento do técnico com os dispositivos.

## Soluções

Há várias maneiras de melhorar essa situação, dependendo da infraestrutura disponível no ambiente.

| Solução | Benefícios | Requisitos |
| --- | --- | --- |
| Pacote de provisionamento com o adaptador Ethernet | Melhora a experiência do OOBE e permite uma experiência técnica mais rápida. | A HubTechnician USB-C do HoloLens compatível ainda será necessária para interagir com o dispositivo para MAC Capture e a finalizar o OOBE |
| Piloto automático com registro do Intune na Ethernet | A conexão de etapa única e o registro do dispositivo com o cliente a captura environmentMAC podem ser concluídas sem interagir com o dispositivo | Intune habilitado para o cliente AAD TenantHoloLens adaptador de rede USB-C compatível com o cliente |
| Relatório automatizado de endereços MAC | Quando dispositivos forem registrados no locatário do Intune, script o relatório do endereço MAC para o técnico. | Intune PowerShell commandlets |

## Pacote de provisionamento com o adaptador Ethernet

> [!NOTE] 
> Se a rede com fio também estiver sujeita a restrições de MAC, o endereço MAC do adaptador ou do hub Ethernet deve ser pré-impresso. Tome cuidado com esse Hub, pois permite o acesso à rede de outros dispositivos.

### Requisitos

- Porta de rede com fio com acesso à rede do cliente
- Hub USB-C compatível com o HoloLens, que contém um adaptador Ethernet, o Hub que não &#39; requer nenhum driver adicional ou instalações de aplicativos devem ser apropriados.
- Pacote de provisionamento contendo:
  - Contendo certificados e informações de rede sem fio
  - Opcionalmente, que contém informações de registro para o &#39; Azure Active Directory da organização
  - Contendo outras configurações de provisionamento necessárias

### Processo

O processo pode variar dependendo do nível de software do dispositivo. Se o dispositivo tiver a [Atualização do maio do 2004](hololens-release-notes.md#windows-holographic-version-2004), siga as etapas abaixo.

1. Coloque o pacote de configuração na raiz de um pente USB e conecte-o ao Hub.
2. Conecte o cabo Ethernet ao Hub.
3. Conecte o hub USB-C ao dispositivo do HoloLens.
4. Ative o dispositivo do HoloLens e use o dispositivo.
5. Pressione o **Botão Diminuir Volume e Ligar** para aplicar o Pacote de Provisionamento.
6. O técnico agora pode acompanhar o OOBE e, quando concluir, abrir o aplicativo de configurações e recuperar o endereço MAC do dispositivo.

Se o dispositivo tiver um build de sistema operacional antes de a [Atualização do maio do 2004](hololens-release-notes.md#windows-holographic-version-2004), siga as etapas abaixo.

1. Ative o dispositivo do HoloLens e conecte-o a um PC.
2. O dispositivo deve ser exibido no PC como um dispositivo de armazenamento de arquivos.
3. Copiar o pacote de provisionamento para o dispositivo
4. Conecte o cabo Ethernet ao Hub.
5. Conecte o hub USB-C ao dispositivo do HoloLens.
6. Use o dispositivo.
7. Pressione o botão **Diminuir Volume e Ligar** para aplicar o Pacote de Provisionamento.
8. O técnico agora pode acompanhar o OOBE e, quando concluir, abrir o aplicativo de configurações e recuperar o endereço MAC do dispositivo.

### Benefícios

Isso permitirá um &quot;toque único&quot; do dispositivo para aplicar o pacote de provisionamento correto e coletar o endereço MAC do dispositivo. [Os pacotes de provisionamento podem ser criados seguindo as orientações aqui.](https://docs.microsoft.com/hololens/hololens-provisioning)

## Piloto automático com o Intune Enrolment

### Requisitos

- Porta de rede com fio com acesso à rede do cliente
- Dispositivos do HoloLens executando o Windows Holographic 2004
- Hub USB-C compatível com HoloLens
- Configurar e habilitar o Intune para o locatário do cliente
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

### Processo

1. Conecte o Hub USB-C e o cabo ethernet no dispositivo do HoloLens 2.
2. Ative o HoloLens 2.
3. O dispositivo deve se conectar automaticamente à Internet no OOBE por meio do adaptador Ethernet, detectar a configuração piloto automático e se registrar automaticamente com o Microsoft Azure Active Directory e o Intune
4. O dispositivo aplica os certificados Wi-Fi necessários e outras configurações conforme necessário por meio do Intune
5. Quando for concluído, o técnico será capaz de carregar o portal do Intune (Gerenciador de pontos de extremidade) e detalhar na página de propriedades do dispositivo no **Home -> Dispositivos -> Nome do dispositivo -> Hardware**
6. O endereço MAC WiFi ficará visível no portal do Intune

![Endereço MAC por meio do Intune](images/mac-address-intune.jpg)

7. O técnico adicionará esse endereço MAC como um dispositivo permitido.

### Benefícios

Isso permitirá que uma experiência de implantação &quot;atalhada&quot; para o técnico, com a capacidade de um dispositivo ser acessado no AAD e no Intune sem o técnico ter que usar o dispositivo ou interagir manualmente com o ambiente do HoloLens.

## Relatórios de endereços MAC para o técnico

### Requisitos

- Autorização do &quot;Powershell do Intune Graph&quot; contra o locatário do cliente
- Instalação do PowerShell do Intune Graph na máquina dos técnicos.
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

### Processo

Depois que o Enrolment do Intune tiver sido concluído, o técnico executaria o script acima para recuperar o endereço MAC.
