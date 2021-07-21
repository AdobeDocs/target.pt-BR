---
keywords: opções do navegador, tipo, tipo do navegador, idioma do navegador, idioma, versão, versão do navegador
description: Saiba como criar públicos-alvo no [!DNL Adobe Target] para direcionar usuários que usam um navegador específico ou opções específicas de navegador quando visitam sua página.
title: Posso definir metas para visitantes com base no tipo de navegador?
feature: Públicos-alvo
exl-id: 8420bbe3-b58a-4ddb-89bb-0265dab6b5fc
source-git-commit: b46966a8dbb2ff6d2efbfb8f126783f750c2f08c
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 76%

---

# Navegador

Você pode direcionar os usuários que utilizam um determinado navegador ou determinadas opções de navegador quando visitam sua página.

Estes navegadores podem ser direcionados:

* Google Chrome
* Firefox
* Safari
* Internet Explorer
* Microsoft Edge
* Opera
* iPad 
* iPhone|

Há duas formas de direcionar navegadores:

* **Público-alvo previamente criado:** use o público-alvo previamente criado se quiser direcionar somente visitantes que usam um navegador específico para visitar seu site. Por exemplo, se estiver oferecendo uma extensão do Chrome, você só direcionará usuários do Chrome.

   1. Ao configurar sua atividade, selecione o navegador na lista suspensa.

      Essa opção direciona a atividade somente a visitantes que usam um navegador especificado.

      ![Direcionar usuários do Chrome](/help/c-target/c-audiences/c-target-rules/assets/target-chrome.png)

* **Regra do público-alvo personalizado do navegador:** um público-alvo personalizado permite direcionar vários navegadores ou configurar regras ou exclusões para navegadores específicos, versões de navegadores ou idiomas de navegadores. Essa funcionalidade oferece flexibilidade significativa ao direcionar uma atividade com base em atributos de navegador.

   1. Na interface do [!DNL Target], clique em **[!UICONTROL Públicos-alvo]** > **[!UICONTROL Criar público-alvo]**.
   1. Nomeie o público-alvo e adicione uma descrição opcional.
   1. Arraste e solte **[!UICONTROL Browser]** no painel do construtor de público-alvo.

      ![Regras > Navegador](assets/target_browser.png)

   1. Clique em **[!UICONTROL Selecionar]** e selecione uma destas opções:

      * **Tipo:** direcione ou exclua um determinado navegador. Consulte [Tipo](/help/c-target/c-audiences/c-target-rules/browser.md#section_6ADC758F23F145B3A310151546D83D56).
      * **Idioma:** direcione ou exclua determinados navegadores configurados para usar idiomas específicos. Consulte [Idioma](/help/c-target/c-audiences/c-target-rules/browser.md#section_7520D1AA464A45A6843EABE2D2B431A1).
      * **Versão:** direcione ou exclua determinadas versões de um navegador. Consulte [Versão](/help/c-target/c-audiences/c-target-rules/browser.md#section_37CC8CE45DA04E8682AE6388321BA6EF).
   1. (Opcional) Configure regras adicionais para o público-alvo.
   1. Clique em **[!UICONTROL Concluído]**.

   O exemplo a seguir mostra um público-alvo que inclui usuários do Microsoft Edge nas versões 91 ou 92:

   ![Target Edge 91 ou 92](assets/target_edge.png)

## Opções de navegador {#concept_221D8EEF53CC45AEACEB17CF336A3658}

Direcione ou exclua participantes das atividades com base em tipo de navegador, idioma ou versão.

### Tipo {#section_6ADC758F23F145B3A310151546D83D56}

Direcione ou exclua um determinado navegador.

Selecione **[!UICONTROL Tipo]** e escolha “é igual” ou “não é igual”.

* É igual: direciona os navegadores selecionados.
* Não é igual: exclui os navegadores selecionados.

Selecione um ou mais navegadores. Várias opções estão conectadas a um OR.

### Idioma  {#section_7520D1AA464A45A6843EABE2D2B431A1}

Direcione ou exclua determinados navegadores configurados para usar idiomas específicos.

Por exemplo, se uma oferta está disponível em inglês, você pode direcionar navegadores cujo idioma definido seja o inglês. Ou, se sua página não está habilitada para byte duplo, você pode excluir navegadores definidos para idiomas do Leste Asiático.

A inclusão ou exclusão de idiomas de navegador pode proporcionar um direcionamento de visitante mais preciso do que o direcionamento baseado em localização geográfica nos casos em que o idioma é mais importante que o local. Por exemplo, se está oferecendo um artigo escrito em inglês, você pode direcionar países de língua inglesa ou navegadores configurados para língua inglesa. O direcionamento ao navegador disponibiliza o artigo para falantes de inglês em países nos quais o inglês não é o idioma principal.

Selecione **[!UICONTROL Idioma]** e escolha “é igual” ou “não é igual”.

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

## Vídeo de treinamento: Criação de públicos-alvo ![Selo do tutorial](/help/assets/tutorial.png)

Este vídeo inclui as informações sobre o uso das categorias de público-alvo.

* Criar públicos-alvo
* Definir categorias de públicos-alvo

>[!VIDEO](https://video.tv.adobe.com/v/17392)
