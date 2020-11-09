---
keywords: qa;preview;preview link;mobile;mobile preview
description: Use o link de visualização móvel para realizar facilmente tarefas completas de controle da qualidade e participar de experiências diferentes diretamente do dispositivo, sem dispositivos de teste especiais.
title: Uso do link de visualização móvel no Adobe Target Mobile
feature: mobile implementation
topic: Advanced,Standard,Classic
uuid: 313150fa-a7ec-46fe-9166-742a5c246a72
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 94%

---


# Visualização do Target Mobile{#target-mobile-preview}

Use o link de visualização móvel para realizar facilmente tarefas completas de controle da qualidade e participar de experiências diferentes diretamente do dispositivo, sem dispositivos de teste especiais.

>[!NOTE]
>
>O recurso de visualização móvel exige que você baixe e instale a versão 4.14 (ou posterior) apropriada do SDK do Adobe Mobile.

## Visão geral {#section_981D6FA4AEE64098809EA606E89E4A5E}

A funcionalidade visualização móvel permite que você teste completamente suas atividades no aplicativo móvel antes de inicializá-las.

## Pré-requisitos {#section_A763C564C9E84B0EB448237B5B1E4068}

1. **Use uma versão suportada do SDK:** o recurso visualização móvel exige que você baixe e instale a versão 4.14 (ou posterior) apropriada do SDK do Adobe Mobile em seus aplicativos correspondentes.

   Para instruções de como baixar o SDK apropriado, consulte:

   * **iOS:** [Antes de start](https://experienceleague.adobe.com/docs/mobile-services/ios/getting-started-ios/requirements.html) na Ajuda *do iOS do* Mobile Services.
   * **Android:** [Antes de start](https://experienceleague.adobe.com/docs/mobile-services/android/getting-started-android/requirements.html) na Ajuda *do Android do* Mobile Services.

1. **Defina um esquema de URL:** o link de visualização usa um esquema de URL para abrir seu aplicativo. Você deve especificar um esquema de URL único para a visualização.

   A ilustração a seguir é um exemplo no iOS:

   ![](assets/mobile-preview-url-scheme-ios.png)

   A ilustração a seguir é um exemplo no Android:

   ![](assets/Android_Deeplink.png)

1. **Rastrear Adobe DeepLink**

   **iOS:** no delegar do aplicativo, chame `[ADBMobile trackAdobeDeepLink:url` quando o delegar pedir para abrir o recurso com o esquema de URL que foi especificado no passo anterior.

   O fragmento de código a seguir é um exemplo:

   ```
   - (BOOL) application:(UIApplication *)app openURL:(NSURL *)url 
                options:(NSDictionary<NSString *,id> *)options { 
   
       if ([[url scheme] isEqualToString:@"com.adobe.targetmobile"]) { 
           [ADBMobile trackAdobeDeepLink:url]; 
           return YES; 
       } 
       return NO; 
   } 
   ```

   **Android:** no aplicativo, chame `Config.trackAdobeDeepLink(URL);`; quando o chamado pedir para abrir o recurso com o esquema de URL que foi especificado no passo anterior.

   ```
    private Boolean shouldOpenDeeplinkUrl() { 
        Intent appLinkIntent = getIntent(); 
        String appLinkAction = appLinkIntent.getAction(); 
        Uri appLinkData = appLinkIntent.getData; 
        if (appLinkData.toString().startsWith("com.adobe.targetmobile")) { 
            Config.trackAdobeDeepLink(appLinkData); 
            return true; 
        } 
        return false; 
     }
   ```

   Para fazer a visualização móvel funcionar no Android, você também deve adicionar o seguinte fragmento de código em [!DNL AndroidManifest.xml]:

   ```
   <activity android:name="com.adobe.marketing.mobile.FullscreenMessageActivity" />
   ```

## Gerar um link de visualização {#section_D9D58173FFF34E9BB75EBF357273F128}

1. Na interface de usuário do Target, clique no ícone **[!UICONTROL Mais opções]** (três elipses verticais), depois selecione **[!UICONTROL Criar visualização móvel]**.

   ![](assets/mobile-preview-create.png)

1. Selecione as atividades que deseja visualizar e clique em **[!UICONTROL Gerar link de visualização móvel]**.

   >[!NOTE]
   >
   >Somente atividades baseadas em formulário AB e XT podem ser selecionadas.

   ![](assets/mobile-preview-select-activities.png)

1. Especifique o esquema de URL do seu aplicativo.

   Isso precisa ser o mesmo que está presente no seu aplicativo iOS ou Android. Repita este processo separadamente para iOS e Android, se necessário.

   ![](assets/mobile-preview-enter-url-scheme.png)

1. Clique em **[!UICONTROL Gerar link de visualização móvel]**, depois copie o link.

   ![](assets/mobile-preview-generate-and-copy.png)

## Visualizar no seu dispositivo {#section_521F0D46F3DE4A2A98283A1B73FF69F6}

Abra o link em um navegador móvel em um dispositivo onde você tem seu aplicativo instalado. Este aplicativo pode ser o aplicativo de produção que você baixou da App store da Apple ou Google Play. Ele não precisa ser uma versão especial. Se você tem um link de visualização ativo, você poderá ver as experiência em seu dispositivo.

1. Abra o link no seu navegador móvel.

   Compartilhe o link que copiou na etapa anterior na interface de usuário do Target com seu dispositivo móvel de um modo conveniente, por exemplo através de uma mensagem, email ou Slack.

   |![link direto da visualização 1](/help/c-target-mobile-app/assets/mobile-preview-open-deeplink.png)|![link direto da visualização 2](/help/c-target-mobile-app/assets/mobile-preview-open-app.png)|

   Seu aplicativo abre e inicia o modo de visualização móvel do Target.

1. Selecione a combinação de experiências que deseja ver e clique em **[!UICONTROL Executar experiências]**.

   |![visualização móvel 1](/help/c-target-mobile-app/assets/mobile-preview-experience-selection-1.png)|![visualização móvel 2](/help/c-target-mobile-app/assets/mobile-preview-experience-result-1-france.png)|![visualização móvel 3](/help/c-target-mobile-app/assets/mobile-preview-experience-result-1-shipfree.png)|
|![visualização móvel 4](/help/c-target-mobile-app/assets/mobile-preview-experience-selection-2.png)|![visualização móvel 5](/help/c-target-mobile-app/assets/mobile-preview-experience-result-2-aus.png)|![visualização móvel 6](/help/c-target-mobile-app/assets/mobile-preview-experience-result-2-10off.png)|

## Limitações {#section_4E9BDED0F718485292527EFB508305BD}

* A visualização deve carregar novamente para que o novo conteúdo seja exibido após o botão [!UICONTROL Executar experiências] é clicado. O modo mais fácil é mudar para uma tela diferente e voltar para a tela onde você esperava a mudança acontecer.
* A visualização móvel não é suportada em versões do Android anteriores a API-19 (KitKat).