---
keywords: criador de experiências baseado em forma; criador baseado em forma; refinamentos
description: Saiba como usar o Adobe [!DNL Target] Experience Composer baseado em formulário para criação de experiência não visual. Use este compositor quando o VEC não estiver disponível ou não for prático.
title: Como usar o Experience Composer baseado em formulário?
feature: Form-based Experience Composer
exl-id: d06a271b-f058-4c83-af75-da2a29774967
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 46%

---

# Experience Composer baseado em formulário

A variável [!DNL Adobe Target] [!UICONTROL Experience Composer baseado em formulário] é uma experiência não visual e uma interface de criação de ofertas útil na criação de experiências para uso no [!UICONTROL Teste A/B], [!UICONTROL Direcionamento de experiência], [!UICONTROL Automated Personalization], e [!UICONTROL Recommendations] atividades quando a variável [!UICONTROL Visual Experience Composer] O (VEC) não está disponível ou não é prático para uso. Por exemplo, você pode usar o Experience Composer baseado em formulário para criar experiências e ofertas para entrega em emails, quiosques e assistentes de voz.

Se você estiver criando uma [!UICONTROL Recommendations] atividade, não há experiências. Escolha seu critério e design. Se você escolher vários critérios ou designs, [!UICONTROL Target] O gera automaticamente as experiências.

1. Clique em **[!UICONTROL Criar atividade]** e selecione o tipo de atividade que deseja criar.

   A variável [!UICONTROL Experience Composer baseado em formulário] está disponível para [!UICONTROL Teste A/B], [!UICONTROL Direcionamento de experiência], [!UICONTROL Automated Personalization], e [!UICONTROL Recommendations] atividades.

1. Selecionar **[!UICONTROL Formulário]** do [!UICONTROL Criar atividade] caixa de diálogo.

1. (Condicional) Escolha um espaço de trabalho e uma propriedade.

1. Clique em **[!UICONTROL Avançar]**.

   A variável [!UICONTROL Experience Composer baseado em formulário] é aberto.

   ![imagem location_refinements](assets/location_refinements.png)

   Esta tela é diferente se você estiver criando uma [!UICONTROL Recommendations] atividade. [!UICONTROL Atividades do Recommendations não incluem experiências.]

1. Nomeie a atividade clicando em &quot;[!UICONTROL Atividade sem título].&quot;
1. Selecione um local.

   Ao clicar no botão [!UICONTROL Selecionar localização] é exibida uma lista de locais disponíveis. Selecione um desses locais.

   Você também pode inserir um local que não esteja listado. Isto pode ser útil se a mbox ainda não foi criada ou visualizada em uma página. Insira o nome do local. Cuidado ao inserir um local que ainda não existe. Se a grafia ou capitalização não for compatível com a grafia e capitalização quando a chamada da mbox for feita, a atividade não será entregue. Os locais inseridos manualmente são salvos na lista de locais disponíveis. Na próxima vez que você tentar selecionar um local inserido manualmente, ele estará disponível no [!UICONTROL Selecionar localização] lista suspensa para essa atividade.

   >[!NOTE]
   >
   >A criação de um local inserido manualmente durante a criação da atividade não cria automaticamente um novo local. O nome do local é salvo somente no contexto da atividade. O local é criado quando há uma chamada de delivery de conteúdo. Após a criação do local, ele estará disponível para uso em outras atividades, para criar públicos-alvo etc. na lista suspensa de locais disponíveis.

1. Clique em **[!UICONTROL Adicionar refinamentos de público-alvo]**, escolha um ou mais [público](/help/main/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522) para esta atividade e clique em **[!UICONTROL Concluído]**.

   ![imagem location_refinements_2](assets/location_refinements_2.png)

   No [!UICONTROL Experience Composer baseado em formulário], os refinamentos foram substituídos pela funcionalidade completa de público-alvo. Os refinamentos das atividades existentes foram migrados para  [públicos-alvo somente de atividades](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483).

1. Selecione o tipo de conteúdo que você quer que apareça naquele local.

   ![imagem form_content](assets/form_content.png)

1. Para o tipo de conteúdo que você selecionou, especifique o conteúdo.

   **Alterar oferta HTML:** escolha uma oferta HTML.

   **Alterar oferta da imagem:** escolha uma imagem salva na biblioteca de conteúdo no Target.

   Você também pode adicionar um link para uma imagem (click-through, destino, aterrissagem e assim por diante.)

   1. Clique em [!UICONTROL Alterar oferta de imagem].
   1. Selecione a imagem desejada e clique em [!UICONTROL Editar links].
   1. Especifique o URL desejado ou página no seu site e clique em [!UICONTROL Atualizar].

   **Altere a oferta JSON:** escolha uma oferta json.

   **Alterar fragmento de experiência:** escolha um fragmento de experiência. Para obter mais informações, consulte [Fragmento de experiência](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

   **Alterar oferta de redirecionamento:** escolha uma oferta de redirecionamento. Para obter mais informações, consulte [Criar ofertas de redirecionamento](/help/main/c-experiences/c-manage-content/offer-redirect.md).

   **Alterar oferta remota:** escolha uma oferta remota. Para obter mais informações, consulte [Criar ofertas remotas](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

   **Criar uma oferta HTML:**

   1. Clique em [!UICONTROL Ofertas] e selecione a guia [!UICONTROL Ofertas de código].
   1. Clique em [!UICONTROL Criar] > [!UICONTROL Oferta HTML].
   1. Insira um nome de oferta.
   1. Digite ou cole seu código HTML na caixa Código.
   1. Clique em [!UICONTROL Salvar].

   **Criar oferta JSON:**

   1. Clique em [!UICONTROL Ofertas] e selecione a guia [!UICONTROL Ofertas de código].
   1. Clique em [!UICONTROL Criar] > [!UICONTROL Oferta JSON].
   1. Insira um nome de oferta.
   1. Insira ou cole seu código JSON na caixa Código.
   1. Clique em [!UICONTROL Salvar].

   **Adicionar recomendação:**

   Para uma atividade do Recommendations, o menu suspenso Conteúdo fornece a [!UICONTROL Adicionar recomendação] opção. Clique em **[!UICONTROL Adicionar recomendação]** e selecione o tipo de página. Depois siga as etapas normais como definido na interface para [criar uma atividade do Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).

   Ao selecionar o critério do Recommendations no Experience Composer baseado em formulário, agora há um link para o cartão Critérios selecionado, para que possa editar fácil e rapidamente os critérios.

   ![imagem change_criteria](assets/change_criteria.png)

   Na página Direcionamento do fluxo de trabalho guiado de três etapas do Target:

   ![imagem change_criteria_2](assets/change_criteria_2.png)

   **Adicionar decisão de oferta:**

   Adicionar uma oferta criada em [!DNL Adobe Journey Optimizer] (AJO) para um [!DNL Adobe Target] Atividade para apresentar a melhor oferta dinâmica e experiência aos visitantes em seu site ou site móvel usando o offer decisioning. Esta opção está disponível para manual [!UICONTROL Teste A/B] e [!UICONTROL Direcionamento de experiência] (XT) somente atividades do.

   Para obter mais informações, consulte [Usar decisões de oferta](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

1. (Opcional, para [!UICONTROL Teste A/B], [!UICONTROL Automated Personalization], e [!UICONTROL Direcionamento de experiência] atividades) Para repetir esse processo em locais adicionais, clique em **[!UICONTROL Adicionar localização]** e configure a localização e o conteúdo.
1. Clique em **[!UICONTROL Próxima]**, em seguida, conclua as etapas de criação da atividade como de costume para o tipo de atividade.

* [Criar um teste A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
* [Criar uma atividade de direcionamento de experiência](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
* [Criar uma atividade do Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

## Vídeo de treinamento: criador baseado em forma ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo oferece uma demonstração do compositor baseado em formulário.

* Criar uma atividade usando o Experience Composer baseado em formulário
* Entenda quando usar o Experience Composer baseado em formulário ou o Visual Experience Composer
* Use refinamentos para direcionar um local

>[!VIDEO](https://video.tv.adobe.com/v/17390)
