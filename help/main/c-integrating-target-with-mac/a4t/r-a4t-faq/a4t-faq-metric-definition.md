---
keywords: perguntas frequentes; perguntas frequentes; analytics para target; a4T; métrica; definições de métricas
description: Encontre respostas para perguntas sobre definições de métrica e uso do Analytics for [!DNL Target] (A4T). O A4T permite usar os relatórios do Analytics com atividades Adobe [!DNL Target] .
title: Onde posso encontrar informações sobre definições de métricas com o A4T?
feature: Analytics for Target (A4T)
exl-id: 97442622-ba6d-46f8-bfac-72638875d889
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 31%

---

# Definições de métricas - Perguntas frequentes sobre o A4T

Este tópico contém respostas para as perguntas mais frequentes sobre definições de métrica e uso do [!DNL Adobe Analytics] como origem de geração de relatórios para [!DNL Adobe Target] (A4T).

## Qual é a expiração para a associação de atividades? Quanto tempo depois que os visitantes entram na atividade, suas ações são contadas na atividade se não a virem novamente? {#section_41B4958F33534E4B96DEE0C981227A79}

+++Resposta
A expiração padrão da atividade é de 90 dias após a última interação do visitante com a atividade. Esta configuração pode ser ajustada pelo ClientCare, se necessário. Essa configuração é global para todas as atividades, no entanto, não deve ser ajustada para um caso.

+++

## Ao configurar minhas métricas de meta, por que não posso acessar as opções de Configurações avançadas? {#adv-settings}

+++Resposta
As opções [!UICONTROL Advanced Settings] não estão disponíveis para atividades que usam [!DNL Analytics] como fonte de relatórios (A4T).

Para atividades que usam o A4T, a métrica de meta sempre usa as configurações &quot;[!UICONTROL Increment Count & Keep User in Activity]&quot; e &quot;[!UICONTROL On Every Impression]&quot;. Estas configurações são *não* configuráveis.

Para atividades que não sejam do A4T, você pode usar as [opções de Configurações Avançadas](/help/main/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B) para gerenciar a maneira como mede o sucesso. As opções incluem adicionar dependências, escolher se deseja manter o usuário na atividade ou removê-lo e se deseja contar a métrica uma vez por participante ou em cada impressão. Você acessa as opções [!UICONTROL Advanced Settings] em uma atividade que não seja do A4T clicando nas reticências verticais > [!UICONTROL Advanced Settings], conforme mostrado abaixo:

![Configurações avançadas](/help/main/c-activities/r-success-metrics/assets/advanced-settings.png)

+++

## O que são métricas calculadas e como elas substituem a mbox SiteCatalyst:Event que eu costumava usar?  {#section_D59F4719E6B94758A2187427C17F8EF3}

+++Resposta
As métricas calculadas permitem criar métricas personalizadas que são derivadas de segmentos ou cálculos matemáticos. Anteriormente, quando você pode ter usado a `SiteCatlayst:Event` mbox onde `evar27=shoes` e o evento seria `purchase`, agora você criaria um segmento onde `evar27=shoes` e, em seguida, criaria uma métrica calculada onde o evento é `purchase` com o segmento aplicado. Essas métricas podem ser criadas a qualquer momento, mesmo depois que a atividade estiver em andamento. Elas podem ser usadas em qualquer relatório do Analytics.

+++

## O A4T atribui conversões a várias campanhas?  {#section_7F15C727206440CD86B3A8CE77087DF9}

+++Resposta
Sim, usando a configuração &quot;Alocação completa&quot;.

+++