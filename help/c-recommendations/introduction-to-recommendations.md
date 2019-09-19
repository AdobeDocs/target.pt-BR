---
description: Introdução às atividades do Target Recommendations que exibem automaticamente produtos ou conteúdo que possam interessar seus clientes com base em atividades anteriores do usuário ou outros algoritmos. O Recommendations ajuda a direcionar os clientes para itens relevantes que podem ser novidade para eles.
keywords: Recommendations;introdução;introdução;webinar;demo
seo-description: Introdução às atividades do Adobe Target Recommendations que exibem automaticamente produtos ou conteúdo que possam interessar seus clientes com base em atividades anteriores do usuário ou outros algoritmos. O Recommendations ajuda a direcionar os clientes para itens relevantes que podem ser novidade para eles.
seo-title: Introdução às atividades do Recommendations no Adobe Target
solution: Target
title: Introdução ao Recommendations
title-outputclass: premium
topic: Premium
badge: premium
translation-type: tm+mt
source-git-commit: 516433edd366fad5950c99d748aa7f6f718dd5fd

---


# ![PRÊMIO](/help/assets/premium.png) Introdução ao Recommendations

O texto neste artigo vem do webinar *Introdução ao Recommendations* , que você pode exibir na íntegra abaixo.

O webinar de *Introdução ao Recommendations* inclui uma análise detalhada de como utilizar o valor de [!DNL Adobe Target Recommendations]. Descubra como essa atividade do [!DNL Target] exibe automaticamente os produtos ou conteúdos que talvez interessem aos seus clientes, otimizando sugestões em tempo real com base nas visitas anteriores. Além disso, acesse a interface do usuário do [!DNL Target] para obter uma visão geral passo a passo sobre como criar uma atividade do [!DNL Recommendations].

## Introdução

Todos nós conhecemos o tipo de recomendações que vemos no varejo. Cada vez mais, os clientes esperam esse tipo de recomendações e as usam como ponto de partida para explorar outras opções disponíveis. Se você pensar no seu próprio comportamento de compra, esse tipo de recomendação funciona muito bem. Quase todos entre nós compraram um produto que vimos primeiro em uma recomendação em algum lugar, seja numa loja ou em uma propriedade digital.

A ilustração a seguir mostra uma recomendação que mostra os acessórios que geralmente são comprados com um novo telefone, incluindo estações de recarga, caixas e fones de ouvido.

![Recomendação mostrando acessórios que outras pessoas compraram com um novo telefone.](/help/c-recommendations/assets/intro-1.png)

Mas o que nem sempre pensamos é como as marcas digitais estão elevando o nível das expectativas dos clientes. Cada vez mais, a forma como consumimos mídia e conteúdo é impulsionada por recomendações personalizadas. Pense na primeira coisa que você vê quando abre o Netflix, o Spotify ou o YouTube. Essas marcas iniciam a experiência do cliente com recomendações. Em um mundo onde há mais alternativas disponíveis do que nunca, é importante identificar o conteúdo mais relevante para o cliente no ponto de interação.

![Recomendação mostrando as marcas digitais primárias](/help/c-recommendations/assets/intro-2.png)

Os profissionais de marketing usam [!DNL Adobe Target] para conduzir experiências personalizadas em uma grande variedade de setores, tipos de clientes e canais.

[!DNL Adobe Target] fornece conteúdo personalizado em qualquer lugar.

![Ilustração mostrando como o Target fornece recomendações em vários locais](/help/c-recommendations/assets/intro-3.png)

* **Publicação**: Os editores da Web usam [!DNL Target Recommendations] para recomendar artigos aos visitantes do site e aumentar o envolvimento.
* **Tutoriais** em vídeo: [!DNL Adobe Creative Cloud] usa [!DNL Target] para recomendar tutoriais em vídeo para usuários do Photoshop no aplicativo do Photoshop.
* **Jogos**: As empresas de jogos usam [!DNL Target] para recomendar jogos e conteúdo aos usuários em seus consoles.
* **Vendas** B2B: As empresas [de negócios usam o Target para recomendar vídeos, documentos e publicações de blog a clientes potenciais do B2B; fornecer downloads; e fornecer ajuda aos clientes](https://theblog.adobe.com/testing-shifts-high-gear-intel)existentes.

* **Viagem**: [Um organizador de viagens alemão usa o Target para recomendar hotéis e muito mais para viajantes](https://2017.summit.adobe.com/na/sessions/summit-online/online-2017/#17608).

* **Varejo**: [Um varejista líder B2B usa o Target para recomendar as principais categorias e produtos para retornar visitantes no navegador e em seu aplicativo](https://theblog.adobe.com/optimization-personalization-b2b-powerhouse-grainger/)móvel.

Essas são apenas algumas das maneiras que os clientes usam o Target para fornecer recomendações personalizadas.

O que significa grandes recomendações?

![Ilustração mostrando os três elementos que fazem excelentes recomendações](/help/c-recommendations/assets/intro-4.png)

Grandes recomendações devem ser relevantes e personalizadas. Isso significa que você precisa de três itens para impulsionar a relevância e a personalização:

* **Controles** do comerciante para ajudar a direcionar a relevância dos itens recomendados. Como comerciante, você traz um contexto valioso para a tabela e sabe quais atributos de seus produtos ou conteúdo são relevantes para um modelo de recomendações considerar. Se você estiver executando um site de vídeo, você sabe que os usuários podem estar interessados em ver filmes do mesmo diretor, mas provavelmente não se importam em ver filmes produzidos pelo mesmo estúdio. [!DNL Target] capacita você com controles que permitem aprimorar seus algoritmos com esse conhecimento de domínio.
* **Modelos** sofisticados para dar sentido a milhões de itens no catálogo e eventos de interação. [!DNL Target] tem capacidades sofisticadas de aprendizado de máquina, construídas ao longo de uma década de experiência e nós lidamos com bilhões de recomendações por ano.
* **Contexto** do usuário para garantir que as recomendações sejam oportunas e relevantes para seus usuários. Você não quer recomendar o vídeo que alguém acabou de assistir ou a camisa que alguém acabou de adicionar ao carrinho. O perfil de usuário avançado do Target pode ser usado em recomendações para garantir a personalização.

## Implementar Recomendações do Target

Comece com uma estratégia.

![Ilustração mostrando a estratégia de recomendações](/help/c-recommendations/assets/intro-5.png)

* **Que itens você deseja recomendar?** Primeiro, pense sobre quais itens você deseja recomendar. Podem ser produtos, vídeos ou conteúdo.
* **Onde deseja mostrar recomendações?** Em seguida, pense sobre onde deseja fazer recomendações. Em geral, quais canais (Web, móvel, na loja, um quiosque e assim por diante). Que partes da jornada do cliente contêm recomendações? Quais páginas do site contêm recomendações?
* **Como você determinará se as recomendações são bem-sucedidas?** Suponha que você tenha uma experiência sem recomendações e uma experiência com recomendações, ou que tenha dois tipos diferentes de recomendações. Como você determinaria qual experiência seria melhor para seus clientes? Algumas métricas podem ser mais difíceis de medir do que outras. Por exemplo, o impacto das recomendações sobre o Valor da Vida Útil do Cliente geralmente é difícil de obter diretamente. Portanto, geralmente é mais fácil chegar a uma métrica menos abstrata e mais concreta, por exemplo, receita por visita, valor médio de pedido ou número de cliques. Em alguns casos, talvez você esteja procurando minimizar uma métrica, por exemplo, o número de chamadas de suporte.

Depois que você apresentar sua estratégia, estará pronto para iniciar a implementação do [!DNL Target Recommendations].

Há três etapas gerais envolvidas na criação da implementação das recomendações:

![Ilustração mostrando as etapas para criar sua implementação de recomendações](/help/c-recommendations/assets/intro-6.png)

1. Ensine [!DNL Target] sobre seu contexto ou produtos.
1. Capture o comportamento do usuário.
1. Obtenha recomendações com o contexto correto.

### Ensine [!DNL Target] sobre seu contexto ou produtos

Ao começar com [!DNL Recommendations], você passa informações sobre cada item que deseja recomendar. [!DNL Target] oferece várias opções de integração para criar seu catálogo.

![Ilustração mostrando como ensinar o Target sobre seu contexto ou produtos](/help/c-recommendations/assets/intro-7.png)

O método mais simples e usado com mais frequência é o envio de um arquivo CSV diário ou semanal do sistema de gerenciamento de informações do produto ou do sistema de gerenciamento de conteúdo. Mas também é possível passar informações na camada de dados de sua página usando a biblioteca do [!DNL Adobe Target] Javascript, aproveitar nossas APIs para passar informações diretamente do sistema de origem ou usar nossa [!DNL Adobe Analytics] integração se já estiver transmitindo dados de catálogo para [!DNL Analytics].

Às vezes, é possível usar várias opções juntas, por exemplo, passar a maioria dos dados diariamente por um arquivo CSV e passar as atualizações de inventário com mais frequência por meio de uma API.

Seu departamento de TI geralmente estará envolvido na ajuda para configurar essa etapa.

Qualquer que seja o método escolhido, você deve incluir metadados sobre cada item em três categorias:

![Ilustração mostrando informações de metadados para seu catálogo](/help/c-recommendations/assets/intro-8.png)

* Dados que você deseja exibir ao usuário que recebe a recomendação. Por exemplo, o nome do filme e um URL de imagem em miniatura.
* Dados úteis para aplicar controles de marketing e comercialização. Por exemplo, a classificação do filme para que você não recomende filmes NC-17.
* Dados úteis para determinar a similaridade de itens com outros itens. Por exemplo, o gênero do filme ou os atores que estão no filme.

### Capturar comportamento do usuário

Em seguida, você deve adicionar tags ou aproveitar sua [!DNL Analytics] implementação existente para rastrear os eventos de conversão (como exibições e compras) que geram [!DNL Target] algoritmos.

![Ilustração mostrando como capturar o comportamento do usuário](/help/c-recommendations/assets/intro-9.png)

É necessário garantir que [!DNL Target] esteja ciente dos itens que seus usuários estão visualizando e comprando. Se a compra não for relevante para o seu contexto, você pode desejar rastrear um tipo diferente de evento de conversão, por exemplo, baixar um PDF, concluir uma pesquisa, assinar um boletim informativo, assistir a um vídeo e assim por diante.

Se você já estiver usando [!DNL Target] para executar atividades de Testes A/B em seu site, talvez você já tenha concluído esta etapa. Ou se você já estiver usando [!DNL Adobe Analytics] para relatar sobre visitas ao site e comportamento de conversão, você pode usar [!DNL Analytics] como sua fonte de dados comportamental. Caso contrário, é mais fácil configurar isso usando um gerenciador de tags, como o [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md). Também é possível enviar interações offline ou no aplicativo para a API [!DNL Target] em tempo real.

### Obter recomendações com o contexto correto

Passe informações sobre o usuário e o contexto no ponto de interação para [!DNL Target] retornar recomendações relevantes e personalizadas.

![Ilustração mostrando como obter recomendações com o contexto correto](/help/c-recommendations/assets/intro-10.png)

Além do comportamento do usuário no agregado, é necessário passar [!DNL Target] o contexto específico onde as recomendações estão sendo exibidas. Isso inclui informações sobre a página e informações do perfil do usuário. [!DNL Target] usa essas informações para fazer recomendações personalizadas. Por exemplo, em um site de varejo, você deseja saber o produto e a categoria do produto que o visitante está visualizando no momento. Você também quer saber informações sobre esse usuário (marca favorita, categoria de produto favorita, nível de fidelidade e assim por diante). Essas informações são importantes para que [!DNL Target] possam filtrar itens e melhorar a personalização das recomendações.

## Crie sua primeira atividade do Recommendations

O que é uma [!DNL Recommendations] atividade?

![Ilustração mostrando as partes que fazem uma boa atividade de recomendações](/help/c-recommendations/assets/intro-11.png)

Uma [!DNL Recommendations] atividade é composta pelos seguintes componentes:

* **Público-alvo**: Quem deveria ver essas recomendações?
* **Critérios**: Quais itens devem ser recomendados?
* **Design**: Como os itens recomendados devem ser exibidos?

![Ilustração mostrando o que constitui uma atividade de recomendações: Públicos-alvo, critérios e designs](/help/c-recommendations/assets/intro-12.png)

Desde o início, [!DNL Target] inclui 14 públicos incorporados, 42 critérios incorporados e 10 modelos de design integrados. Você pode personalizar cada um desses itens ou adicionar seus próprios. Tivemos [webinars anteriores sobre como criar públicos](https://landing.adobe.com/acs/2018/na/adobe-target/registration.html) em [!DNL Target]. Esta seção foca na definição dos critérios, que definem quais itens serão recomendados.

O Target usa o conceito do cartão de critérios. Um cartão de critérios é como uma receita para personalização.

![Ilustração do cartão de critérios](/help/c-recommendations/assets/intro-13.png)

É importante escolher ou criar os critérios certos para obter os resultados de personalização que você deseja. Um critério é como um funil que o leva de todo o catálogo para o conjunto final de recomendações.

![Ilustração do funil](/help/c-recommendations/assets/intro-14.png)

As seções a seguir descrevem as várias partes desse funil e como elas funcionam em [!DNL Target]:

### Filtros estáticos (coleções e exclusões)

Os filtros estáticos são regras amplamente aplicáveis relacionadas aos atributos do catálogo que você não espera alterar com frequência.

![Ilustração de coleções e exclusões](/help/c-recommendations/assets/intro-16.png)

Por exemplo, em um contexto de conteúdo, você pode querer incluir todos os filmes em recomendações, mas excluir filmes com classificação NC-17. Em um contexto de varejo, você pode ter várias marcas em diferentes partes do mundo, mas deseja recomendar somente os produtos disponíveis nos Estados Unidos. Você também pode querer excluir produtos de um rótulo privado regional.

Todos esses atributos de catálogo são amplamente aplicáveis e podem ser usados em várias recomendações e não é de se esperar que sejam alterados com frequência.

### Algoritmo (chave de recomendação e lógica)

A próxima etapa é escolher uma chave de recomendação e uma lógica. É aqui que você decide qual é a base para sua recomendação.

![Ilustração do algoritmo](/help/c-recommendations/assets/intro-17.png)

A primeira coisa que você precisa escolher é a chave da recomendação. A chave de recomendação é o que você está "procurando" para escolher a recomendação. É nisso que se baseia a sua recomendação.

Você pode basear sua recomendação em:

* O item que o visitante está visualizando no momento
* A categoria que o visitante está visualizando no momento
* O item que o visitante comprou pela última vez ou adicionou ao carrinho de compras
* Um atributo personalizado relacionado a um visitante ou a um item

Com base nessas chaves, você escolhe a lógica de recomendação desejada:

* Itens com atributos similares
* Os itens mais visualizados em uma categoria específica
* Os clientes que compraram este item também compraram estes itens
* Um atributo personalizado

A partir de agora, [!DNL Target] inclui um portfólio de algoritmos.

![Exemplo de portfólio de algoritmos](/help/c-recommendations/assets/intro-15.png)

* **Os algoritmos** baseados em popularidade incluem os Mais Visualizados e os Mais Vendidos.
* **Os algoritmos** baseados em conteúdo incluem Semelhança de conteúdo.
* **Os algoritmos** de filtragem colaborativa baseados em itens incluem Visualizado/Visualizado, Visualizado/Comprado e Comprado/Comprado. Observe que "comprado" pode ser qualquer conversão.
* **Os algoritmos** personalizados incluem: Visualizados recentemente, Afinidade do site e filtragem colaborativa aprimorada por perfil.
* **Os algoritmos** Trazer para você permitem usar seus próprios algoritmos personalizados.

### Regras de negócios online

O último passo é aplicar regras de negócios online. É aqui que você capacita seus algoritmos com conhecimento de domínio e contexto atual com base no que o visitante está fazendo em sua propriedade digital.

![Ilustração de regras de negócios online](/help/c-recommendations/assets/intro-18.png)

Por exemplo, no contexto de conteúdo, você pode querer excluir filmes que o visitante tenha assistido anteriormente, recomendar filmes pelo mesmo diretor ou aumentar filmes no mesmo gênero. No contexto de varejo, você pode querer excluir produtos indisponíveis, mostrar itens em uma faixa de preço de US$ 5 a US$ 500 ou aumentar itens da mesma marca.

## Demonstração

Depois de concluir as tarefas ilustradas no funil de recomendação descrito acima, você terá sua recomendação final. Para assistir a uma demonstração dentro do produto, [!DNL Target]a demonstração começa às 21h00 no Webinar *de noções básicas do* Adobe Target, vinculado ao link abaixo.

## Webinar de noções básicas do Adobe Target: Introdução ao Recommendations {#intro-to-recs}

[Introdução ao Recommendations](https://forums.adobe.com/external-link.jspa?url=https%3A%2F%2Fadobecustomersuccess.adobeconnect.com%2Fp8gt31drhs3e%2F%3FOWASP_CSRFTOKEN%3D4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)