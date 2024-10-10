---
keywords: vários públicos-alvo; versões de experiência; versões de experiência de direcionamento
description: Descubra como direcionar diferentes segmentos de público-alvo com versões da mesma experiência em atividades A/B.
title: Posso usar várias versões de experiência em uma atividade A/B?
feature: A/B Tests
hide: true
hidefromtoc: true
source-git-commit: ec35109b5d668a96f7e71149df7c965ce2bf3ceb
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 52%

---

# Vários públicos-alvo de uma experiência em um Teste A/B

Você pode direcionar versões da mesma experiência para públicos diferentes em [!DNL Adobe Target] atividades A/B. Você pode configurar vários públicos-alvo para uma experiência no [!UICONTROL Visual Experience Composer] (VEC) ou no Experience Composer baseado em formulário.

Os visitantes podem alternar entre públicos-alvo de experiência à medida que seu perfil muda. Os visitantes não ficam presos na mesma experiência ao longo da vida útil da atividade.

Por exemplo, se seu site usa um design consistente em suas páginas ou produtos e você quer usar a mesma experiência para vários públicos-alvo (como visitantes com navegadores em idiomas diferentes), você pode definir várias versões da experiência. Você pode apresentar a mesma experiência para visitantes que falam inglês e japonês, sendo a única diferença o texto apresentado no idioma do visitante. Dados são coletados para a experiência, independentemente do idioma, para que o relatório apresente a performance da experiência, em vez da versão.

Sem a habilidade de definir versões de experiência, você teria que definir testes diferentes para cada idioma (neste exemplo), e então agregar os resultados manualmente para tentar obter uma ideia de como seria o desempenho de uma única experiência com dois idiomas. Isso produz resultados menos precisos. Para alguns testes, estes cálculos podem até mesmo não serem úteis devido ao modo que visitantes são randomizados.

Ao criar versões diferentes de uma experiência, você recebe informações mais precisas sem a necessidade de cálculos manuais e suposições.

## Cenário

Você está testando duas experiências: um banner direcionado geograficamente e um banner genérico. O banner para cada geografia precisa ser diferente, mas o teste geral é determinar se o geolocalização é melhor do que mostrar o conteúdo genérico. Se você configurasse uma experiência separada para cada local, estaria medindo o desempenho de cada geolocalização em relação à outra, em vez de avaliar se a geolocalização ajuda a atingir suas metas de sucesso quando medida em relação ao banner genérico.

Nesse caso, o que você precisa são versões geográficas específicas da experiência, para testar a experiência com geolocalização em relação a um controle não geolocalizado.

1. [Crie uma atividade A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) normalmente.

   Ao configurar a experiência que terá múltiplas versões, selecione o público-alvo para cada versão, conforme os passos a seguir.

1. Selecione a experiência e clique em **[!UICONTROL Configure]** > **[!UICONTROL Multiple Audiences]**.

1. Clique no ícone **[!UICONTROL Add Audience]** ( ![Ícone Adicionar](/help/main/assets/icons/Add.svg) ) no painel Públicos-alvo de experiência e selecione o primeiro público-alvo que deseja direcionar. Repita para cada público-alvo.

   Se o público-alvo ainda não existir, clique em [Criar público-alvo](/help/main/c-target/c-audiences/create-audience.md#task_E18BD77A9A8F4ED0AC50569F94556558) e configure-o.

   Se um visitante se qualifica para mais de um público-alvo, o conteúdo para todos públicos-alvo são exibidos, com o último na lista renderizando a página.

1. Continue configurando a atividade.

## Práticas recomendadas

* Escolha públicos-alvo mutuamente exclusivos. Se a atividade foi criada no VEC, se um visitante corresponder a mais de um público-alvo, o conteúdo para cada público será retornado, com o conteúdo do público listado por último sendo exibido na página.
* Públicos-alvo de entrada de atividade definidos no diagrama são combinados com os públicos-alvo da experiência usando uma condição E. Para entrar na atividade, um visitante deve fazer parte do público-alvo da atividade e um dos públicos-alvo da experiência.
* Adicione os mesmos públicos-alvo como segmentos para relatórios. Isso ajuda você a observar os resultados do teste no nível superior da experiência A versus B e no nível inferior da experiência A versus B apenas para o &quot;idioma do navegador ja_JP&quot;. Isso funciona somente para relatórios baseados em [!DNL Target], não para relatórios baseados em [!DNL Analytics].