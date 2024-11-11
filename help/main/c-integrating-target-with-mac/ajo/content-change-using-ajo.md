---
keywords: otimização;personalização;adobe jornada otimizer;ajo;casos de uso;cenários;alteração de conteúdo/teste ab;atributo de perfil;alterar imagem;trocar imagem
description: Desbloqueie os segredos para ver as alterações eficazes de conteúdo do teste A/B no Adobe Journey Optimizer
title: Alterações de conteúdo por meio do teste A/B em  [!DNL Adobe Journey Optimizer]
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#beta newtab=true" tooltip="O que são recursos beta no  [!DNL Adobe Target]."
feature: Integrations
hide: true
hidefromtoc: true
exl-id: e5aed7cd-7701-4133-ac7c-98e528c8a763
source-git-commit: b4f9e14f9dfa94f8648686e43e66eee7e0f7daa1
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 1%

---

# Alterações de conteúdo por meio do teste A/B em [!DNL Adobe Journey Optimizer]

Este caso de uso ajuda a desbloquear os segredos para alterações eficazes no conteúdo do teste A/B no [!DNL Adobe Journey Optimizer].

Este caso de uso demonstra como executar tarefas familiares, como teste A/B com uma [atividade de Teste A/B](/help/main/c-activities/t-test-ab/test-ab.md) em [!DNL Adobe Target], usando [!DNL Journey Optimizer] em vez de [!DNL Adobe Target].

## Benefícios e valor

* **Otimizar a eficácia do conteúdo**: descubra quais variações de conteúdo e elementos mais refletem nos seus clientes, resultando em mais engajamento e conversões.
* **Decisões orientadas por dados**: aproveite os dados para tomar decisões informadas em toda a sua estratégia de conteúdo, garantindo o impacto máximo.
* **Experiência do usuário personalizada**: personalize o conteúdo para atender às preferências e necessidades exclusivas de todos os seus segmentos de público-alvo.

## Cenários possíveis

* Uma empresa de vestuário aumentou as conversões testando várias imagens e personalizando páginas de aterrissagem de campanha com os nomes dos usuários no texto de chamada para ação.

* Uma empresa de comércio eletrônico descobriu que seus membros de fidelidade Gold tinham taxas de conversão mais altas ao testar várias descrições e imagens de produtos em uma página de aterrissagem de campanha, resultando em um aumento nas vendas.

## Etapas

>[!NOTE]
>
>As instruções nesta seção destacam as etapas necessárias para alterar uma imagem e usar atributos de perfil para personalizar mensagens de texto. Para obter mais informações sobre as opções disponíveis no web designer [!DNL Journey Optimizer], consulte [Editar conteúdo da Web](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/web/author-web-pages/edit-web-content){target=_blank} na *documentação do Journey Optimizer*.
>
>O vídeo na parte inferior da página é especialmente útil.

Para otimizar uma página da Web testando várias imagens e personalizando mensagens com os nomes de usuário usando um script de perfil:

1. Em [!DNL Journey Optimizer], clique em **Campanhas** no painel esquerdo para exibir a página [!UICONTROL Campaigns].

1. Clique em **[!UICONTROL Create Campaign]** no canto superior direito da página [!UICONTROL Campaigns].

1. Selecione **[!UICONTROL Scheduled - Marketing]** (o padrão) e clique em **Criar** para exibir a página de detalhes [!UICONTROL Campaign].

1. Na seção **[!UICONTROL Properties]**, forneça um nome descritivo e uma descrição opcional para a campanha.

1. (Condicional) Na seção **[!UICONTROL Audience]**, clique em **[!UICONTROL Select Audience]** e escolha o público-alvo desejado.

   Para este caso de uso, você pode ativar a campanha para [!UICONTROL All Visitors] (o padrão).

1. Na seção **[!UICONTROL Action]**, escolha **[!UICONTROL Web]** na lista suspensa **[!UICONTROL Action]** e selecione ou crie uma nova configuração da Web.

   Uma configuração da Web, ou superfície de canal, é uma configuração definida por um administrador do sistema. A configuração da Web contém todos os parâmetros técnicos para enviar a mensagem, como parâmetro de cabeçalho, subdomínio, aplicativos móveis e assim por diante.

   Para obter mais informações, consulte [Configurar superfícies de canal](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/configuration/channel-surfaces#set-up-channel-surfaces){target=_blank} na *documentação do Journey Optimizer*.

1. Na seção **[!UICONTROL Action]**, clique em **[!UICONTROL Edit Content]** para abrir seu site no web designer [!DNL Journey Optimizer].

   Dois ou mais experimentos são necessários para o teste A/B. Você pode usar sua página inicial existente como o primeiro experimento. As etapas subsequentes explicam como configurar um segundo experimento.

   ![Página de aterrissagem de Yoga no site da LUMA](/help/main/c-integrating-target-with-mac/ajo/assets/luma-yoga-landing.png)

1. Para criar um experimento para determinar qual conteúdo tem melhor desempenho, clique em **[!UICONTROL Create Experiment]**.

   Experimentos de conteúdo permitem variar o conteúdo da mensagem, o assunto ou o remetente para definir vários tratamentos e determinar a melhor combinação para seus públicos. Para obter mais informações, consulte [Criar um experimento de conteúdo](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/content-experiment/content-experiment){target=_blank} na *documentação do Journey Optimizer*.

1. Selecione uma métrica de sucesso e clique em ação.

   Clique nos ícones de Ajuda para obter mais informações e links para artigos relevantes.

1. Clique em **[!UICONTROL Add Treatment]** e depois em **[!UICONTROL Create]**.

   Nesse caso de uso, é possível deixar a distribuição em 50% para cada experimento.

1. Na página de detalhes [!UICONTROL Campaign], em **[!UICONTROL Action]**, clique em **[!UICONTROL Edit Content]**.

1. Clique em Web em Tratamento B.

   Neste caso de uso, mantenha [!UICONTROL Treatment A] inalterado para usar a experiência original como a primeira experiência no teste A/B.

1. Clique em **[!UICONTROL Edit Web Page]** no painel direito.

   ![Editar página de conteúdo na página de aterrissagem do Yoga](/help/main/c-integrating-target-with-mac/ajo/assets/edit-yoga-page.png)

1. Para alterar a imagem herói, clique na imagem que você deseja alterar e, em seguida, clique no botão **[!UICONTROL Choose Image]**.

   ![Botão Escolher imagem](/help/main/c-integrating-target-with-mac/ajo/assets/choose-image.png)

1. Procure e selecione a imagem desejada e clique em **[!UICONTROL Use This Image]**.

   ![Nova imagem herói na página Yoga](/help/main/c-integrating-target-with-mac/ajo/assets/new-hero-image.png)

1. Para personalizar a mensagem com os nomes de usuários usando atributos de perfil, clique no texto que deseja personalizar e clique em **[!UICONTROL Add Personalization]** para exibir a página [!UICONTROL Add Personalization].

   ![Botão Adicionar Personalization.](/help/main/c-integrating-target-with-mac/ajo/assets/add-personalization-button.png)

   Para obter mais informações sobre atributos de perfil, consulte [Introdução ao editor de personalização](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/personalization/expression-editor/personalization-build-expressions){target=_blank} na *documentação do Journey Optimizer*.

1. Procure e clique no sinal de mais para adicionar o atributo de perfil &quot;nome&quot;, ajuste o texto como desejado e clique em **[!UICONTROL Save]**.

   ![Adicionar atributo de perfil para o nome](/help/main/c-integrating-target-with-mac/ajo/assets/add-profile-attribute-for-name.png)

   Para obter mais informações, consulte [Introdução ao editor de personalização](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/personalization/expression-editor/personalization-build-expressions){target=_blank} na *documentação do Journey Optimizer*.

1. Clique na seta para trás no canto superior esquerdo para retornar ao web designer.

   ![Seta para trás](/help/main/c-integrating-target-with-mac/ajo/assets/back-arrow.png)

1. Clique em **[!UICONTROL Review to Activate]**, certifique-se de que tudo está conforme o esperado e clique em **Ativar**.

## Exibir relatórios

Clique no botão [!UICONTROL Reports] e depois clique no período de geração de relatório desejado:

* [!UICONTROL View all time report]
* [!UICONTROL View last 24hrs report]

Para obter mais informações, consulte [Introdução à nova interface de relatórios](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channel-report/report-gs-cja){target=_blank} na *documentação do Journey Optimizer*.

>[!MORELIKETHIS]
>
>[Editar conteúdo da Web](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/web/author-web-pages/edit-web-content){target=_blank} na *documentação do Journey Optimizer*
>[Vídeo explicativo](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/web/author-web-pages/edit-web-content#video){target=_blank} na *documentação do Journey Optimizer*
>[Criar uma campanha](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/create-campaigns/create-a-campaign){target=_blank} em *Journey Optimizer Tutorials*
