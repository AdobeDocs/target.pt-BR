---
keywords: opções do navegador, tipo, tipo do navegador, idioma do navegador, idioma, versão, versão do navegador
description: Saiba como criar públicos-alvo no [!DNL Adobe Target] para direcionar os usuários que utilizam um determinado navegador ou determinadas opções de navegador quando visitam sua página.
title: Posso definir visitantes como alvo com base no tipo de navegador?
feature: Audiences
exl-id: 8420bbe3-b58a-4ddb-89bb-0265dab6b5fc
source-git-commit: 784f41a73941877135a5902f2331972ba9d0e880
workflow-type: tm+mt
source-wordcount: '1015'
ht-degree: 33%

---

# [!UICONTROL Browser]

Você pode direcionar os usuários que utilizam um determinado navegador ou determinadas opções de navegador quando visitam sua página.

Estes navegadores podem ser direcionados:

* [!UICONTROL Chrome]
* [!UICONTROL Firefox]
* [!UICONTROL Safari]
* [!UICONTROL Internet Explorer]
* [!UICONTROL Microsoft Edge]
* [!UICONTROL Opera]
* [!DNL iPad]
* [!DNL iPhone]

>[!IMPORTANT]
>
>Começando com o [!DNL Target] Standard/Premium 24.3.1 (4-6 de março de 2024), públicos-alvo integrados criados usando a interface do usuário do Target, como `Browser:iPad` e `Browser:iPhone` foram atualizadas para executar o direcionamento adequado para [!DNL iPad] e [!DNL iPhone] usar `profile.mobile.deviceVendor`, `profile.mobile.isMobilePhone`, e `profile.mobile.isTablet`.
>
>Esta atualização não requer nenhuma ação por parte dos clientes. Os rótulos na variável [!DNL Target] A interface será alterada no futuro e será anunciada em [[!DNL Target] Notas de versão (atuais) do](/help/main/r-release-notes/release-notes.md) quando essas alterações forem feitas.
>
>Para obter configurações alternativas, consulte [Atualizações para [!DNL iPad] e [!DNL iPhone] in [!UICONTROL Browser] atributos do público-alvo (30 de abril de 2024)](#updates) abaixo.

Há duas formas de direcionar navegadores:

* **Público-alvo previamente criado:** use o público-alvo previamente criado se quiser direcionar somente visitantes que usam um navegador específico para visitar seu site. Por exemplo, se você estiver oferecendo uma [!DNL Chrome] extensão, você somente direcionaria [!DNL Chrome] usuários.

   1. Ao configurar sua atividade, selecione o navegador na lista suspensa.

      Essa opção direciona a atividade somente a visitantes que usam um navegador especificado.

      ![Usuários do Chrome do Target](/help/main/c-target/c-audiences/c-target-rules/assets/target-chrome.png)

* **Regra de público-alvo do navegador personalizado:** Um público-alvo personalizado permite direcionar vários navegadores ou configurar regras ou exclusões para navegadores, versões de navegadores ou idiomas específicos. Essa funcionalidade oferece flexibilidade significativa no direcionamento de uma atividade com base em atributos de navegador.

   1. No [!DNL Target] clique em **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
   1. Nomeie o público-alvo e adicione uma descrição opcional.
   1. Arrastar e soltar **[!UICONTROL Browser]** no Construtor de público-alvo.

      ![Regras > Navegador](assets/target_browser.png)

   1. Clique em **[!UICONTROL Select]**, em seguida, selecione uma das seguintes opções:

      * **Tipo:** direcione ou exclua um determinado navegador. Consulte [Tipo](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_6ADC758F23F145B3A310151546D83D56).
      * **Idioma:** Direcione ou exclua determinados navegadores configurados para usar idiomas específicos. Consulte [Idioma](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_7520D1AA464A45A6843EABE2D2B431A1).
      * **Versão:** direcione ou exclua determinadas versões de um navegador. Consulte [Versão](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_37CC8CE45DA04E8682AE6388321BA6EF).

   1. (Opcional) Configure regras adicionais para o público-alvo.
   1. Clique em **[!UICONTROL Done]**.

  O exemplo a seguir mostra um público-alvo que inclui [!DNL Microsoft Edge] usuários nas versões 91 ou 92:

  ![Target Edge 91 ou 92](assets/target_edge.png)

## Opções de navegador {#concept_221D8EEF53CC45AEACEB17CF336A3658}

Direcione ou exclua participantes das atividades com base em tipo de navegador, idioma ou versão.

### Tipo {#section_6ADC758F23F145B3A310151546D83D56}

Direcione ou exclua um determinado navegador.

Selecionar **[!UICONTROL Type]** e escolha &quot;é igual&quot; ou &quot;não é igual&quot;.

* [!UICONTROL Equals]: Direciona os navegadores selecionados.
* [!UICONTROL Does not equal]: exclua os navegadores selecionados.

Selecione um ou mais navegadores. Várias opções estão conectadas a um OR.

### Idioma  {#section_7520D1AA464A45A6843EABE2D2B431A1}

Direcione ou exclua determinados navegadores configurados para usar idiomas específicos.

Por exemplo, se uma oferta está disponível em inglês, você pode direcionar navegadores cujo idioma definido seja o inglês. Ou, se sua página não está habilitada para byte duplo, você pode excluir navegadores definidos para idiomas do Leste Asiático.

A inclusão ou exclusão de idiomas de navegador pode proporcionar um direcionamento de visitante mais preciso do que o direcionamento baseado em localização geográfica nos casos em que o idioma é mais importante que o local. Por exemplo, se está oferecendo um artigo escrito em inglês, você pode direcionar países de língua inglesa ou navegadores configurados para língua inglesa. O direcionamento ao navegador disponibiliza o artigo para falantes de inglês em países nos quais o inglês não é o idioma principal.

Selecionar **[!UICONTROL Language]** e escolha &quot;é igual&quot; ou &quot;não é igual&quot;.

* [!UICONTROL Equals]: segmenta os idiomas do navegador selecionados.
* [!UICONTROL Does not equal]: exclua os idiomas do navegador selecionados.

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

Por exemplo, se a página não for exibida corretamente no [!DNL Internet Explorer] versão 11 ou anterior, você pode criar um público-alvo que exclua essas versões. Nesse caso, você configuraria uma regra em que o tipo de navegador fosse igual a [!DNL Internet Explorer] e adicione uma segunda regra quando a versão for menor ou igual a 11.

Selecionar **[!UICONTROL Version]**, em seguida, escolha um operador:

* [!UICONTROL Equals]
* [!UICONTROL Does not equal]
* [!UICONTROL Is greater than]
* É maior que ou igual a
* [!UICONTROL Is less than]
* [!UICONTROL Is less than or equal to]

Digite o número da versão. Somente versões principais podem ser inseridas no campo de texto. A versão especificada inclui todas as versões intermediárias. Por exemplo, se você especificar a versão 10, os visitantes da versão 10.1 também serão incluídos.

Várias opções estão conectadas a um OR.

## Vídeo de treinamento: Criação de públicos-alvo ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo inclui as informações sobre o uso das categorias de público-alvo.

* Criar públicos-alvo
* Definir categorias de públicos-alvo

>[!VIDEO](https://video.tv.adobe.com/v/17392)

## Atualizações para [!DNL iPad] e [!DNL iPhone] in [!UICONTROL Browser] atributos do público-alvo (30 de abril de 2024) {#updates}

[!DNL Adobe Target] permite [direcionar em qualquer um dos vários atributos de categoria](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), incluindo usuários que utilizam um determinado navegador ou opções de navegador quando visitam sua página.

Começando com o [!DNL Target] Standard/Premium 24.3.1 (4-6 de março de 2024), públicos-alvo integrados criados usando a interface do usuário do Target, como `Browser:iPad` e `Browser:iPhone` foram atualizadas para executar o direcionamento adequado para [!DNL iPad] e [!DNL iPhone] usar `profile.mobile.deviceVendor`, `profile.mobile.isMobilePhone` e `profile.mobile.isTablet`.

Públicos-alvo integrados criados usando o [!DNL Target] Interface do usuário do, como `Browser:iPad` e `Browser:iPhone`, serão movidos automaticamente para a nova definição de Público-alvo e não requer nenhuma ação da parte do cliente. No entanto, a partir de agora, você deverá usar as configurações [descrito abaixo](#ui).

Se você usar `user.browserType` em qualquer script de perfil para verificar se é um [!DNL iPhone] ou [!DNL iPad] (por exemplo, `user.browserType == 'iphone'` ou `user.browserType != 'ipad'`), esses scripts de perfil devem ser alterados como [instruído abaixo](#profile-scripts) antes de 30 de abril de 2024 para garantir que esses públicos-alvo continuem funcionando conforme o esperado.

Os públicos-alvo do JavaScript são públicos-alvo herdados que usam [!DNL Target] expressões que foram descontinuadas com o [!DNL Target Classic] IU. Esses públicos-alvo só podem ser modificados por meio da API. Os clientes devem atualizar esses públicos-alvo somente se continuarem usando públicos-alvo herdados em atividades.

### Públicos-alvo criados usando o [!DNL Target] IU {#ui}

As seguintes configurações podem ser usadas a partir de agora:

* **Para correspondências de navegador[!DNL Apple]**: [!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL matches] [!DNL Apple]

  ![Apple](/help/main/r-release-notes/assets/apple.png)

* **Para navegador corresponde ao tablet**: [!UICONTROL Mobile] > [!UICONTROL is Tablet] > [!UICONTROL true]

  ![dispositivo móvel é tablet](/help/main/r-release-notes/assets/is-tablet.png)

* **Para correspondências de navegador iPad**: [!UICONTROL Mobile] > [!UICONTROL Device Marketing Name] [!UICONTROL matches] [!DNL iPad] com um contêiner And com [!UICONTROL Mobile] > [!UICONTROL Is Tablet] é [!DNL true]

  ![iPad](/help/main/r-release-notes/assets/ipad.png)

* **Para correspondências de navegador iPhone**: [!UICONTROL Mobile] > [!UICONTROL Device Marketing Name] [!UICONTROL matches] [!DNL iPhone] com um contêiner And com [!UICONTROL Mobile] > [!UICONTROL Is Mobile Phone] é [!DNL true]

  ![iPhone](/help/main/r-release-notes/assets/iphone.png)

Há muitas outras configurações possíveis que podem ser usadas, por exemplo, quando as condições são negadas. Exemplos de condições negadas podem ser semelhantes ao seguinte:

* **Para navegador não corresponde ao iPhone**: [!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL does not match] [!UICONTROL Apple] com um contêiner Ou com [!UICONTROL Mobile] > [!UICONTROL Is Mobile Phone] é [!UICONTROL false]

  ![Não é telefone celular](/help/main/r-release-notes/assets/mobile-phone-false.png)

* **Para navegador não corresponde ao iPad**: [!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL does not match] [!UICONTROL Apple] com um contêiner Ou com [!UICONTROL Mobile] > [!UICONTROL Is Tablet] é [!UICONTROL false].

  ![Não tablet](/help/main/r-release-notes/assets/tablet-false.png)

### Públicos-alvo criados usando scripts de perfil {#profile-scripts}

Se você usar `user.browserType` em herdados [!DNL Target Classic] públicos-alvo ou em scripts de perfil, as alterações devem incluir o seguinte:

* **BrowserType é iPhone**:

  Substituir:

  `user.browserType=="iphone"`

  Com:

  `profile.mobile.deviceVendor == "Apple" && profile.mobile.isMobilePhone`

* **BrowserType não é iPhone**:

  Substituir:

  `user.browserType!="iphone"`

  Com:

  `profile.mobile.deviceVendor != "Apple" || !profile.mobile.isMobilePhone`

* **BrowserType é iPad**:

  Substituir:

  `user.browserType=="ipad"`

  Com:

  `profile.mobile.deviceVendor == "Apple" && profile.mobile.isTablet`

* **BrowserType não é iPad**:

  Substituir:

  `user.browserType!="ipad"`

  Com:

  `profile.mobile.deviceVendor != "Apple" || !profile.mobile.isTablet`