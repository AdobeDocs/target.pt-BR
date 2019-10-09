---
description: Notas de versão relacionadas às APIs e SDKs do servidor do Adobe Target
keywords: at.js;api;release;updates;apis;sdks;server-side;server-side;server-side;api;delivery api
seo-description: Notas de versão relacionadas às APIs do servidor do Adobe Target.
seo-title: Notas de versão relacionadas às APIs do servidor do Adobe Target.
solution: Target
title: Notas de versão - APIs do servidor do Target
topic: Padrão
translation-type: tm+mt
source-git-commit: 434b103cee15e2e3efdb53febe15c689b5ccd48e

---


# Notas de versão - APIs do servidor do Target

Notas de versão relacionadas às APIs [do servidor do](https://developers.adobetarget.com/api/delivery-api/)Adobe Target.

## V1/entrega (9 de outubro de 2019)

Um endpoint da API de entrega totalmente novo foi lançado.

* New [documentation](https://developers.adobetarget.com/api/delivery-api/) is available.
* Um terminal para recuperar experiências para uma ou mais mboxes.
* Recupere atividades criadas pelo VEC por meio da API.

   A resposta que contém atividades criadas por VEC tem seletores que podem ser usados para ocultar apenas partes da sua página que precisam ser personalizadas. Isso ajuda a otimizar a métrica [](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html)Primeira pintura em Conteúdo da sua página, que é um KPI importante para sua empresa atingir uma pontuação alta no sistema [Google PageRank](https://en.wikipedia.org/wiki/PageRank) .

* Suporte para um objeto totalmente novo chamado Exibições, usado para aplicativos [de página](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md) única (SPAs) e aplicativos [](/help/c-target-mobile-app/target-mobile-app.md)móveis.
* Suporte para busca prévia de exibições e mboxes para otimizar o desempenho por meio do cache.
* Suporte para enviar notificações para exibições e mboxes pré-buscadas.

>[!IMPORTANT]
>
>A documentação da API legacy [/v1/mbox e /v2/batchmbox](https://developers.adobetarget.com/api/legacy-api/index.html) ainda pode ser acessada. Entretanto, novos recursos serão desenvolvidos na nova API de entrega e não serão suportados pelas APIs herdadas.
