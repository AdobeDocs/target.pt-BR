---
keywords: A/B; métricas de atividade; métricas; definir métricas; métrica de objetivo; configurações de atividade; métrica de sucesso; conversão; receita; engajamento
description: Saiba como especificar métricas em uma atividade  [!DNL Adobe Target] A/B para determinar quando uma visita é bem-sucedida, como [!UICONTROL Conversão], [!UICONTROL Receita] e [!UICONTROL Envolvimento].
title: Como definir métricas de meta em uma atividade A/B?
feature: A/B Tests
exl-id: 9e9e8787-c0cd-4aab-bd2d-0e9591e0a07d
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 57%

---

# Definir métricas

Use métricas em uma atividade A/B [!DNL Adobe Target] para determinar quando uma visita é bem-sucedida.

Para obter informações detalhadas sobre métricas de sucesso, consulte [Métricas de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Na seção **[!UICONTROL Configurações de Relatórios]** da página **[!UICONTROL Metas e Configurações]**, selecione uma [métrica de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Selecionar métrica de sucesso](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_metrics-new.png)

   A opção [!UICONTROL Selecionar métricas] lista as métricas de sucesso que você pode escolher para a sua atividade. As métricas de sucesso são divididas nas seguintes categorias:

   * [!UICONTROL Conversão]
   * [!UICONTROL Receita]
   * [!UICONTROL Participação]

   Você pode usar qualquer uma das métricas de sucesso predefinidas ou criar uma métrica de sucesso personalizadas. Você também pode marcar uma métrica de sucesso como uma métrica principal. Cartões de relatórios e Experience Cloud mostram a primeira métrica por padrão, se alguma estiver definida.

1. Especifique as configurações para suas métricas.

   As configurações disponíveis dependem da métrica de sucesso que você estiver usando.

   Se estiver habilitado, o campo [!UICONTROL Valor estimado de Conversão] (não disponível para as métricas de [!UICONTROL Pontuação da página]) fornece um valor para a meta. Este valor permite que o [!DNL Target] calcule a estimativa de aumento da receita. Este campo é opcional, mas a receita incremental para qualquer métrica que não seja de receita não pode ser calculada sem ele. O tipo de dados é a moeda. Este campo é exibido progressivamente depois que o usuário indica a ação realizada para satisfazer o objetivo. Consulte [Aumento estimado na receita](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) para obter mais informações.

   A configuração correta das métricas de sucesso é essencial para garantir que você obtenha os dados esperados.

   Para obter mais informações, consulte [Métricas de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. (Opcional) Adicione condições adicionais.

Ao nomear ou renomear uma métrica, os seguintes caracteres não são permitidos:

| Caractere | Descrição |
|--- |--- |
| / | Barra |
| ? | Ponto de interrogação |
| # | Sinal numérico |
| : | Dois-pontos |
| = | Igual a |
| + | Plus |
| - | Menos |
| @ | Sinal de arroba |

## Vídeo de treinamento: Métricas de atividade (7:43) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo inclui informações sobre trabalhar com métricas de sucesso.

* Compreender métricas de &quot;meta&quot;
* Entender e construir métricas de conversão, receita e envolvimento
* Criar uma métrica de rastreamento de cliques

>[!VIDEO](https://video.tv.adobe.com/v/17380)
