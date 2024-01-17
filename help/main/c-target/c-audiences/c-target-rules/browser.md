---
keywords: opções do navegador, tipo, tipo do navegador, idioma do navegador, idioma, versão, versão do navegador
description: Saiba como criar públicos-alvo no [!DNL Adobe Target] para direcionar os usuários que utilizam um determinado navegador ou determinadas opções de navegador quando visitam sua página.
title: Posso definir visitantes como alvo com base no tipo de navegador?
feature: Audiences
exl-id: 8420bbe3-b58a-4ddb-89bb-0265dab6b5fc
source-git-commit: 335b5eaa9240fb4ecc592063bebd3ba977fb8d6e
workflow-type: tm+mt
source-wordcount: '943'
ht-degree: 53%

---

# Navegador

Você pode direcionar os usuários que utilizam um determinado navegador ou determinadas opções de navegador quando visitam sua página.

Estes navegadores podem ser direcionados:

* Chrome
* Firefox
* Safari
* Internet Explorer
* Microsoft Edge
* Opera
* iPad  
* iPhone

>[!IMPORTANT]
>
>A partir de 30 de abril de 2024, o iPad e o iPhone serão removidos do disponível [!UICONTROL Navegador] digite a lista suspensa ao criar categorias para públicos-alvo. Para obter configurações alternativas, consulte [Substituição do iPad e do iPhone pelo atributo de público-alvo do navegador (30 de abril de 2024)](#deprecation) abaixo.

Há duas formas de direcionar navegadores:

* **Público-alvo previamente criado:** use o público-alvo previamente criado se quiser direcionar somente visitantes que usam um navegador específico para visitar seu site. Por exemplo, se estiver oferecendo uma extensão do Chrome, você só direcionará usuários do Chrome.

   1. Ao configurar sua atividade, selecione o navegador na lista suspensa.

      Essa opção direciona a atividade somente a visitantes que usam um navegador especificado.

      ![Usuários do Chrome do Target](/help/main/c-target/c-audiences/c-target-rules/assets/target-chrome.png)

* **Regra de público-alvo do navegador personalizado:** Um público-alvo personalizado permite direcionar vários navegadores ou configurar regras ou exclusões para navegadores, versões de navegadores ou idiomas específicos. Essa funcionalidade oferece flexibilidade significativa no direcionamento de uma atividade com base em atributos de navegador.

   1. No [!DNL Target] clique em **[!UICONTROL Públicos-alvo]** > **[!UICONTROL Criar público-alvo]**.
   1. Nomeie o público-alvo e adicione uma descrição opcional.
   1. Arrastar e soltar **[!UICONTROL Navegador]** no Construtor de público-alvo.

      ![Regras > Navegador](assets/target_browser.png)

   1. Clique em **[!UICONTROL Selecionar]** e selecione uma destas opções:

      * **Tipo:** direcione ou exclua um determinado navegador. Consulte [Tipo](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_6ADC758F23F145B3A310151546D83D56).
      * **Idioma:** Direcione ou exclua determinados navegadores configurados para usar idiomas específicos. Consulte [Idioma](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_7520D1AA464A45A6843EABE2D2B431A1).
      * **Versão:** direcione ou exclua determinadas versões de um navegador. Consulte [Versão](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_37CC8CE45DA04E8682AE6388321BA6EF).

   1. (Opcional) Configure regras adicionais para o público-alvo.
   1. Clique em **[!UICONTROL Concluído]**.

  O exemplo a seguir mostra um público-alvo que inclui usuários do Microsoft Edge nas versões 91 ou 92:

  ![Target Edge 91 ou 92](assets/target_edge.png)

## Opções de navegador {#concept_221D8EEF53CC45AEACEB17CF336A3658}

Direcione ou exclua participantes das atividades com base em tipo de navegador, idioma ou versão.

### Tipo {#section_6ADC758F23F145B3A310151546D83D56}

Direcione ou exclua um determinado navegador.

Selecione **[!UICONTROL Tipo]** e escolha &quot;é igual&quot; ou &quot;não é igual&quot;.

* É igual: direciona os navegadores selecionados.
* Não é igual: exclui os navegadores selecionados.

Selecione um ou mais navegadores. Várias opções estão conectadas a um OR.

### Idioma  {#section_7520D1AA464A45A6843EABE2D2B431A1}

Direcione ou exclua determinados navegadores configurados para usar idiomas específicos.

Por exemplo, se uma oferta está disponível em inglês, você pode direcionar navegadores cujo idioma definido seja o inglês. Ou, se sua página não está habilitada para byte duplo, você pode excluir navegadores definidos para idiomas do Leste Asiático.

A inclusão ou exclusão de idiomas de navegador pode proporcionar um direcionamento de visitante mais preciso do que o direcionamento baseado em localização geográfica nos casos em que o idioma é mais importante que o local. Por exemplo, se está oferecendo um artigo escrito em inglês, você pode direcionar países de língua inglesa ou navegadores configurados para língua inglesa. O direcionamento ao navegador disponibiliza o artigo para falantes de inglês em países nos quais o inglês não é o idioma principal.

Selecione **[!UICONTROL Idioma]** e escolha &quot;é igual&quot; ou &quot;não é igual&quot;.

* É igual: direciona os idiomas de navegador selecionados.
* Não é igual: exclui os idiomas de navegador selecionados.

Selecione um ou mais idiomas. Várias opções estão conectadas a um OR.

Os seguintes idiomas de navegador podem ser direcionados ou excluídos:

* Inglês
* Francês
* Alemão
* Japonês
* Coreano
* Português
* Russo
* Espanhol
* Chinês tradicional

### Versão  {#section_37CC8CE45DA04E8682AE6388321BA6EF}

Direcione ou exclua determinadas versões de um navegador.

Por exemplo, se sua página não aparece corretamente no Internet Explorer 11 ou em versões anteriores, você pode criar um público-alvo que exclua essas versões. Nesse caso, você configurará uma regra na qual o tipo de navegador &quot;é igual&quot; a Internet Explorer e adicionará uma segunda regra na qual a versão &quot;é menor que ou igual a&quot; 11.

Selecione **[!UICONTROL Versão]** e escolha um operador:

* Igual
* Não é igual
* É maior que
* É maior que ou igual a
* É menor que
* É menor que ou igual a

Digite o número da versão. Somente versões principais podem ser inseridas no campo de texto. A versão especificada inclui todas as versões intermediárias. Por exemplo, se você especificar a versão 10, os visitantes da versão 10.1 também serão incluídos.

Várias opções estão conectadas a um OR.

## Vídeo de treinamento: Criação de públicos-alvo ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo inclui as informações sobre o uso das categorias de público-alvo.

* Criar públicos-alvo
* Definir categorias de públicos-alvo

>[!VIDEO](https://video.tv.adobe.com/v/17392)

## Substituição do iPad e do iPhone pelo atributo de público-alvo do navegador (30 de abril de 2024) {#deprecation}

[!DNL Adobe Target] permite [direcionar em qualquer um dos vários atributos de categoria](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), incluindo usuários que utilizam um determinado navegador ou opções de navegador quando visitam sua página.

A partir de 30 de abril de 2024, o iPad e o iPhone serão removidos do disponível [!UICONTROL Navegador] digite a lista suspensa ao criar categorias para públicos-alvo.

Se você tiver públicos-alvo que direcionem iPads ou iPhones usando o [!UICONTROL Navegador] você deve alterar essas configurações antes de 30 de abril de 2024 para garantir que esses públicos-alvo continuem a funcionar conforme esperado.

As seguintes configurações podem ser usadas a partir de agora:

* [!UICONTROL Dispositivo móvel] > [!UICONTROL Fornecedor do dispositivo] [!UICONTROL corresponde a] [!DNL Apple]

  ![Apple](/help/main/r-release-notes/assets/apple.png)

* [!UICONTROL Dispositivo móvel] > [!UICONTROL é tablet] > [!UICONTROL true]

  ![dispositivo móvel é tablet](/help/main/r-release-notes/assets/is-tablet.png)

* [!UICONTROL Dispositivo móvel] > [!UICONTROL Nome de comercialização do dispositivo] [!UICONTROL corresponde a] [!DNL iPad] com um contêiner And com [!UICONTROL Dispositivo móvel] > [!UICONTROL É tablet] é [!DNL true]

  ![iPad](/help/main/r-release-notes/assets/ipad.png)

* [!UICONTROL Dispositivo móvel] > [!UICONTROL Nome de comercialização do dispositivo] [!UICONTROL corresponde a] [!DNL iPhone] com um contêiner And com [!UICONTROL Dispositivo móvel] > [!UICONTROL É telefone celular] é [!DNL true]

  ![iPhone](/help/main/r-release-notes/assets/iphone.png)

Há muitas outras configurações possíveis que podem ser usadas, por exemplo, quando as condições são negadas. Exemplos de condições negadas podem ser semelhantes ao seguinte:

* [!UICONTROL Dispositivo móvel] > [!UICONTROL Fornecedor do dispositivo] [!UICONTROL não corresponde] [!UICONTROL Apple] com um contêiner Ou com [!UICONTROL Dispositivo móvel] > [!UICONTROL É telefone celular] é [!UICONTROL false]

  ![Não é telefone celular](/help/main/r-release-notes/assets/mobile-phone-false.png)

* [!UICONTROL Dispositivo móvel] > [!UICONTROL Fornecedor do dispositivo] [!UICONTROL não corresponde] [!UICONTROL Apple] com um contêiner Ou com [!UICONTROL Dispositivo móvel] > [!UICONTROL É tablet] é [!UICONTROL false].

  ![Não tablet](/help/main/r-release-notes/assets/tablet-false.png)

Se você usar `user.browserType` nos segmentos do JavaScript, as alterações podem incluir o seguinte:

* BrowserType é iPhone

  Substituir:

  `user.browserType=="iphone"`

  Com:

  `user.mobile.deviceVendor == "Apple" && user.mobile.deviceModel && user.mobile.deviceModel.toLowerCase().includes("iphone")`

* BrowserType não é iPhone

  Substituir:

  `user.browserType!="iphone"`

  Com:

  `user.mobile.deviceVendor != "Apple" || user.mobile.deviceModel == null !! !user.mobile.deviceModel.toLowerCase().includes("iphone")`

* BrowserType é iPad

  Substituir:

  `user.browserType=="ipad"`

  Com:

  `user.mobile.deviceVendor == "Apple" && user.mobile.deviceModel && user.mobile.deviceModel.toLowerCase().includes("ipad")`

* BrowserType não é iPad

  Substituir:

  `user.browserType!="ipad"`

  Com:

  `user.mobile.deviceVendor != "Apple" || user.mobile.deviceModel == null !! !user.mobile.deviceModel.toLowerCase().includes("ipad")`