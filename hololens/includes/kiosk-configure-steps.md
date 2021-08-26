---
ms.openlocfilehash: 7a7122790d3e0257c07cdd8bc8c7f658b3a0e279
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859066"
---
# <a name="microsoft-intune-single-app-kiosk-template"></a>[Microsoft Intune quiosque de aplicativo único](#tab/uisak)

## <a name="microsoft-intune-single-app-kiosk-template"></a>Microsoft Intune de quiosque de aplicativo único

1. Criar um perfil de configuração <br> 
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Escolher modelo de quiosque <br> 
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Escolha se um único aplicativo ou vários quiosques de aplicativo e também escolha o tipo de direcionamento de usuário para o modo de quiosque <br> 
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-sa-3.png"/>
</kbd>

<br>

4. Escolha o aplicativo a ser executado no modo de quiosque <br> 
<kbd>
    <img alt="Choose the app" src="../images/kiosk-steps/kiosk-template-sa-4.png"/>
</kbd>

<br>

5. Deixe o restante das opções como está <br> 
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Escolha a quais grupos/dispositivos ou usuários esse perfil de configuração deve ser atribuído <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

7. Revisar e criar para salvar o perfil de configuração
8. Execute a sincronização de MDM a partir do dispositivo ou do Intune para aplicar a configuração ao dispositivo. Sincronizar dispositivos do [Intune](/mem/intune/remote-actions/device-sync#sync-a-device) ou no dispositivo por meio **de Configurações -> Accounts -> Work** ou school ->selecione a conta conectada **-> Informações -> Sincronização**
9. Entre como o usuário de destino para experimentar o quiosque.

# <a name="microsoft-intune-multi-app-kiosk-template"></a>[Microsoft Intune quiosque de vários aplicativos](#tab/uimak)

## <a name="microsoft-intune-multi-app-kiosk-template"></a>Microsoft Intune quiosque de vários aplicativos

1. Criar um perfil de configuração <br> 
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Escolher modelo de quiosque <br> 
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Escolha se um único aplicativo ou vários quiosques de aplicativo e também escolha o tipo de direcionamento de usuário para o modo de quiosque <br> 
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-mak-3.png"/>
</kbd>

<br>

4. Escolha os aplicativos a executar no modo de quiosque <br> 
<kbd>
    <img alt="Choose the app(s)" src="../images/kiosk-steps/kiosk-template-mak-4.png"/>
</kbd>

<br>

5. Deixe o restante das opções como está <br> 
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Escolha a quais grupos/dispositivos ou usuários esse perfil de configuração deve ser atribuído <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

<br>

7. Revisar e criar para salvar o perfil de configuração
8. Execute a sincronização de MDM a partir do dispositivo ou do Intune para aplicar a configuração ao dispositivo. Sincronizar dispositivos do [Intune](/mem/intune/remote-actions/device-sync#sync-a-device) ou no dispositivo por meio **de Configurações -> Accounts -> Work** ou school ->selecione a conta conectada **-> Informações -> Sincronização**
9. Entre como o usuário de destino para experimentar o quiosque.

# <a name="microsoft-intune-custom-template"></a>[Microsoft Intune modelo personalizado](#tab/intunecustom)

## <a name="microsoft-intune-custom-template"></a>Microsoft Intune modelo personalizado

1. Crie a configuração xml para sua experiência de quiosque desejada. Veja [exemplos](../hololens-kiosk-reference.md#kiosk-xml-code-samples) aqui para começar.

1. Criar um perfil de configuração personalizado <br>
<kbd>
    <img alt="Create a custom configuration profile" src="../images/kiosk-steps/kiosk-custom-1.png"/>
</kbd>

<br>

3. Especifique o nome do perfil de configuração personalizada e clique em "Adicionar" na seção "Definições de configuração" para adicionar as definições de OMA-URI. <br>
<kbd>
    <img alt="Name and add" src="../images/kiosk-steps/kiosk-custom-2.png"/>
</kbd>

<br>

4. Especifique o nome das configurações de OMA-URI.

    1. Na caixa de texto OMA-URI, insira **./Device/Vendor/MSFT/AssignedAccess/Configuration**
    1. Escolha Tipo de dados como Cadeia **de Caracteres.**
    1. Na caixa de texto valor, copie e copie o xml de configuração de acesso atribuído (consulte links de referência para ver exemplos com base em seu cenário e atualize conforme necessário antes da cópia colar).
    1. Selecione o botão Salvar para salvar a configuração e a configuração.

    <kbd>
        <img alt="Specify OMA-URI settings" src="../images/kiosk-steps/kiosk-custom-3.png"/>
    </kbd>

<br>

5. Escolha a quais grupos/dispositivos ou usuários esse perfil de configuração deve ser atribuído. <br>
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-custom-4.png"/>
</kbd>

<br>

6. Revise e crie para salvar o perfil de configuração.
1. Execute a sincronização de MDM a partir do dispositivo ou do Intune para aplicar a configuração ao dispositivo. Sincronizar dispositivos do [Intune](/mem/intune/remote-actions/device-sync#sync-a-device) ou no dispositivo por meio **de Configurações -> Accounts -> Work** ou school ->selecione a conta conectada **-> Informações -> Sincronização**
1. Entre como o usuário de destino para experimentar o quiosque.

# <a name="runtime-provisioning---multi-app"></a>[Provisionamento em runtime – Vários aplicativos](#tab/ppkgmak)

## <a name="runtime-provisioning---multi-app"></a>Provisionamento em runtime – Vários aplicativos

1. Crie a configuração xml para sua experiência de quiosque desejada. Veja [exemplos](../hololens-kiosk-reference.md#kiosk-xml-code-samples) aqui para começar.

1. Abra [Windows Designer de Configuração do](https://www.microsoft.com/store/apps/9nblggh4tx22).

1. Na página Iniciar, selecione **Provisionamento HoloLens dispositivos.** <br>
<kbd>
    <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
</kbd>

<br>

4. Selecione **Provisionamento HoloLens 2 dispositivos e, em seguida,** selecione próximo. <br>
<kbd>
    <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
</kbd>

<br>

5. Nomeie o projeto. Opcionalmente, escreva uma descrição. Selecione **Concluir** para continuar.

6. Na parte inferior esquerda da tela, selecione **Alternar para o editor avançado.** Confirme a alternação para o editor avançado selecionando **Sim.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

7. No lado esquerdo, expanda Configurações de runtime, AssignedAccess e **selecione MultiAppAssignedAccess**. <br>

    <kbd>
        <img alt="select MultiAppAssignedAccess" src="../images/kiosk-steps/kiosk-provision-3.png"/>
    </kbd>

<br>

8. Selecione o botão **Procurar…** botão para abrir o explorador de arquivos. E selecione o arquivo xml do Quiosque configurado.

9. Selecione **Exportar** e, em **seguida, Provisionando Pacote**.

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

10. Altere o tipo de proprietário **para Administrador de IT.** <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

11. Marque **Avançar** três vezes. Em seguida, **selecione Build**.

12. Depois que o pacote de provisionamento é build, abra a pasta Local de saída. O arquivo .ppkg é seu pacote de provisionamento. Etapa opcional: salve seu projeto.

13. Agora você pode aplicar seu pacote de provisionamento. Você pode aplicar [um pacote de provisionamento](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) ao HoloLens durante a instalação ou aplicar um pacote de [provisionamento](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)ao HoloLens após a instalação do .

14. Entre como o usuário de destino para experimentar o quiosque.

# <a name="runtime-provisioning---single-app"></a>[Provisionamento em runtime – aplicativo único](#tab/ppkgsak)

## <a name="runtime-provisioning---single-app"></a>Provisionamento em runtime – aplicativo único

1. Abra [Windows Designer de Configuração do](https://www.microsoft.com/store/apps/9nblggh4tx22).

1. Na página Iniciar, selecione **Provisionamento HoloLens dispositivos.** <br>

    <kbd>
        <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
    </kbd>

<br>

3. Selecione **Provisionamento HoloLens 2 dispositivos e, em seguida,** selecione próximo. <br>

    <kbd>
        <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

4. Nomeie o projeto. Opcionalmente, escreva uma descrição. Selecione **Concluir** para continuar.

5. Na parte inferior esquerda da tela, selecione **Alternar para o editor avançado.** Confirme a alternação para o editor avançado selecionando **Sim.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

6. No lado esquerdo, expanda Configurações de runtime, AssignedAccess e **selecione AssignedAccessSettings**. <br>

    <kbd>
        <img alt="Navigate to assigned access settings" src="../images/kiosk-steps/kiosk-provision-sak-1.png"/>
    </kbd>

<br>

7. Defina seu quiosque na caixa de texto. Por exemplo, o seguinte cria um quiosque de aplicativo único para uma conta local chamada LocalAccount que é o aplicativo de configurações.
```{"Account":"LocalAccount","AUMID":"BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App"}```

8. Selecione **Exportar** e, em **seguida, Provisionando Pacote**. <br>

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

9. Altere o tipo de proprietário **para Administrador de IT.** <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

10. Marque **Avançar** três vezes. Em seguida, **selecione Build**.

11. Depois que o pacote de provisionamento é build, abra a pasta Local de saída. O arquivo .ppkg é seu pacote de provisionamento. Etapa opcional: salve seu projeto.

12. Agora você pode aplicar seu pacote de provisionamento. Você pode aplicar [um pacote de provisionamento](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) ao HoloLens durante a instalação ou aplicar um pacote de [provisionamento](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)ao HoloLens após a instalação do .