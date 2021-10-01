---
ms.openlocfilehash: 3d6b36124cd50dcc9f420227cb7787f0d787c013
ms.sourcegitcommit: c73cdefbdb4411f6a187cc38bb2570dadeb156bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2021
ms.locfileid: "129220604"
---
# <a name="microsoft-intune-single-app-kiosk-template"></a>[Modelo de quiosque de aplicativo único do Microsoft Intune](#tab/uisak)

### <a name="microsoft-intune-single-app-kiosk-template"></a>Modelo de quiosque de aplicativo único do Microsoft Intune

1. Crie um perfil de configuração <br>
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Escolha um modelo de quiosque <br>
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Escolha um quiosque de aplicativo único ou de vários aplicativos e também o tipo de direcionamento ao usuário do modo de quiosque <br>
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-sa-3.png"/>
</kbd>

<br>

4. Escolha o aplicativo a ser executado no modo de quiosque <br>
<kbd>
    <img alt="Choose the app" src="../images/kiosk-steps/kiosk-template-sa-4.png"/>
</kbd>

<br>

5. Deixe o restante das opções com os padrões <br>
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Escolha a quais grupos, dispositivos ou usuários esse perfil de configuração deve ser atribuído <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

7. Examine e crie o perfil de configuração para salvá-lo
8. Execute a sincronização do MDM usando o dispositivo ou o Intune para aplicar a configuração ao dispositivo. [Sincronize os dispositivos no Intune](/mem/intune/remote-actions/device-sync#sync-a-device) ou no dispositivo por meio de **Configurações -> Contas -> Corporativa ou de estudante ->** selecione a conta conectada **-> Informações -> Sincronização**
9. Entre como o usuário de destino para experimentar o quiosque.

# <a name="microsoft-intune-multi-app-kiosk-template"></a>[Modelo de quiosque de vários aplicativos do Microsoft Intune](#tab/uimak)

### <a name="microsoft-intune-multi-app-kiosk-template"></a>Modelo de quiosque de vários aplicativos do Microsoft Intune

1. Crie um perfil de configuração <br>
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Escolha um modelo de quiosque <br>
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Escolha um quiosque de aplicativo único ou de vários aplicativos e também o tipo de direcionamento ao usuário do modo de quiosque <br>
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-mak-3.png"/>
</kbd>

<br>

4. Escolha os aplicativos a serem executados no modo de quiosque <br>
<kbd>
    <img alt="Choose the app(s)" src="../images/kiosk-steps/kiosk-template-mak-4.png"/>
</kbd>

<br>

5. Deixe o restante das opções com os padrões <br>
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Escolha a quais grupos, dispositivos ou usuários esse perfil de configuração deve ser atribuído <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

<br>

7. Examine e crie o perfil de configuração para salvá-lo
8. Execute a sincronização do MDM usando o dispositivo ou o Intune para aplicar a configuração ao dispositivo. [Sincronize os dispositivos no Intune](/mem/intune/remote-actions/device-sync#sync-a-device) ou no dispositivo por meio de **Configurações -> Contas -> Corporativa ou de estudante ->** selecione a conta conectada **-> Informações -> Sincronização**
9. Entre como o usuário de destino para experimentar o quiosque.

# <a name="microsoft-intune-custom-template"></a>[Modelo personalizado do Microsoft Intune](#tab/intunecustom)

### <a name="microsoft-intune-custom-template"></a>Modelo personalizado do Microsoft Intune

1. Crie a configuração XML da experiência de quiosque desejada. Veja [exemplos](../hololens-kiosk-reference.md#kiosk-xml-code-samples) aqui para começar.

1. Criar um perfil de configuração personalizado <br>
<kbd>
    <img alt="Create a custom configuration profile" src="../images/kiosk-steps/kiosk-custom-1.png"/>
</kbd>

<br>

3. Especifique o nome do perfil de configuração personalizado e clique em “Adicionar” na seção “Definições de configuração” para adicionar as configurações de OMA-URI. <br>
<kbd>
    <img alt="Name and add" src="../images/kiosk-steps/kiosk-custom-2.png"/>
</kbd>

<br>

4. Especifique o nome das configurações de OMA-URI.

    1. Na caixa de texto OMA-URI, insira **./Device/Vendor/MSFT/AssignedAccess/Configuration**
    1. Escolha o Tipo de dados como **String**.
    1. Copie o XML de configuração de acesso atribuído e cole-o na caixa de texto de valor (confira os links de referência para ver exemplos baseados no seu cenário e atualize-os conforme o necessário antes de copiá-los).
    1. Selecione o botão Salvar para salvar a definição e a configuração.

    <kbd>
        <img alt="Specify OMA-URI settings" src="../images/kiosk-steps/kiosk-custom-3.png"/>
    </kbd>

<br>

5. Escolha a quais grupos, dispositivos ou usuários esse perfil de configuração deve ser atribuído. <br>
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-custom-4.png"/>
</kbd>

<br>

6. Examine e crie o perfil de configuração para salvá-lo.
1. Execute a sincronização do MDM usando o dispositivo ou o Intune para aplicar a configuração ao dispositivo. [Sincronize os dispositivos no Intune](/mem/intune/remote-actions/device-sync#sync-a-device) ou no dispositivo por meio de **Configurações -> Contas -> Corporativa ou de estudante ->** selecione a conta conectada **-> Informações -> Sincronização**
1. Entre como o usuário de destino para experimentar o quiosque.

# <a name="runtime-provisioning---multi-app"></a>[Provisionamento de runtime – Vários aplicativos](#tab/ppkgmak)

### <a name="runtime-provisioning---multi-app"></a>Provisionamento de runtime – Vários aplicativos

1. Crie a configuração XML da experiência de quiosque desejada. Veja [exemplos](../hololens-kiosk-reference.md#kiosk-xml-code-samples) aqui para começar.

1. Abra o [Designer de Configuração do Windows](https://www.microsoft.com/store/apps/9nblggh4tx22).

1. Na página Iniciar, selecione **Provisionamento de dispositivos HoloLens.** <br>
<kbd>
    <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
</kbd>

<br>

4. Selecione **Provisionamento de dispositivos HoloLens 2** e clique em Próximo. <br>
<kbd>
    <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
</kbd>

<br>

5. Nomeie o projeto. Como opção, escreva uma descrição. Selecione **Concluir** para continuar.

6. Na parte inferior esquerda da tela, selecione **Mudar para o editor avançado.** Confirme a mudança para o editor avançado selecionando **Sim.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

7. No lado esquerdo, expanda Configurações de runtime, AssignedAccess e selecione **MultiAppAssignedAccess**. <br>

    <kbd>
        <img alt="select MultiAppAssignedAccess" src="../images/kiosk-steps/kiosk-provision-3.png"/>
    </kbd>

<br>

8. Selecione o botão **Procurar…** para abrir o Explorador de Arquivos. E selecione o arquivo XML do quiosque configurado.

9. Selecione **Exportar** e depois **Pacote de Provisionamento**.

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

10. Altere o tipo de proprietário para **Administrador de TI**. <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

11. Marque **Avançar** três vezes. Depois selecione **Criar**.

12. Depois que o pacote de provisionamento for criado, abra a pasta local de saída. O arquivo .ppkg é seu pacote de provisionamento. Etapa opcional: salvar o projeto.

13. Agora você pode aplicar o pacote de provisionamento. Você pode [aplicar um pacote de provisionamento ao HoloLens durante a instalação](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) ou [após a instalação](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup).

14. Entre como o usuário de destino para experimentar o quiosque.

# <a name="runtime-provisioning---single-app"></a>[Provisionamento de runtime – Aplicativo único](#tab/ppkgsak)

### <a name="runtime-provisioning---single-app"></a>Provisionamento de runtime – Aplicativo único

1. Abra o [Designer de Configuração do Windows](https://www.microsoft.com/store/apps/9nblggh4tx22).

1. Na página Iniciar, selecione **Provisionar dispositivos HoloLens.** <br>

    <kbd>
        <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
    </kbd>

<br>

3. Selecione **Provisionamento de dispositivos HoloLens 2** e clique em Próximo. <br>

    <kbd>
        <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

4. Nomeie o projeto. Como opção, escreva uma descrição. Selecione **Concluir** para continuar.

5. Na parte inferior esquerda da tela, selecione **Alternar para editor avançado.** Confirme a mudança para o editor avançado selecionando **Sim.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

6. No lado esquerdo, expanda Configurações de runtime, AssignedAccess e selecione **AssignedAccessSettings**. <br>

    <kbd>
        <img alt="Navigate to assigned access settings" src="../images/kiosk-steps/kiosk-provision-sak-1.png"/>
    </kbd>

<br>

7. Defina seu quiosque na caixa de texto. O exemplo a seguir cria um quiosque de aplicativo único para uma conta local chamada LocalAccount que é o aplicativo de configurações.
```{"Account":"LocalAccount","AUMID":"BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App"}```

8. Selecione **Exportar** e depois **Pacote de Provisionamento**. <br>

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

9. Altere o tipo de proprietário para **Administrador de TI**. <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

10. Marque **Avançar** três vezes. Depois selecione **Criar**.

11. Depois que o pacote de provisionamento for criado, abra a pasta local de saída. O arquivo .ppkg é seu pacote de provisionamento. Etapa opcional: salvar o projeto.

12. Agora você pode aplicar o pacote de provisionamento. Você pode [aplicar um pacote de provisionamento ao HoloLens durante a instalação](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) ou [após a instalação](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup).