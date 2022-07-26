---
keywords: A/B; métricas de atividade; métricas; definir métricas; métrica de objetivo; configurações de atividade; métrica de sucesso; conversão; receita; envolvimento
description: Saiba como especificar métricas em um Adobe [!DNL Target] Atividade A/B para determinar quando uma visita é bem-sucedida, como Conversão, Receita e Envolvimento.
title: Como defino métricas de meta em uma atividade A/B?
feature: A/B Tests
exl-id: 9e9e8787-c0cd-4aab-bd2d-0e9591e0a07d
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 85%

---

# Definir métricas

Use métricas em uma [!DNL Adobe Target] Atividade A/B para determinar quando uma visita é bem-sucedida.

Para obter informações detalhadas sobre métricas de sucesso, consulte  [Métricas de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Especifique a meta da atividade.
1. Selecione uma métrica [de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Selecionar métrica de sucesso](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_metrics-new.png)

   A página de [!UICONTROL Métricas selecionadas] lista as métricas de sucesso que você pode escolher para sua atividade. As métricas de sucesso são divididas nas seguintes categorias:

   * Conversão
   * Receita
   * Envolvimento

   Você pode usar qualquer uma das métricas de sucesso predefinidas ou criar uma métrica de sucesso personalizadas. Você também pode marcar uma métrica de sucesso como uma métrica principal. Cartões de relatórios e Experience Cloud mostram a primeira métrica por padrão, se alguma estiver definida.
1. Especifique as configurações para suas métricas.

   As configurações disponíveis dependem da métrica de sucesso que você estiver usando.

   Se estiver habilitado, o campo [!UICONTROL Valor estimado de conversão] (não disponível para as métricas de Pontuação da página) fornece um valor para a meta. Este valor permite que o Target calcule a estimativa de aumento da receita. Este campo é opcional, mas a receita incremental para qualquer métrica que não seja de receita não pode ser calculada sem ele. O tipo de dados é a moeda. Este campo é exibido progressivamente depois que o usuário indica a ação realizada para satisfazer o objetivo. Consulte [Aumento estimado na receita](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) para obter mais informações.

   A configuração correta das métricas de sucesso é essencial para garantir que você obtenha os dados que espera.

   Para obter mais informações, consulte [Métricas de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).
1. (Opcional) Adicione condições adicionais.
1. Clique em **[!UICONTROL Continuar]** quando terminar de definir suas métricas. 


Observe que quando você nomeia ou renomeia uma métrica, os seguintes caracteres não são permitidos:

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

## Vídeo de treinamento: métricas de atividade (7:43) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo inclui informações sobre trabalhar com métricas de sucesso.

* Compreender métricas de &quot;meta&quot;
* Entender e construir métricas de conversão, receita e envolvimento
* Criar uma métrica de rastreamento de cliques

>[!VIDEO](https://video.tv.adobe.com/v/17380)
