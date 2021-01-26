---
keywords: faq;frequently asked questions;analytics for target;a4T;inflated;visit;visitor;partial hit;orphaned;orphan;partial-hit
description: Este tópico contém respostas para as perguntas mais frequentes sobre as contagens aumentadas de visitas e visitantes ao usar o Analytics como fonte de relatórios do Target (A4T).
title: Contagem aumentada de visitas e visitantes - Perguntas frequentes sobre o A4T
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: cf47b7f3625bb1c3430b9fba00c573f489efc448
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 100%

---


# Contagem aumentada de visitas e visitantes - Perguntas frequentes sobre o A4T{#inflated-visit-and-visitor-counts-a-t-faq}

Este tópico contém respostas para as perguntas mais frequentes sobre as contagens aumentadas de visitas e visitantes ao usar o Analytics como fonte de relatórios do Target (A4T).

## Por que meus dados do Analytics mostram visitas que não têm exibições de página ou outros valores de variáveis? {#section_4D8C2C2D766842E6B12F3ECC774A64D5}

Quando o [!DNL Adobe Analytics] é usado para medir as atividades do [!DNL Target] (chamado A4T), o [!DNL Analytics] coleta dados adicionais que não estão disponíveis quando não há nenhuma atividade do [!DNL Target] na página. Isso ocorre porque a atividade do [!DNL Target] aciona uma chamada na parte superior da página, mas o [!DNL Analytics] geralmente aciona suas chamadas de coleta de dados na parte inferior da página. Na implementação do A4T até o momento, incluímos estes dados adicionais sempre que uma atividade do [!DNL Target] estava ativa.

Para obter mais informações, consulte [Redução de visitas aumentadas e contagem de visitantes em A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## O que é um hit de dados parciais? {#section_59A203E289564576BF6821F96B0B9E11}

Um hit de dados parciais ocorre quando uma guia do [!DNL Target] na parte superior da página é acionada, mas uma guia do [!DNL Analytics] na parte inferior da página não é acionada. Existem várias razões pelas quais isso acontece. Na implementação do [!DNL A4T] até o momento, incluímos dados parciais sobre estes hits sempre que uma atividade do [!DNL Target] estava ativa. A partir de agora, incluiremos esses dados adicionais apenas quando as tags do [!DNL Target] e do [!DNL Analytics] forem acionadas.

Para obter mais informações, consulte [Redução de visitas aumentadas e contagem de visitantes em A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Posso ver um pico nas visitas. Como posso dizer que eles foram causados por hits de dados parciais?   {#section_28506672C6224ED18AC74F6A02F6F811}

Você pode entrar em contato com o [Atendimento ao cliente da Adobe](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para recuperar um relatório de Dados parciais. Estas informações não estão disponíveis diretamente na interface do usuário do [!DNL Analytics].

## Quais são as possíveis causas de hits de dados parciais? {#section_C4BB9925CE6444BE8CB9FBEFE5085546}

Os hits de dados parciais geralmente são o resultado de uma implementação inadequada, como IDs de conjuntos de relatórios desalinhadas. Há também causas legítimas, que incluem páginas lentas, erros de página, ofertas de redirecionamento em uma atividade ou versões de biblioteca desatualizadas.

Para obter mais informações, consulte &quot;O que contribui para dados parciais&quot; em  [Minimizar contagens inflacionadas de visitas e visitantes no A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Tenho hits de dados parciais. O que posso fazer para apagar meus dados?   {#section_CBE778A9D07A469E8FF98F68BACC7124}

Você pode criar um conjunto de relatórios virtuais para excluir dados parciais históricos de seus relatórios.

Para mais informações, consulte &quot;Como posso exibir as tendências históricas sem dados parciais?&quot; em [Minimizar contagens inflacionadas de visitas e visitantes no A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Há algo que eu possa fazer para impedir que minhas páginas gerem hits de dados parciais? {#section_4B00E7E618444BE98A0798DE98F08B21}

Depois de 14 de novembro de 2016, incluiremos esses dados apenas quando as tags do [!DNL Target] e do [!DNL Analytics] forem adicionadas. Essa alteração não é retroativa. Se seus relatórios históricos mostrarem contagens aumentadas e você quiser excluí-las de seus relatórios, poderá criar um conjunto de relatórios virtuais, conforme explicado em &quot;Como posso ver as tendências históricas sem dados parciais?&quot; em [Minimizar contagens inflacionadas de visitas e visitantes no A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

Há também etapas que você pode executar para minimizar os hits de dados parciais. Para obter mais informações, consulte &quot;Quais são as práticas recomendadas para reduzir dados parciais?&quot; em [Minimizar contagens inflacionadas de visitas e visitantes no A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Se os dados do hit de dados parciais forem removidos dos relatórios, não estamos perdendo dados valiosos do Target e do Analytics? {#section_EBC39E8A0F6A40E58F51E776936F7D9E}

A inclusão de dados parciais nos relatórios do [!DNL Analytics] realmente fornece informações adicionais, mas também cria inconsistência com dados históricos de períodos em que não havia atividades do [!DNL Target] em execução. Isso pode causar problemas para os usuários do [!DNL Analytics] que estão analisando tendências ao longo do tempo.

Há etapas que você pode executar para minimizar os hits de dados parciais. Para obter mais informações, consulte &quot;Quais são as práticas recomendadas para reduzir dados parciais?&quot; em [Minimizar contagens inflacionadas de visitas e visitantes no A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Existem tipos específicos de atividades do Target com maior probabilidade de causar hits de dados parciais? {#section_69837442A9B84366BEFDA4588B31E574}

As ofertas de redirecionamento enviam imediatamente um usuário para uma página diferente, o que significa que o [!DNL Analytics] não é acionado na primeira página.
