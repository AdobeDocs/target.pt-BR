---
keywords: multivariado; mvt; métricas; definir métricas; métrica de objetivo; configurações de atividade; métrica de sucesso; conversão; receita; envolvimento
description: Saiba como especificar métricas em uma atividade  [!DNL Adobe Target] [!UICONTROL Multivariate Test] para determinar quando uma visita é bem-sucedida, como [!UICONTROL Conversion], [!UICONTROL Revenue] e [!UICONTROL Engagement].
title: Como definir métricas de meta em uma atividade [!UICONTROL Multivariate Test] (MVT)?
feature: Multivariate Tests
exl-id: 8530b3f1-5daa-4a03-a482-93b10eb23208
source-git-commit: 8f9c0ea65197fd639d463628e54db79db993c2da
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 60%

---

# Definir métricas para uma atividade [!UICONTROL Multivariate Test]

Use métricas em um [!DNL Adobe Target] [!UICONTROL Multivariate Test] para determinar quando uma visita é bem-sucedida.

Para obter informações detalhadas sobre métricas de sucesso, consulte [Métricas de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Especifique a meta da atividade.
1. Selecione uma métrica [de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Definir lista de métricas](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_metrics-list.png)

   A página [!UICONTROL Select Metrics] lista as métricas de sucesso que você pode escolher para a sua atividade. As métricas de sucesso são divididas nas seguintes categorias:

   * [!UICONTROL Conversion]
   * [!UICONTROL Revenue]
   * [!UICONTROL Engagement]

   Você pode usar qualquer uma das métricas de sucesso predefinidas ou criar uma métrica de sucesso personalizadas. Você também pode marcar uma métrica de sucesso como uma métrica principal. Cartões de relatórios e Experience Cloud mostram a primeira métrica por padrão, se alguma estiver definida.

1. Especifique as configurações para suas métricas.

   As configurações disponíveis dependem da métrica de sucesso que você está usando.

   Se estiver habilitado, o campo [!UICONTROL Estimated Value of the Conversion] (não disponível para as métricas [!UICONTROL Page Score]) fornece um valor para a meta. Este valor permite que o [!DNL Target] calcule a estimativa de aumento da receita. Este campo é opcional, mas a receita incremental para qualquer métrica que não seja de receita não pode ser calculada sem ele. O tipo de dados é a moeda. Este campo é exibido progressivamente depois que o usuário indica a ação realizada para satisfazer o objetivo. Consulte [Aumento estimado na receita](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) para obter mais informações.

   A configuração correta das métricas de sucesso é essencial para garantir que você obtenha os dados que espera.

   Para obter mais informações, consulte [Métricas de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

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
