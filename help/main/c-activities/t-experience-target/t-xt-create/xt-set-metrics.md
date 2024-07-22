---
keywords: direcionamento de experiência; xt; métricas; definir métricas; métrica de objetivo; configurações de atividade; métrica de sucesso; conversão; receita; envolvimento
description: Saiba como especificar métricas em uma atividade  [!DNL Adobe Target] [!UICONTROL Experience Targeting] para determinar quando uma visita é bem-sucedida, como [!UICONTROL Conversion], [!UICONTROL Revenue] ou [!UICONTROL Engagement].
title: Como definir métricas de meta em uma atividade [!UICONTROL Experience Targeting]?
feature: Experience Targeting
exl-id: 16249930-8b9c-441c-bd14-5f32332556d2
source-git-commit: d7c1bbbbc8d1dcc45ac09a09f6b3be01f7542384
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 56%

---

# Definir métricas em [!UICONTROL Experience Targeting] (XT) atividades

Use métricas em uma atividade [!DNL Adobe Target] [!UICONTROL Experience Targeting] (XT) para determinar quando uma visita obtém sucesso.

Para obter informações detalhadas sobre métricas de sucesso, consulte [Métricas de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Especifique a meta da atividade.
1. Selecione uma métrica [de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Selecionar métrica de sucesso](/help/main/c-activities/t-experience-target/t-xt-create/assets/ab_metrics-new.png)

   A página [!UICONTROL Select Metrics] lista as métricas de sucesso que você pode escolher para a sua atividade. As métricas de sucesso são divididas nas seguintes categorias:

   * [!UICONTROL Conversion]
   * [!UICONTROL Revenue]
   * [!UICONTROL Engagement]

   Use qualquer uma das métricas de sucesso pré-criadas ou crie uma métrica de sucesso personalizada. Você também pode marcar uma métrica de sucesso como uma métrica principal. Cartões de relatórios e Experience Cloud mostram a primeira métrica por padrão, se alguma estiver definida.
1. Especifique as configurações para suas métricas.

   As configurações disponíveis dependem da métrica de sucesso que você está usando.

   Se estiver habilitado, o campo [!UICONTROL Estimated Value of the Conversion] (não disponível para métricas [!UICONTROL Page Score]) fornece um valor para a meta. Este valor permite que o [!DNL Target] calcule a estimativa de aumento da receita. Este campo é opcional, mas a receita incremental para qualquer métrica que não seja de receita não pode ser calculada sem ele. O tipo de dados é a moeda. Este campo é exibido progressivamente depois que o usuário indica a ação realizada para satisfazer o objetivo. Consulte [Aumento estimado na receita](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) para obter mais informações.

   A configuração correta das métricas de sucesso é essencial para garantir que você obtenha os dados que espera.

   Para obter mais informações, consulte [Métricas de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. (Opcional) Adicione condições adicionais.
1. Clique em **[!UICONTROL Continue]** quando terminar de definir suas métricas.

Ao nomear ou renomear uma métrica, os seguintes caracteres não são permitidos:

| Caractere | Descrição |
|--- |--- |
| `/` | Barra |
| `?` | Ponto de interrogação |
| `#` | Sinal numérico |
| `:` | Dois-pontos |
| `=` | Igual a |
| `+` | Plus |
| `-` | menos |
| `@` | Sinal de arroba |

## Vídeo de treinamento: métricas de atividade (7:43) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo inclui informações sobre trabalhar com métricas de sucesso.

* Compreender métricas de &quot;meta&quot;
* Entender e compilar métricas [!UICONTROL Conversion], [!UICONTROL Revenue] e [!UICONTROL Engagement]
* Criar uma métrica de rastreamento de cliques

>[!VIDEO](https://video.tv.adobe.com/v/17380)
