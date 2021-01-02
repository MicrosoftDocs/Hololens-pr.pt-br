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
ms.openlocfilehash: 3e06540dd7dca8892cd69abaf9a318d46ca0f3f2
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253138"
---
# Registro corporativo de dispositivos do HoloLens no endereço MAC, ambiente Wi-Fi restrito

Este documento descreverá um cenário comum que identificamos em ambientes do cliente em que o Wi-Fi é restrito por endereços MAC, ou os certificados são necessários para se juntar a redes sem fio.

## Cenário de exemplo:

Muitos clientes em ambientes seguros têm restrições em suas redes Sem fio ou com fio, o que permitirá que apenas dispositivos aprovados (baseados em Endereços MAC) se conectem com êxito (com a filtragem de endereços MAC em um Ponto de Acesso Sem Fio ou em um servidor DHCP). Além disso, algumas redes Sem fio podem ser protegidas com PEAP, o que exige que um certificado seja aplicado ao dispositivo antes de poder autenticar a rede Sem fio com êxito.

Dois problemas importantes podem surgir com dispositivos do HoloLens, o que pode fazer com que os atrasos e o trabalho manual se associem aos dispositivos do HoloLens à rede.

- O certificado PEAP sem fio deve ser aplicado ao dispositivo antes que o dispositivo ingresse na rede sem fio com êxito.
- O endereço MAC do adaptador de rede Wi-Fi do HoloLens deve ser registrado.

Estes são os principais desafios para isso:

1. No momento, o endereço MAC só pode ser identificado no aplicativo configurações no dispositivo ou no Intune após um registro bem-sucedido do Intune.
2. Sem o endereço MAC, o dispositivo não pode se conectar à rede Wi-Fi para iniciar o registro.
3. As soluções manuais para esses desafios exigem o envolvimento do técnico com os dispositivos.

## Soluções

Há muitas maneiras de melhorar essa situação, dependendo da infraestrutura disponível no ambiente.

| Solução | Benefícios | Requisitos |
| --- | --- | --- |
| Pacote de provisionamento com o adaptador Ethernet | Melhora a experiência do OOBE e permite uma experiência técnica mais rápida. | HoloLens compatível com USB C HubTechnician ainda precisará interagir com o dispositivo para captura MAC e finalização OOBE |
| Piloto automático com registro do Intune na Ethernet | A conexão de etapa única e o registro do dispositivo com o cliente a captura environmentMAC podem ser concluídas sem interagir com o dispositivo | Intune habilitado para o adaptador de rede USB-C Compatível com Microsoft Azure Active Directory TenantHoloLens do cliente |
| Relatório automatizado de endereços MAC | Quando dispositivos forem registrados no locatário do Intune, script o relatório do endereço MAC para o técnico. | Commandlets do Windows PowerShell do Intune |

## Pacote de provisionamento com o adaptador Ethernet

> [!NOTE] 
> Se a rede com fio também estiver sujeita a restrições de MAC, o endereço MAC do adaptador ou do hub Ethernet deve ser pré-impresso. Tome cuidado com esse Hub, pois permite o acesso à rede de outros dispositivos.

### Requisitos

- Porta de rede com fio com acesso à rede do cliente
- Hub USB-C compatível com o HoloLens, que contém um adaptador Ethernet, o Hub que não &#39; requer nenhum driver adicional ou instalações de aplicativos devem ser apropriados.
- Pacote de provisionamento contendo:
  - Contendo certificados e informações de rede sem fio
  - Opcionalmente, contendo informações de inscrição para a Organização&#39;s do Microsoft Azure Active Directory
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

## AutoPilot com Inscrição do Intune

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
6. O endereço Wi-Fi MAC estará visível no Portal do Intune

![Endereço MAC por meio do Intune](images/mac-address-intune.jpg)

7. O técnico adicionará esse endereço MAC como um dispositivo permitido.

### Benefícios

Isso permitirá que uma experiência de implantação &quot;Atalhada&quot; para o Técnico, com a capacidade de um dispositivo ser acessado no Microsoft Azure Active Directory e no Intune sem o técnico ter que usar o dispositivo ou interagir manualmente com o ambiente do HoloLens.

## Relatórios de endereços MAC para o técnico

### Requisitos

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

### Processo

Depois que o Enrolment do Intune tiver sido concluído, o técnico executaria o script acima para recuperar o endereço MAC.
