---
description: Você pode exibir valores de perfil e informações de atividade diretamente em uma oferta HTML ou JSON.
keywords: dados dinâmicos; ativos; dados; ofertas; ofertas personalizadas; ofertas pessoais; substituição de token
seo-description: Você pode exibir valores de perfil e informações de atividade diretamente em uma oferta HTML ou JSON.
seo-title: Envio de dados dinâmicos em ofertas
solution: Target
title: Envio de dados dinâmicos em ofertas
topic: Premium
uuid: 1910a7f5-e4bd-413a-9875-e0b005407f50
translation-type: tm+mt
source-git-commit: f792c0b995e0f4445d3c3849a431d64b6bd60324

---


# Envio de dados dinâmicos em ofertas{#pass-dynamic-data-into-offers}

É possível exibir dinamicamente as informações do visitante armazenadas no perfil do Target. Da mesma forma, as informações de atividade (como o nome da atividade ou o nome da experiência) também podem ser usadas para criar uma única oferta que retorna dinamicamente o conteúdo personalizado, com base nos interesses do visitante, no comportamento anterior e no perfil geral.

**Casos de negócios**

* Promova uma oferta com desconto para &quot;refill&quot; ou &quot;reuniish&quot; o último produto comprado. Em vez de criar uma oferta separada para cada item no catálogo, você pode criar uma oferta com texto dinâmico que lê o &quot;último produto comprado&quot; do perfil e exibir um link na oferta.
* Um visitante chega à página de aterrissagem com `keyword=world` `cup`. Você exibe o termo *Copa do mundo* na oferta.
* Personalize um rótulo de recomendações com informações como (1) o último item adicionado ao carrinho (Nike Air Máx. 1000 s), (2) a preferência de cor do visitante (preto) e (3) a categoria favorita do visitante (ganodies). Exemplo: &quot; Acesse &quot;Nike Air Max 1000 s&quot; com &quot;preto&quot; legal &quot;ganhe&quot;! &quot;


**Vantagens técnicas**

Como preferências específicas do usuário, comportamentos, status etc. pode ser armazenado no perfil do usuário, você pode repetir esta mensagem nas próximas visitas. As ofertas dinâmicas permitem maior escala permitindo que você configure uma única oferta dentro de uma atividade que exibe mensagens personalizadas para todos os seus visitantes. Conforme o objetivo do visitante muda, o conteúdo do seu site reflete automaticamente essas alterações.

**Exemplo**

* `mboxCreate("landingpage"`, `"profile.keyword=World Cup");`

* Código da oferta HTML: `Get your ${profile.keyword} information here!`
* O usuário vê: Saiba tudo sobre a Copa do mundo aqui!

Os valores a seguir podem ser &quot;substituídos por token&quot;:

| Valores | Exemplos |
|--- |--- |
| Parâmetros do perfil da in-mbox | `${profile.age}` |
| Parâmetros do perfil de script | `${user.lifetimeSpend}` |
| Parâmetros de mbox | `${mbox.favoriteColor}` |
| Informações da campanha | `${campaign.name}`, `${campaign.recipe.name}`, `${campaign.id}`, `${campaign.recipe.id}` e `${campaign.recipe.trafficType}` |
| Id única do visitante | `${user.pcId}` |
| Id única da sessão | `${user.sessionId}` |
| Primeira sessão do visitante (true ou false) | `${user.isFirstSession}` |
| Comportamento anterior | `{$user.endpoint.lastPurchasedEntity}`, `{$user.endpoint.lastViewedEntity}`, `{$user.endpoint.mostViewedEntity}`, `{$user.endpoint.categoryAffinity}` |

As informações de log no console para fins de depuração, como `${campaign.name}``${campaign.id}``${campaign.recipe.name}``${campaign.recipe.id}``${offer.name}``${offer.id}`, `${campaign.name}`

Para designs do Recommendations, consulte mais exemplos na [Visão geral do design](/help/c-recommendations/c-design-overview/design-overview.md).

**Implementação**

Para parâmetros de perfil passados para uma mbox, use a sintaxe: `${profile.parameter}` Para parâmetros de perfil criados em um script de perfil, use a sintaxe:

`${user.parameter}`

Ao usar atributos dinâmicos em um design do Recommendations, você deve inserir uma barra invertida (&#39;\&#39;) antes do cifrão (&#39; $&#39;) para que o valor dinâmico seja renderizado adequadamente: `\${user.endpoint.lastViewedEntity}`

Essas variáveis são substituídas pelo valor no lado do servidor. Não há necessidade de aspas ou JavaScript para a exibição correta.

Valores padrão também podem ser especificados para valores que você deseja expor para ofertas. A sintaxe é:

`${user.testAttribute default="All Items!"}`

Quando `testAttribute` não existe ou está em branco, &quot;Todos os itens!&quot; será escrito. Se um valor de atributo vazio é válido, e você quer gravá-lo em vez de mostrar o padrão, você pode usar:

`${user.testAttribute default="All Items!" show_blank="true"}`

Você também pode utilizar valores escape e unescape para serem exibidos. Por exemplo, se o seu valor tem um apóstrofo, você pode querer utilizar o valor escape para que ele não quebre as linhas do JavaScript na página. (As ofertas são escritas em JavaScript. Dessa forma, um único apóstrofo pode ser confundido com uma citação.) Por exemplo:

`${user.encodedValue encode="unescape"}`

`${user.unencodedValue encode="escape"}`