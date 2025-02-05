---
keywords: A/B; métricas de atividade; métricas; definir métricas; métrica de objetivo; configurações de atividade; métrica de sucesso; conversão; receita; envolvimento
description: Descubra como definir métricas em uma atividade A/B para determinar o sucesso da visita, incluindo [!UICONTROL Conversion], [!UICONTROL Revenue] e [!UICONTROL Engagement].
title: Como definir métricas de meta em uma atividade A/B?
feature: A/B Tests
exl-id: 9e9e8787-c0cd-4aab-bd2d-0e9591e0a07d
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 58%

---

# Definir métricas

Use métricas em uma atividade A/B [!DNL Adobe Target] para determinar quando uma visita é bem-sucedida.

Para obter informações detalhadas sobre métricas de sucesso, consulte [Métricas de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Na seção **[!UICONTROL Reporting Settings]** da página **[!UICONTROL Goals & Settings]**, selecione uma [métrica de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

   A opção [!UICONTROL Select Metrics] lista as métricas de sucesso que você pode escolher para sua atividade. As métricas de sucesso são divididas nas seguintes categorias:

   * [!UICONTROL Conversion]
   * [!UICONTROL Revenue]
   * [!UICONTROL Engagement]

   Você pode usar qualquer uma das métricas de sucesso predefinidas ou criar uma métrica de sucesso personalizadas. Você também pode marcar uma métrica de sucesso como uma métrica principal. Cartões de relatórios e Experience Cloud mostram a primeira métrica por padrão, se alguma estiver definida.

1. Especifique as configurações para suas métricas.

   As configurações disponíveis dependem da métrica de sucesso que você estiver usando.

   Se estiver habilitado, o campo [!UICONTROL Estimated Value of the Conversion] (não disponível para as métricas [!UICONTROL Page Score]) fornece um valor para a meta. Este valor permite que o [!DNL Target] calcule a estimativa de aumento da receita. Este campo é opcional, mas a receita incremental para qualquer métrica que não seja de receita não pode ser calculada sem ele. O tipo de dados é a moeda. Este campo é exibido progressivamente depois que o usuário indica a ação realizada para satisfazer o objetivo. Consulte [Aumento estimado na receita](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) para obter mais informações.

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
