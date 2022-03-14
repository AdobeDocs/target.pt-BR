---
keywords: google;samesite;cookies;chrome 80;ietf
description: Descubra como o Adobe [!DNL Target] O lida com o padrão SameSite IETF introduzido no Google Chrome versão 80 e com o que é necessário fazer para estar em conformidade com essas políticas.
title: Como [!DNL Target] Lidar com as políticas de cookies do Samesite da Google?
feature: Privacy & Security
role: Developer
exl-id: 5abd2065-3692-4a6d-9ac9-6d416604c2d2
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1948'
ht-degree: 7%

---

# Políticas de cookies do Google Chrome para SameSite

A Google começará a impor novas políticas de cookies por padrão para os usuários a partir do Chrome 80, que deverá ser lançado no início de 2020. Este artigo explica tudo o que você precisa saber sobre as novas políticas de cookies do SameSite, como [!DNL Adobe Target] O suporta essas políticas e como você pode usar [!DNL Target] para estar em conformidade com as novas Políticas de cookies do SameSite do Google Chrome.

A partir do Chrome 80, os desenvolvedores da Web devem especificar explicitamente quais cookies podem funcionar entre sites. Este é o primeiro de muitos anúncios que a Google pretende fazer para melhorar a privacidade e a segurança na Web.

Dado o fato de a Facebook ter estado no centro das atenções no que diz respeito à privacidade e à segurança, outros grandes intervenientes, como a Apple e agora a Google, aproveitaram rapidamente a oportunidade para criar novas identidades como campeões da privacidade e da segurança. A Apple liderou o pacote, anunciando primeiro alterações em suas políticas de cookies no início deste ano por meio da ITP 2.1 e, recentemente, da ITP 2.2. Na ITP 2.1, a Apple bloqueia completamente os cookies de terceiros e mantém os cookies criados no navegador por apenas sete dias. Na ITP 2.2, os cookies são mantidos por apenas um dia. O anúncio da Google não é tão agressivo quanto o da Apple, mas é o primeiro passo para a mesma meta final. Para obter mais informações sobre as políticas da Apple, consulte [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

## O que são cookies e como eles são usados?

Antes de mergulharmos nas alterações da Google em suas políticas de cookies, vamos nos debruçar sobre o que são cookies e como eles são usados. Simplificando, os cookies são arquivos de texto pequenos armazenados no navegador da Web, usados para lembrar atributos do usuário.

Os cookies são importantes porque melhoram a experiência do usuário ao navegar na Web. Por exemplo, se você estiver fazendo compras em um site de comércio eletrônico e adicionar algo ao carrinho, mas não fizer logon ou comprar nessa visita, os cookies lembram dos itens e os mantêm no carrinho para a próxima visita. Ou imagine se tiver sido forçado a reinserir seu nome de usuário e senha toda vez que visitar seu site de mídia social favorito. Os cookies também resolvem esse problema, pois armazenam informações que ajudam os sites a identificar quem você é. Esses tipos de cookies são chamados de cookies primários porque são criados e usados pelo site visitado.

Cookies de terceiros também existem. Para entendê-los melhor, considere este exemplo:

Digamos que uma hipotética empresa de mídia social chamada &quot;Amigos&quot; forneça um botão Compartilhar que outros sites implementam para permitir que os usuários do Amigos compartilhem o conteúdo do site no feed Amigos. Agora, um usuário lê um artigo de notícias em um site de notícias que está usando o botão Compartilhar e clica nele para postar automaticamente em sua conta Amigos.

Para que isso aconteça, o navegador busca o botão Compartilhar amigos do `platform.friends.com` quando o artigo de notícias for carregado. Nesse processo, o navegador anexa os cookies Amigos, que contêm as credenciais conectadas do usuário, à solicitação para os servidores Amigos. Isso permite que os amigos publiquem o artigo de notícias em seu feed em nome do usuário, sem exigir que o usuário faça logon.

Isso é tudo possível usando cookies de terceiros. Nesse caso, o cookie de terceiros é salvo no navegador para `platform.friends.com`, para que `platform.friends.com` O pode fazer a publicação no aplicativo Amigos em nome do usuário.

Se você imaginar por um momento como obter esse caso de uso sem cookies de terceiros, o usuário precisará seguir várias etapas manuais. Primeiro, o usuário teria que copiar o link para o artigo de notícias. Segundo, o usuário teria que fazer logon no aplicativo Amigos separadamente. Em seguida, o usuário clicaria no botão Criar publicação . Em seguida, o usuário copiava e colava o link no campo de texto e, por fim, clicava em Publicar. Como você pode ver, os cookies de terceiros ajudam imensamente o usuário a experimentar, pois as etapas manuais podem ser drasticamente reduzidas.

Em geral, os cookies de terceiros permitem que os dados sejam armazenados no navegador de um usuário sem exigir que ele visite explicitamente um site.

## Questões de segurança

Embora os cookies aprimorem as experiências do usuário e a publicidade de energia, eles também podem apresentar vulnerabilidades de segurança como ataques de falsificação de solicitação entre sites (CSRF). Por exemplo, se um usuário fizer logon em um site bancário para pagar contas de cartão de crédito e sair do site sem sair e, em seguida, navegar até um site mal-intencionado na mesma sessão, um ataque CSRF poderá ocorrer. O site mal-intencionado pode incluir um código que faz uma solicitação ao site bancário que é executado quando a página é carregada. Como o usuário ainda é autenticado no site bancário, o cookie da sessão pode ser usado para iniciar um ataque CSRF para iniciar um evento de transferência de fundos fora da conta bancária do usuário. Isso ocorre porque sempre que você visita um site, todos os cookies são anexados na solicitação HTTP. E por causa dessas preocupações de segurança, a Google agora está tentando atenuá-las.

## Como [!DNL Target] usar cookies?

Com tudo isso, vamos ver como [!DNL Target] O usa cookies. Para usar [!DNL Target] em primeiro lugar, é necessário instalar o [!DNL Target] Biblioteca de JavaScript no seu site. Isso permite que você coloque um cookie próprio no navegador do usuário que visita seu site. Conforme seu usuário interage com seu site, você pode transmitir os dados comportamentais e de interesse do usuário para [!DNL Target] por meio da biblioteca do JavaScript. O [!DNL Target] A biblioteca de JavaScript usa cookies primários para extrair informações de identificação sobre o usuário para mapear para o comportamento e os dados de interesse do usuário. Esses dados são usados por [!DNL Target] para potencializar suas atividades de personalização.

O Target também (às vezes) usa cookies de terceiros. Se você possuir vários sites que residem em domínios diferentes e quiser rastrear a jornada do usuário nesses sites, poderá usar cookies de terceiros aproveitando o rastreamento entre domínios. Ao ativar o rastreamento entre domínios no [!DNL Target] Biblioteca de JavaScript, sua conta começará a usar cookies de terceiros. Conforme um usuário pula de um domínio para outro, o navegador se comunica com o servidor de back-end de [!DNL Target]e, nesse processo, um cookie de terceiros é criado e colocado no navegador do usuário. Por meio do cookie de terceiros que está no navegador do usuário, [!DNL Target] O é capaz de fornecer uma experiência consistente em diferentes domínios para um único usuário.

## A nova receita de cookie do Google

Para fornecer garantias sobre quando os cookies são enviados entre sites para que os usuários fiquem protegidos, a Google pretende adicionar suporte para um padrão IETF chamado SameSite, que requer que os desenvolvedores da Web gerenciem cookies com o componente de atributo SameSite no cabeçalho Set-Cookie.

Há três valores diferentes que podem ser passados para o atributo SameSite: Strict, Lax ou None.

| Valor | Descrição |
| --- | --- |
| Strict | Os cookies com essa configuração podem ser acessados somente ao visitar o domínio em que foram definidos inicialmente. Em outras palavras, Strict bloqueia rigorosamente o cookie de ser usado entre sites. Essa opção seria mais adequada para aplicativos que exigem alta segurança, como bancos. |
| Lax | Os cookies com essa configuração são enviados somente em solicitações de mesmo site ou na navegação de primeiro nível com solicitações HTTP não idempotentes, como `HTTP GET`. Portanto, essa opção seria usada se o cookie pudesse ser usado por terceiros, mas com um benefício de segurança adicional que protege os usuários de serem vítimas de ataques de CSRF. |
| None | Os cookies com essa configuração funcionarão da mesma forma que os cookies atualmente. |

Lembrando o acima, o Chrome 80 apresenta duas configurações independentes para os usuários: &quot;Cookies SameSite por padrão&quot; e &quot;Cookies sem SameSite devem ser seguros&quot;. Essas configurações serão ativadas por padrão no Chrome 80.

![Caixa de diálogo SameSite](/help/main/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

* **Cookies SameSite por padrão**: Quando definido, todos os cookies que não especificam o atributo SameSite serão forçados automaticamente a usar `SameSite = Lax`.
* **Os cookies sem SameSite devem ser seguros**: Quando definido, os cookies sem o atributo SameSite ou com `SameSite = None` precisam ser Seguros. “Seguros” neste contexto significa que todas as solicitações do navegador devem seguir o protocolo HTTPS. Os cookies que não aderirem a esse requisito serão rejeitados. Todos os sites devem usar HTTPS para atender a esse requisito.

## O Target segue as práticas de segurança recomendadas do Google

No Adobe, sempre queremos oferecer suporte às práticas recomendadas mais recentes do setor para segurança e privacidade. Temos o prazer de anunciar que [!DNL Target] O suporta as novas configurações de segurança e privacidade introduzidas pelo Google.

Para a configuração &quot;Cookies SameSite por padrão&quot;, [!DNL Target] O continuará a fornecer personalização sem qualquer impacto e intervenção da sua parte. [!DNL Target]O usa cookies próprios e continuará a funcionar corretamente, pois o sinalizador `SameSite = Lax` é aplicado pelo Google Chrome.

Para a opção &quot;Cookies sem SameSite devem ser seguros&quot;, se você não optar pelo recurso de rastreamento entre domínios no [!DNL Target], os cookies primários em [!DNL Target] O continuará a funcionar.

No entanto, quando você opta por usar o rastreamento entre domínios para aproveitar [!DNL Target] em vários domínios, o Chrome requer `SameSite = None` Sinalizadores e seguros a serem usados para cookies de terceiros. Isso significa que você deve garantir que seus sites usem o protocolo HTTPS. Bibliotecas do lado do cliente em [!DNL Target] usará automaticamente o protocolo HTTPS e anexará o `SameSite = None` e Proteger sinalizadores para cookies de terceiros em [!DNL Target] para garantir que todas as atividades continuem a funcionar.

## O que você precisa fazer?

Para entender o que você precisa fazer para ter [!DNL Target] continue a funcionar para usuários do Google Chrome 80+, consulte a tabela abaixo, da qual você verá as seguintes colunas:

* **Biblioteca JavaScript do Target**: Se estiver usando a at.js 1.*x* ou at.js 2.*x* em seus sites.
* **Cookies SameSite por padrão = Ativado**: Se os usuários tiverem a opção &quot;Cookies SameSite por padrão&quot; ativada, como isso afeta você e se há algo que você precisa fazer para [!DNL Target] para continuar a trabalhar.
* **Cookies sem SameSite devem ser seguros = Ativado**: Se os usuários tiverem a opção &quot;Cookies sem SameSite devem ser seguros&quot; ativada, como isso afeta você e se há algo que você precisa fazer para ter [!DNL Target] continue a funcionar.

| Biblioteca JavaScript do Target | Cookies SameSite por padrão = Ativado | Cookies sem SameSite devem ser seguros = Ativado |
| --- | --- | --- |
| at.js 1.*x*  com cookie próprio. | Sem impacto. | Nenhum impacto se você não estiver usando o rastreamento entre domínios. |
| at.js 1.*x*  com o rastreamento entre domínios ativado. | Sem impacto. | Você deve ativar o protocolo HTTPS para seu site.<br>[!DNL Target] O usa um cookie de terceiros para rastrear usuários e o Google requer que os cookies de terceiros tenham `SameSite = None` e Sinalizador Seguro. O sinalizador Seguro exige que seus sites usem o protocolo HTTPS. |
| at.js 2.*x*  | Sem impacto. | Sem impacto. |

## O que [!DNL Target] precisa fazer?

Então, o que precisávamos fazer em nossa plataforma para ajudar você a cumprir as novas políticas de cookies do Google Chrome 80+ SameSite?

| Biblioteca JavaScript do Target | Cookies SameSite por padrão = Ativado | Cookies sem SameSite devem ser seguros = Ativado |
| --- | --- | --- |
| at.js 1.*x*  com cookie próprio. | Sem impacto. | Nenhum impacto se você não estiver usando o rastreamento entre domínios. |
| at.js 1.*x*  com o rastreamento entre domínios ativado. | Sem impacto. | at.js 1.*x*  com o rastreamento entre domínios ativado. |
| at.js 2.*x*  | Sem impacto. | Sem impacto. |

## Qual é o impacto se você não mudar para o uso do protocolo HTTPS?

O único caso de uso que afetará você é se estiver usando o recurso de rastreamento entre domínios no [!DNL Target] por meio da at.js 1.*x*. Sem mudar para HTTPS, que é um requisito do Google, você verá um pico em visitantes únicos em seus domínios, pois o cookie de terceiros que usamos será descartado pelo Google. E como o cookie de terceiros será descartado, [!DNL Target] O não poderá fornecer uma experiência consistente e personalizada para esse usuário enquanto ele navega de um domínio para outro. O cookie de terceiros é usado principalmente para identificar um único usuário que navega nos domínios que você possui.

## Conclusão 

Conforme o setor se esforça para criar uma rede mais segura para os consumidores, [!DNL Adobe] O tem o absoluto compromisso de ajudar nossos clientes a fornecer experiências personalizadas de uma maneira que garanta a segurança e a privacidade para os usuários finais. Tudo o que você precisa fazer é seguir as práticas recomendadas acima e aproveitar [!DNL Target] para estar em conformidade com as novas Políticas de cookies do SameSite do Google Chrome.
