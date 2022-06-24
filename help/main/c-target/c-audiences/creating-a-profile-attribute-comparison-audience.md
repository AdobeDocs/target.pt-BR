---
keywords: público-alvo, propensão, atributo de perfil, comparar, comparação, criar público-alvo, criação de público-alvo
description: Saiba como definir um público-alvo para comparar dois atributos de perfil.
title: Posso comparar dois atributos de perfil para uso nos públicos-alvo?
feature: Audiences
exl-id: 033e90f1-5a05-4fce-a520-68826860a908
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 62%

---

# Criar um público-alvo de comparação do atributo de perfil

Defina um público-alvo em [!DNL Adobe Target] para comparar dois atributos de perfil do [Biblioteca de público-alvo](/help/main/c-target/c-audiences/audiences.md) ou em [público-alvo somente de atividades](/help/main/c-target/creating-activity-only-audience.md). O uso de operadores, como maior que, menor que ou igual a, define um público-alvo para comparar dinamicamente os valores de dois atributos de perfil diferentes.

>[!NOTE]
>
>Essa funcionalidade está disponível somente para a categoria de [[!UICONTROL Perfil do visitante]](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E).

## Visão geral {#section_303CBC78194D49A2A004945D425441E1}

Os públicos-alvo são definidos por regras que determinam quem está incluso ou foi excluído de uma atividade no [!DNL Target]. Uma definição de público-alvo pode incluir diversas regras, e cada uma delas pode incluir vários parâmetros. Se uma das regras incluídas usar a variável [!UICONTROL Perfil do visitante] , você pode definir uma regra com base no valor específico de um atributo de perfil de visitante ou comparar o valor desse atributo com outro atributo de perfil de visitante.

Por exemplo, suponhamos que você trabalhe para uma empresa de móveis e tenha feito o upload de duas pontuações de propensão de cliente no [!DNL Target]:

* Probabilidade de comprar móveis para a sala de jantar nos próximos 90 dias
* Probabilidade de comprar móveis para a sala de estar nos próximos 90 dias

Você poderia criar um público-alvo definido como a propensão para comprar móveis para a sala de jantar maior do que para comprar móveis para a sala de estar. [!DNL Target]O compararia dinamicamente as pontuações de propensão para sala de jantar e sala de estar de um visitante específico, para determinar se ele é qualificável para esse público-alvo.

Para obter mais informações, consulte [Métodos para colocar os dados no Target](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/){target=_blank}.

## Criar um público-alvo de comparação do atributo de perfil {#section_7A62FD47D5C74C3EBC3417ACDBB85013}

1. Clique em **[!UICONTROL Públicos-alvo]** > **[!UICONTROL Criar público-alvo]**.
1. Nomeie o público-alvo e adicione uma descrição opcional.
1. Arrastar e soltar **[!UICONTROL Perfil do visitante]** no painel do construtor de público-alvo.
1. Na lista suspensa **[!UICONTROL Perfil do visitante]**, escolha um atributo:

   ![Pontuação de propensão 1](assets/propensity_score_1.png)

1. Escolha o avaliador:

   ![Pontuação de propensão 2](assets/propensity_score_2.png)

1. Na lista suspensa **[!UICONTROL Escolher o tipo de comparação]**, escolha **[!UICONTROL Atributo]**.

   O tipo de comparação de &quot;valor estático&quot; permite comparar o atributo de perfil do visitante com valores específicos.

   ![Pontuação de propensão 3](assets/propensity_score_3.png)

   >[!NOTE]
   >
   >Se você estiver usando uma das categorias de perfil do visitante padrão (por exemplo, Novo visitante ou Visitante recorrente), poderá escolher apenas a opção de valor estático. As opções de comparação dinâmica não estão disponíveis para as categorias padrão. Outros exemplos em que as opções de comparação dinâmica não estão disponíveis incluem &quot;Primeira página da sessão&quot;, &quot;Não em outros testes&quot;, &quot;Não é primeira página da sessão&quot; e &quot;Afinidade de categorias&quot;.

1. Escolha o atributo adicional que deseja comparar com o atributo inicial.

   ![](assets/propensity_score_4.png)

1. Clique em **[!UICONTROL Concluído]**.

## Vídeo de Treinamento ![Selo de visão geral](/help/main/assets/overview.png) {#section_3BB8DBF3418F4520B3E274B6F40AF8F3}

Assista ao vídeo a seguir para obter mais informações e um cenário no qual seja possível usar esse recurso:

>[!VIDEO](https://video.tv.adobe.com/v/23218/)
