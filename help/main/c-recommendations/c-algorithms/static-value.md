---
keywords: regras de inclusão;critérios de inclusão;recomendações;promoção;promoções;filtragem dinâmica;estático;filtro estático
description: Saiba como inserir manualmente um ou mais valores estáticos para filtrar usando regras de inclusão no Adobe [!DNL Target] Recommendations.
title: Como Filtro Por Valores Estáticos Em Atividades Do Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: 217e19bf-521f-4913-9b41-099c9af8b393
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 45%

---

# [!UICONTROL Static Filter]

Insira manualmente um ou mais valores estáticos para filtrar usando regras de inclusão em [!DNL Adobe Target Recommendations].

Por exemplo, apenas recomende um conteúdo com uma classificação de MPA (Motion Picture Association) de &quot;G&quot; ou &quot;PG&quot;.

Você pode criar a quantidade de regras de inclusão necessária. As regras de inclusão são unidas por um operador E. Todas as regras devem ser cumpridas para incluir um item em uma recomendação.

>[!NOTE]
>
>Se você estiver familiarizado com a configuração das regras de inclusão antes do Target versão 17.6.1 (junho de 2017), perceberá que algumas opções e operadores foram alterados. Somente os operadores aplicáveis à opção selecionada são exibidos e alguns operadores foram renomeados (&quot;matches&quot; agora é &quot;equals&quot;) para ficarem mais consistentes e intuitivos. Todas as regras de exclusão existentes criadas antes desta versão foram migradas automaticamente para a nova estrutura. Nenhuma reestruturação é necessária da sua parte.

## Conteúdo recomendado classificado como G ou PG

Para criar uma regra de inclusão com valores estáticos para recomendar conteúdo com uma classificação MPA de &quot;G&quot; ou &quot;PG&quot; apenas (excluir conteúdo &quot;R&quot; e &quot;NC17&quot;), você pode criar as seguintes regras de filtragem &quot;classificação de filme é igual a qualquer um dos g-ratings&quot; e &quot;classificação de filme é igual a qualquer um dos pg-ratings&quot;.
