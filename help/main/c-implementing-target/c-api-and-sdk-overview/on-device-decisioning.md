---
keywords: lado do servidor; lado do servidor; sdk; sdks; no dispositivo; decisão; no dispositivo; no dispositivo; latência zero; latência; próximo de zero; node.js
description: Saiba como usar a decisão no dispositivo para armazenar em cache seu [!DNL Target] Atividades A/B e MVT no seu servidor para executar decisões na memória a uma latência próxima de zero.
title: O que é o On-Device Decisioning?
feature: Implement Server-side
role: Developer
exl-id: ae782511-6f32-4123-be76-838584e05b39
source-git-commit: 3c64945eb1898457a9d6a3e7bbfa64420bf1250a
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 9%

---

# Decisão no dispositivo

A decisão no dispositivo oferece a capacidade de armazenar em cache seu [!DNL Adobe Target] [!UICONTROL Teste A/B] e [!UICONTROL Direcionamento de experiência] (XT) em seu servidor e executar decisões na memória a uma latência próxima de zero, sem bloquear solicitações de rede para a [!DNL Adobe Target] Edge Network.

Para obter mais informações, consulte os tópicos:

* [Decisão no dispositivo para o lado do cliente](https://developer.adobe.com/target/implement/client-side/){target=_blank}
* [Decisão no dispositivo para o lado do servidor](https://developer.adobe.com/target/implement/server-side/sdk-guides/on-device-decisioning/){target=_blank}

## Webinário: Personalize e teste em latência zero com decisões no dispositivo do [!DNL Adobe Target]

Mais do que nunca, os profissionais de marketing, proprietários de produtos e desenvolvedores estão sendo incumbidos de otimizar a experiência geral do cliente em sites, aplicativos e em todos os outros lugares onde eles se conectam com seus clientes. Várias ferramentas com silos de dados e implementações complicadas são inadequadas.

Neste webinário gravado, [!DNL Adobe Target] especialistas em produtos discutem como mover as decisões de otimização de experiência crítica no dispositivo para executar localmente com latência próxima de zero pode abrir portas para novos casos de uso interessantes e, ao mesmo tempo, melhorar o desempenho do site para seus clientes.

>[!VIDEO](https://video.tv.adobe.com/v/328148)

## Práticas recomendadas

O Adobe recomenda as seguintes práticas recomendadas ao usar decisões no dispositivo:

### Práticas recomendadas para o método de decisão &quot;no dispositivo&quot; {#best-practices-on-device}

Ao usar &quot;no dispositivo&quot; como método de decisão, o artefato é baixado quando o visitante carrega a página da Web pela primeira vez. Qualquer qualificação de atividade que precisa ocorrer no primeiro carregamento da página (sem cache) só acontece depois que o artefato é totalmente baixado. Há determinadas práticas recomendadas que você pode seguir para garantir que as qualificações de atividade aconteçam rapidamente para um novo visitante anônimo.

* Desative atividades com capacidade &quot;no dispositivo&quot; que não devem estar no artefato.
* Se tiver [!DNL Target Premium], você pode usar [propriedades/espaços de trabalho](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) para criar arquivos de artefatos diferentes para espaços de trabalho diferentes.
* Se os arquivos de artefato se tornarem muito grandes devido a motivos legítimos, você poderá usar o método de decisão &quot;híbrido&quot;. Este método permite baixar o artefato simultaneamente e tudo [!DNL Target] As chamadas de API passam pela rede até que o artefato seja baixado. Leia o melhor [seção de práticas no modo de decisão &quot;híbrido&quot;](#best-practices-hybrid) abaixo para saber mais sobre essa abordagem.
* Se você tiver um Aplicativo de página única (SPA), [!DNL Adobe] O recomenda carregar e inicializar a at.js antes de carregar o arquivo JavaScript principal do seu aplicativo durante o primeiro carregamento da página. Essa abordagem inicia o download de artefatos muito antes, fornecendo uma renderização de experiência mais rápida.

### Práticas recomendadas quando o método de decisão é &quot;híbrido&quot; {#best-practices-hybrid}

Ao usar &quot;híbrido&quot; como método de decisão, o artefato é baixado em paralelo. Até que o artefato seja baixado, qualquer [!DNL Target] As chamadas de API passam pela rede mesmo se os &quot;locais&quot; forem capazes no dispositivo. Esse comportamento é padrão para todos `getOffers()` O e o fornecem o melhor desempenho na maioria das situações. Se você alterar o comportamento padrão de `getOffers()` definindo a variável `decisioningMethod` para `on-device`, siga as práticas recomendadas para evitar erros e garantir o melhor desempenho.

* Se decidir chamar o `getOffers()` com `decisioningMethod` as `on-device` quando a página é carregada pela primeira vez, você deve fazer isso dentro do manipulador de eventos at.js &quot;ARTIFACT_DOWNLOAD_SUCCEEDED&quot; para evitar erros. Se o artefato for muito grande, qualquer &quot;local&quot; usando essa abordagem será renderizado somente após o download completo do artefato, o que pode atrasar a renderização da experiência. [!DNL Adobe] O recomenda que você raramente use essa abordagem. Siga as práticas recomendadas para reduzir o tamanho do artefato no [Seção de práticas recomendadas &quot;No dispositivo&quot;](#best-practices-on-device) acima ao usar essa abordagem.

## Tutorial: Decisão no dispositivo

[!DNL Adobe Target] a decisão no dispositivo permite a entrega de conteúdo de latência quase zero.

Este vídeo de 7 minutos:

* Descreve a decisão no dispositivo, incluindo como ela se compara a outros métodos de [!DNL Target] implementação
* Demonstra como ativar a decisão no dispositivo no [!DNL Target]
* Examina uma atividade de compositor baseada em formulário de amostra que foi configurada com conteúdo JSON
* Mostra exemplos de código do SDK Node.JS contendo a configuração de chave necessária para a tomada de decisão no dispositivo
* Demonstra resultados em um navegador

>[!VIDEO](https://video.tv.adobe.com/v/329032)

Para obter mais vídeos e tutoriais, consulte o [Adobe Target Tutorials](https://experienceleague.adobe.com/docs/target-learn/tutorials/overview.html?lang=pt-BR) guia.

## Adobe Tech Blog - Parte 1: Executar [!DNL Adobe Target] SDK do NodeJS para experimentação e personalização em plataformas de borda (Trabalhadores do Akamai Edge)

[Clique aqui para acessar a publicação do blog](https://medium.com/adobetech/part-1-run-adobe-target-nodejs-sdk-for-experimentation-and-personalization-on-edge-platforms-4d8660964ed9).

## Adobe Tech Blog — Parte 2: Execute o SDK NodeJS do [!DNL Adobe Target] para experimentação e personalização em plataformas de borda (AWS Lambda@Edge)

[Clique aqui para acessar a publicação do blog](https://medium.com/adobetech/part-2-run-adobe-target-nodejs-sdk-for-experimentation-and-personalization-on-edge-platforms-aws-4d6bdac24563).