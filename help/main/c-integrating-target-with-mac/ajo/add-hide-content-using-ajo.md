---
keywords: otimização;personalização;adobe jornada otimizer;ajo;casos de uso;cenários;adicionar conteúdo;ocultar conteúdo;adicionar componentes;ocultar componentes
description: Saiba como adicionar ou ocultar componentes na sua página da Web usando o [!DNL Adobe Journey Optimizer].
title: Adicionar ou Ocultar Componentes à sua Página da Web no [!DNL Adobe Journey Optimizer]
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#beta newtab=true" tooltip="O que são recursos beta no  [!DNL Adobe Target]."
feature: Integrations
hide: true
hidefromtoc: true
exl-id: 8c4fba88-908e-4742-ac4b-bdf7f4c882db
source-git-commit: 52f11998149cddeb4245a0f07280562d79332a04
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 2%

---

# Adicionar ou ocultar componentes da página da Web

Este caso de uso ajuda a desbloquear os segredos para alterações eficazes no conteúdo do teste A/B no [!DNL Adobe Journey Optimizer].

Este caso de uso demonstra como executar tarefas familiares, como testes A/B com uma [atividade de Teste A/B](/help/main/c-activities/t-test-ab/test-ab.md), usando [!DNL Journey Optimizer] em vez de [!DNL Adobe Target].

Este caso de uso foi projetado para demonstrar como executar tarefas familiares que você possa ter executado usando o [!DNL Adobe Target], teste A/B usando uma [atividade de Teste A/B](/help/main/c-activities/t-test-ab/test-ab.md), mas usando o [!DNL Journey Optimizer].

## Benefícios e valor

* **Aprimorar o engajamento do usuário**: capture a atenção dos usuários com um design de página otimizado que destaque informações relevantes, como promoções.
* **Melhore a descoberta**: coloque estrategicamente novos componentes ou conteúdo na Web ou em aplicativos móveis para simplificar ações e aprimorar a navegação.
* **Aumente os pontos de contato adicionais**: oriente os usuários efetivamente para eventos de conversão e metas para acelerar o impacto nos negócios.

## Cenários possíveis

* Uma empresa de serviços financeiros planeja adicionar um novo bloco em sua página inicial para obter acesso rápido à calculadora de empréstimos, reduzindo o tempo de pesquisa e aumentando os aplicativos de empréstimos.

* Uma empresa de vestuário aumentou as conversões adicionando um novo botão do call-to-action em sua página da Web.

## Etapas

>[!NOTE]
>
>As instruções nesta seção destacam as etapas necessárias para alterar uma imagem e usar atributos de perfil para personalizar mensagens de texto. Para obter mais informações sobre as opções disponíveis no web designer [!DNL Journey Optimizer], consulte [Trabalhar com o web designer](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/web/author-web-pages/web-visual-editor){target=_blank} na *documentação do Journey Optimizer*.
>
>O vídeo na parte inferior da página é especialmente útil.

Execute as seguintes etapas para adicionar componentes ou ocultar componentes em sua página da Web:

1. Em [!DNL Adobe Journey Optimizer], clique em **Campanhas** no painel esquerdo para exibir a página [!UICONTROL Campaigns].

   ![Página de aterrissagem do Adobe Journey Optimizer com guia Campanhas realçada.](/help/main/c-integrating-target-with-mac/ajo/assets/ajo-landing-page.png)

1. Clique em **[!UICONTROL Create Campaign]** no canto superior direito da página [!UICONTROL Campaigns].

1. Selecione **[!UICONTROL Scheduled - Marketing]** (o padrão) e clique em **Criar** para exibir a página de detalhes [!UICONTROL Campaign].

   ![Página de detalhes da campanha no Adobe Journey Optimizer](/help/main/c-integrating-target-with-mac/ajo/assets/campaign-details.png)

1. Na seção **[!UICONTROL Properties]**, forneça um nome descritivo e uma descrição opcional para a campanha.

1. (Condicional) Na seção **[!UICONTROL Audience]**, clique em **[!UICONTROL Select Audience]** e escolha o público-alvo desejado.

   Para este caso de uso, você pode ativar a campanha para [!UICONTROL All Visitors] (o padrão).

1. Na seção **[!UICONTROL Action]**, escolha **[!UICONTROL Web]** na lista suspensa **[!UICONTROL Action]** e selecione ou crie uma nova configuração da Web.

   Uma configuração da Web, ou superfície de canal, é uma configuração definida por um administrador do sistema. A configuração da Web contém todos os parâmetros técnicos para enviar a mensagem, como parâmetro de cabeçalho, subdomínio, aplicativos móveis e assim por diante.

   Para obter mais informações, consulte [Configurar superfícies de canal](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/configuration/channel-surfaces#set-up-channel-surfaces){target=_blank} na *documentação do Journey Optimizer*.

1. Na seção **[!UICONTROL Action]**, clique em **[!UICONTROL Edit Content]** para abrir seu site no web designer [!DNL Journey Optimizer].

   ![Página de aterrissagem de Yoga no site da LUMA](/help/main/c-integrating-target-with-mac/ajo/assets/luma-yoga-landing.png)

1. Para adicionar ou ocultar um elemento, clique em **[!UICONTROL Edit Web Page]** no painel direito.

1. Clique no elemento que você deseja ocultar e no botão [!UICONTROL Hide] no painel direito.

   O painel direito exibe uma opção que pode ser executada no elemento selecionado. Essas opções variam, dependendo do elemento selecionado.

   ![Botão Ocultar elemento](/help/main/c-integrating-target-with-mac/ajo/assets/hide-element.png)

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
>[Trabalhar com o web designer](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/web/author-web-pages/web-visual-editor){target=_blank} na *documentação do Journey Optimizer*
>&#x200B;>[Criar uma campanha](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/create-campaigns/create-a-campaign){target=_blank} em *Tutoriais do Journey Optimizer*
