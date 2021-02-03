---
keywords: Recommendations;introdução;introdução;webinar;demo
description: Introdução às atividades do Adobe Target Recommendations que exibem automaticamente produtos ou conteúdo que podem ser do interesse dos clientes com base nas atividades anteriores do usuário ou em outros algoritmos. O Recommendations ajuda a direcionar os clientes para itens relevantes que podem ser novidade para eles.
title: Introdução ao Recommendations Atividade
feature: Recommendations
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '2131'
ht-degree: 96%

---


# ![PREMIUM](/help/assets/premium.png) Introdução ao Recommendations

O texto deste artigo vem do webinário *Introdução ao Recommendations*, que pode ser exibido na íntegra abaixo.

O webinar de *Introdução ao Recommendations* inclui uma análise detalhada de como utilizar o valor de [!DNL Adobe Target Recommendations]. Descubra como essa atividade do [!DNL Target] exibe automaticamente os produtos ou conteúdos que talvez interessem aos seus clientes, otimizando sugestões em tempo real com base nas visitas anteriores. Além disso, acesse a interface do usuário do [!DNL Target] para obter uma visão geral passo a passo sobre como criar uma atividade do [!DNL Recommendations].

## Introdução

Todos nós conhecemos os tipos de recomendações que vemos no varejo. Cada vez mais os clientes esperam esse tipo de recomendações e as usam como um ponto de partida para explorar outras opções disponíveis. Se você pensar em seu próprio comportamento de compra, esses tipos de recomendações funcionam muito bem. Quase todos nós compramos um produto que vimos primeiro em uma recomendação em algum lugar, seja em uma loja ou em uma propriedade digital.

A ilustração a seguir mostra uma recomendação que exibe acessórios que são comprados normalmente com um novo telefone, incluindo carregadores, cases e fones de ouvido.

![A recomendação mostra os acessórios que outras pessoas compraram com um novo telefone.](/help/c-recommendations/assets/intro-1.png)

Mas o que nem sempre pensamos é como as primeiras marcas digitais estão elevando os padrões das expectativas dos clientes. Cada vez mais, o modo como consumimos mídia e conteúdo é orientado por recomendações personalizadas. Pense na primeira coisa que você vê ao abrir a Netflix, o Spotify ou o YouTube. Essas marcas iniciam a experiência do cliente com recomendações. Em um mundo em que há mais alternativas disponíveis do que nunca, é importante identificar o conteúdo mais relevante para o cliente no ponto de interação.

![Recomendação que mostra marcas digitais](/help/c-recommendations/assets/intro-2.png)

Os profissionais de marketing usam o [!DNL Adobe Target] para impulsionar experiências personalizadas em diversos setores, tipos de clientes e canais.

O [!DNL Adobe Target] entrega conteúdo personalizado em todos os locais.

![Ilustração que mostra como o Target fornece recomendações em vários lugares](/help/c-recommendations/assets/intro-3.png)

* **Publicação**: os editores da Web usam o [!DNL Target Recommendations] para recomendar artigos aos visitantes do site e impulsionar maior engajamento.
* **Tutoriais em vídeo**: o [!DNL Adobe Creative Cloud] usa o [!DNL Target] para recomendar tutoriais em vídeo aos usuários do Photoshop no aplicativo Photoshop.
* **Jogos**: as empresas de jogos usam o [!DNL Target] para recomendar jogos e conteúdo aos usuários em seus consoles.
* **Vendas B2B**: [As empresas B2B usam o Target para recomendar vídeos, whitepapers e publicações do blog para prospectos B2B; entregar downloads; e fornecer ajuda aos clientes](https://theblog.adobe.com/testing-shifts-high-gear-intel).

* **Viagem**:  [Um corretor de viagens alemão usa o Público alvo para recomendar hotéis e muito mais para viajantes](https://2017.summit.adobe.com/na/sessions/summit-online/online-2017/#17608).

* **Varejo**: [um varejista BB líder usa o Target para recomendar as principais categorias e produtos para retornar visitantes no navegador e em seu aplicativo](https://theblog.adobe.com/optimization-personalization-b2b-powerhouse-grainger/)2/ móvel.

Essas são apenas algumas das formas em que os clientes usam o Target para fornecer recomendações personalizadas.

O que faz para excelentes recomendações?

![Ilustração que mostra os três elementos que fazem excelentes recomendações](/help/c-recommendations/assets/intro-4.png)

Excelentes recomendações devem ser relevantes e personalizadas. Isso significa que você precisa de três elementos para impulsionar relevância e personalização:

* **Controles do profissional de marketing** para ajudar a impulsionar a relevância dos itens recomendados. Como profissional de marketing, você apresenta um contexto importante e sabe quais atributos de seus produtos ou conteúdo são relevantes para ser considerados em um modelo de recomendações. Se estiver operando um site de vídeo, você sabe que os usuários podem estar interessados em ver filmes do mesmo diretor, mas provavelmente não se importam em ver filmes produzidos pelo mesmo estúdio. O [!DNL Target] capacita você com controles que permitem aprimorar seus algoritmos com esse conhecimento de domínio.
* **Modelos sofisticados** para dar sentido a milhões de itens nos eventos de catálogo e interação. O [!DNL Target] possui recursos sofisticados de aprendizado de máquina criados em uma década de experiência e nós lidamos com bilhões de recomendações por ano.
* **Contexto do usuário** para garantir que as recomendações sejam oportunas e relevantes para os usuários. Você não vai querer recomendar o vídeo que alguém acabou de assistir ou a camisa que alguém acabou de adicionar ao carrinho. O perfil de usuário avançado do Target pode ser usado nas recomendações para garantir a personalização.

## Implementar o Target Recommendations

Comece com uma estratégia.

![Ilustração que mostra a estratégia de recomendações](/help/c-recommendations/assets/intro-5.png)

* **Quais itens você deseja recomendar?** Primeiro, pense em quais itens você deseja recomendar. Pode ser produto, vídeo ou conteúdo.
* **Onde você deseja mostrar as recomendações?** Em seguida, pense em onde você deseja fazer recomendações. Em geral, quais canais (Web, dispositivos móveis, lojas, quiosques e assim por diante). Quais partes da jornada do cliente conterão recomendações? Quais páginas do site conterão recomendações?
* **Como você determinará se as recomendações obtiveram êxito?** Suponha que você tenha uma experiência sem recomendações e uma experiência com recomendações ou que você tem dois tipos diferentes de recomendações. Como você poderia determinar qual experiência foi a melhor para os clientes? Algumas métricas podem ser mais difíceis de medir do que outras. Por exemplo, o impacto das recomendações no Valor vitalício do cliente geralmente é difícil de entender diretamente. Por isso, muitas vezes, é mais fácil obter uma métrica menos abstrata e outra mais concreta, por exemplo, receita por visita, valor médio de pedido ou número de cliques. Em alguns casos, talvez você queira minimizar uma métrica, por exemplo, o número de chamadas de suporte.

Após estabelecer sua estratégia, você estará pronto para iniciar a implementação do [!DNL Target Recommendations].

Há três etapas abrangentes envolvidas na criação da implementação das recomendações:

![Ilustração que mostra as etapas para criar sua implementação de recomendações](/help/c-recommendations/assets/intro-6.png)

1. Ensine o [!DNL Target] sobre seu contexto ou seus produtos.
1. Capture o comportamento do usuário.
1. Obtenha recomendações com o contexto adequado.

### Ensine o [!DNL Target] sobre seu contexto ou seus produtos

Ao iniciar o [!DNL Recommendations], você transmite as informações sobre cada item que deseja recomendar. O [!DNL Target] oferece várias opções de integração para criar o catálogo.

![Ilustração que mostra como ensinar o Target sobre seu contexto ou seus produtos](/help/c-recommendations/assets/intro-7.png)

O método mais simples e usado com mais frequência é enviar um arquivo CSV diária ou semanalmente do sistema de gerenciamento de informações do produto ou do sistema de gerenciamento de conteúdo. Mas você também pode transmitir informações sobre a camada de dados da página usando a biblioteca JavaScript do [!DNL Adobe Target], aproveitar as APIs para transmitir informações diretamente do sistema de origem ou usar a integração do [!DNL Adobe Analytics], caso já esteja transmitindo dados de catálogo para o [!DNL Analytics].

Às vezes, convém usar várias opções juntas, por exemplo, transmitir a maioria dos dados diariamente por meio de um arquivo CSV e transmitir as atualizações de inventário com mais frequência por meio de uma API.

Normalmente, o departamento de TI estará envolvido em ajudar a definir essa etapa.

Seja qual for o método escolhido, você deve incluir metadados sobre cada item em três categorias:

![Ilustração que mostra as informações de metadados para o catálogo](/help/c-recommendations/assets/intro-8.png)

* Os dados que você deseja exibir para o usuário que recebe a recomendação. Por exemplo, o nome do filme e um URL da imagem em miniatura.
* Dados úteis para aplicar controles de marketing e merchandising. Por exemplo, a classificação do filme para que você não recomende filmes NC-17.
* Dados úteis para determinar a similaridade dos itens com outros itens. Por exemplo, o gênero do filme ou os atores que estão no filme.

### Capture o comportamento do usuário

Em seguida, você deve adicionar tags ou aproveitar a implementação existente do [!DNL Analytics] para rastrear os eventos de conversão (como exibições e compras) que impulsionam os algoritmos do [!DNL Target].

![Ilustração que mostra como capturar o comportamento do usuário](/help/c-recommendations/assets/intro-9.png)

Você precisa garantir que o [!DNL Target] esteja ciente dos itens que os usuários estão vendo e comprando. Se a compra não for relevante para o contexto, talvez você queira rastrear um tipo diferente de evento de conversão, por exemplo, baixar um PDF, concluir uma pesquisa, inscrever-se em um boletim informativo, assistir a um vídeo e assim por diante.

Se já estiver usando o [!DNL Target] para executar as atividades dos Testes A/B no site, talvez você já tenha concluído essa etapa. Ou se já estiver usando o [!DNL Adobe Analytics] para o relatório sobre visitas do site e comportamento de conversão, você poderá usar o [!DNL Analytics] como fonte de dados comportamentais. Caso contrário, é mais fácil definir essa etapa usando um gerenciador de tags, como o [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md). Também é possível enviar interações offline ou no aplicativo para o [!DNL Target] por meio da API em tempo real.

### Obter recomendações com o contexto adequado

Transmita informações sobre o usuário e contexto no ponto de interação para o [!DNL Target], para retornar recomendações relevantes e personalizadas.

![Ilustração que mostra como obter recomendações com o contexto adequado](/help/c-recommendations/assets/intro-10.png)

Além do comportamento do usuário na agregação, você precisa transmitir ao [!DNL Target] o contexto específico em que as recomendações são exibidas. Isso inclui informações sobre a página e informações do perfil do usuário. O [!DNL Target] usa essas informações para fazer recomendações personalizadas. Por exemplo, em um site de varejo, você deseja saber o produto e a categoria do produto que o visitante está visualizando no momento. Talvez você queira saber também as informações sobre esse usuário (marca favorita, categoria de produto favorita, nível de fidelidade e assim por diante). Essas informações são importantes para que o [!DNL Target] possa filtrar os itens e aprimorar a personalização das recomendações.

## Criar sua primeira atividade do Recommendations

O que é uma atividade do [!DNL Recommendations]?

![Ilustração que mostra as partes que fazem uma boa atividade de recomendações](/help/c-recommendations/assets/intro-11.png)

Uma atividade do [!DNL Recommendations] consiste nos seguintes componentes:

* **Público-alvo**: quem deve ver essas recomendações?
* **Critérios**: quais itens devem ser recomendados?
* **Design**: como os itens recomendados devem ser exibidos?

![Ilustração que mostra em que consiste uma atividade de recomendações: públicos-avo, critérios e designs](/help/c-recommendations/assets/intro-12.png)

Imediatamente, o [!DNL Target] inclui 14 públicos-alvo integrados, 42 critérios integrados e 10 modelos de design integrados. Você pode personalizar cada um desses itens ou adicionar os seus próprios. Tivemos webinars anteriores [sobre como criar audiência](https://landing.adobe.com/acs/2018/na/adobe-target/registration.html) em [!DNL Target]. Esta seção foca na definição dos critérios que determinam quais itens serão recomendados.

O Target usa o conceito do cartão de critérios. Um cartão de critérios é como uma fórmula para personalização.

![Ilustração do cartão de critérios](/help/c-recommendations/assets/intro-13.png)

É importante escolher ou criar os critérios corretos para atingir os resultados de personalização desejados. Um critério é como um funil que leva você do catálogo inteiro até o conjunto final de recomendações.

![Ilustração de funil](/help/c-recommendations/assets/intro-14.png)

As seções a seguir descrevem as várias partes desse funil e como elas funcionam no [!DNL Target]:

### Filtros estáticos (coleções e exclusões)

Os filtros estáticos são regras gerais aplicáveis aos atributos do catálogo que você não espera alterar com frequência.

![Ilustração de coleções e exclusões](/help/c-recommendations/assets/intro-16.png)

Por exemplo, em um contexto de conteúdo, você pode querer incluir todos os filmes nas recomendações, mas excluir os filmes classificados como NC-17. Em um contexto de varejo, você pode ter várias marcas em diferentes partes do mundo, mas deseja recomendar apenas os produtos disponíveis nos Estados Unidos. Você também pode querer excluir os produtos de um rótulo privado regional.

Todos esses são atributos de catálogo amplamente aplicáveis, que podem ser usados em várias recomendações e que você não espera que sejam alterados com frequência.

### Algoritmo (chave e lógica de recomendação)

A próxima etapa é escolher a chave e a lógica de recomendação. É aqui que você decide qual é a base da recomendação.

![Ilustração de algoritmo](/help/c-recommendations/assets/intro-17.png)

A primeira coisa que você precisa escolher é a chave de recomendação. A chave de recomendação é o que você está “procurando” para escolher a recomendação. É em que se baseia a recomendação.

A recomendação pode ser baseada no seguinte:

* O item que o visitante está vendo no momento
* A categoria que o visitante está visualizando no momento
* O último item que o visitante comprou ou adicionou ao carrinho de compras
* Um atributo personalizado relacionado a um visitante ou item

Com base nessas chaves, você escolhe a lógica de recomendação desejada:

* Itens com atributos similares
* Os itens mais visualizados em uma categoria específica
* Os clientes que compraram esse item também compraram esses itens
* Um atributo personalizado

Imediatamente, o [!DNL Target] inclui um portfólio de algoritmos.

![Ilustração do portfólio de algoritmos](/help/c-recommendations/assets/intro-15.png)

* Os **algoritmos baseados em popularidade** incluem Mais visualizados e Principais vendedores.
* Os **algoritmos baseados em conteúdo** incluem Semelhança de conteúdo.
* Os **algoritmos de filtros colaborativos baseados em itens** incluem Visualizados/Visualizados, Visualizados/Comprados e Comprados/Comprados. Observe que “comprados” podem incluir qualquer conversão.
* Os **algoritmos personalizados** incluem Visualizados recentemente, Afinidade do site e Filtros colaborativos aprimorados por perfil.
* Os **algoritmos próprios** permitem usar seus próprios algoritmos personalizados.

### Regras de ebusiness

A última etapa é aplicar as regras de ebusiness. É aqui que você capacita os algoritmos com conhecimento de domínio e contexto atual com base no que o visitante está fazendo em sua propriedade digital.

![Ilustração de regras de ebusiness](/help/c-recommendations/assets/intro-18.png)

Por exemplo, no contexto de conteúdo, você pode excluir os filmes que o visitante assistiu anteriormente, recomendar os filmes do mesmo diretor ou impulsionar os filmes do mesmo gênero. No contexto de varejo, talvez você queira excluir os produtos indisponíveis, mostrar os itens em um intervalo de preço de $5 a $500 ou impulsionar os itens da mesma marca.

## Demonstração

Após concluir as tarefas ilustradas no funil de recomendações descrito acima, você fica com a recomendação final. Para assistir a uma demonstração do produto no [!DNL Target], a demonstração começa às 21:00 no *Webinário de noções básicas do Adobe Target*, vinculado abaixo.

## Webinário de noções básicas do Adobe Target: Introdução ao Recommendations {#intro-to-recs}

[Introdução ao Recommendations](https://forums.adobe.com/external-link.jspa?url=https%3A%2F%2Fadobecustomersuccess.adobeconnect.com%2Fp8gt31drhs3e%2F%3FOWASP_CSRFTOKEN%3D4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)