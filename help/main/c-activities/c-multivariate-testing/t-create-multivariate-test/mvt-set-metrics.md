---
keywords: multivariado; mvt; métricas; definir métricas; métrica de objetivo; configurações de atividade; métrica de sucesso; conversão; receita; engajamento
description: Saiba como especificar métricas em uma atividade de  [!DNL Adobe Target] [!UICONTROL Teste multivariado] para determinar quando uma visita é bem-sucedida, como [!UICONTROL Conversão], [!UICONTROL Receita] e [!UICONTROL Envolvimento].
title: Como definir métricas de meta em uma atividade de [!UICONTROL Teste multivariado] (MVT)?
feature: Multivariate Tests
exl-id: 8530b3f1-5daa-4a03-a482-93b10eb23208
TQID: https://experienceleague.adobe.com/iJntBcXy4QNgEq0SnzLpqMX6S5HQ6kBy4PMoQivlVxw
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 353
ht-degree: 56%

---

# Definir métricas para uma atividade de [!UICONTROL Teste multivariado]

Use métricas em um [!DNL Adobe Target] [!UICONTROL Teste multivariado] para determinar quando uma visita obtém sucesso.

Para obter informações detalhadas sobre métricas de sucesso, consulte [Métricas de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Especifique a meta da atividade.
1. Selecione uma métrica [de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Definir lista de métricas](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_metrics-list-new.png)

   A página [!UICONTROL Selecionar métricas] lista as métricas de sucesso que você pode escolher para a sua atividade. As métricas de sucesso são divididas nas seguintes categorias:

   * [!UICONTROL Conversão]
   * [!UICONTROL Receita]
   * [!UICONTROL Participação]

   Você pode usar qualquer uma das métricas de sucesso predefinidas ou criar uma métrica de sucesso personalizadas. Você também pode marcar uma métrica de sucesso como uma métrica principal. Cartões de relatórios e Experience Cloud mostram a primeira métrica por padrão, se alguma estiver definida.

1. Especifique as configurações para suas métricas.

   As configurações disponíveis dependem da métrica de sucesso que você está usando.

   Se estiver habilitado, o campo [!UICONTROL Valor estimado de Conversão] (não disponível para as métricas de [!UICONTROL Pontuação da página]) fornece um valor para a meta. Este valor permite que o [!DNL Target] calcule a estimativa de aumento da receita. Este campo é opcional, mas a receita incremental para qualquer métrica que não seja de receita não pode ser calculada sem ele. O tipo de dados é a moeda. Este campo é exibido progressivamente depois que o usuário indica a ação realizada para satisfazer o objetivo. Consulte [Aumento estimado na receita](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) para obter mais informações.

   A configuração correta das métricas de sucesso é essencial para garantir que você obtenha os dados que espera.

   Para obter mais informações, consulte [Métricas de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

1. (Opcional) Adicione condições adicionais.
1. Clique em **[!UICONTROL Salvar e fechar]** quando terminar de definir suas métricas.

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

## Vídeo de treinamento: Métricas de atividade (7:43) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo inclui informações sobre trabalhar com métricas de sucesso.

* Compreender métricas de &quot;meta&quot;
* Compreender e compilar métricas de [!UICONTROL Conversão], [!UICONTROL Receita] e [!UICONTROL Envolvimento]
* Criar uma métrica de rastreamento de cliques

>[!VIDEO](https://video.tv.adobe.com/v/17380)
