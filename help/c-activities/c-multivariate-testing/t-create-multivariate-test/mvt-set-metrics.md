---
keywords: multivariate;mvt;metrics;set metrics;goal metric;activity settings;success metric;conversion;revenue;engagement
description: Use métricas em um teste multivariado quando uma visita obtém sucesso.
title: Definir métricas
feature: mvt
solution: Target
uuid: 0fb297ba-f1c3-4139-ac37-7fa0bf2ac308
translation-type: tm+mt
source-git-commit: a37753336786efdde392c8c7cd2c546aac79dd12
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 99%

---


# Definir métricas{#set-metrics}

Use métricas em um teste multivariado quando uma visita obtém sucesso.

Para obter informações detalhadas sobre métricas de sucesso, consulte  [Métricas de sucesso](../../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Especifique a meta da atividade.
1. Selecione uma métrica [de sucesso](../../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Definir lista de métricas](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_metrics-list.png)

   A página de [!UICONTROL Métricas selecionadas] lista as métricas de sucesso que você pode escolher para sua atividade. As métricas de sucesso são divididas nas seguintes categorias:

   * Conversão
   * Receita
   * Envolvimento

   Você pode usar qualquer uma das métricas de sucesso predefinidas ou criar uma métrica de sucesso personalizadas. Você também pode marcar uma métrica de sucesso como uma métrica principal. Cartões de relatórios e Experience Cloud mostram a primeira métrica por padrão, se alguma estiver definida.
1. Especifique as configurações para suas métricas.

   As configurações disponíveis dependem da métrica de sucesso que você estiver usando.

   Se estiver habilitado, o campo [!UICONTROL Valor estimado de conversão] (não disponível para as métricas de Pontuação da página) fornece um valor para a meta. Este valor permite que o Target calcule a estimativa de aumento da receita. Este campo é opcional, mas a receita incremental para qualquer métrica que não seja de receita não pode ser calculada sem ele. O tipo de dados é a moeda. Este campo é exibido progressivamente depois que o usuário indica a ação realizada para satisfazer o objetivo. Consulte [Aumento estimado na receita](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) para obter mais informações.

   A configuração correta das métricas de sucesso é essencial para garantir que você obtenha os dados que espera.

   Para obter mais informações, consulte [Métricas de sucesso](../../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)
1. (Opcional) Adicione condições adicionais.
1. Clique em **[!UICONTROL Continuar]** quando terminar de definir suas métricas. 
Observe que quando você nomeia ou renomeia uma métrica, os seguintes caracteres não são permitidos:

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

## Vídeo de treinamento: métricas de atividade (7:43) ![Crachá do tutorial](/help/assets/tutorial.png)

Este vídeo inclui informações sobre trabalhar com métricas de sucesso.

* Compreender métricas de &quot;meta&quot;
* Entender e construir métricas de conversão, receita e envolvimento
* Criar uma métrica de rastreamento de cliques

>[!VIDEO](https://video.tv.adobe.com/v/17380)
