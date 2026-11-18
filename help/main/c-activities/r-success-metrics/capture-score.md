---
keywords: pontuação de captura;pontuação
description: Saiba mais sobre a métrica de envolvimento de Pontuação de captura no Adobe [!DNL Target] que calcula uma pontuação agregada com base no valor atribuído às páginas visitadas no site.
title: Qual é a métrica Pontuação de captura?
feature: Success Metrics
exl-id: 3446cdef-7ee0-40dd-bf17-27def56668d4
TQID: 'https://experienceleague.adobe.com/iqCPEY9x7Lg9TlAhxn8e-B1XOnUfNgUWFdOf8Bw2F3w'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
subfeature_v2:
  - id: eb2bfbe8-b0f3-4cc3-ae8d-af79179585eb
    internal-label: Success metrics
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 8c6f23b495228ab930e6649aa2f9e6dae506cae2
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 13%
---
# Pontuação de captura {#capture-score}

>[!BEGINSHADEBOX]

**Nesta página:** saiba como a métrica de envolvimento de Pontuação de Captura calcula a pontuação de uma visita e como atribuir uma pontuação a uma página.

>[!ENDSHADEBOX]

A métrica de envolvimento de Pontuação de captura no [!DNL Adobe Target] calcula a pontuação agregada com base no valor atribuído às páginas que um visitante visualiza no site. A pontuação começa no ponto em que o visitante vê a primeira solicitação [!DNL Target] de exibição da atividade.

O exemplo a seguir mostra como a pontuação é calculada em uma atividade que testa duas experiências, uma com uma imagem de gato e outra com uma imagem de cachorro.

![Fluxo de página da visita de experiência do gato, com uma pontuação para cada página](assets/example_score.png)

Neste exemplo, o primeiro visitante vê a experiência do gato. Suponha que uma solicitação global [!DNL Target] passe em uma pontuação de página com base no valor da página. Se o profissional de marketing tiver capturado o envolvimento de contagem de páginas em uma métrica de sucesso associada a **qualquer solicitação do Target**, a pontuação de visitas será acumulada para qualquer solicitação visualizada após a solicitação de exibição ao redor da imagem do gato.

A primeira página adiciona 1 à pontuação, a segunda página 0,25, a terceira 0,10 e a quarta 0,10, para um total de 1,45. Esse total pode ser interpretado como moeda ou pontos. Em uma visita separada, um visitante vê a experiência do cachorro. Embora esse visitante visualize menos páginas, a pontuação é de 2,10, que é maior do que a outra visita, porque o visitante visualizou páginas mais valiosas.

Você pode levar em consideração os custos de aquisição e receita de links associados ao enviar adboxes e redirecionadores, conforme demonstrado no fluxo da página a seguir. Neste exemplo, ambas as solicitações [!DNL Target] na página do artigo passam uma pontuação, possivelmente representando um CPM conhecido.

![Fluxo de páginas com custos de aquisição e receita de links afiliados passado como pontuações](assets/example_score2.png)

## Atribuir uma pontuação de página

Você pode atribuir um valor à qualquer página em seu site, com base no quão valiosa é a página para você. Por exemplo, um site de culinária pode ser capaz de vender anúncios por mais dinheiro em suas páginas de artigo de recurso do que em sua seção de experiência. Os artigos em destaque são então mais valiosos do que a seção experiência. Uma pontuação de página permite desenvolver um &quot;valor&quot; geral de uma visita, para que uma pessoa que lê mais artigos de recursos receba mais &quot;pontos&quot; do que alguém que só navega pelas experiências.

Existem dois métodos para atribuir uma pontuação a uma página:

* Na solicitação [!DNL Target], crie um parâmetro chamado `mboxPageValue`.

  Exemplo: `('global_mbox', 'mboxPageValue=10');`

  O valor especificado é adicionado à pontuação toda vez que a página com essa solicitação [!DNL Target] é exibida. Se várias solicitações na página incluírem valores de pontuação, a pontuação da página será o total de todos os valores de solicitação. `mboxPageValue` é um parâmetro reservado usado para transmitir valores em uma solicitação [!DNL Target] para capturar uma pontuação de envolvimento. Valores positivos e negativos podem ser enviados. A soma é calculada no final de cada visita para determinar a pontuação total da visita.

* Passe o parâmetro `?mboxPageValue=n` na URL da página.

  Exemplo: `https://www.mydomain.com?mboxPageValue=5`

  O valor especificado é adicionado à pontuação para cada solicitação [!DNL Target] na página. Por exemplo, se você passar o parâmetro `?mboxPageValue=10` e há três solicitações [!DNL Target] na página, a pontuação da página será 30.

>[!NOTE]
>
>O contador começa com a primeira solicitação de exibição da atividade, não com a solicitação de entrada, e [!DNL Target] solicitações localizadas acima dessa solicitação não são incluídas na pontuação. Por exemplo, se você inserir a atividade na página inicial, que não tem uma solicitação de exibição, e em seguida se vincular a uma página de catálogo que contém uma solicitação de exibição, o contador será iniciado quando você for para a página de catálogo.

A prática recomendada é atribuir valores na solicitação [!DNL Target]. Esse método permite que você seja preciso sobre os valores que mede, dependendo do conteúdo de cada solicitação.

>[!NOTE]
>
>Para obter uma manutenção mais simples, você pode configurar as atribuições de valor de pontuação da página de seu site no arquivo [!DNL at.js] com um pouco de lógica condicional JavaScript. Essa abordagem elimina a necessidade de adicionar mais código às suas páginas. Entre em contato com um consultor para obter ajuda.

Você pode combinar os dois métodos, mas isso pode resultar em uma pontuação maior do que a esperada. Por exemplo, você atribui um valor de 10 a cada três solicitações [!DNL Target] e nenhuma pontuação a uma quarta solicitação, em seguida, passa o parâmetro de URL `?mboxPageValue=5`. A pontuação da página é 50: 30 para as três solicitações com valores atribuídos, mais 20 para o parâmetro de URL (5 para cada uma das quatro solicitações na página).

Você também pode enviar valores negativos em páginas específicas que custam dinheiro ou não são boas para os visitantes visualizarem. Valores negativos também afetam a pontuação geral. Essa técnica pode ser usada em uma página que os visitantes acessam por meio de um anúncio, para que você saiba quanto foi o CPC. Ele também pode ser usado em uma página de suporte ou contato, onde os visitantes podem chamar ou solicitar assistência.
