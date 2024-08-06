---
keywords: dados dinâmicos; ativos; dados; ofertas; ofertas personalizadas; ofertas pessoais; substituição de token
description: Saiba como transmitir dados dinâmicos para Ofertas no [!DNL Adobe Target].
title: Como transfiro dados dinâmicos em ofertas?
feature: Experiences and Offers
exl-id: b8f9c6eb-1000-41a2-aa3f-bc42c1ef5669
source-git-commit: 2e607b92e9d3408c1e91abd4646fe8eb840f2c30
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 55%

---

# Envio de dados dinâmicos em ofertas

Você pode exibir dinamicamente as informações do visitante armazenadas no perfil [!DNL Adobe Target]. Da mesma forma, as informações de atividade (como o nome da atividade ou o nome da experiência) também podem ser usadas para criar uma oferta única, que retorna dinamicamente o conteúdo personalizado com base nos interesses do visitante, no comportamento anterior e no perfil geral.

## Casos de negócios

* Promova uma oferta com desconto para &quot;recarregar&quot; ou &quot;repor&quot; o último produto comprado. Em vez de criar uma oferta separada para cada item no catálogo, você pode criar uma oferta com texto dinâmico que lê o &quot;último produto comprado&quot; do perfil e exibe um link na oferta.
* Um visitante chega à página de aterrissagem com `keyword=world` `cup`. Você exibe o termo *Copa do mundo* na oferta.
* Personalize um rótulo de recomendações com informações, como (1) o último item adicionado ao carrinho do visitante (Nike Air Max 1000s), (2) a preferência de cor do visitante (preto) e (3) a categoria favorita do visitante sem ser sapatos (moletons). Exemplo: &quot;Complemente o look do seu &#39;Nike Air Max 1000s&#39; com esse &#39;moletom&#39; &#39;preto&#39; despojado!&quot;

## Vantagens técnicas

Como as preferências, os comportamentos e o status específicos do visitante podem ser armazenados no perfil do visitante, você pode repetir essa mensagem nas próximas visitas. As ofertas dinâmicas possibilitam uma escala maior, permitindo que você configure uma oferta única dentro de uma atividade que exibe mensagens personalizadas para todos os seus visitantes. Conforme a intenção do visitante muda, o conteúdo do site reflete automaticamente essas alterações.

## Exemplo

* `mboxCreate("landingpage"`, `"profile.keyword=World Cup");`

* Código da oferta HTML: `Get your ${profile.keyword} information here!`
* Visitantes podem ver: Obtenha aqui as suas informações sobre a Copa do Mundo!

Os valores a seguir podem ser &quot;substituídos por token&quot;:

| Valor | Exemplos |
|--- |--- |
| Parâmetros do perfil da in-mbox | `${profile.age}` |
| Parâmetros do perfil de script | `${user.lifetimeSpend}` |
| Parâmetros de mbox | `${mbox.favoriteColor}` |
| Informações da campanha | `${campaign.name}`, `${campaign.recipe.name}`, `${campaign.id}`, `${campaign.recipe.id}` e `${campaign.recipe.trafficType}` |
| Id única do visitante | `${user.pcId}` |
| Id única da sessão | `${user.sessionId}` |
| Primeira sessão do visitante (true ou false) | `${user.isFirstSession}` |
| Comportamento anterior | `${user.endpoint.lastPurchasedEntity}`, `${user.endpoint.lastViewedEntity}`, `${user.endpoint.mostViewedEntity}`, `${user.endpoint.categoryAffinity}` |

Informações de log no console para fins de depuração, como `${campaign.name}`, `${campaign.id}`, `${campaign.recipe.name}`, `${campaign.recipe.id}`, `${offer.name}`, `${offer.id}`, `${campaign.name}`

Para designs do [!DNL Recommendations], consulte mais exemplos na [Visão geral do design](/help/main/c-recommendations/c-design-overview/design-overview.md).

## Implementação

Em parâmetros de perfil passados para uma mbox, use a sintaxe:

`${profile.parameter}`

Em parâmetros de perfil criados em um script de perfil, use a sintaxe:

`${user.parameter}`

Ao usar atributos dinâmicos em um design do [!DNL Recommendations], você deve inserir uma barra invertida ( \ ) antes do cifrão ( $ ) para que o valor dinâmico seja renderizado adequadamente:

`\${user.endpoint.lastViewedEntity}`

Essas variáveis são substituídas pelo valor no lado do servidor. Não há necessidade de aspas ou JavaScript para a exibição correta.

Os valores padrão também podem ser especificados para valores que você deseja expor às ofertas. A sintaxe é:

`${user.testAttribute default="All Items!"}`

Quando `testAttribute` não existe ou está em branco, &quot;Todos os itens!&quot; está escrito. Se um valor de atributo vazio é válido, e você quer gravá-lo em vez de mostrar o padrão, você pode usar:

`${user.testAttribute default="All Items!" show_blank="true"}`

Você também pode utilizar valores escape e unescape para serem exibidos. Se o valor tiver um apóstrofo, por exemplo, você pode omitir o valor para que ele não quebre a JavaScript na página. (As ofertas são escritas em JavaScript. Dessa forma, um único apóstrofo pode ser confundido com uma citação.) Por exemplo:

`${user.encodedValue encode="unescape"}`

`${user.unencodedValue encode="escape"}`

Para parâmetros de oferta (offer.name, offer.id) usados no conteúdo de uma oferta:

Se essa oferta for uma das várias ofertas definidas em uma experiência, o valor da última oferta adicionada preencherá o valor do parâmetro. Ou seja, esses parâmetros são avaliados no nível da experiência.