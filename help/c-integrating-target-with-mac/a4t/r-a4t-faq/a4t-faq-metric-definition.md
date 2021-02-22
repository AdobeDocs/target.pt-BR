---
keywords: perguntas frequentes; perguntas frequentes; analytics para target; a4T; métrica; definições de métricas
description: Encontre respostas para perguntas sobre definições de métricas e como usar o Analytics para Públicos alvos (A4T). O A4T permite que você use o relatórios do Analytics com o Adobe Target atividade.
title: Onde posso encontrar informações sobre definições de métricas com A4T?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 418a178aea06e29a1886cf77cb32fde2b8dcb9df
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 58%

---


# Definições de métricas - Perguntas frequentes sobre o A4T

Este tópico contém respostas para as perguntas mais frequentes sobre definições de métrica e uso do Analytics como origem de geração de relatórios para o Target (A4T).

## Qual é a expiração para a associação de atividades? Quanto tempo depois que os visitantes entram na atividade, suas ações serão contadas na atividade se não a virem novamente?   {#section_41B4958F33534E4B96DEE0C981227A79}

A expiração padrão para a atividade é de 90 dias após a última interação do visitante com a atividade. Isso pode ser configurado pelo Atendimento ao cliente. Essa configuração é global para todas as atividades, no entanto, não deve ser ajustada para um caso.

## Ao configurar minhas métricas de objetivo, por que não posso acessar as opções de Configurações avançadas? {#adv-settings}

As opções [!UICONTROL Configurações avançadas] não estão disponíveis para atividades que usam [!DNL Analytics] como a fonte do relatórios (A4T).

Para atividade usando A4T, a métrica de meta sempre usará as configurações &quot;[!UICONTROL Aumentar a contagem e manter o usuário na Atividade]&quot; e &quot;[!UICONTROL Em cada impressão]&quot;. Isso é *não* configurável.

Para atividades não-A4T, você pode usar as [opções de Configurações avançadas](/help/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B) para gerenciar como você avalia o sucesso. As opções incluem adicionar dependências, escolher manter o usuário na atividade ou removê-lo e contar a métrica uma vez por participante ou em cada impressão. Para acessar as opções [!UICONTROL Configurações avançadas] em uma atividade que não seja A4T, clique nas elipses verticais > [!UICONTROL Configurações avançadas], conforme mostrado abaixo:

![Configurações avançadas](/help/c-activities/r-success-metrics/assets/advanced-settings.png)

## O que são métricas calculadas e como elas substituem a mbox SiteCatalyst:Event que eu costumava usar?   {#section_D59F4719E6B94758A2187427C17F8EF3}

As métricas calculadas permitem criar métricas personalizadas que são derivadas de segmentos ou cálculos matemáticos. Anteriormente, quando você pode ter usado a `SiteCatlayst:Event` mbox onde `evar27=shoes` e o evento seria `purchase`, agora você criaria um segmento onde `evar27=shoes` e, em seguida, criaria uma métrica calculada onde o evento é `purchase` com o segmento aplicado. A vantagem disso é que essas métricas podem ser criadas a qualquer momento, mesmo depois que a atividade estiver em andamento. Elas podem ser usadas em qualquer relatório do Analytics.

## O A4T atribui conversões a várias campanhas?   {#section_7F15C727206440CD86B3A8CE77087DF9}

Sim. Isso é feito usando a configuração &quot;Alocação completa&quot;.
