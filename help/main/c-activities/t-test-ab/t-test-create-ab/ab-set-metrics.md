---
keywords: A/B; métricas de atividade; métricas; definir métricas; métrica de objetivo; configurações de atividade; métrica de sucesso; conversão; receita; engajamento
description: Descubra como definir métricas em uma atividade A/B, de Direcionamento de experiência ou de Teste multivariado para determinar o sucesso da visita, incluindo [!UICONTROL Conversão], [!UICONTROL Receita] e [!UICONTROL Envolvimento].
title: Como definir métricas de meta em uma atividade A/B?
feature: A/B Tests
exl-id: 9e9e8787-c0cd-4aab-bd2d-0e9591e0a07d
TQID: 'https://experienceleague.adobe.com/WE27AidwrwYLn-ZlnpxKNfOG2jT07iPYztdrovRl0Qk'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: c87804d95464cc31658be23bc7de051c6e1bc12e
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 24%
---
# Definir métricas {#ab-set-metrics}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba como definir a métrica de meta e as métricas adicionais de uma atividade A/B, de Direcionamento de experiência (XT) ou de Teste multivariado (MVT) e quais caracteres não são permitidos em nomes de métricas.

>[!ENDSHADEBOX]

Use métricas em uma atividade de [!DNL Adobe Target] A/B, [!UICONTROL Direcionamento de experiência] (XT) ou [!UICONTROL Teste multivariado] (MVT) para determinar quando uma visita obtém sucesso. Para obter informações detalhadas sobre métricas de sucesso, consulte [Métricas de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#overview).

>[!NOTE]
>
>Esta página se aplica quando [!DNL Adobe Target] é a fonte de relatórios. Para as outras fontes de relatórios, consulte [[!DNL Adobe Analytics] como fonte de relatórios para [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) and [[!DNL Target] relatórios em [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md).

## Definir uma métrica {#set-a-metric}

1. Na seção **[!UICONTROL Configurações de Relatórios]** da página **[!UICONTROL Metas e Configurações]**, selecione uma [métrica de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#overview).

   A opção **[!UICONTROL Selecionar métricas]** lista as métricas de sucesso que você pode escolher para a sua atividade. As métricas de sucesso são divididas nas seguintes categorias:

   * **[!UICONTROL Conversão]**
   * **[!UICONTROL Receita]**
   * **[!UICONTROL Participação]**

   Você pode usar qualquer uma das métricas de sucesso predefinidas ou criar uma métrica de sucesso personalizadas. Você também pode marcar uma métrica de sucesso como uma métrica principal. Cartões de relatórios e Experience Cloud mostram a primeira métrica por padrão, se alguma estiver definida.

   ![](../../assets/metric-1.png)

1. Especifique as configurações para suas métricas. As configurações disponíveis dependem da métrica de sucesso que você está usando.

1. Se estiver habilitado, o campo **[!UICONTROL Valor estimado de Conversão]** fornece um valor para a meta:

   * O valor permite que [!DNL Target] calcule o aumento estimado da receita.
   * O campo é opcional; no entanto, a receita incremental para qualquer métrica que não seja de receita não pode ser calculada sem ele.
   * O campo não está disponível para as métricas **[!UICONTROL Pontuação da página]**.
   * O tipo de dados é a moeda.
   * O campo é exibido progressivamente depois que o usuário indica a ação tomada para atender à meta.

   Consulte [Aumento estimado na receita](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) para obter mais informações. A configuração correta das métricas de sucesso é essencial para garantir que você obtenha os dados esperados.

   ![](../../assets/metric-2.png)

1. (Opcional) Para rastrear mais do que a métrica de meta, clique em **[!UICONTROL Adicionar uma nova métrica]**, selecione e configure cada métrica adicional conforme descrito nas etapas anteriores.

1. Quando terminar de definir suas métricas, clique em **[!UICONTROL Continuar]** em uma atividade de XT ou **[!UICONTROL Salvar e Fechar]** em uma atividade de MVT.

## Caracteres não permitidos em nomes de métricas {#metric-name-rules}

![](../../assets/metric-3.png)

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
