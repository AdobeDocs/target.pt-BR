---
keywords: direcionamento de experiência; xt; métricas; definir métricas; métrica de objetivo; configurações de atividade; métrica de sucesso; conversão; receita; envolvimento
description: Saiba como especificar métricas em uma [!DNL Adobe Target] [!UICONTROL Direcionamento de experiência] atividade para determinar quando uma visita é bem-sucedida, como [!UICONTROL Conversão], [!UICONTROL Receita]ou [!UICONTROL Envolvimento].
title: Como definir métricas de meta em uma [!UICONTROL Direcionamento de experiência] Atividade?
feature: Experience Targeting
exl-id: 16249930-8b9c-441c-bd14-5f32332556d2
source-git-commit: d7c1bbbbc8d1dcc45ac09a09f6b3be01f7542384
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 62%

---

# Definir métricas no [!UICONTROL Direcionamento de experiência] Atividades do (XT)

Usar métricas em uma [!DNL Adobe Target] [!UICONTROL Direcionamento de experiência] (XT) para determinar quando uma visita obtém sucesso.

Para obter informações detalhadas sobre métricas de sucesso, consulte  [Métricas de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Especifique a meta da atividade.
1. Selecione uma métrica [de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Selecionar métrica de sucesso](/help/main/c-activities/t-experience-target/t-xt-create/assets/ab_metrics-new.png)

   A variável [!UICONTROL Selecionar métricas] A página lista as métricas de sucesso que você pode escolher para a sua atividade. As métricas de sucesso são divididas nas seguintes categorias:

   * [!UICONTROL Conversão]
   * [!UICONTROL Receita]
   * [!UICONTROL Participação]

   Use qualquer uma das métricas de sucesso pré-criadas ou crie uma métrica de sucesso personalizada. Você também pode marcar uma métrica de sucesso como uma métrica principal. Cartões de relatórios e Experience Cloud mostram a primeira métrica por padrão, se alguma estiver definida.
1. Especifique as configurações para suas métricas.

   As configurações disponíveis dependem da métrica de sucesso que você está usando.

   Se ativado, a variável [!UICONTROL Valor estimado da conversão] campo (não disponível para [!UICONTROL Pontuação da página] ) fornece um valor para a meta. Este valor permite que o [!DNL Target] calcule a estimativa de aumento da receita. Este campo é opcional, mas a receita incremental para qualquer métrica que não seja de receita não pode ser calculada sem ele. O tipo de dados é a moeda. Este campo é exibido progressivamente depois que o usuário indica a ação realizada para satisfazer o objetivo. Consulte [Aumento estimado na receita](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) para obter mais informações.

   A configuração correta das métricas de sucesso é essencial para garantir que você obtenha os dados que espera.

   Para obter mais informações, consulte [Métricas de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. (Opcional) Adicione condições adicionais.
1. Clique em **[!UICONTROL Continuar]** quando terminar de definir suas métricas. 


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
* Entender e construir métricas de [!UICONTROL conversão], [!UICONTROL receita] e [!UICONTROL envolvimento]
* Criar uma métrica de rastreamento de cliques

>[!VIDEO](https://video.tv.adobe.com/v/17380)
