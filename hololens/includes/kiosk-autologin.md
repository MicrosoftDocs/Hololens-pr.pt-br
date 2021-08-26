---
ms.openlocfilehash: d96a769b40daba0948f8f3c71a88513576c531b5
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859064"
---
# <a name="non-aad-configuration"></a>[Configuração não AAD](#tab/nonaadlogon)

#### <a name="non-aad-configuration"></a>Configuração não AAD

1. Crie um pacote de provisionamento que:
    1. Define as configurações de tempo de execução/AssignedAccess para permitir contas de visitante.
    1. Opcionalmente, registra o dispositivo no MDM (configurações de tempo de execução/local de trabalho/registros) para que possa ser gerenciado posteriormente.
    1. Não criar uma conta local
2. [Aplique o pacote de provisionamento](../hololens-provisioning.md).

# <a name="aad-configuration"></a>[Configuração do AAD](#tab/aadlogon)

#### <a name="aad-configuration"></a>Configuração do AAD

Os dispositivos ingressados no AAD configurados para o modo de quiosque podem entrar em uma conta de visitante com um único toque de botão na tela de entrada. Depois de entrar na conta de visitante, o dispositivo não solicitará a entrada novamente até que o visitante seja explicitamente desconectado do menu iniciar ou o dispositivo seja reiniciado.

O logon automático do visitante pode ser gerenciado por meio [de uma política de OMA-URI personalizada](/mem/intune/configuration/custom-settings-windows-10):

- Valor do URI:./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Política | Descrição | Configurações |
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | Permite que um visitante faça logon automaticamente em um quiosque. | 1 (Sim), 0 (não, padrão.) |