---
keywords: at.js;api;release;updates;apis;sdks;server side;serverside;server-side;api;delivery api
description: Notas de versão relacionadas às APIs do lado do servidor da Adobe Target.
title: Notas de versão relacionadas às APIs do lado do servidor da Adobe Target.
feature: null
topic: Standard
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 2%

---


# Notas de versão - APIs do lado do servidor do Target

Notas de versão relacionadas às APIs [do servidor da](https://developers.adobetarget.com/api/delivery-api/)Adobe Target.

## V1/delivery (9 de outubro de 2019)

Um terminal totalmente novo da API de delivery foi lançado.

* New [documentation](https://developers.adobetarget.com/api/delivery-api/) is available.
* Um terminal para recuperar experiências para uma ou mais mboxes.
* Recupere atividades criadas por VEC por meio da API.

   A resposta que contém atividades criadas por VEC tem seletores que podem ser usados para ocultar apenas partes da sua página que precisam ser personalizadas. Isso ajuda a otimizar a métrica [](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html)Primeira pintura em Conteúdo da sua página, que é um KPI importante para sua empresa atingir uma pontuação alta no sistema [Google PageRank](https://en.wikipedia.org/wiki/PageRank) .

* Suporte para um objeto totalmente novo, chamado Visualização, usado para aplicativos [de página](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md) única (SPAs) e aplicativos [](/help/c-target-mobile-app/target-mobile-app.md)móveis.
* Suporte para pré-busca de visualização e mboxes para otimizar o desempenho por meio do cache.
* Suporte para enviar notificações para visualizações e mboxes pré-buscadas.

>[!IMPORTANT]
>
>A documentação da API legacy [/v1/mbox e /v2/batchmbox](https://developers.adobetarget.com/api/legacy-api/index.html) ainda pode ser acessada. Entretanto, novos recursos serão desenvolvidos na nova API do delivery e não serão suportados pelas APIs herdadas.
