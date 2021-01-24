---
title: Perguntas frequentes sobre segurança
description: Mantenha-se atualizado com as perguntas e respostas de segurança mais comuns sobre os dispositivos de realidade mista HoloLens.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: pawinfie
ms.author: pawinfie
ms.date: 02/19/2020
keywords: hololens, Windows Mixed Reality, segurança
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: high
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: bradke
ms.openlocfilehash: 0e3b7f40aa6d5163b6d58b7f21b9ea6daa9cc9b4
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284002"
---
# Perguntas Frequentes sobre Segurança do HoloLens (1ª geração)

1. **Que nível de proteção de dados o HoloLens 1 oferece?**
    1. Confira [Criptografia BitLocker do HoloLens (1ª geração)](hololens1-encryption.md)
1. **Que tipo de wireless é usado?**
    1. 802.11ac e Bluetooth 4.1 LE
1. **Qual é o tipo de arquitetura da incorporação?  Por exemplo: ponto de extremidade, malha ou outra coisa?**
    1. O Wi-Fi pode ser usado no modo de infraestrutura para se comunicar com outros pontos de acesso sem fio.
    1. O Bluetooth pode ser usado para falar ponto a ponto entre vários HoloLens se o aplicativo dos clientes oferecer suporte a ele ou a outros dispositivos Bluetooth.
1. **O que é a ID da FCC?**
    1. C3K1688
1. **Em que faixa de frequência e canais o dispositivo opera e é configurável?**
    1. Wi-Fi: a faixa de frequência não é configurável pelo usuário e depende do país de uso. Nos EUA, o Wi-Fi usa dois canais de 2.4 GHz (1-11) e 5 GHz (36-64, 100-165).
    1. Bluetooth: p Bluetooth usa o intervalo padrão de 2.4 - 2.48 GHz.
1. **O dispositivo pode permitir ou bloquear frequências específicas?**
    1. Isso não é controlável pelo usuário/dispositivo.
1. **Qual é o nível de energia para transmitir e receber? Ele é ajustável? O que é o intervalo de operações?**
    1. É possível encontrar nossos padrões de teste de emissões [aqui](https://fccid.io/C3K1688). O intervalo de operações é muito dependente do ponto de acesso e do ambiente, mas equivale a outros telefones, tablets ou PCs de alta qualidade.
1. **O que é o ciclo de vida/duração da operação normal?**
    1. 2 – 3hrs de uso ativo e até 2 semanas de tempo de espera
    1. A duração da bateria não está disponível.
1. **Qual é o comportamento transmissão e recebimento quando uma ferramenta não está no intervalo?**
    1. O recebimento/transmissão do HoloLens acompanha o padrão Wi-Fi/Bluetooth padrão. Na borda do intervalo, você provavelmente perceberá que a entrada ficará instável até que ela se desconecte completamente, mas depois que você voltar a usar a faixa, ela deverá se reconectar rapidamente.
1. **O que é a densidade de implantação por metro quadrado?**
    1. Isso depende da infraestrutura de rede.
1. **O dispositivo pode usar a infraestrutura como cliente?**
    1. Sim
1. **Qual protocolo é usado?**
    1. O HoloLens não usa protocolos proprietários
1. **Frequência de atualização do OS: Qual é a frequência das atualizações do sistema operacional para o HL?  Há um conjunto de agendas?  A Microsoft lança patches de segurança conforme necessário, etc.**
    1. A Microsoft fornece atualizações do sistema operacional para o HoloLens exatamente da mesma forma que é feita no Windows 10. Geralmente, há duas atualizações principais por ano, uma na primavera e outra no outono. Como o HoloLens é um dispositivo Windows, o conceito de atualização é o mesmo de qualquer outro dispositivo Windows. A Microsoft libera os patches de segurança conforme necessário e segue o mesmo conceito utilizado em qualquer dispositivo com Windows.
1. **Blindagem do sistema operacional: quais são as opções de proteção do sistema operacional?  Podemos remover ou desligar aplicativos ou serviços desnecessários?**
    1. O HoloLens se comporta como um smartphone. É comparável a outros dispositivos modernos do Windows. O HoloLens pode ser gerenciado pelo Microsoft Intune ou por outras soluções de gerenciamento de dispositivo modernas, como MobileIron, AirWatch ou Soti. Existem políticas que você pode definir nesses sistemas de gerenciamento para colocar políticas de segurança no dispositivo e para otimizar o seu dispositivo. Também é possível excluir todos os aplicativos desnecessários.
1. **Como os aplicativos de software serão gerenciados e atualizados? Que tipo de controle precisamos ter para definir quais aplicativos são carregados e o processo de atualização de aplicativos para aplicativos que estão na Microsoft Store?**
    1. O HoloLens obtém aplicativos de software somente na Windows Store. É possível instalar somente pacotes de aplicativos Appx, desenvolvidos para o uso do HoloLens. Você pode ver isso na Microsoft Store com um pequeno logotipo ao lado do aplicativo que mostra o dispositivo do HoloLens. Todos os controles que você tiver sobre o gerenciamento de aplicativos da loja também se aplicam ao HoloLens. Você pode usar o conceito da loja oficial ou da loja de negócios. Os aplicativos podem ser carregados por side-load (processo manual para carregar um aplicativo em um dispositivo Windows) ou podem ser gerenciados por meio de um MDM, para que os aplicativos sejam automaticamente extraídos da loja quando necessário.
1. **Qual é a frequência das atualizações dos aplicativos no repositório do HoloLens?**
    1. Como acompanhamos o mesmo conceito da loja da Microsoft e extraímos os aplicativos dali, o ciclo de atualização é determinado pelo desenvolvedor do aplicativo. Todas as opções de gerenciamento que você tem para controlar o mecanismo de atualização na loja também se aplicam ao HoloLens.
1. **Há um recurso de inicialização segura para o HoloLens?**
    1. Sim
1. **Existe uma capacidade de desabilitar ou desconectar o suporte a periféricos do dispositivo?**
    1. Sim
1. **Existe uma capacidade de controlar ou desabilitar o uso de portas no dispositivo?**
    1. O HoloLens só contém duas portas (uma para fones de ouvido e outra para carregar ou se conectar a PCs). Não é possível desabilitar a porta por motivos de funcionalidade e recuperação.
1. **Antivirus, detecção de ponto de extremidade, IPS, lista de permissões de controle de aplicativos – qualquer capacidade de executar antivírus, detecção de ponto de extremidade, IPS, lista de permissão de controle de aplicativo etc.**
    1. O Windows Holographic for Business (pacote comercial) é compatível com a tela inteligente do Windows Defender. Se uma empresa antivírus criar e publicar seus aplicativos na plataforma universal do Windows, eles poderá ser baixado no HoloLens. Até o momento, nenhuma empresa fez isso para o HoloLens.
    1. É possível permitir aplicativos usando a Microsoft Enterprise Store, onde você pode escolher apenas quais aplicativos específicos podem ser baixados. Além disso, por meio do MDM, você pode bloquear quais aplicativos específicos podem ser executados ou até mesmo vistos no dispositivo.
1. **Podemos colocar o dispositivo em quarentena na rede de produção até atualizá-lo se ele estiver off-line por um longo período de tempo?  Ex. O dispositivos está em uma gaveta sem energia por um período (6 meses) e não recebeu atualizações, patches etc.  Quando ele tenta entrar na rede, podemos sinalizar e dizer que você deve atualizar em outra rede antes de ser reclamado para se juntar à rede.**
    1. Isso é algo que pode ser gerenciado no nível da infraestrutura por um MDM ou um servidor local. O dispositivo pode ser sinalizado como não compatível se não atender a uma versão de atualização especificada.
1. **A Microsoft inclui portas traseiras ou acesso a serviços que permitem que a Microsoft se conecte ao dispositivo para compartilhamento de tela ou suporte remoto à vontade?**
    1. Não
1. **Quando um certificado PKI está sendo gerado para uma comunicação confiável, queremos que o certificado seja gerado no dispositivo, para que possamos saber que é apenas desse dispositivo, exclusivo para esse dispositivo, e não pode ser exportado ou usado para representar o dispositivo. Isso é verdadeiro no HoloLens? Caso contrário, existe uma possível mitigação?**
    1. O CSR para SCEP é gerado no próprio dispositivo. O Intune e o conector SCEP local ajudam a proteger as solicitações por conta própria, adicionando e verificando uma cadeia de desafio que é enviada ao cliente.
    1. Como o HoloLens (1ªe 2ª geração) têm um módulo TPM, esses certificados seriam armazenados no módulo TPM e não poderiam ser extraídos. Além disso, mesmo que pudessem ser extraídas, as cadeias de desafio não poderiam ser verificadas em um dispositivo diferente, renderizando os certificados/chaves inutilizáveis ​​em dispositivos diferentes..
