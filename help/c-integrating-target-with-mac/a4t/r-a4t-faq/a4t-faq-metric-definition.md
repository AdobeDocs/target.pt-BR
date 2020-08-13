---
keywords: faq;frequently asked questions;analytics for target;a4T;metric;metric definitions
description: Este tópico contém respostas para as perguntas mais frequentes sobre definições de métrica e uso do Analytics como origem de geração de relatórios para o Target (A4T).
title: Definições de métricas - Perguntas frequentes sobre o A4T
feature: a4t troubleshooting
topic: Standard
uuid: 41d41665-9057-479d-b0a8-7cffb90ca843
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 100%

---


# Definições de métricas - Perguntas frequentes sobre o A4T{#metric-definitions-a-t-faq}

Este tópico contém respostas para as perguntas mais frequentes sobre definições de métrica e uso do Analytics como origem de geração de relatórios para o Target (A4T).

## Qual é a expiração para a associação de atividades? Quanto tempo depois que os visitantes entram na atividade, suas ações serão contadas na atividade se não a virem novamente?  {#section_41B4958F33534E4B96DEE0C981227A79}

A expiração padrão para a atividade é de 90 dias após a última interação do visitante com a atividade. Isso pode ser configurado pelo Atendimento ao cliente. Essa configuração é global para todas as atividades, no entanto, não deve ser ajustada para um caso.

## As opções avançadas para métricas de sucesso no Target funcionam com o A4T?  {#section_F060E3438F4144258BB95813EDEABDAA}

Atualmente, essas opções não funcionam com o A4T.

## O que são métricas calculadas e como elas substituem a mbox SiteCatalyst:Event que eu costumava usar?  {#section_D59F4719E6B94758A2187427C17F8EF3}

As métricas calculadas permitem criar métricas personalizadas que são derivadas de segmentos ou cálculos matemáticos. Anteriormente, quando você pode ter usado a `SiteCatlayst:Event` mbox onde `evar27=shoes` e o evento seria `purchase`, agora você criaria um segmento onde `evar27=shoes` e, em seguida, criaria uma métrica calculada onde o evento é `purchase` com o segmento aplicado. A vantagem disso é que essas métricas podem ser criadas a qualquer momento, mesmo depois que a atividade estiver em andamento. Elas podem ser usadas em qualquer relatório do Analytics.

## O A4T atribui conversões a várias campanhas?  {#section_7F15C727206440CD86B3A8CE77087DF9}

Sim. Isso é feito usando a configuração &quot;Alocação completa&quot;.
