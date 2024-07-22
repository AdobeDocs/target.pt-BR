---
keywords: opções do navegador, tipo, tipo do navegador, idioma do navegador, idioma, versão, versão do navegador
description: Saiba como criar públicos-alvo no [!DNL Adobe Target]  para direcionar usuários que utilizam um determinado navegador ou determinadas opções de navegador quando visitam sua página.
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
>A partir do [!DNL Target] Standard/Premium 24.3.1 (4-6 de março de 2024), os públicos-alvo internos criados usando a interface do usuário do Target, como `Browser:iPad` e `Browser:iPhone`, foram atualizados para executar o direcionamento adequado para [!DNL iPad] e [!DNL iPhone] usando `profile.mobile.deviceVendor`, `profile.mobile.isMobilePhone` e `profile.mobile.isTablet`.
>
>Esta atualização não requer nenhuma ação por parte dos clientes. Os rótulos na interface do usuário do [!DNL Target] serão alterados no futuro e serão anunciados nas [[!DNL Target] notas de versão (atuais)](/help/main/r-release-notes/release-notes.md) quando essas alterações forem feitas.
>
>Para configurações alternativas, consulte [Atualizações para [!DNL iPad] e [!DNL iPhone] em [!UICONTROL Browser] atributos de público-alvo (30 de abril de 2024)](#updates) abaixo.

Há duas formas de direcionar navegadores:

* **Público-alvo previamente criado:** use o público-alvo previamente criado se quiser direcionar somente visitantes que usam um navegador específico para visitar seu site. Por exemplo, se você estiver oferecendo uma extensão [!DNL Chrome], direcionaria apenas [!DNL Chrome] usuários.

   1. Ao configurar sua atividade, selecione o navegador na lista suspensa.

      Essa opção direciona a atividade somente a visitantes que usam um navegador especificado.

      ![Usuários do Chrome do Target](/help/main/c-target/c-audiences/c-target-rules/assets/target-chrome.png)

* **Regra de Público-Alvo de Navegador Personalizado:** Um público-alvo personalizado permite que você direcione vários navegadores ou configure regras ou exclusões para navegadores, versões de navegadores ou idiomas específicos. Essa funcionalidade oferece flexibilidade significativa no direcionamento de uma atividade com base em atributos de navegador.

   1. Na interface [!DNL Target], clique em **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
   1. Nomeie o público-alvo e adicione uma descrição opcional.
   1. Arraste e solte **[!UICONTROL Browser]** no Construtor de público-alvo.

      ![Regras > Navegador](assets/target_browser.png)

   1. Clique em **[!UICONTROL Select]** e selecione uma das seguintes opções:

      * **Tipo:** direcione ou exclua um determinado navegador. Consulte [Tipo](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_6ADC758F23F145B3A310151546D83D56).
      * **Idioma:** Direcione ou exclua determinados navegadores configurados para usar idiomas específicos. Consulte [Idioma](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_7520D1AA464A45A6843EABE2D2B431A1).
      * **Versão:** direcione ou exclua determinadas versões de um navegador. Consulte [Versão](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_37CC8CE45DA04E8682AE6388321BA6EF).

   1. (Opcional) Configure regras adicionais para o público-alvo.
   1. Clique em **[!UICONTROL Done]**.

  O exemplo a seguir mostra um público-alvo que inclui [!DNL Microsoft Edge] usuários nas versões 91 ou 92:

  ![Edge 91 ou 92 do Target](assets/target_edge.png)

## Opções de navegador {#concept_221D8EEF53CC45AEACEB17CF336A3658}

Direcione ou exclua participantes das atividades com base em tipo de navegador, idioma ou versão.

### Tipo {#section_6ADC758F23F145B3A310151546D83D56}

Direcione ou exclua um determinado navegador.

Selecione **[!UICONTROL Type]** e escolha &quot;é igual&quot; ou &quot;não é igual&quot;.

* [!UICONTROL Equals]: Direcionar os navegadores selecionados.
* [!UICONTROL Does not equal]: Excluir os navegadores selecionados.

Selecione um ou mais navegadores. Várias opções estão conectadas a um OR.

### Idioma  {#section_7520D1AA464A45A6843EABE2D2B431A1}

Direcione ou exclua determinados navegadores configurados para usar idiomas específicos.

Por exemplo, se uma oferta está disponível em inglês, você pode direcionar navegadores cujo idioma definido seja o inglês. Ou, se sua página não está habilitada para byte duplo, você pode excluir navegadores definidos para idiomas do Leste Asiático.

A inclusão ou exclusão de idiomas de navegador pode proporcionar um direcionamento de visitante mais preciso do que o direcionamento baseado em localização geográfica nos casos em que o idioma é mais importante que o local. Por exemplo, se está oferecendo um artigo escrito em inglês, você pode direcionar países de língua inglesa ou navegadores configurados para língua inglesa. O direcionamento ao navegador disponibiliza o artigo para falantes de inglês em países nos quais o inglês não é o idioma principal.

Selecione **[!UICONTROL Language]** e escolha &quot;é igual&quot; ou &quot;não é igual&quot;.

* [!UICONTROL Equals]: Direcionar os idiomas de navegador selecionados.
* [!UICONTROL Does not equal]: Excluir os idiomas de navegador selecionados.

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

Por exemplo, se a página não for exibida corretamente no [!DNL Internet Explorer] versão 11 ou anterior, você poderá criar um público-alvo que exclua essas versões. Nesse caso, você configuraria uma regra em que o tipo de navegador é igual a [!DNL Internet Explorer] e adicionaria uma segunda regra em que a versão é menor ou igual a 11.

Selecione **[!UICONTROL Version]** e escolha um operador:

* [!UICONTROL Equals]
* [!UICONTROL Does not equal]
* [!UICONTROL Is greater than]
* É maior que ou igual a
* [!UICONTROL Is less than]
* [!UICONTROL Is less than or equal to]

Digite o número da versão. Somente versões principais podem ser inseridas no campo de texto. A versão especificada inclui todas as versões intermediárias. Por exemplo, se você especificar a versão 10, os visitantes da versão 10.1 também serão incluídos.

Várias opções estão conectadas a um OR.

## Vídeo de treinamento: Criando públicos-alvo ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo inclui as informações sobre o uso das categorias de público-alvo.

* Criar públicos-alvo
* Definir categorias de públicos-alvo

>[!VIDEO](https://video.tv.adobe.com/v/17392)

## Atualizações para [!DNL iPad] e [!DNL iPhone] em [!UICONTROL Browser] atributos de público (30 de abril de 2024) {#updates}

O [!DNL Adobe Target] permite [segmentar qualquer um dos vários atributos de categoria](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), incluindo usuários que utilizam um determinado navegador ou opções de navegador quando visitam sua página.

A partir do [!DNL Target] Standard/Premium 24.3.1 (4-6 de março de 2024), os públicos-alvo internos criados usando a interface do usuário do Target, como `Browser:iPad` e `Browser:iPhone`, foram atualizados para executar o direcionamento adequado para [!DNL iPad] e [!DNL iPhone] usando `profile.mobile.deviceVendor`, `profile.mobile.isMobilePhone` e `profile.mobile.isTablet`.

Públicos-alvo internos criados com a interface do usuário [!DNL Target], como `Browser:iPad` e `Browser:iPhone`, serão movidos automaticamente para a nova definição de Público-alvo e não requer nenhuma ação por parte dos clientes. No entanto, a partir de agora, você deve usar as configurações [descritas abaixo](#ui).

Se você usar `user.browserType` em qualquer script de perfil para verificar se é um [!DNL iPhone] ou [!DNL iPad] (por exemplo, `user.browserType == 'iphone'` ou `user.browserType != 'ipad'`), esses scripts de perfil deverão ser alterados conforme as [instruções abaixo](#profile-scripts) antes de 30 de abril de 2024 para garantir que esses públicos continuem a funcionar conforme esperado.

Os públicos-alvo da JavaScript são públicos-alvo herdados que usam expressões [!DNL Target] que foram descontinuadas com a interface do usuário [!DNL Target Classic]. Esses públicos-alvo só podem ser modificados por meio da API. Os clientes devem atualizar esses públicos-alvo somente se continuarem usando públicos-alvo herdados em atividades.

### Públicos-alvo criados usando a interface do usuário [!DNL Target] {#ui}

As seguintes configurações podem ser usadas a partir de agora:

* **Para correspondências de navegador[!DNL Apple]**: [!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL matches] [!DNL Apple]

  ![Apple](/help/main/r-release-notes/assets/apple.png)

* **Para navegador corresponde ao tablet**: [!UICONTROL Mobile] > [!UICONTROL is Tablet] > [!UICONTROL true]

  ![dispositivo móvel é tablet](/help/main/r-release-notes/assets/is-tablet.png)

* **Para correspondência de navegador iPad**: [!UICONTROL Mobile] > [!UICONTROL Device Marketing Name] [!UICONTROL matches] [!DNL iPad] com um contêiner E com [!UICONTROL Mobile] > [!UICONTROL Is Tablet] é [!DNL true]

  ![iPad](/help/main/r-release-notes/assets/ipad.png)

* **Para correspondência de navegador iPhone**: [!UICONTROL Mobile] > [!UICONTROL Device Marketing Name] [!UICONTROL matches] [!DNL iPhone] com um contêiner E com [!UICONTROL Mobile] > [!UICONTROL Is Mobile Phone] é [!DNL true]

  ![iPhone](/help/main/r-release-notes/assets/iphone.png)

Há muitas outras configurações possíveis que podem ser usadas, por exemplo, quando as condições são negadas. Exemplos de condições negadas podem ser semelhantes ao seguinte:

* **Para navegador não corresponde ao iPhone**: [!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL does not match] [!UICONTROL Apple] com um contêiner Ou com [!UICONTROL Mobile] > [!UICONTROL Is Mobile Phone] é [!UICONTROL false]

  ![Não é celular](/help/main/r-release-notes/assets/mobile-phone-false.png)

* **Para navegador não corresponde ao iPad**: [!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL does not match] [!UICONTROL Apple] com um contêiner Ou com [!UICONTROL Mobile] > [!UICONTROL Is Tablet] é [!UICONTROL false].

  ![Não é tablet](/help/main/r-release-notes/assets/tablet-false.png)

### Públicos-alvo criados usando scripts de perfil {#profile-scripts}

Se você usar `user.browserType` em públicos-alvo [!DNL Target Classic] herdados ou em scripts de perfil, as alterações deverão incluir o seguinte:

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