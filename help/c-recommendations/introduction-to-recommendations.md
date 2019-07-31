---
description: Introdução às atividades do Target Recommendations que exibem automaticamente produtos ou conteúdos que podem interessar seus clientes com base na atividade anterior do usuário ou em outros algoritmos. O Recommendations ajuda a direcionar os clientes para itens relevantes que podem ser novidade para eles.
keywords: Recommendations;
seo-description: Introdução às atividades do Adobe Target Recommendations que exibem automaticamente produtos ou conteúdo que podem interessar seus clientes com base na atividade anterior do usuário ou em outros algoritmos. O Recommendations ajuda a direcionar os clientes para itens relevantes que podem ser novidade para eles.
seo-title: Introdução às atividades do Recommendations no Adobe Target
solution: Target
title: Introdução ao Recommendations
title-outputclass: premium
topic: Premium
badge: premium
translation-type: tm+mt
source-git-commit: 04a4585e1d56f1754b65a248715fa5bdd4f8986f

---


# ![Introdução PREMIUM](/help/assets/premium.png) ao Recommendations

The text in this article comes from the *Introduction to Recommendations* webinar, which you can view in its entirety below.

The *Introduction to Recommendations* webinar includes an in-depth exploration of how to leverage the value of [!DNL Adobe Target Recommendations]. Descubra como essa atividade do [!DNL Target] exibe automaticamente os produtos ou conteúdos que talvez interessem aos seus clientes, otimizando sugestões em tempo real com base nas visitas anteriores. Além disso, acesse a interface do usuário do [!DNL Target] para obter uma visão geral passo a passo sobre como criar uma atividade do [!DNL Recommendations].

## Introdução

Todos sabemos sobre os tipos de recomendações que vemos em varejo. Cada vez mais os clientes esperam esse tipo de recomendação e usam-os como um ponto de partida para explorar outras opções disponíveis. Se você pensar em seu próprio comportamento de compra, esses tipos de recomendações funcionam bem. Quase todos os participantes compraram um produto que vimos primeiro em uma recomendação, seja ele em uma loja ou em uma propriedade digital.

A ilustração a seguir mostra uma recomendação que exibe acessórios que são comumente comprados com um novo telefone, incluindo estações de pagamento, casos e fones de ouvido.

![A recomendação mostra os acessórios que outras pessoas compraram com um novo telefone.](/help/c-recommendations/assets/intro-1.png)

No entanto, nem sempre acreditamos como as marcas digitais estão aumentando a barra das expectativas do cliente. Cada vez mais, o modo como consumimos mídia e conteúdo é orientado por recomendações personalizadas. Pense na primeira coisa que você vê ao abrir Netflix, Spotify ou youtube. Essas marcas iniciam a experiência do cliente com recomendações. Em um mundo em que há mais alternativas disponíveis do que nunca, é importante identificar o conteúdo mais relevante para o cliente no ponto de interação.

![Recomendação mostrando marcas digitais](/help/c-recommendations/assets/intro-2.png)

Marketers use [!DNL Adobe Target] to drive personalized experiences across a wide variety of industries, customer types, and channels.

[!DNL Adobe Target] proporciona conteúdo personalizado em todos os locais.

![Ilustração que mostra como o Target fornece recomendações em vários lugares](/help/c-recommendations/assets/intro-3.png)

* **Publicação**: Os editores da Web usam [!DNL Target Recommendations] para recomendar artigos aos visitantes do site e promover maior envolvimento.
* **Tutoriais em vídeo**: [!DNL Adobe Creative Cloud] usa [!DNL Target] para recomendar tutoriais em vídeo aos usuários do Photoshop no aplicativo Photoshop.
* **Gaming**: As empresas de jogos usam [!DNL Target] para recomendar jogos e conteúdo aos usuários em seus consoles.
* **Vendas B 2 B**: As empresas corporativas usam [!DNL Target] para recomendar vídeos, documentos e postagens de blog para as perspectivas B 2 B; entregar downloads; e forneça ajuda para clientes existentes (https://theblog.adobe.com/testing-shifts-high-gear-intel).
* **Viagem**: Um banco de viagens alemão usa [!DNL Target] para recomendar hotéis e mais para viajantes (https://2017.summit.adobe.com/na/sessions/summit-online/online-2017/#17608).
* **Varejo**: Um revendedor B 2 B líder usa [!DNL Target] para recomendar categorias e produtos principais para retornar visitantes no navegador e em seu aplicativo móvel (https://theblog.adobe.com/optimization-personalization-b2b-powerhouse-grainger/).

Estas são apenas algumas das formas como os clientes usam o Target para fornecer recomendações personalizadas.

O que faz para excelentes recomendações?

![Ilustração mostrando os três elementos que fazem excelentes recomendações](/help/c-recommendations/assets/intro-4.png)

As excelentes recomendações devem ser relevantes e personalizadas. Isso significa que você precisa de três coisas para promover relevância e personalização:

* **Controles de comerciante** para ajudar a promover a relevância dos itens recomendados. Como comerciante, você traz contexto valioso para a tabela e sabe quais atributos de seus produtos ou conteúdo são relevantes para um modelo de recomendações considerar. Se você estiver executando um site de vídeo, sabe que os usuários podem estar interessados em ver filmes do mesmo diretor, mas provavelmente não se importa de ver filmes produzidos pelo mesmo estúdio. [!DNL Target] capacita você com controles que permitem aprimorar seus algoritmos com este conhecimento de domínio.
* **Modelos sofisticados** para fazer sentido de milhões de itens nos eventos de catálogo e interação. [!DNL Target] possuem recursos sofisticados de aprendizado automatizado criados em uma década de experiência e lidamos com bilhões de recomendações por ano.
* **Contexto do usuário** para garantir que as recomendações sejam oportunas e relevantes para os usuários. Não recomenda o vídeo que alguém acabou de assistir ou a camisa que alguém acabou de adicionar ao carrinho. O perfil de usuário avançado do Target pode ser usado em recomendações para garantir a personalização.

## Implementar Recomendações do Target

Comece com uma estratégia.

![Ilustração que mostra a estratégia de recomendações](/help/c-recommendations/assets/intro-5.png)

* **Que itens deseja recomendar?** Primeiro, pense em quais itens deseja recomendar. Isso pode ser produtos, vídeos ou conteúdo.
* **Onde deseja mostrar recomendações?** Em seguida, pense em onde deseja fazer recomendações. Em geral, quais canais (Web, dispositivos móveis, armazenamento em lojas, quiosques e assim por diante). Quais partes da jornada do cliente conterão recomendações? Quais páginas do site contêm recomendações?
* **Como você determinará se as recomendações estão com êxito?** Suponha que você tenha uma experiência sem recomendações e uma experiência com recomendações, ou tem dois tipos diferentes de recomendações. Como você poderia determinar qual experiência foi uma experiência melhor para seus clientes? Algumas métricas podem ser mais difíceis do que outras medidas. Por exemplo, o impacto das recomendações no Valor do tempo de vida do cliente geralmente é difícil de acessar diretamente. Por isso, geralmente é mais fácil obter uma métrica menos abstrata e algo mais concreto, por exemplo, receita por visita, valor médio de pedido ou número de cliques. Em alguns casos, talvez você queira minimizar uma métrica, por exemplo, o número de chamadas de suporte.

After you come up with your strategy, you are ready to start the implementation of [!DNL Target Recommendations].

Há três etapas abrangentes envolvidas na criação da implementação do Recommendations:

![Ilustração que mostra as etapas para criar sua implementação de recomendações](/help/c-recommendations/assets/intro-6.png)

1. Teach [!DNL Target] about your context or products.
1. Captura comportamento do usuário.
1. Obtenha recomendações com o contexto adequado.

### Teach [!DNL Target] about your context or products

When you start with [!DNL Recommendations], you pass information about every item you want to recommend. [!DNL Target] oferecem várias opções de integração para criar seu catálogo.

![Ilustração mostrando como ensinar o Target sobre seu contexto ou produtos](/help/c-recommendations/assets/intro-7.png)

O método mais simples e usado com mais frequência é enviar um arquivo CSV diariamente ou semanalmente do sistema de gerenciamento de informações do produto ou do sistema de gerenciamento de conteúdo. But you can also pass information on the data layer from your page using the [!DNL Adobe Target] Javascript library, leverage our APIs to pass information directly from your source system, or use our [!DNL Adobe Analytics] integration if you are already passing catalog data to [!DNL Analytics].

Às vezes, talvez você queira usar várias opções juntas, por exemplo, transmitir a maioria dos dados diariamente por um arquivo CSV e enviar atualizações de inventário com mais frequência por meio de uma API.

O departamento de TI geralmente será envolvido na ajuda para definir esta etapa.

Qualquer método escolhido, você deve incluir metadados sobre cada item em três categorias:

![Ilustração mostrando informações de metadados para o catálogo](/help/c-recommendations/assets/intro-8.png)

* Os dados que você deseja exibir para o usuário recebendo a recomendação. Por exemplo, o nome do filme e um URL da imagem em miniatura.
* Dados úteis para aplicar controles de marketing e merchandising. Por exemplo, a classificação do filme para que você não recomende os filmes NC -17.
* Dados úteis para determinar a similaridade dos itens a outros itens. Por exemplo, o gênero do filme ou os atores que estão no filme.

### Captura do comportamento do usuário

Next, you should add tags or leverage you existing [!DNL Analytics] implementation to track the conversion events (such as views and purchases) that drive [!DNL Target] algorithms.

![Ilustração mostrando como capturar o comportamento do usuário](/help/c-recommendations/assets/intro-9.png)

You need to ensure that [!DNL Target] is aware of the items that your users are viewing and purchasing. Se a compra não for relevante para o contexto, talvez você queira rastrear um tipo diferente de evento de conversão, por exemplo, baixar um PDF, concluir uma pesquisa, inscrever-se em um boletim informativo, assistir a um vídeo e assim por diante.

If you are already using [!DNL Target] to run A/B Tests activities on your site, you might have already completed this step. Or if you are already using [!DNL Adobe Analytics] to report on site visits and conversion behavior, you can use [!DNL Analytics] as your behavioral datasource. If not, it’s easiest to set this up using a tag manager such as [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md). It’s also possible to send offline or in-app interactions to [!DNL Target] via real-time API.

### Obter recomendações com o contexto adequado

Pass information about the user and context at the point of interaction to [!DNL Target] to return relevant and personalized recommendations.

![Ilustração mostrando como obter recomendações com o contexto adequado](/help/c-recommendations/assets/intro-10.png)

Besides user behavior in aggregate, you need to pass [!DNL Target] the specific context where recommendations are being shown. Isso inclui informações sobre a página e as informações do perfil do usuário. [!DNL Target] usa essas informações para fazer recomendações personalizadas. Por exemplo, em um site de varejo, você quer saber a categoria produto e produto que o visitante está visualizando atualmente. Você também pode saber informações sobre esse usuário (marca favorita, categoria de produto favorita, nível de fidelidade e assim por diante). This information is important so that [!DNL Target] can filter items and improve the personalization of recommendations.

## Crie sua primeira atividade do Recommendations

What is a [!DNL Recommendations] activity?

![Ilustração que mostra as partes que fazem uma boa atividade de recomendações](/help/c-recommendations/assets/intro-11.png)

A [!DNL Recommendations] activity is made up of the following components:

* **Público-alvo**: Quem deve ver essas recomendações?
* **Critérios**: Quais itens devem ser recomendados?
* **Design**: Como os itens recomendados devem ser exibidos?

![Ilustração que mostra o que cria uma atividade de recomendações: Públicos, critérios e designs](/help/c-recommendations/assets/intro-12.png)

Out of the box, [!DNL Target] includes 14 built-in audiences, 42 built-in criteria, and 10 built-in design templates. Você pode personalizar cada um desses itens ou adicionar os seus próprios. We’ve had previous [webinars about building audiences](https://landing.adobe.com/acs/2018/na/adobe-target/registration.html) in [!DNL Target]. Esta seção se concentra na definição dos critérios, que definem os itens de assinatura.

O Target usa o conceito do cartão de critérios. Um cartão de critérios é como uma fórmula para personalização.

![Ilustração do cartão de critérios](/help/c-recommendations/assets/intro-13.png)

É importante escolher ou criar os critérios corretos para atingir os resultados de personalização desejados. Um critério é como um funil que leva você de todo o seu catálogo para o conjunto final de recomendações.

![Ilustração de funil](/help/c-recommendations/assets/intro-14.png)

The following sections describe the various parts of this funnel and how they work in [!DNL Target]:

### Filtros estáticos (coleções e exclusões)

Os filtros estáticos são regras gerais aplicáveis a atributos de catálogo que você não espera alterar com frequência.

![Ilustrações e exclusões de coleções](/help/c-recommendations/assets/intro-16.png)

Por exemplo, em um contexto de conteúdo, você pode querer incluir todos os filmes nas recomendações, mas excluir filmes classificados como NC -17. Em um contexto de varejo, você pode ter várias marcas em diferentes partes do mundo, mas deseja recomendar apenas produtos disponíveis nos Estados Unidos. Você também pode querer excluir produtos de um rótulo privado regional.

Todos esses são atributos de catálogo amplamente aplicáveis que podem ser usados em várias recomendações e você não espera que eles sejam alterados com frequência.

### Algoritmo (chave de recomendação e lógica)

A próxima etapa é escolher uma chave de recomendação e uma lógica. É aqui que você decide qual é a base para sua recomendação.

![Ilustração de algoritmo](/help/c-recommendations/assets/intro-17.png)

A primeira coisa que você precisa escolher é a chave de recomendação. A chave de recomendação é o que você está "procurando" para escolher a recomendação. É o que você está baseando com base em sua recomendação.

Você pode basear sua recomendação em:

* O item que o visitante está vendo atualmente
* A categoria que o visitante está visualizando atualmente
* O item por último comprado ou adicionado ao carrinho de compras
* Um atributo personalizado relacionado a um visitante ou item

Com base nessas chaves, escolha a lógica de recomendação:

* Itens com atributos similares
* Os itens mais visualizados em uma categoria específica
* Os clientes que compraram este item também compraram esses itens
* Um atributo personalizado

Out of the box, [!DNL Target] includes a portfolio of algorithms.

![Portfólio de ilustração de algoritmos](/help/c-recommendations/assets/intro-15.png)

* **Os algoritmos baseados em popularidade** incluem Mais visualizados e Principais vendedores.
* **Algoritmos baseados em conteúdo** incluem Semelhança de conteúdo.
* **Algoritmos de filtragem colaborativos baseados em itens** incluem Visualizados/Visualizados, Exibidos/Comprados e Compraram/Compraram. Observe que "compraram" pode ser qualquer conversão.
* **Algoritmos personalizados** incluem recentemente visualização, Afinidade de site e filtragem colaborativa aprimorada para perfis.
* **Os algoritmos próprios** permitem usar seus próprios algoritmos personalizados.

### Regras de negócios online

A última etapa está aplicando regras de negócios online. É aqui que você capacita seus algoritmos com conhecimento de domínio e contexto atual com base no que o visitante está fazendo em sua propriedade digital.

![Ilustração de regras online](/help/c-recommendations/assets/intro-18.png)

Por exemplo, no contexto do conteúdo, você pode excluir filmes que o visitante assistiu anteriormente, recomendar filmes pelo mesmo diretor ou aumentar filmes no mesmo gênero. No contexto de varejo, talvez você queira excluir produtos indisponíveis, mostrar itens em um intervalo de preço de $ 5 a $ 500 ou aumentar itens da mesma marca.

## Demonstração

Após concluir as tarefas ilustradas no funil da recomendação descrito acima, você fica com sua recomendação final. To watch an in-product demonstration inside [!DNL Target], the demo begins at 21:00 in the *Adobe Target Basics Webinar*, linked to below.

## Webinar de noções básicas do Adobe Target: Introdução ao Recommendations {#intro-to-recs}

[Introdução ao Recommendations](https://forums.adobe.com/external-link.jspa?url=https%3A%2F%2Fadobecustomersuccess.adobeconnect.com%2Fp8gt31drhs3e%2F%3FOWASP_CSRFTOKEN%3D4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)