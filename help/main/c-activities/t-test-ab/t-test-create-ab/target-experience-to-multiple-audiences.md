---
keywords: vários públicos-alvo; versões de experiência; versões de experiência de direcionamento
description: Descubra como direcionar diferentes segmentos de público-alvo com versões da mesma experiência em atividades A/B.
title: Posso usar várias versões de experiência em uma atividade A/B?
feature: A/B Tests
exl-id: 7afe36f0-ec46-4d63-bfff-45d2c8923a04
TQID: 'https://experienceleague.adobe.com/FleyH-u5cWI5vku9E4-RMWeIc95WgPy-VQ-eytxka18'
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
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 4876228feee28031373f7e0abe62a66b05b15274
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 8%
---
# Vários públicos-alvo de uma experiência em um Teste A/B {#multiple-experience-audiences}

>[!BEGINSHADEBOX]

**Nesta página:** saiba como direcionar públicos diferentes com versões da mesma experiência em uma atividade A/B, ilustrada por um caso de uso com as etapas a serem seguidas e as práticas recomendadas.

>[!ENDSHADEBOX]

Em [!DNL Adobe Target] atividades A/B, você pode direcionar versões da mesma experiência para públicos diferentes. Você pode configurar vários públicos-alvo para uma experiência no **[!UICONTROL Visual Experience Composer]** (VEC) ou no Experience Composer baseado em formulário.

Os dados são coletados para a experiência, independentemente da versão, de modo que o relatório mostra o desempenho da experiência, não de cada versão. Os visitantes também podem alternar entre públicos-alvo de experiência à medida que seu perfil muda. Eles não ficam presos na mesma experiência durante o tempo de vida da atividade.

## Caso de uso {#use-case}

Você está testando duas experiências:

* um banner de geolocalização

* um banner genérico.

O banner precisa ser diferente para cada região, mas o objetivo do teste é determinar se o geolocalização tem melhor desempenho do que o conteúdo genérico.

Se você configurar uma experiência separada para cada local, avaliará o desempenho de cada região em relação às outras. Você não mede se a geolocalização ajuda a atingir suas metas de sucesso em comparação ao banner genérico.

Nesse caso, você precisa de versões geográficas específicas da experiência, para testar a experiência com geolocalização em relação a um controle não direcionado geograficamente.

Para configurar as versões específicas da região:

1. [Crie uma atividade A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) normalmente.

   Ao configurar a experiência com várias versões, selecione o público-alvo para cada versão, conforme descrito nas etapas a seguir.

1. Selecione a experiência e clique em **[!UICONTROL Configurar]** > **[!UICONTROL Vários públicos-alvo]**.

1. No painel **[!UICONTROL Públicos-alvo de experiência]**, clique no ícone **[!UICONTROL Adicionar público-alvo]** ( ![ícone Adicionar](/help/main/assets/icons/Add.svg) ) e selecione o primeiro público-alvo que deseja direcionar. Repita para cada público-alvo.

   Se o público-alvo ainda não existir, [crie o público-alvo](/help/main/c-target/c-audiences/create-audience.md) e configure-o.

1. Continue configurando a atividade.

## Práticas recomendadas {#best-practices}

* Escolha públicos-alvo mutuamente exclusivos. Se um visitante se qualificar para mais de um público-alvo, o conteúdo de todos esses públicos-alvo será retornado e o conteúdo do público listado por último será exibido na página. Isso se aplica às atividades criadas no VEC.
* Os públicos-alvo de entrada de atividade definidos no diagrama são combinados com os públicos-alvo de experiência usando uma condição AND. Para entrar na atividade, um visitante deve se qualificar para o público-alvo da atividade e para um dos públicos-alvo da experiência.
* Adicione os mesmos públicos-alvo como segmentos para relatórios. Isso ajuda a observar os resultados do teste no alto nível da experiência A versus B e no nível inferior da experiência A versus B somente para &quot;idioma do navegador ja_JP&quot;. Isso funciona somente para relatórios baseados em [!DNL Target], não para relatórios baseados em [!DNL Analytics].
