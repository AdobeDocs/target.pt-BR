---
keywords: google;samesite;cookies;chrome 80;ietf
description: Descubra como a Adobe Target lida com o padrão IETF SameSite introduzido no Google Chrome versão 80 e o que você precisa fazer para seguir essas políticas.
title: Como o Público alvo lida com as políticas de cookies do Samesite do Google?
feature: Privacy & Security
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '2050'
ht-degree: 7%

---


# Políticas de cookies do Google Chrome para SameSite

Por padrão, o Google começará a impor novas políticas de cookies para os usuários a partir do Chrome 80, que será lançado no início de 2020. Este artigo explica tudo o que você precisa saber sobre as novas políticas de cookies do SameSite, como [!DNL Adobe Target] suporta essas políticas e como você pode usar [!DNL Target] para seguir as novas Políticas de cookies do SameSite do Google Chrome.

A partir do Chrome 80, os desenvolvedores da Web devem especificar explicitamente quais cookies podem funcionar em sites. Este é o primeiro de muitos anúncios que o Google pretende fazer para melhorar a privacidade e a segurança na Web.

Dado que o Facebook tem estado no centro das atenções no que diz respeito à privacidade e à segurança, outros atores importantes como a Apple, e agora o Google, têm aproveitado a oportunidade para criar novas identidades como campeões de privacidade e segurança. A Apple liderou o pacote, primeiro anunciando mudanças em suas políticas de cookies no início deste ano por meio do ITP 2.1 e, recentemente, do ITP 2.2. No ITP 2.1, a Apple bloqueia completamente cookies de terceiros e mantém os cookies criados no navegador por apenas sete dias. No ITP 2.2, os cookies são mantidos por apenas um dia. O anúncio do Google não é tão agressivo quanto o da Apple, mas é o primeiro passo para a mesma meta final. Para obter mais informações sobre as políticas da Apple, consulte [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

## O que são cookies e como eles são usados?

Antes de mergulharmos nas mudanças do Google em suas políticas de cookies, vamos tocar no que os cookies são e como eles são usados. Resumindo, os cookies são pequenos arquivos de texto armazenados no navegador da Web que são usados para lembrar os atributos do usuário.

Os cookies são importantes porque aprimoram a experiência do usuário ao navegar na Web. Por exemplo, se você estiver fazendo compras em um site de comércio eletrônico e adicionar algo ao seu carrinho, mas não fizer logon ou compra nessa visita, os cookies lembram de seus itens e os mantêm no carrinho para sua próxima visita. Ou, imagine se você fosse forçado a inserir novamente seu nome de usuário e senha toda vez que visitar seu site favorito de mídia social. Os cookies também resolvem esse problema, pois armazenam informações que ajudam os sites a identificar quem você é. Esses tipos de cookies são chamados de cookies primários porque são criados e usados pelo site visitado.

Cookies de terceiros também existem. Para compreendê-los melhor, considere este exemplo:

Vamos supor que uma empresa hipotética de mídia social chamada &quot;Amigos&quot; fornece um botão Compartilhar que outros sites implementam para permitir que os usuários de Amigos compartilhem o conteúdo do site no feed de Amigos. Agora, um usuário lê um artigo de notícias em um site de notícias que está usando o botão Compartilhar e clica nele para publicar automaticamente em sua conta de amigos.

Para que isso ocorra, o navegador recupera o botão Compartilhar amigos de `platform.friends.com` quando o artigo de notícias é carregado. Nesse processo, o navegador anexa os cookies Amigos, que contêm as credenciais conectadas do usuário, à solicitação aos servidores Amigos. Isso permite que os amigos publiquem o artigo de notícias em seu feed em nome do usuário, sem exigir que o usuário faça logon.

Isso é tudo possível usando cookies de terceiros. Nesse caso, o cookie de terceiros é salvo no navegador para `platform.friends.com`, de modo que `platform.friends.com` possa fazer a publicação no aplicativo Amigos em nome do usuário.

Se você imaginar por um momento como obter esse caso de uso sem cookies de terceiros, o usuário teria que seguir várias etapas manuais. Primeiro, o usuário teria que copiar o link para o artigo de notícias. Em segundo lugar, o usuário precisaria fazer logon no aplicativo Amigos separadamente. Em seguida, o usuário clicaria no botão Criar publicação. Em seguida, o usuário copiava e colava o link no campo de texto e, por fim, clicava em Postar. Como você pode ver, os cookies de terceiros ajudam imensamente o usuário a experimentar, pois as etapas manuais podem ser drasticamente reduzidas.

Em geral, cookies de terceiros permitem que os dados sejam armazenados no navegador de um usuário sem exigir que esse usuário visite explicitamente um site.

## Questões de segurança

Embora os cookies aprimorem as experiências dos usuários e a publicidade de energia, eles também podem apresentar vulnerabilidades de segurança como ataques CSRF (Cross-Site Request Forgery). Por exemplo, se um usuário fizer logon em um site bancário para pagar contas de cartão de crédito e sair do site sem fazer logoff e, em seguida, navegar até um site mal-intencionado na mesma sessão, um ataque do CSRF poderá ocorrer. O site mal-intencionado pode incluir um código que faz uma solicitação ao site bancário que é executado quando a página é carregada. Como o usuário ainda está autenticado no site bancário, o cookie da sessão pode ser usado para iniciar um ataque CSRF para iniciar um evento de transferência de fundos fora da conta bancária do usuário. Isso ocorre porque sempre que você visita um site, todos os cookies são anexados na solicitação HTTP. E por causa dessas preocupações de segurança, o Google está agora tentando atenuá-las.

## Como o Público alvo usa cookies?

Com tudo isso dito, vamos ver como [!DNL Target] usa cookies. Para usar [!DNL Target] em primeiro lugar, é necessário instalar a biblioteca [!DNL Target] JavaScript no seu site. Isso permite que você coloque um cookie primário no navegador do usuário que visita seu site. Conforme o usuário interage com seu site, você pode passar os dados comportamentais e de interesse do usuário para [!DNL Target] pela biblioteca do JavaScript. A biblioteca JavaScript [!DNL Target] usa cookies primários para extrair informações de identificação sobre o usuário a serem mapeadas para o comportamento do usuário e os dados de interesse. Esses dados são usados por [!DNL Target] para potencializar suas atividades de personalização.

O público alvo também (às vezes) usa cookies de terceiros. Se você possui vários sites que vivem em domínios diferentes e deseja rastrear a jornada do usuário nesses sites, você pode usar cookies de terceiros aproveitando o rastreamento entre domínios. Ao ativar o rastreamento entre domínios na biblioteca JavaScript [!DNL Target], sua conta será start usando cookies de terceiros. Quando um usuário salta de um domínio para outro, o navegador se comunica com o servidor backend [!DNL Target] e, nesse processo, um cookie de terceiros é criado e colocado no navegador do usuário. Por meio do cookie de terceiros que reside no navegador do usuário, [!DNL Target] é capaz de fornecer uma experiência consistente em diferentes domínios para um único usuário.

## A nova receita de cookie do Google

Para fornecer proteções sobre quando os cookies são enviados pelos sites para que os usuários estejam protegidos, o Google pretende adicionar suporte para um padrão IETF chamado SameSite, que requer que desenvolvedores da Web gerenciem cookies com o componente de atributo SameSite no cabeçalho Set-Cookie.

Há três valores diferentes que podem ser passados para o atributo SameSite: Strict, Lax ou None.

| Valor | Descrição |
| --- | --- |
| Strict | Os cookies com essa configuração podem ser acessados somente ao visitar o domínio em que foram definidos inicialmente. Em outras palavras, Strict bloqueia rigorosamente o cookie de ser usado entre sites. Essa opção seria melhor para aplicativos que exigem alta segurança, como bancos. |
| Lax | Os cookies com essa configuração são enviados somente em solicitações do mesmo site ou navegação de nível superior com solicitações HTTP não idempotentes, como `HTTP GET`. Portanto, essa opção seria usada se o cookie pudesse ser usado por terceiros, mas com um benefício adicional de segurança que protege os usuários de serem vitimizados por ataques CSRF. |
| None | Os cookies com essa configuração funcionarão da mesma forma que os cookies funcionam hoje. |

Tendo em mente o que precede, o Chrome 80 apresenta duas configurações independentes para os usuários: &quot;SameSite por cookies padrão&quot; e &quot;Cookies sem SameSite devem ser seguros.&quot; Essas configurações serão ativadas por padrão no Chrome 80.

![Caixa de diálogo MesmoSite](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

* **SameSite por cookies** padrão: Quando definido, todos os cookies que não especificam o atributo SameSite serão forçados a usar automaticamente  `SameSite = Lax`.
* **Os cookies sem o SameSite devem ser seguros**: Quando definido, os cookies sem o atributo SameSite ou com  `SameSite = None` necessidade de ser seguro. “Seguros” neste contexto significa que todas as solicitações do navegador devem seguir o protocolo HTTPS. Os cookies que não aderirem a esse requisito serão rejeitados. Todos os sites devem usar HTTPS para atender a esse requisito.

## O Target segue as práticas de segurança recomendadas do Google

Na Adobe, queremos sempre oferecer suporte às práticas recomendadas mais recentes do setor para segurança e privacidade. Temos o prazer de anunciar que [!DNL Target] suporta as novas configurações de segurança e privacidade introduzidas pelo Google.

Para a configuração &quot;SameSite by default cookies&quot;, [!DNL Target] continuará fornecendo personalização sem qualquer impacto e intervenção por você. [!DNL Target]O usa cookies próprios e continuará a funcionar corretamente, pois o sinalizador `SameSite = Lax` é aplicado pelo Google Chrome.

Para a opção &quot;Cookies sem o mesmo site devem ser seguros&quot;, se você não optar pelo recurso de rastreamento entre domínios em [!DNL Target], os cookies primários em [!DNL Target] continuarão funcionando.

No entanto, quando você opta por usar o rastreamento entre domínios para aproveitar [!DNL Target] em vários domínios, o Chrome requer `SameSite = None` e sinalizadores Seguros para serem usados em cookies de terceiros. Isso significa que você deve garantir que seus sites usem o protocolo HTTPS. As bibliotecas do lado do cliente em [!DNL Target] usarão automaticamente o protocolo HTTPS e anexarão os sinalizadores `SameSite = None` e Secure a cookies de terceiros em [!DNL Target] para garantir que todas as atividades continuem a fornecer.

## O que você precisa fazer?

Para entender o que você precisa fazer para que [!DNL Target] continue trabalhando para usuários do Google Chrome 80+, consulte a tabela abaixo, da qual você verá as seguintes colunas:

* **Biblioteca** do JavaScript do público alvo: Se você estiver usando mbox.js, at.js 1.*x* ou a at.js 2.** xon seus sites.
* **SameSite por cookies padrão = Enabled**: Se os usuários tiverem &quot;SameSite by default cookies&quot; ativado, como isso afeta você e há algo que você precisa fazer para continuar  [!DNL Target] a trabalhar.
* **Os cookies sem o SameSite devem ser seguros = Enabled**: Se os usuários tiverem &quot;Cookies sem o mesmoSite devem estar protegidos&quot; ativado, como isso afeta você e há algo que você precisa fazer para  [!DNL Target] continuar trabalhando.

| Biblioteca JavaScript do público alvo | Cookies SameSite por padrão = Ativado | Cookies sem SameSite devem ser seguros = Ativado |
| --- | --- | --- |
| mbox.js somente com cookie primário. | Sem impacto. | Nenhum impacto se você não estiver usando o rastreamento entre domínios. |
| mbox.js com rastreamento entre domínios ativado. | Sem impacto. | Você deve ativar o protocolo HTTPS para o seu site.<br>[!DNL Target] usa um cookie de terceiros para rastrear usuários e o Google requer cookies de terceiros para ter  `SameSite = None` e o sinalizador Proteger. O sinalizador de segurança requer que seus sites usem o protocolo HTTPS. |
| at.js 1.*x*  com cookie próprio. | Sem impacto. | Nenhum impacto se você não estiver usando o rastreamento entre domínios. |
| at.js 1.*x*  com rastreamento entre domínios ativado. | Sem impacto. | Você deve ativar o protocolo HTTPS para o seu site.<br>[!DNL Target] usa um cookie de terceiros para rastrear usuários e o Google requer cookies de terceiros para ter  `SameSite = None` e o sinalizador Proteger. O sinalizador de segurança requer que seus sites usem o protocolo HTTPS. |
| at.js 2.*x*  | Sem impacto. | Sem impacto. |

## O que o Público alvo precisa fazer?

Então, o que precisávamos fazer em nossa plataforma para ajudá-lo a seguir as novas políticas de cookies do Google Chrome 80+ SameSite?

| Biblioteca JavaScript do público alvo | Cookies SameSite por padrão = Ativado | Cookies sem SameSite devem ser seguros = Ativado |
| --- | --- | --- |
| mbox.js somente com cookie primário. | Sem impacto. | Nenhum impacto se você não estiver usando o rastreamento entre domínios. |
| mbox.js com rastreamento entre domínios ativado. | Sem impacto. | [!DNL Target] adiciona  `SameSite = None` e sinalizador Protegido ao cookie de terceiros quando  [!DNL Target] os servidores são chamados. |
| at.js 1.*x*  com cookie próprio. | Sem impacto. | Nenhum impacto se você não estiver usando o rastreamento entre domínios. |
| at.js 1.*x*  com rastreamento entre domínios ativado. | Sem impacto. | at.js 1.*x*  com rastreamento entre domínios ativado. |
| at.js 2.*x*  | Sem impacto. | Sem impacto. |

## Qual é o impacto se você não passar para o protocolo HTTPS?

O único caso de uso que afetará você é se você estiver usando o recurso de rastreamento entre domínios em [!DNL Target] por meio do mbox.js ou do at.js 1.*x*. Sem mudar para HTTPS, que é um requisito do Google, você verá um pico em visitantes únicos em seus domínios, pois o cookie de terceiros que usamos será descartado pelo Google. E como o cookie de terceiros será descartado, [!DNL Target] não poderá fornecer uma experiência consistente e personalizada para esse usuário enquanto ele navega de um domínio para outro. O cookie de terceiros é usado principalmente para identificar um único usuário que navega pelos domínios que você possui.

## Conclusão 

À medida que o setor avança para criar uma Web mais segura para os consumidores, [!DNL Adobe] está absolutamente comprometido em ajudar nossos clientes a fornecer experiências personalizadas de uma maneira que garanta segurança e privacidade para os usuários finais. Tudo o que você precisa fazer é seguir as práticas recomendadas acima e aproveitar as vantagens de [!DNL Target] para estar em conformidade com as novas Políticas de cookies do mesmo site do Google Chrome.
