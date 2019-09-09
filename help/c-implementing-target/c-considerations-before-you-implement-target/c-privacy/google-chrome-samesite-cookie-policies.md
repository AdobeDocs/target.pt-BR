---
description: Informações sobre o Target e o padrão SameSite IETF usado a partir do Google Chrome versão 76.
keywords: google;samesite; cookies; chrome 80; ietf
seo-description: Informações sobre o Adobe Target e o padrão SameSite IETF introduzido com a versão 80 do Google Chrome.
seo-title: Políticas de cookie do Adobe Target e do Google do Google
solution: Target
subtopic: Introdução
title: Políticas de cookies do Google Chrome para SameSite
topic: Padrão
uuid: aaeda1e6-7b2c-4a00-b65d-bfc95ea796b5
translation-type: tm+mt
source-git-commit: df40d69676cea586451e3b64b56ef602da91173f

---


# Políticas de cookies do Google Chrome para SameSite

O Google começará a impor novas políticas de cookie por padrão para usuários que iniciam com o Chrome 80, que é cortado para ser lançado no início de 2020. Este artigo explica tudo o que você precisa saber sobre as novas políticas de cookies do samesite, como [!DNL Adobe Target] oferecer suporte a essas políticas e como você pode usar [!DNL Target] para manter as novas Políticas de cookie do Google Chrome.

A partir do Chrome 80, os desenvolvedores da Web devem especificar explicitamente quais cookies podem funcionar em todos os sites. Esse é o primeiro de muitos anúncios que o Google planeja fazer para melhorar a privacidade e a segurança na Web.

Devido ao fato do Facebook estar na licença ativa com relação à privacidade e à segurança, outros players importantes, como a Apple e agora o Google, foram rapidamente capitalizar na oportunidade de criar novas identidades como defensores de privacidade e segurança. A Apple lançou o pacote primeiro anunciando as alterações nas políticas de cookie no começo deste ano por meio do ITP 2.1 e do ITP 2.2. No ITP 2.1, a Apple bloqueia completamente cookies de terceiros e mantém cookies criados no navegador por apenas sete dias. No ITP 2.2, os cookies são mantidos por apenas um dia. O anúncio do Google não é mais próximo do que o agressivo da Apple, mas é a primeira etapa para o mesmo objetivo final. Para obter mais informações sobre as políticas da Apple, consulte [a Apple Intelligent Prevention Prevention (ITP) 2. x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

## O que são cookies e como são usados?

Antes de mergulharmos nas alterações do Google em suas políticas de cookies, vamos tocar em quais são os cookies e como eles são usados. Simplesmente, os cookies são arquivos de texto pequenos armazenados no navegador da Web que são usados para lembrar os atributos do usuário.

Os cookies são importantes porque aumentam a experiência do usuário enquanto navegam na Web. Por exemplo, se você estiver fazendo compras em um site de ecommerce e adicionar algo ao carrinho, mas não fizer logon ou comprar nessa visita, os cookies lembram dos itens e os mantêm no carrinho da próxima visita. Ou imagine se foi forçado a reinserir seu nome de usuário e senha toda vez que visitar seu site de mídia social favorita. Os cookies resolvem esse problema também, pois armazenam informações que ajudam os sites a identificar quem você está. Esses tipos de cookies são chamados de cookies primários porque são criados e usados pelo site que você visitou.

Cookies de terceiros também existem. Para entendê-los melhor, considere este exemplo:

Vamos supor que uma empresa de mídia social hipotética chamada "Amigos" fornece um botão Compartilhar que outros sites implementam para permitir que os usuários de amigos compartilhem o conteúdo do site no feed de Amigos. Agora, um usuário lê um artigo de notícias em um site de notícias que usa o botão Compartilhar e o clica para publicar automaticamente em sua conta de Amigos.

Para que isso aconteça, o navegador obterá o botão Compartilhar amigos a partir `platform.friends.com` do momento em que o artigo de notícias for carregado. Nesse processo, o navegador anexa os cookies de Amigos, que contêm as credenciais conectadas do usuário, à solicitação para servidores de amigos. Isso permite que os amigos postem o artigo de notícias em seu feed em nome do usuário sem exigir que o usuário faça logon.

Isso é tudo possível usando cookies de terceiros. Nesse caso, o cookie de terceiros é salvo no navegador para `platform.friends.com`que possa fazer `platform.friends.com` a publicação no aplicativo de Amigos em nome do usuário.

Se você imaginar por um momento como conseguir esse caso de uso sem cookies de terceiros, o usuário deve seguir várias etapas manuais. Primeiro, o usuário teria que copiar o link para o artigo de notícias. Em segundo lugar, o usuário precisaria fazer logon no aplicativo de Amigos separadamente. Em seguida, o usuário clicaria no botão Criar publicação. Em seguida, o usuário copiaria e cola o link no campo de texto e, por fim, clique em Publicar. Como você pode ver, os cookies de terceiros ajudam a que a experiência do usuário, como etapas manuais, seja drasticamente reduzida.

Geralmente, os cookies de terceiros possibilitam o armazenamento de dados no navegador do usuário sem exigir que o usuário visite explicitamente um site.

## Questões de segurança

Embora os cookies aprimorem experiências do usuário e publicidade de energia, também podem introduzir vulnerabilidades de segurança como ataques de Falsificação de solicitação entre sites (CSRF). Por exemplo, se um usuário fizer logon em um site bancário para pagar faturas de cartão de crédito e sair do site sem sair e, em seguida, navegar para um site mal-intencionado na mesma sessão, poderá ocorrer um ataque CSRF. O site mal-intencionado pode incluir código que faz uma solicitação para o site de banco que é executado quando a página é carregada. Como o usuário ainda é autenticado no site da banca, o cookie de sessão pode ser usado para iniciar um ataque CSRF para iniciar um evento de transferência de créditos fora da conta bancária do usuário. Isso ocorre porque sempre que você visita um site, todos os cookies são anexados na solicitação HTTP. E devido a essas questões de segurança, o Google agora está tentando mitigá-los.

## Como o Target usa cookies?

Com tudo isso dito, vejamos como [!DNL Target] usa cookies. Para usar [!DNL Target] o primeiro local, é necessário instalar a biblioteca [!DNL Target] do javascript em seu site. Isso permite que você coloque um cookie primário no navegador do usuário que visita seu site. Conforme o usuário interage com seu site, você pode passar os dados comportamentais e de interesse do usuário para [!DNL Target] a biblioteca do javascript. A biblioteca [!DNL Target] javascript usa cookies primários para extrair informações de identificação sobre o usuário para mapear para o comportamento e os dados de interesse do usuário. Esses dados são usados para [!DNL Target] potencializar suas atividades de personalização.

O Target também (às vezes) usa cookies de terceiros. Se você possuir vários sites que moram em domínios diferentes e quiser rastrear a jornada do usuário nesses sites, você pode usar cookies de terceiros aproveitando o rastreamento entre domínios. Ao ativar o rastreamento entre domínios na biblioteca [!DNL Target] do javascript, sua conta começará a usar cookies de terceiros. Como um usuário de um domínio para outro, o navegador se comunica com o servidor de backend e [!DNL Target], nesse processo, um cookie de terceiros é criado e colocado no navegador do usuário. Por meio do cookie de terceiros que fica no navegador do usuário, [!DNL Target] é possível fornecer uma experiência consistente em diferentes domínios para um único usuário.

## Nova fórmula de cookie do Google

Para fornecer proteções sobre quando os cookies são enviados entre sites para que os usuários sejam protegidos, o Google planeja adicionar suporte a um padrão IETF chamado samesite, que requer que os desenvolvedores da Web gerenciem cookies com o componente de atributo samesite no cabeçalho Set-Cookie.

Há três valores diferentes que podem ser passados para o atributo SameSite: Strict, Lax ou None.

| Valor | Descrição |
| --- | --- |
| Strict | Os cookies com essa configuração podem ser acessados somente ao visitar o domínio em que foram definidos inicialmente. Em outras palavras, Strict bloqueia rigorosamente o cookie de ser usado entre sites. Essa opção seria melhor para aplicativos que exigem alta segurança, como bancos. |
| Lax | Cookies with this setting are sent only on same-site requests or top-level navigation with non-idempotent HTTP requests, like `HTTP GET`. Portanto, essa opção seria usada se o cookie pudesse ser usado por terceiros, mas com uma vantagem de segurança adicional que protege os usuários contra ataques de ataques CSRF. |
| None | Os cookies com essa configuração funcionam da mesma forma que os cookies funcionam hoje. |

Ao manter o acima em mente, o Chrome 80 introduz duas configurações independentes para usuários: " Samesite por cookies padrão "e" Cookies sem samesite devem ser seguros ". Essas configurações serão ativadas por padrão no Chrome 80.

![Caixa de diálogo samesite](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

* **Samesite por cookies padrão**: Quando definido, todos os cookies que não especificam o atributo samesite serão forçados a usar `SameSite = Lax`automaticamente.
* **Os cookies sem samesite devem ser seguros**: Quando definido, cookies sem o atributo samesite ou com `SameSite = None` a necessidade de Proteger. “Seguros” neste contexto significa que todas as solicitações do navegador devem seguir o protocolo HTTPS. Os cookies que não aderirem a esse requisito serão rejeitados. Todos os sites devem usar HTTPS para atender a esse requisito.

## O Target segue as práticas de segurança recomendadas do Google

Na Adobe, sempre queremos oferecer suporte às práticas recomendadas mais recentes do setor para segurança e privacidade. We are happy to announce that [!DNL Target] supports the new security and privacy settings introduced by Google.

Para a configuração "samesite por cookies padrão", [!DNL Target] continuará a fornecer personalização sem qualquer impacto e intervenção por você. [!DNL Target]O usa cookies próprios e continuará a funcionar corretamente, pois o sinalizador `SameSite = Lax` é aplicado pelo Google Chrome.

Para os "Cookies sem samesite", se você não optar pelo recurso de rastreamento entre domínios no [!DNL Target], os cookies originais continuarão [!DNL Target] funcionando.

However, when you opt-in to use cross-domain tracking to leverage [!DNL Target] across multiple domains, Chrome requires `SameSite = None` and Secure flags to be used for third-party cookies. Isso significa que você deve garantir que seus sites usem o protocolo HTTPS. As bibliotecas do cliente em [!DNL Target] usarão automaticamente o protocolo HTTPS e anexarão sinalizadores `SameSite = None` e sinalizadores seguros aos cookies de terceiros para [!DNL Target] garantir que todas as atividades continuem a oferecer.

## O que você precisa fazer?

Para entender o que você precisa fazer para [!DNL Target] continuar trabalhando para usuários do Google Chrome 80 +, consulte a tabela abaixo, da qual você verá as seguintes colunas:

* **Biblioteca do javascript do Target**: Se estiver usando mbox. js, at. js 1.*x* ou a at.js 2.*x* em seus sites.
* **Samesite por cookies padrão = Ativado**: Se os usuários tiverem "samesite por cookies padrão" ativados, como isso afeta você e há algo que você precisa fazer [!DNL Target] para continuar trabalhando.
* **Os cookies sem samesite devem ser seguros = Ativados**: Se os usuários tiverem "Cookies sem samesite" ativados, como isso afeta você e há algo que você precisa fazer para [!DNL Target] continuar trabalhando.

| Biblioteca de javascript do Target | Cookies SameSite por padrão = Ativado | Cookies sem SameSite devem ser seguros = Ativado |
| --- | --- | --- |
| mbox. js apenas com cookies primários. | Sem impacto. | Nenhum impacto se você não estiver usando o rastreamento entre domínios. |
| mbox. js com rastreamento entre domínios ativado. | Sem impacto. | Você deve ativar o protocolo HTTPS para seu site.<br>[!DNL Target] usa um cookie de terceiros para rastrear os usuários e o Google requer que os cookies de terceiros tenham `SameSite = None` e sinalizem o sinalizador Seguro. O sinalizador Seguro requer que os sites usem o protocolo HTTPS. |
| at.js 1.*x* com cookies primários. | Sem impacto. | Nenhum impacto se você não estiver usando o rastreamento entre domínios. |
| at.js 1.*x* com rastreamento entre domínios ativado. | Sem impacto. | Você deve ativar o protocolo HTTPS para seu site.<br>[!DNL Target] usa um cookie de terceiros para rastrear os usuários e o Google requer que os cookies de terceiros tenham `SameSite = None` e sinalizem o sinalizador Seguro. O sinalizador Seguro requer que os sites usem o protocolo HTTPS. |
| at.js 2.*x* | Sem impacto. | Sem impacto. |

## O que o Target precisa fazer?

Então, o que precisamos fazer em nossa plataforma para ajudá-lo a cumprir as novas políticas de cookie do Google Chrome 80 + samesite?

| Biblioteca de javascript do Target | Cookies SameSite por padrão = Ativado | Cookies sem SameSite devem ser seguros = Ativado |
| --- | --- | --- |
| mbox. js apenas com cookies primários. | Sem impacto. | Nenhum impacto se você não estiver usando o rastreamento entre domínios. |
| mbox. js com rastreamento entre domínios ativado. | Sem impacto. | [!DNL Target] adicionar `SameSite = None` e sinalizador Seguro ao cookie de terceiros quando [!DNL Target] servidores são chamados. |
| at.js 1.*x* com cookies primários. | Sem impacto. | Nenhum impacto se você não estiver usando o rastreamento entre domínios. |
| at.js 1.*x* com rastreamento entre domínios ativado. | Sem impacto. | at.js 1.*x* com rastreamento entre domínios ativado. |
| at.js 2.*x* | Sem impacto. | Sem impacto. |

## Qual é o impacto se você não mover o protocolo HTTPS?

O único caso de uso que afetará você é se você estiver usando o recurso de rastreamento entre domínios em [!DNL Target] uma mbox. js ou em um at. js 1.*x*. Sem mover-se para HTTPS, o que é um requisito do Google, você verá um pico em visitantes únicos em todos os domínios, pois o cookie de terceiros que usamos será descartado pelo Google. E como o cookie de terceiros será perdido, [!DNL Target] não será possível fornecer uma experiência consistente e personalizada para esse usuário à medida que o usuário navega de um domínio para outro. O cookie de terceiros é usado principalmente para identificar um único usuário navegando pelos domínios que você possui.

## Conclusão

Conforme o setor faz strides para criar uma Web mais segura para os consumidores, [!DNL Adobe] é absolutamente compromisso ajudar nossos clientes a fornecer experiências personalizadas de uma maneira que garanta a segurança e a privacidade dos usuários finais. Tudo que você precisa fazer é seguir as práticas recomendadas mencionadas anteriormente [!DNL Target] e aproveitar as novas Políticas de cookie do Google Chrome.
