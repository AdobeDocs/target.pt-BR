---
keywords: perguntas frequentes; perguntas frequentes; analytics para target; a4T; métrica; definições de métricas
description: Encontre respostas para perguntas sobre definições de métricas e uso do Analytics para [!DNL Target] (A4T). O A4T permite usar os relatórios do Analytics com o Adobe [!DNL Target] atividades.
title: Onde posso encontrar informações sobre definições de métricas com o A4T?
feature: Analytics for Target (A4T)
exl-id: 97442622-ba6d-46f8-bfac-72638875d889
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 29%

---

# Definições de métricas - Perguntas frequentes sobre o A4T

Este tópico contém respostas para as perguntas mais frequentes sobre definições de métricas e uso [!DNL Adobe Analytics] como fonte de relatórios para [!DNL Adobe Target] (A4T).

## Qual é a expiração para a associação de atividades? Quanto tempo depois que os visitantes entram na atividade, suas ações são contadas na atividade se não a virem novamente? {#section_41B4958F33534E4B96DEE0C981227A79}

+++Resposta A expiração padrão para a atividade é de 90 dias após a última interação do visitante com a atividade. Essa configuração pode ser ajustada pelo ClientCare, se necessário. Essa configuração é global para todas as atividades, no entanto, não deve ser ajustada para um caso.

+++

## Ao configurar minhas métricas de meta, por que não posso acessar as opções de Configurações avançadas? {#adv-settings}

+++Responda O [!UICONTROL Configurações avançadas] não estão disponíveis para atividades que usam [!DNL Analytics] como fonte de geração de relatórios (A4T).

Para atividades que usam A4T, a métrica de meta sempre usa o &quot;[!UICONTROL Aumentar a contagem e manter o usuário na atividade]&quot; e &quot;[!UICONTROL Em todas as impressões]&quot;. Essas configurações são *not* configurável.

Para atividades não-A4T, você pode usar o [Opções de configurações avançadas](/help/main/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B) para gerenciar a medição do sucesso. As opções incluem adicionar dependências, escolher manter o usuário na atividade ou removê-lo e contar a métrica uma vez por participante ou em todas as impressões. Você acessa o [!UICONTROL Configurações avançadas] opções em uma atividade não A4T clicando nos elipses verticais > [!UICONTROL Configurações avançadas], conforme mostrado abaixo:

![Configurações avançadas](/help/main/c-activities/r-success-metrics/assets/advanced-settings.png)

+++

## O que são métricas calculadas e como elas substituem a mbox SiteCatalyst:Event que eu costumava usar?  {#section_D59F4719E6B94758A2187427C17F8EF3}

+++Resposta As métricas calculadas permitem criar métricas personalizadas que são derivadas de segmentos ou cálculos matemáticos. Anteriormente, quando você pode ter usado a `SiteCatlayst:Event` mbox onde `evar27=shoes` e o evento seria `purchase`, agora você criaria um segmento onde `evar27=shoes` e, em seguida, criaria uma métrica calculada onde o evento é `purchase` com o segmento aplicado. Essas métricas podem ser criadas a qualquer momento, mesmo após a atividade estar em andamento. Elas podem ser usadas em qualquer relatório do Analytics.

+++

## O A4T atribui conversões a várias campanhas?  {#section_7F15C727206440CD86B3A8CE77087DF9}

+++Responda Sim, usando a configuração &quot;Alocação completa&quot;.

+++