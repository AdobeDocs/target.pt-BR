---
keywords: Recomendações; intro; introdução, webinar, demonstração
description: Saiba mais sobre as atividades do Recommendations no Adobe [!DNL Target] que exibem automaticamente conteúdo que pode ser do interesse dos clientes com base em atividades anteriores do usuário ou em outros algoritmos.
title: O que são as atividades do Recomendações?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: bc4d9a46-ea21-4687-b8a0-7f2e1dc33ebf
TQID: 'https://experienceleague.adobe.com/6jmXI9CsdCnyyQrQXKzq5WF8OQPQSCbE2Zb8AnpUvks'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
source-git-commit: 4f38c80880eedd9b966cdb2f178f408bb529b60c
workflow-type: tm+mt
source-wordcount: '1633'
ht-degree: 9%
---
# Introdução ao Recomendações {#introduction-to-recommendations}

>[!BEGINSHADEBOX]

**Nesta página:** saiba como as atividades do [!DNL Recommendations] no [!DNL Adobe Target] exibem produtos ou conteúdo relevantes para os visitantes e como planejar e criar uma implementação e atividade do [!DNL Recommendations].

>[!ENDSHADEBOX]

Esta página é baseada no webinário *Introdução ao Recommendations*. Uma atividade do [!DNL Recommendations] exibe automaticamente produtos ou conteúdo que podem ser do interesse dos clientes, otimizando sugestões em tempo real com base nas visitas anteriores. A página também descreve como criar uma atividade [!DNL Recommendations] na interface do usuário [!DNL Target].

## Introdução

Os clientes esperam cada vez mais recomendações e as usam como ponto de partida para explorar outras opções disponíveis. Quase todos compraram um produto que viram pela primeira vez em uma recomendação, seja em uma loja ou em uma propriedade digital.

![A recomendação mostra os acessórios que normalmente são comprados com um novo telefone, incluindo carregadores, maletas e fones de ouvido.](/help/main/c-recommendations/assets/intro-1.png)

O modo como as pessoas consomem mídia e conteúdo é cada vez mais orientado por recomendações personalizadas, e marcas digitais como Netflix, Spotify e YouTube iniciam a experiência do cliente com recomendações. À medida que mais alternativas estão disponíveis do que nunca, é essencial identificar o conteúdo mais relevante para um cliente no ponto de interação.

Os profissionais de marketing usam o [!DNL Adobe Target] para impulsionar experiências personalizadas em diversos setores, tipos de clientes e canais. A tabela a seguir lista alguns exemplos de como os clientes usam o [!DNL Target] para fornecer recomendações personalizadas.

| Caso de uso | Exemplo |
|---|---|
| Publicação | Os editores da Web usam o [!DNL Target Recommendations] para recomendar artigos aos visitantes do site e impulsionar maior engajamento. |
| Tutoriais em vídeo | O [!DNL Adobe Creative Cloud] usa o [!DNL Target] para recomendar tutoriais em vídeo aos usuários do Photoshop no aplicativo Photoshop. |
| Jogos | As empresas de jogos usam o [!DNL Target] para recomendar jogos e conteúdo aos usuários em seus consoles. |
| Vendas B2B | As empresas B2B usam o [!DNL Target] para recomendar vídeos, whitepapers e publicações do blog para prospetos B2B, entregar downloads e fornecer ajuda aos clientes. |
| Viagens | Uma agência de viagens alemã usa [!DNL Target] para recomendar hotéis e muito mais aos viajantes. Para obter detalhes, consulte a [sessão do Adobe Summit](https://2017.summit.adobe.com/na/sessions/summit-online/online-2017/#17608){target=_blank}. |
| Varejo | Um retailer B2B líder usa o [!DNL Target] para recomendar as principais categorias e produtos para retornar visitantes no navegador e em seu aplicativo móvel. |

## Elementos de excelentes recomendações

Excelentes recomendações são relevantes e personalizadas. Três elementos impulsionam relevância e personalização:

* **Controles do profissional de marketing** para orientar a relevância dos itens recomendados. Os profissionais de marketing sabem quais atributos de seus produtos ou conteúdo um modelo de recomendações deve considerar. Por exemplo, em um site de vídeo, os usuários podem estar interessados em filmes do mesmo diretor, mas provavelmente não em filmes do mesmo estúdio. [!DNL Target] fornece controles para aprimorar algoritmos com esse conhecimento de domínio.
* **Modelos sofisticados** para dar sentido a milhões de itens de catálogo e eventos de interação. O [!DNL Target] possui recursos de aprendizado de máquina criados em uma década de experiência e lida com bilhões de recomendações por ano.
* **Contexto do usuário** para garantir que as recomendações sejam oportunas e relevantes. Por exemplo, as recomendações não devem incluir o vídeo que alguém acabou de assistir ou a camisa que alguém acabou de adicionar ao carrinho. O perfil de usuário [!DNL Target] pode ser usado em recomendações para garantir a personalização.

## Implementar o [!DNL Target] Recomendações

Comece com uma estratégia que define os seguintes pontos:

* **Itens a recomendar**: produtos, vídeos ou conteúdo.
* **Locais para recomendações**: os canais (Web, celular, na loja, quiosque e assim por diante), as partes da jornada do cliente e as páginas do site que contêm recomendações.
* **Medição de sucesso**: como determinar se as recomendações obtiveram êxito, por exemplo, comparando uma experiência sem recomendações a uma experiência com recomendações ou comparando dois tipos diferentes de recomendações. Algumas métricas, como o impacto no Valor vitalício do cliente, são difíceis de medir diretamente, de modo que uma métrica mais concreta é geralmente mais fácil de usar, como a receita por visita, o valor médio de pedido ou o número de cliques. Em alguns casos, o objetivo é minimizar uma métrica, por exemplo, o número de chamadas de suporte.

Depois que a estratégia é definida, a implementação do [!DNL Target Recommendations] envolve três etapas amplas:

![Ilustração que mostra as três etapas de uma implementação de recomendações: ensine o Target sobre seu conteúdo ou seus produtos, capture o comportamento do usuário e obtenha recomendações com o contexto adequado.](assets/intro-6.png)

### Ensine [!DNL Target] sobre seu conteúdo ou seus produtos

Ao iniciar com [!DNL Recommendations], você transmite informações sobre cada item que deseja recomendar.

![Ilustração que mostra como ensinar o Target sobre seu conteúdo ou seus produtos: feeds no formato CSV ou Feed Google, a camada de dados com o Target, a API e a integração do Analytics.](assets/intro-7.png)

O método mais simples e usado com mais frequência é enviar um arquivo CSV diária ou semanalmente de um sistema de gerenciamento de informações do produto ou de um sistema de gerenciamento de conteúdo. Outras opções são transmitir informações sobre a camada de dados da página usando a biblioteca JavaScript do [!DNL Adobe Target], usar as APIs para transmitir informações diretamente do sistema de origem ou usar a integração do [!DNL Adobe Analytics] se você já estiver transmitindo dados de catálogo para o [!DNL Analytics]. É possível usar várias opções juntas, por exemplo, transmitir a maioria dos dados diariamente por meio de um arquivo CSV e transmitir as atualizações de inventário com mais frequência por meio de uma API. O departamento de TI geralmente está envolvido na configuração dessa etapa.

Qualquer que seja o método escolhido, inclua metadados sobre cada item em três categorias:

* **Dados que você deseja exibir para o usuário que recebe a recomendação.** Por exemplo, o nome do filme e um URL da imagem em miniatura.
* **Dados úteis para aplicar controles de marketing e merchandising.** Por exemplo, a classificação do filme para que você não recomende filmes NC-17.
* **Dados úteis para determinar a similaridade dos itens com outros itens.** Por exemplo, o gênero do filme ou os atores que estão no filme.

### Capture o comportamento do usuário

![Ilustração que mostra como capturar o comportamento do usuário: exibições e cliques levam a compras, conversões, downloads, assinaturas e reproduções, acompanhados pelo Target, Analytics ou pela API.](assets/intro-9.png)

Adicione marcas ou use sua implementação existente do [!DNL Analytics] para que o [!DNL Target] esteja ciente dos itens que seus usuários visualizam e compram. Se a compra não for relevante para o seu contexto, rastreie um tipo diferente de evento de conversão, por exemplo, baixar uma PDF, concluir uma pesquisa, assinar um boletim informativo ou assistir a um vídeo.

Se você já usa o [!DNL Target] para executar atividades de Teste A/B no site, talvez já tenha concluído essa etapa. Se você já usa o [!DNL Adobe Analytics] para o relatório sobre visitas do site e comportamento de conversão, você pode usar o [!DNL Analytics] como sua fonte de dados comportamentais. Caso contrário, a opção mais simples é configurar isso com um gerenciador de tags, como em [[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-using-adobe-launch.html?lang=pt-BR){target=_blank}. Interações offline ou no aplicativo também podem ser enviadas para [!DNL Target] por meio da API em tempo real.

### Obter recomendações com o contexto adequado

![Ilustração que mostra como obter recomendações com o contexto adequado: o produto atual visualizado, a categoria do produto atual, a categoria favorita do usuário, a marca favorita do usuário e a camada de fidelidade do usuário são passadas para o Target.](assets/intro-10.png)

Além do comportamento do usuário na agregação, o [!DNL Target] precisa do contexto específico em que as recomendações são exibidas, que inclui informações sobre a página e informações do perfil do usuário. [!DNL Target] usa essas informações para filtrar itens e melhorar a personalização das recomendações.

## Criar sua primeira atividade do Recomendações

Uma atividade [!DNL Recommendations] combina um público-alvo, critérios e um design. [!DNL Target] inclui 14 públicos-alvo internos, 42 critérios internos e 10 modelos de design integrados. Você pode personalizar cada um desses itens ou adicionar os seus próprios.

![Ilustração que mostra as partes que fazem uma boa atividade de recomendações: o público-alvo (quem deve ver essas recomendações), os critérios (quais itens devem ser recomendados) e o design (como os itens recomendados são exibidos).](assets/intro-11.png)

[!DNL Target] usa o conceito do cartão de critérios, que é como uma fórmula para personalização. Escolher ou criar os critérios corretos é importante para alcançar os resultados de personalização desejados. Um cartão de critérios funciona como uma funnel que leva você do catálogo inteiro até o conjunto final de recomendações.

![Ilustração dos critérios funnel: conteúdo de catálogo, filtros estáticos (coleções e exclusões), algoritmo (lógica e chave de recomendação), regras de negócios online (filtragem dinâmica e ponderação de atributos) e recomendações finais, ao lado de um exemplo de cartão de critérios.](assets/intro-14.png)

As seções a seguir descrevem as partes desta funnel e como elas funcionam no [!DNL Target].

### Filtros estáticos (coleções e exclusões)

Os filtros estáticos são regras gerais aplicáveis aos atributos do catálogo que você não espera alterar com frequência, portanto, você pode usá-los em várias recomendações.

![Ilustração de filtros estáticos. Conteúdo: incluir todos os filmes e excluir os filmes classificados como NC-17 das recomendações. Produtos: inclua todos os produtos disponíveis nos Estados Unidos e exclua produtos de um rótulo privado regional.](assets/intro-16.png)

### Algoritmo (chave e lógica de recomendação)

A próxima etapa é escolher a chave e a lógica de recomendação, que são a base para sua recomendação. A chave de recomendação é o que você está “procurando” para escolher a recomendação.

![Ilustração da etapa de algoritmo. Chave de recomendação: item exibido no momento, categoria exibida no momento, último item comprado ou atributo personalizado. Lógica de recomendação: itens com atributos semelhantes, itens mais visualizados na categoria, clientes que compraram esse item também compraram esses itens ou algoritmo personalizado.](assets/intro-17.png)

[!DNL Target] inclui um portfólio de algoritmos.

![Ilustração do portfólio de algoritmos: baseado em popularidade (Mais visualizados, Mais vendidos), baseado em conteúdo (Semelhança de conteúdo), filtragem colaborativa baseada em itens (Visualizado/Visualizado, Visualizado/Comprado, Comprado/Comprado, onde comprado pode ser qualquer conversão), personalizado (Visualizado recentemente, Afinidade do site, Colaboração aprimorada por perfil. Filtragem) e traga seus próprios (algoritmos personalizados).](assets/intro-15.png)

### Regras de negócios online

A última etapa é aplicar as regras de negócios online, que aprimoram seus algoritmos com conhecimento de domínio e contexto atual, com base no que o visitante está fazendo em sua propriedade digital.

![Ilustração de regras de negócios online. Conteúdo: excluir filmes assistidos anteriormente, mostrar filmes do mesmo diretor e impulsionar filmes com o mesmo gênero. Produtos: exclua produtos esgotados, mostre itens com preço de US$ 5 a US$ 500 e impulsione itens da mesma marca.](/help/main/c-recommendations/assets/intro-18.png)
