---
keywords: lado do servidor; lado do servidor; sdk; sdks; no dispositivo; decisão; no dispositivo; no dispositivo; latência zero; latência; próximo de zero; node.js
description: Saiba como usar a tomada de decisão no dispositivo para armazenar em cache as atividades  [!DNL Target] A/B e MVT em seu servidor para executar decisões na memória em latência próxima a zero.
title: O que é o On-Device Decisioning?
feature: Implementar o lado do servidor
role: Developer
exl-id: ae782511-6f32-4123-be76-838584e05b39
source-git-commit: fe70f357e2298f1656d713aae5fae800e6775d64
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 10%

---

# Decisão no dispositivo

A decisão no dispositivo fornece a capacidade de armazenar em cache as atividades [!DNL Adobe Target] [!UICONTROL Teste A/B] e [!UICONTROL Direcionamento de experiência] (XT) em seu servidor e executar decisões na memória a uma latência próxima de zero, sem bloquear solicitações de rede para a [!DNL Adobe Target] Edge Network.

Para obter mais informações, consulte [Introdução à decisão no dispositivo](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning) na *[documentação dos SDKs do Adobe Target](https://adobetarget-sdks.gitbook.io/docs/)*.

## Webinar: personalize e teste em latência zero com decisões no dispositivo do [!DNL Adobe Target]

Mais do que nunca, os profissionais de marketing, proprietários de produtos e desenvolvedores estão sendo incumbidos de otimizar a experiência geral do cliente em sites, aplicativos e em todos os outros lugares onde eles se conectam com seus clientes. Várias ferramentas com silos de dados e implementações complicadas são inadequadas.

Neste webinário gravado, os especialistas em produtos [!DNL Adobe Target] discutem como mover as decisões de otimização de experiência crítica no dispositivo para executar localmente com latência próxima a zero pode abrir portas para novos casos de uso interessantes e, ao mesmo tempo, melhorar o desempenho do site para seus clientes.

>[!VIDEO](https://video.tv.adobe.com/v/328148)

## Práticas recomendadas

O Adobe recomenda as seguintes práticas recomendadas ao usar decisões no dispositivo:

### Práticas recomendadas para o método de decisão &quot;no dispositivo&quot; {#best-practices-on-device}

Ao usar &quot;no dispositivo&quot; como método de decisão, o artefato é baixado quando o visitante carrega a página da Web pela primeira vez. Qualquer qualificação de atividade que precisa ocorrer no primeiro carregamento da página (sem cache) só acontece depois que o artefato é totalmente baixado. Há determinadas práticas recomendadas que você pode seguir para garantir que as qualificações de atividade aconteçam rapidamente para um novo visitante anônimo.

* Desative atividades com capacidade &quot;no dispositivo&quot; que não devem estar no artefato.
* Se você tiver [!DNL Target Premium], poderá usar [properties/workspaces](/help/administrating-target/c-user-management/property-channel/property-channel.md) para criar arquivos de artefatos diferentes para espaços de trabalho diferentes.
* Se os arquivos de artefato se tornarem muito grandes devido a motivos legítimos, você poderá usar o método de decisão &quot;híbrido&quot;. Esse método permite baixar o artefato em paralelo e todas as chamadas da API [!DNL Target] passam pela rede até que o artefato seja baixado. Leia a seção de [práticas recomendadas no modo de decisão &quot;Híbrido&quot;](#best-practices-hybrid) abaixo para saber mais sobre essa abordagem.
* Se você tiver um Aplicativo de página única (SPA), [!DNL Adobe] recomenda carregar e inicializar a at.js antes de carregar o arquivo JavaScript principal do seu aplicativo durante o carregamento da primeira página. Essa abordagem inicia o download de artefatos muito antes, fornecendo uma renderização de experiência mais rápida.

### Práticas recomendadas quando o método de decisão é &quot;híbrido&quot; {#best-practices-hybrid}

Ao usar &quot;híbrido&quot; como método de decisão, o artefato é baixado em paralelo. Até que o artefato seja baixado, qualquer chamada de API [!DNL Target] passa pelo fio mesmo se os &quot;locais&quot; forem capazes no dispositivo. Esse comportamento é o padrão para todas as chamadas `getOffers()` e fornece o melhor desempenho na maioria das situações. Se você alterar o comportamento padrão de `getOffers()` definindo `decisioningMethod` para `on-device`, siga estas práticas recomendadas para evitar erros e garantir o melhor desempenho.

* Se você decidir chamar `getOffers()` com `decisioningMethod` como `on-device` quando a página for carregada pela primeira vez, deverá fazer isso dentro do manipulador de eventos at.js &quot;ARTIFACT_DOWNLOAD_SUCCEEDED&quot; para evitar erros. Se o artefato for muito grande, qualquer &quot;local&quot; usando essa abordagem será renderizado somente após o download completo do artefato, o que pode atrasar a renderização da experiência. [!DNL Adobe] O recomenda que você raramente use essa abordagem. Siga as práticas recomendadas para reduzir o tamanho do artefato na seção [ Práticas recomendadas &quot;No dispositivo&quot;](#best-practices-on-device) acima ao usar essa abordagem.

## Tutorial: Decisão no dispositivo

[!DNL Adobe Target] a decisão no dispositivo permite a entrega de conteúdo de latência quase zero.

Este vídeo de 7 minutos:

* Descreve a decisão no dispositivo, incluindo como ela se compara a outros métodos de implementação [!DNL Target]
* Demonstra como ativar a decisão no dispositivo em [!DNL Target]
* Examina uma atividade de compositor baseada em formulário de amostra que foi configurada com conteúdo JSON
* Mostra exemplos de código do SDK Node.JS contendo a configuração de chave necessária para a tomada de decisão no dispositivo
* Demonstra resultados em um navegador

>[!VIDEO](https://video.tv.adobe.com/v/329032)

Para obter mais vídeos e tutoriais, consulte o guia [Adobe Target Tutorials](https://experienceleague.adobe.com/docs/target-learn/tutorials/overview.html?lang=pt-BR).

## Adobe Tech Blog - Parte 1: Execute [!DNL Adobe Target] o SDK do NodeJS para experimentação e personalização em plataformas de borda (Trabalhadores do Akamai Edge)

[Clique aqui para acessar a publicação](https://medium.com/adobetech/part-1-run-adobe-target-nodejs-sdk-for-experimentation-and-personalization-on-edge-platforms-4d8660964ed9) do blog.

## Adobe Tech Blog — Parte 2: Execute o SDK NodeJS do [!DNL Adobe Target] para experimentação e personalização em plataformas de borda (AWS Lambda@Edge)

[Clique aqui para acessar a publicação](https://medium.com/adobetech/part-2-run-adobe-target-nodejs-sdk-for-experimentation-and-personalization-on-edge-platforms-aws-4d6bdac24563) do blog.