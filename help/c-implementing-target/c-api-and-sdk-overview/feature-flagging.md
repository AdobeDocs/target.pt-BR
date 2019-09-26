---
description: As equipes de produtos de tecnologia contemporânea estão adotando princípios de fornecimento contínuo para lançamentos de produtos. O Target ajuda desenvolvedores e equipes de produtos a implantar novos recursos de produto de forma rápida e eficiente.
keywords: roll-out;roll-out;entrega contínua;lançamento do produto;lançamento em fases
seo-description: As equipes de produtos de tecnologia contemporânea estão adotando princípios de fornecimento contínuo para lançamentos de produtos. O Adobe Target ajuda desenvolvedores e equipes de produtos a implantar novos recursos de produto de forma rápida e eficiente em uma implementação em fases.
seo-title: As equipes de produtos de tecnologia contemporânea estão adotando princípios de fornecimento contínuo para lançamentos de produtos. O Adobe Target ajuda desenvolvedores e equipes de produtos a desenvolver novos recursos de produto de modo rápido e eficiente.
solution: Target
title: Sinalização de recurso
topic: Padrão
translation-type: tm+mt
source-git-commit: 08debab3ec3d2f6e6bfd3c42476dc1a021185ab7

---


# Sinalização de recurso

As equipes de produtos de tecnologia contemporânea estão adotando princípios de fornecimento contínuo para lançamentos de produtos. Adobe Target helps developers and product teams roll out new product capabilities quickly and efficiently in a phased rollout.

The following links provide information for key concepts you need to understand to enable continuous delivery:

* [Atividades de teste A/B](/help/c-activities/t-test-ab/test-ab.md)
* [JSON offers](/help/c-experiences/c-manage-content/create-json-offer.md)
* [Audience refinements](/help/c-target/c-audiences/creating-a-profile-attribute-comparison-audience.md)

## Entrega contínua

1. Por padrão, ative o recurso "desligado" na versão.

   Use uma variável no servidor ou no aplicativo para controlar isso.

1. Crie uma oferta JSON do Target que defina essa variável como "on".

1. Crie uma atividade de teste A/B no [Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) com duas experiências e use a oferta JSON criada na etapa anterior em uma experiência.

   Ou

   Crie uma atividade de teste A/B no Criador de experiências baseado em [formulário](/help/c-experiences/form-experience-composer.md) com uma única experiência e use a oferta JSON criada na etapa anterior.

   >[!NOTE]
   >
   >O Criador de experiências baseado em forma permite criar uma atividade de teste A/B com uma única experiência. Não é possível criar a atividade com uma única experiência usando o VEC.

1. Especifique a alocação de tráfego desejada para a atividade.

   Se você quiser começar por implantar esse recurso em 5% dos seus visitantes, especifique 5 na etapa Direcionamento do fluxo de trabalho guiado de três partes e envie 100% dos visitantes qualificados para a experiência com a oferta JSON (Experiência A).

   A ilustração a seguir mostra o VEC com duas experiências.

   ![Alocação de tráfego para sinalização de recurso no VEC](/help/c-implementing-target/c-api-and-sdk-overview/assets/feature-flagging.png)

   A ilustração a seguir mostra o Criador de experiências baseado em forma com uma única experiência.

   ![Alocação de tráfego para sinalizar o recurso no Criador de experiências baseado em formulário](/help/c-implementing-target/c-api-and-sdk-overview/assets/feature-flagging-form.png)

1. Você pode aumentar a alocação de tráfego para essa atividade aumentando gradualmente os 5% por meio da interface do usuário do Target ou usando a API até atingir 100% de alocação de tráfego.

   >[!NOTE]
   >
   >Uma atividade de teste A/B é aderente para um visitante durante a sessão. If you decrease the traffic allocation, visitors who started seeing this feature continue to view it until their sessions are reset.

## Recursos do teste A/B

Se estiver usando A/B/..N Recursos de teste, use a abordagem discutida acima com as seguintes melhorias:

* Each feature variant should be represented using an appropriate JSON offer that makes a Target experience.
* You can manage traffic allocation for this test in the manner described above.

## Parametrized rollouts

The method described above helps you manage a controlled rollout.

You can roll out a feature for your beta participants only and then later roll out the feature to all other customers. This can be easily achieved by leveraging Target Location (mbox) parameters or profile parameters. [](/help/c-target/c-audiences/c-target-rules/custom-parameters.md)[](/help/c-target/c-audiences/c-target-rules/visitor-profile.md) These parameters can be used in conjunction with phased traffic allocation.

## Server-side vs. client-side

Feature rollouts and testing can be delivered via Target APIs (and server-side SDKs) as well as the client side SDKs (JS, Mobile SDK). [](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md) Dependendo de como seu site, aplicativo móvel ou quiosque foi arquitetado, você pode aproveitar as diferentes opções de integração do Target.
