---
description: A métrica de envolvimento de Pontuação de captura calcula a pontuação agregada com base no valor atribuído às páginas visitadas no site, a partir do momento em que o visitante exibe a primeira mbox da campanha.
keywords: pontuação de captura;pontuação
seo-description: A métrica de envolvimento de Pontuação de captura calcula a pontuação agregada com base no valor atribuído às páginas visitadas no site, a partir do momento em que o visitante exibe a primeira mbox da campanha.
seo-title: Pontuação de captura
solution: Target
subtopic: Introdução
title: Pontuação de captura
topic: Padrão
uuid: 977454ad-da32-449a-a8c9-1f3c75220be6
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Pontuação de captura{#capture-score}

A métrica de envolvimento de Pontuação de captura calcula a pontuação agregada com base no valor atribuído às páginas visitadas no site, a partir do momento em que o visitante exibe a primeira mbox da campanha.

O exemplo a seguir mostra como o envolvimento da pontuação é calculado em uma campanha que testa duas experiências, uma com uma imagem de um gato e outra com a imagem de um cão.

![](assets/example_score.png)

Nesse exemplo, o primeiro visitante acessa a experiência do gato. Considere que a mbox global envia uma pontuação de página com base no valor da página. Se o comerciante tiver capturado o envolvimento de contagem de páginas em uma métrica de sucesso associada a `**any mbox**`**qualquer mbox**, a pontuação de visitas será acumulada para toda solicitação de mbox visualizada após a mbox de exibição ao redor da imagem do gato.

A primeira página adiciona 1 à pontuação, a segunda página 0,25, a terceira 0,10, e a quarta 0,10 para um total de 1,45. Isto poderia ser interpretado como moeda ou pontos. Em uma visita separada, um visitante acessou a experiência do cão e, embora o visitante tenha visualizado um número menor de páginas, a pontuação é 2.10, maior do que a outra visita porque o visitante visualizou páginas com valor mais alto.

Você pode levar em consideração os custos de aquisição e receita de links associados ao enviar adboxes e redirecionadores, conforme demonstrado no fluxo da página a seguir. Observe que, nesse exemplo, ambas mboxes na página do artigo enviam uma pontuação, possivelmente representando um CPM conhecido.

![](assets/example_score2.png)

**Atribuindo uma pontuação de página**

Você pode atribuir um valor à qualquer página em seu site, com base no quão valiosa é a página para você. Por exemplo, um site sobre culinária pode vender anúncios por valores mais altos nas páginas de artigo em destaque do que na seção de experiências. Logo, os artigos em destaque são mais valiosos do que a seção de experiências. A pontuação da página permite desenvolver um valor &quot;geral&quot; de uma visita, de forma que a pessoa que ler mais artigos em destaque obtenha mais &quot;pontos&quot; do que alguém que simplesmente navegue pela seção de experiências.

Existem dois métodos para atribuir uma pontuação a uma página:

* No código da mbox, crie um parâmetro de mbox chamado `mboxPageValue`.

   Exemplo: `('global_mbox', 'mboxPageValue=10');`

   O valor especificado é adicionado à pontuação sempre que a página com a mbox é visualizada. Se diversas mboxes na página incluírem valores de pontuação, a pontuação da página é o total de todos os valores mbox. `mboxPageValue` é um parâmetro reservado usado para transmitir valores em uma mbox para capturar uma pontuação de envolvimento. Valores positivos e negativos podem ser enviados. A soma é calculada no fim de cada visita para calcular a pontuação total para a visita.

* Passe o parâmetro `?mboxPageValue=n` no URL da página.

   Exemplo: `https://www.mydomain.com?mboxPageValue=5`

   Utilizando esse método, o valor especificado é adicionado à pontuação de cada mbox na página. Por exemplo, se você passar o parâmetro `?mboxPageValue=10` e há três mboxes na página, a pontuação da página será 30.

>[!NOTE] {class=&quot;- topic/note &quot;}
>
>As mboxes localizadas acima da primeira mbox de exibição da campanha não serão incluídas na pontuação.

A prática recomendada é atribuir valores ao código mbox. Isto fornece valores medidos mais precisos, dependendo do conteúdo de cada mbox.

>[!NOTE] {class=&quot;- topic/note &quot;}
>
>Para obter uma manutenção mais simples, você pode configurar as atribuições de valor de pontuação do site no arquivo da [!DNL at.js] ou [!DNL mbox.js] com um pouco de lógica condicional JavaScript. Isso elimina a necessidade de adicionar mais código às suas páginas. Entre em contato com um consultor para obter ajuda.

Você pode combinar os dois métodos, mas isso pode resultar em uma pontuação maior do que a esperada. Por exemplo, se você atribuir um valor de 10 para cada três mboxes e nenhuma pontuação para uma quarta mbox e enviar o parâmetro de URL `?mboxPageValue=5`, sua pontuação de página será 50, 30 para as três mboxes com valores atribuídos e 5 para cada uma das quatro mboxes na página.

O contador é iniciado com a primeira mbox de exibição e não a mbox de entrada. Por exemplo, se você inserir uma campanha na página inicial que não possui uma mbox de exibição, crie um link para página de catálogo que contém a mbox de exibição. O contador é iniciado no momento em que você mover a página de catálogo.

Você também pode enviar valores negativos em páginas específicas que custam dinheiro ou não são boas para os visitantes visualizarem. Os valores negativos afetam a pontuação geral também. Essa técnica também pode ser utilizada em uma página que os visitantes acessam uma publicidade, para que você saiba qual foi o CPC. Isso também pode ser utilizado para uma página de suporte ou contato, onde você sabe que os visitantes podem ligar ou solicitar ajuda a partir dessa página.
