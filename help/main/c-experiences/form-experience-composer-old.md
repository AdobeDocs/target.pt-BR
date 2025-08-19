---
keywords: criador de experiências baseado em forma; criador baseado em forma; refinamentos
description: Saiba como usar o Adobe [!DNL Target] Experience Composer baseado em formulário para criação de experiências não visuais. Use este compositor quando o VEC não estiver disponível ou não for prático.
title: Como usar o Experience Composer baseado em formulário?
feature: Form-based Experience Composer
exl-id: d06a271b-f058-4c83-af75-da2a29774967
source-git-commit: 2f86c9ee89b4e1698180f6b3dc9df393733eb780
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 37%

---

# Experience Composer baseado em formulário

O [!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] é uma experiência não visual e uma interface de criação de ofertas útil para criar experiências para uso nas atividades do [!UICONTROL A/B Test], [!UICONTROL Experience Targeting], [!UICONTROL Automated Personalization] e [!UICONTROL Recommendations] quando o [!UICONTROL Visual Experience Composer] (VEC) não estiver disponível ou não for prático. Por exemplo, você pode usar o Experience Composer baseado em formulário para criar experiências e ofertas para entrega em emails, quiosques e assistentes de voz.

Se você estiver criando uma atividade [!UICONTROL Recommendations], não há experiências. Escolha seu critério e design. Se você escolher vários critérios ou designs, [!UICONTROL Target] gera automaticamente as experiências.

1. Clique em **[!UICONTROL Create Activity]** e selecione o tipo de atividade que deseja criar.

   O [!UICONTROL Form-Based Experience Composer] está disponível para atividades de [!UICONTROL A/B Test], [!UICONTROL Experience Targeting], [!UICONTROL Automated Personalization] e [!UICONTROL Recommendations].

1. Selecione **[!UICONTROL Form]** na caixa de diálogo [!UICONTROL Create Activity].

1. (Condicional) Escolha um espaço de trabalho e uma propriedade.

1. Clique em **[!UICONTROL Next]**.

   O [!UICONTROL Form-Based Experience Composer] se abre.

   ![imagem location_refinements](assets/location_refinements.png)

   Esta tela é diferente se você estiver criando uma atividade [!UICONTROL Recommendations]. [!UICONTROL Recommendations] atividades não incluem experiências.

1. Nomeie a atividade clicando em &quot;[!UICONTROL Untitled Activity]&quot;.
1. Selecione um local.

   Ao clicar na caixa [!UICONTROL Select Location], uma lista de locais disponíveis é exibida. Selecione um desses locais.

   Você também pode inserir um local que não esteja listado. Isto pode ser útil se a mbox ainda não foi criada ou visualizada em uma página. Insira o nome do local. Cuidado ao inserir um local que ainda não existe. Se a grafia ou capitalização não for compatível com a grafia e capitalização quando a chamada da mbox for feita, a atividade não será entregue. Os locais inseridos manualmente são salvos na lista de locais disponíveis. Na próxima vez que você tentar selecionar um local inserido manualmente, ele estará disponível na lista suspensa [!UICONTROL Select Location] para essa atividade.

   >[!NOTE]
   >
   >A criação de um local inserido manualmente durante a criação da atividade não cria automaticamente um novo local. O nome do local é salvo somente no contexto da atividade. O local é criado quando há uma chamada de delivery de conteúdo. Após a criação do local, ele estará disponível para uso em outras atividades, para criar públicos-alvo etc. na lista suspensa de locais disponíveis.

1. Clique em **[!UICONTROL Add Audience Refinements]**, escolha um ou mais [público-alvo](/help/main/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522) para esta atividade e clique em **[!UICONTROL Done]**.

   Imagem ![location_refinements_2](assets/location_refinements_2.png)

   No [!UICONTROL Form-based Experience Composer], os refinamentos foram substituídos pela funcionalidade completa de público-alvo. Os refinamentos das atividades existentes foram migrados para [públicos somente atividade](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483).

1. Selecione o tipo de conteúdo que você quer que apareça naquele local.

   ![imagem_de_conteúdo_de_formulário](assets/form_content.png)

1. Para o tipo de conteúdo que você selecionou, especifique o conteúdo.

   **Alterar oferta HTML:** escolha uma oferta HTML.

   **Alterar oferta da imagem:** escolha uma imagem salva na biblioteca de conteúdo no Target.

   Você também pode adicionar um link para uma imagem (click-through, destino, aterrissagem e assim por diante.)

   1. Clique em [!UICONTROL Change Image Offer].
   1. Selecione a imagem desejada e clique em [!UICONTROL Edit Links].
   1. Especifique a URL ou página desejada em seu site e clique em [!UICONTROL Update].

   **Altere a oferta JSON:** escolha uma oferta json.

   **Alterar fragmento de experiência:** Escolha um fragmento de experiência. Para obter mais informações, consulte [Fragmento de experiência](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

   **Alterar Oferta de Redirecionamento:** Escolha uma oferta de redirecionamento. Para obter mais informações, consulte [Criar ofertas de redirecionamento](/help/main/c-experiences/c-manage-content/offer-redirect.md).

   **Alterar Oferta Remota:** Escolha uma oferta remota. Para obter mais informações, consulte [Criar ofertas remotas](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

   **Criar uma oferta HTML:**

   1. Clique em [!UICONTROL Offers] e selecione a guia [!UICONTROL Code Offers].
   1. Clique em [!UICONTROL Create] > [!UICONTROL HTML Offer].
   1. Insira um nome de oferta.
   1. Digite ou cole seu código HTML na caixa Código.
   1. Clique em [!UICONTROL Save].

   **Criar oferta JSON:**

   1. Clique em [!UICONTROL Offers] e selecione a guia [!UICONTROL Code Offers].
   1. Clique em [!UICONTROL Create] > [!UICONTROL JSON Offer].
   1. Insira um nome de oferta.
   1. Insira ou cole seu código JSON na caixa Código.
   1. Clique em [!UICONTROL Save].

   **Adicionar recomendação:**

   Para uma atividade do Recommendations, o menu suspenso Conteúdo oferece a opção [!UICONTROL Add Recommendation]. Clique em **[!UICONTROL Add Recommendation]** e selecione o tipo de página. Depois siga as etapas normais como definido na interface para [criar uma atividade do Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).

   Ao selecionar o critério do Recommendations no Experience Composer baseado em formulário, agora há um link para o cartão Critérios selecionado, para que possa editar fácil e rapidamente os critérios.

   ![imagem de change_criteria](assets/change_criteria.png)

   Na página Direcionamento do fluxo de trabalho guiado de três etapas do Target:

   Imagem ![change_criteria_2](assets/change_criteria_2.png)

   **Adicionar decisão de oferta:**

   Adicione uma oferta criada em [!DNL Adobe Journey Optimizer] (AJO) a uma atividade [!DNL Adobe Target] para apresentar a melhor oferta dinâmica e experiência aos visitantes do seu site ou site móvel usando o Offer Decisioning. Esta opção está disponível somente para atividades manuais [!UICONTROL A/B Test] e [!UICONTROL Experience Targeting] (XT).

   Para obter mais informações, consulte [Usar decisões de oferta](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

1. (Opcional, para atividades de [!UICONTROL A/B Test], [!UICONTROL Automated Personalization] e [!UICONTROL Experience Targeting]) Para repetir esse processo em locais adicionais, clique em **[!UICONTROL Add Location]** e configure o local e o conteúdo.
1. Clique em **[!UICONTROL Next]** e conclua as etapas de criação da atividade como de costume para o tipo de atividade.

* [Criar um teste A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
* [Criar uma atividade de direcionamento de experiência](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
* [Criar uma atividade do Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

## Vídeo de treinamento: criador baseado em formulário ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo oferece uma demonstração do compositor baseado em formulário.

* Criar uma atividade usando o Experience Composer baseado em formulário
* Entenda quando usar o Experience Composer baseado em formulário ou o Visual Experience Composer
* Use refinamentos para direcionar um local

>[!VIDEO](https://video.tv.adobe.com/v/17390)
