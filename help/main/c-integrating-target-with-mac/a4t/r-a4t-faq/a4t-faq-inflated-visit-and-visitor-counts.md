---
keywords: perguntas frequentes; perguntas frequentes; analytics para target; a4T; inflacionado; visita; visitante; acesso parcial; órfão; órfão; acesso parcial
description: Encontre respostas para perguntas sobre contagens inflacionadas de visitas e visitantes ao usar o Analytics para [!DNL Target] (A4T). Saiba como minimizar os "dados parciais".
title: Onde posso encontrar perguntas frequentes sobre visitas aumentadas e contagens de visitantes com o A4T?
feature: Analytics for Target (A4T)
exl-id: e936b1f6-dc72-4ab2-9bb5-169d1710edbe
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 49%

---

# Contagem aumentada de visitas e visitantes - Perguntas frequentes sobre o A4T

Este tópico contém respostas para as perguntas mais frequentes sobre as contagens aumentadas de visitas e visitantes ao usar o Analytics como fonte de relatórios do Target (A4T).

## Por que meus dados do Analytics mostram visitas que não têm exibições de página ou outros valores de variáveis? {#section_4D8C2C2D766842E6B12F3ECC774A64D5}

+++Resposta ao [!DNL Adobe Analytics] é usada para medir [!DNL Target] atividades (chamadas de A4T), [!DNL Analytics] coleta dados que não estão disponíveis quando não há [!DNL Target] na página. Isso ocorre porque a atividade do [!DNL Target] aciona uma chamada na parte superior da página, mas o [!DNL Analytics] geralmente aciona suas chamadas de coleta de dados na parte inferior da página. Na implementação do A4T até o momento, a Adobe inclui estes dados adicionais sempre que uma atividade do [!DNL Target] estava ativa.

Para obter mais informações, consulte [Redução de visitas aumentadas e contagem de visitantes em A4T](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

+++

## O que é um hit de dados parciais? {#section_59A203E289564576BF6821F96B0B9E11}

+++Resposta Uma ocorrência de dados parciais ocorre quando um [!DNL Target] na parte superior da página é acionada, mas uma tag [!DNL Analytics] na parte inferior da página não é acionada. Há várias razões pelas quais esta situação acontece. No [!DNL A4T] até o momento, o Adobe inclui dados parciais sobre esses hits sempre que uma [!DNL Target] A atividade estava ativa. A partir de agora, o Adobe incluirá esses dados adicionais somente quando a variável [!DNL Target] e [!DNL Analytics] as tags do foram disparadas.

Para obter mais informações, consulte [Redução de visitas aumentadas e contagem de visitantes em A4T](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

+++

## Posso ver um pico nas visitas. Como posso saber se essas visitas são causadas por hits de dados parciais? {#section_28506672C6224ED18AC74F6A02F6F811}

+++Resposta Você pode entrar em contato [Atendimento ao cliente do Adobe](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para recuperar um relatório de dados parciais. Estas informações não estão disponíveis diretamente na interface do usuário do [!DNL Analytics].

+++

## Quais são as possíveis causas de hits de dados parciais? {#section_C4BB9925CE6444BE8CB9FBEFE5085546}

+++Responder As ocorrências de dados parciais geralmente são o resultado de uma implementação inadequada, como IDs de conjunto de relatórios desalinhadas. Há também causas legítimas, que incluem páginas lentas, erros de página, ofertas de redirecionamento em uma atividade ou versões de biblioteca desatualizadas.

Para obter mais informações, consulte &quot;O que contribui para dados parciais&quot; em  [Minimizar contagens inflacionadas de visitas e visitantes no A4T](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

+++

## Tenho hits de dados parciais. O que posso fazer para apagar meus dados?  {#section_CBE778A9D07A469E8FF98F68BACC7124}

+++Resposta Você pode criar um conjunto de relatórios virtual para excluir dados parciais históricos de seus relatórios.

Para mais informações, consulte &quot;Como posso exibir as tendências históricas sem dados parciais?&quot; em [Minimizar contagens inflacionadas de visitas e visitantes no A4T](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

+++

## Há algo que eu possa fazer para impedir que minhas páginas gerem hits de dados parciais? {#section_4B00E7E618444BE98A0798DE98F08B21}

+++Resposta Depois de 14 de novembro de 2016, o Adobe incluirá os dados somente quando a variável [!DNL Target] e [!DNL Analytics] as tags do foram disparadas. Essa alteração não é retroativa. Se seus relatórios históricos mostrarem contagens infladas, você poderá excluí-las de seus relatórios criando um conjunto de relatórios virtual. Consulte &quot;Como posso visualizar as tendências históricas sem dados parciais?&quot; em [Minimizar contagens inflacionadas de visitas e visitantes no A4T](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

Há também etapas que você pode executar para minimizar os hits de dados parciais. Para obter mais informações, consulte &quot;Quais são as práticas recomendadas para reduzir dados parciais?&quot; em [Minimizar contagens inflacionadas de visitas e visitantes no A4T](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

+++

## Se os dados do hit de dados parciais forem removidos dos relatórios, não estou perdendo valores? [!DNL Target] ou dados do Analytics? {#section_EBC39E8A0F6A40E58F51E776936F7D9E}

+++Resposta Incluindo dados parciais em [!DNL Analytics] os relatórios do realmente fornecem informações adicionais, mas também criam inconsistência com dados históricos de períodos em que não havia [!DNL Target] atividades em execução. A inclusão de dados de ocorrência parcial pode causar problemas para [!DNL Analytics] usuários que estão analisando tendências ao longo do tempo.

Há etapas que você pode executar para minimizar os hits de dados parciais. Para obter mais informações, consulte &quot;Quais são as práticas recomendadas para reduzir dados parciais?&quot; em [Minimizar contagens inflacionadas de visitas e visitantes no A4T](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

+++

## Existem tipos específicos de [!DNL Target] atividades com maior probabilidade de causar hits de dados parciais? {#section_69837442A9B84366BEFDA4588B31E574}

+++Responder as ofertas de redirecionamento enviam imediatamente um usuário para uma página diferente, o que significa que o [!DNL Analytics] não é acionada na primeira página.

+++