---
keywords: A/B; métricas de atividade; métricas; definir métricas; métrica de objetivo; configurações de atividade; métrica de sucesso; conversão; receita; engajamento
description: Descubra como definir métricas em uma atividade A/B para determinar o sucesso da visita, incluindo [!UICONTROL Conversão], [!UICONTROL Receita] e [!UICONTROL Envolvimento].
title: Como definir métricas de meta em uma atividade A/B?
feature: A/B Tests
exl-id: 9e9e8787-c0cd-4aab-bd2d-0e9591e0a07d
TQID: https://experienceleague.adobe.com/WE27AidwrwYLn-ZlnpxKNfOG2jT07iPYztdrovRl0Qk
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 305
ht-degree: 55%

---

# Definir métricas

Use métricas em uma atividade A/B [!DNL Adobe Target] para determinar quando uma visita é bem-sucedida.

Para obter informações detalhadas sobre métricas de sucesso, consulte [Métricas de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Na seção **[!UICONTROL Configurações de Relatórios]** da página **[!UICONTROL Metas e Configurações]**, selecione uma [métrica de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

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
