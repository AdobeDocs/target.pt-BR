---
keywords: criador de experiências baseado em forma; criador baseado em forma; refinamentos
description: Saiba como usar o Adobe [!DNL Target] Experience Composer baseado em formulário para criação de experiências não visuais. Use este compositor quando o VEC não estiver disponível ou não for prático.
title: Como usar o Experience Composer baseado em formulário?
feature: Form-based Experience Composer
exl-id: d06a271b-f058-4c83-af75-da2a29774967
TQID: https://experienceleague.adobe.com/X67IwQIWaOUNZECFjyXCAFsxEr3-FunVIhlRugKsWm8
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 988
ht-degree: 35%

---

# Experience Composer baseado em formulário

O [!DNL Adobe Target] [!UICONTROL Experience Composer baseado em formulário] é uma experiência não visual e uma interface de criação de ofertas útil para criar experiências para uso no [!UICONTROL Teste A/B], [!UICONTROL Direcionamento de experiência], [!UICONTROL Automated Personalization] e [!UICONTROL Recommendations] quando o [!UICONTROL Visual Experience Composer] (VEC) não estiver disponível ou não for prático. Por exemplo, você pode usar o Experience Composer baseado em formulário para criar experiências e ofertas para entrega em emails, quiosques e assistentes de voz.

Se você estiver criando uma atividade do [!UICONTROL Recommendations], não há experiências. Escolha seu critério e design. Se você escolher vários critérios ou designs, o [!UICONTROL Target] gera automaticamente as experiências.

1. Clique em **[!UICONTROL Criar atividade]** e selecione o tipo de atividade que deseja criar.

   O [!UICONTROL Experience Composer baseado em formulário] está disponível para atividades de [!UICONTROL Teste A/B], [!UICONTROL Direcionamento de experiência], [!UICONTROL Automated Personalization] e [!UICONTROL Recommendations].

1. Selecione o **[!UICONTROL Formulário]** na caixa de diálogo [!UICONTROL Criar Atividade].

1. (Condicional) Se você for um [cliente do Target Premium](/help/main/c-intro/intro.md#premium), na lista suspensa **[!UICONTROL Escolher Workspace]**, escolha um [espaço de trabalho](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

   A opção [[!UICONTROL Escolher Local de Trabalho]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) é um recurso do [Target Premium](/help/main/c-intro/intro.md) e talvez não seja exibida se sua organização tiver uma licença do [!UICONTROL Target Standard].

1. Escolha uma propriedade.

1. Clique em **[!UICONTROL Criar]**.

   O [!UICONTROL Experience Composer baseado em formulário] é aberto.

   Esta tela é diferente se você estiver criando uma atividade de [!UICONTROL Recomendações]. As atividades de [!UICONTROL Recommendations] não incluem experiências.

1. 
   1. Clique no ícone **[!UICONTROL Renomear]** ( ![Ícone Renomear](/help/main/assets/icons/MoreSmallListVert.svg) ), clique em **[!UICONTROL Renomear]**, especifique um nome para a atividade e clique em **[!UICONTROL Salvar]**.

   O nome da atividade não pode começar com nenhum dos seguintes caracteres:

   | Caractere | Descrição |
   |--- |--- |
   | `=` | Igual a |
   | `+` | Plus |
   | `-` | menos |
   | `@` | Sinal de arroba |

   O nome da atividade não pode conter nenhuma das sequências de caracteres a seguir:

   | Sequência de caracteres | Descrição |
   |--- |--- |
   | ;= | Ponto e vírgula, Igual a |
   | ;+ | Ponto-e-vírgula, Mais |
   | ;- | Ponto e vírgula, sinal de subtração |
   | ;@ | Ponto e vírgula, no sinal |
   | ,= | Vírgula, Igual a |
   | ,+ | Vírgula, Mais |
   | ,- | Vírgula, menos |
   | ,@ | Vírgula, No sinal |
   | `[`&quot; | Colchete de abertura, aspas duplas |
   | &quot;`]` | Aspas duplas, colchete de fechamento |

1. Selecione um local.

   Ao clicar na caixa [!UICONTROL Selecionar local], uma lista de locais disponíveis é exibida. Selecione um desses locais.

   Você também pode inserir um local que não esteja listado. Isto pode ser útil se a mbox ainda não foi criada ou visualizada em uma página. Insira o nome do local. Cuidado ao inserir um local que ainda não existe. Se a grafia ou capitalização não for compatível com a grafia e capitalização quando a chamada da mbox for feita, a atividade não será entregue. Os locais inseridos manualmente são salvos na lista de locais disponíveis. Na próxima vez que você tentar selecionar um local inserido manualmente, ele estará disponível na lista suspensa [!UICONTROL Selecionar local] para essa atividade.

   >[!NOTE]
   >
   >A criação de um local inserido manualmente durante a criação da atividade não cria automaticamente um novo local. O nome do local é salvo somente no contexto da atividade. O local é criado quando há uma chamada de delivery de conteúdo. Após a criação do local, ele estará disponível para uso em outras atividades, para criação de públicos-alvo etc., na lista suspensa de locais disponíveis.

1. Clique em **[!UICONTROL Adicionar refinamentos de público-alvo]**, escolha um ou mais [públicos-alvo](/help/main/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522) para esta atividade e clique em **[!UICONTROL Concluído]**.

   No [!UICONTROL Experience Composer baseado em formulário], os refinamentos foram substituídos pela funcionalidade completa de público-alvo. Os refinamentos das atividades existentes foram migrados para [públicos somente atividade](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483).

1. Selecione o tipo de conteúdo que você quer que apareça naquele local.

1. Para o tipo de conteúdo que você selecionou, especifique o conteúdo.

   **Alterar oferta HTML:** escolha uma oferta HTML.

   **Alterar oferta da imagem:** escolha uma imagem salva na biblioteca de conteúdo no Target.

   Você também pode adicionar um link para uma imagem (click-through, destino, aterrissagem e assim por diante.)

   1. Clique em [!UICONTROL Alterar oferta de imagem].
   1. Selecione a imagem desejada e clique em [!UICONTROL Editar links].
   1. Especifique o URL desejado ou página no seu site e clique em [!UICONTROL Atualizar].

   **Altere a oferta JSON:** escolha uma oferta json.

   **Alterar fragmento de experiência:** Escolha um fragmento de experiência. Para obter mais informações, consulte [Fragmento de experiência](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

   **Alterar Oferta de Redirecionamento:** Escolha uma oferta de redirecionamento. Para obter mais informações, consulte [Criar ofertas de redirecionamento](/help/main/c-experiences/c-manage-content/offer-redirect.md).

   **Alterar Oferta Remota:** Escolha uma oferta remota. Para obter mais informações, consulte [Criar ofertas remotas](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

   **Criar uma oferta HTML:**

   1. Clique em [!UICONTROL Ofertas] e selecione a guia [!UICONTROL Ofertas de código].
   1. Clique em [!UICONTROL Criar] > [!UICONTROL Oferta da HTML].
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

   Para uma atividade do Recommendations, o menu suspenso Conteúdo oferece a opção [!UICONTROL Adicionar recomendação]. Clique em **[!UICONTROL Adicionar recomendação]** e selecione o tipo de página. Depois siga as etapas normais como definido na interface para [criar uma atividade do Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).

   Ao selecionar o critério do Recommendations no Experience Composer baseado em formulário, agora há um link para o cartão Critérios selecionado, para que possa editar fácil e rapidamente os critérios.

   Na página [!UICONTROL Direcionamento] do fluxo de trabalho guiado de três etapas do [!DNL Target]:

   **Adicionar decisão de oferta:**

   Adicione uma oferta criada em [!DNL Adobe Journey Optimizer] (AJO) a uma atividade [!DNL Adobe Target] para apresentar a melhor oferta dinâmica e experiência aos visitantes do seu site ou site móvel usando o Offer Decisioning. Esta opção está disponível somente para atividades manuais de [!UICONTROL Teste A/B] e [!UICONTROL Direcionamento de experiência] (XT).

   Para obter mais informações, consulte [Usar decisões de oferta](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

1. (Opcional, para atividades de [!UICONTROL Teste A/B], [!UICONTROL Automated Personalization] e [!UICONTROL Direcionamento de Experiência]) Para repetir esse processo em locais adicionais, clique em **[!UICONTROL Adicionar Local]** e configure o local e o conteúdo.
1. Clique em **[!UICONTROL Avançar]** e conclua as etapas de criação da atividade como de costume para o tipo de atividade.

* [Criar um teste A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
* [Criar uma atividade de direcionamento de experiência](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
* [Criar uma atividade do Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

## Vídeo de treinamento: criador baseado em formulário ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo oferece uma demonstração do compositor baseado em formulário.

* Criar uma atividade usando o Experience Composer baseado em formulário
* Entenda quando usar o Experience Composer baseado em formulário ou o Visual Experience Composer
* Use refinamentos para direcionar um local

>[!VIDEO](https://video.tv.adobe.com/v/17390)
