---
keywords: at.js; 2.0; 1.x; cookies
description: Detalhes sobre como o Adobe [!DNL Target] at.js 2.x e at.js 1.x lidam com cookies
title: Cookies da at.js
feature: at.js
role: Developer
exl-id: 101be093-72fa-4f66-95bd-4b60e584a059
source-git-commit: f028d2b439fee5c2a622748126bb0a34d550a395
workflow-type: tm+mt
source-wordcount: '1828'
ht-degree: 96%

---

# Cookies do at.js

Informações sobre a at.js 2.x e a at.js 1.*x* comportamento de cookie.

## Comportamento de cookie da at.js 2.x

Para a versão 2.0.0 do at.js, *somente os cookies primários são suportados*. Exatamente como no at.js 1.*x*, o cookie próprio, “mbox” é armazenado em `clientdomain.com`, onde `clientdomain` é seu domínio.

O at.js gera uma ID da sessão e a armazena no cookie. A primeira resposta contém informações de atividade, bem como a `TNT` ou`PC ID` gerada pelos [!DNL Target] servidores. O at.js grava o `TNT/PC ID` para o cookie.

O `AMCV_###@AdobeOrg` cookie próprio é sempre definido pelo [!DNL Experience Cloud ID Service], embora o `ECID` seja passado em [!DNL Target] solicitações.

### Não há suporte para cookies de terceiros e rastreamento entre domínios

O rastreamento entre domínios possibilita visualizar sessões em dois sites relacionados, mas com domínios diferentes, como uma única sessão. Você poderia criar [!DNL Target] uma atividade que se expande `siteA.com` e `siteB.com` o visitante permaneceria na mesma experiência ao atravessar domínios. Essa funcionalidade se vincula ao at.js 1.*x* comportamento do cookie próprio e de terceiros.

Em at.js 1.*x*, o cookie de terceiros foi armazenado no `[CLIENTCODE].tt.omtrdc.net` domínio e o cookie próprio foi armazenado em `clientdomain.com`. A primeira solicitação retornava cabeçalhos de resposta HTTP que tentavam definir cookies de terceiros chamados `mboxSession` e `mboxPC`, ao passo que uma solicitação de redirecionamento é enviada de volta com um parâmetro extra (`mboxXDomainCheck=true`). Se o navegador aceitou cookies de terceiros, a solicitação de redirecionamento inclui esses cookies e a oferta foi retornada. Esse fluxo de trabalho era possível porque at.js 1.*x* usado o método HTTP GET.

No entanto, na at.js 2.x, é usado o HTTP POST, em vez do HTTP GET. HTTP POST agora é usado via at.js para enviar cargas JSON para servidores [!DNL Target] de borda em vez de parâmetros de valores-chave. Isso significa que a solicitação de redirecionamento para verificar se um navegador suporta cookies de terceiros agora está rompida. Isso ocorre porque as solicitações HTTP GET são transações idempotentes, enquanto HTTP POST é não idempotente e não deve ser repetido arbitrariamente.

Portanto, não há suporte para cookies de terceiros nem rastreamento entre domínios na at.js 2.0.0.

## at.js 1.*x*  comportamento de cookie {#at-js-1x-cookie-behavior}

Para versões do at.js 1.*x*, o comportamento de cookie depende de se é um cookie próprio, um cookie de terceiros com um cookie próprio ou um cookie de terceiros.

### Quando utilizar cookies próprios ou de terceiros

A configuração do site determina quais cookies você deseja utilizar. É útil saber como o Target funciona ao tentar entender cookies próprios e de terceiros. Consulte [Funcionamento do Adobe Target](/help/c-intro/how-target-works.md) para obter mais informações.

Há três casos de uso principais de cookies:

1. Um domínio.

   Todos os seus testes serão feitos no domínio de primeiro nível (`www.domain.com`, `store.domain.com`, `anysub.domain.com`, etc.).

   Utilize somente cookies próprios. Esse é o padrão.

1. Os usuários navegam entre domínios e você deseja rastrear e testar seu comportamento nesses domínios.

   Exemplo: Um usuário acessa o seu site para efetuar uma compra, mas faz o pagamento utilizando a loja do Yahoo. Três abordagens (consulte seu representante de contas para determinar a melhor abordagem):

   * Habilitar cookies próprios e de terceiros.
   * Habilitar somente cookies de terceiros (muito raro, mas tem a vantagem de manter o cookie do at.js fora de seu domínio).
   * Permitir apenas cookies próprios e enviar o parâmetro `mboxSession` ao atravessar domínios.

      O parâmetro `mboxSession` deve ser enviado para uma página inicial com uma referência ao at.js. Uma página intermediária de redirecionador não pode ser utilizada.

1. Você está utilizando apenas adboxes ou Flashboxes em um site de terceiros.

   Duas abordagens (consulte seu gerente de serviços ao cliente para determinar a melhor abordagem):

   * Habilitar cookies próprios e de terceiros.

      Cookies próprios e de terceiros são necessários para Flashbox e anúncios dinâmicos.

   * Habilitar somente cookies de terceiros.

      Essa abordagem é apenas para casos raros em que as implementações AdBox são usadas sem definição de metas no site.

### Comportamento do cookie próprio

O cookie próprio é armazenado em `clientdomain.com`, onde `clientdomain` é o seu domínio.

O at.js gera um `mboxSession ID` e o armazena no cookie. A primeira resposta contém a oferta, assim como o JavaScript, para armazenar o `mboxPC ID` gerado pelo aplicativo, no cookie.

>[!NOTE]
>
>O `AMCV_###@AdobeOrg` cookie próprio sempre é definido com o [!DNL Experience Cloud Visitor ID].

### Comportamento de cookie de terceiros

O cookie de terceiros é armazenado em `clientcode.tt.omtrdc.net` e o cookie próprio é armazenado em `clientdomain.com`, onde `clientdomain` é o seu domínio.

O at.js gera um `mboxSession ID`. A primeira solicitação de local retorna cabeçalhos HTTP de resposta que tentam instalar cookies de terceiros chamados `mboxSession` e `mboxPC`. Uma solicitação de redirecionamento é enviada de volta com um parâmetro extra (`mboxXDomainCheck=true`).

Se o navegador aceitar cookies de terceiros, a solicitação de redirecionamento vai inclui-los, e a oferta será retornada.

Se o navegador rejeita cookies de terceiros, a solicitação de redirecionamento não vai inclui-los, e o conteúdo padrão será exibido em todos os locais da página. Como não existem cookies definidos, o mesmo processo descrito acima é repetido em cada solicitação de página.

### Comportamento do cookie próprio e de terceiros

O cookie de terceiros é armazenado em `clientcode.tt.omtrdc.net` e o cookie próprio é armazenado em `clientdomain.com`, onde `clientdomain` é o seu domínio.

O at.js gera um `mboxSession ID`. A primeira solicitação de local retorna cabeçalhos HTTP de resposta que tentam instalar cookies de terceiros chamados `mboxSession` e `mboxPC`. Uma solicitação de redirecionamento é enviada de volta com um parâmetro extra (`mboxXDomainCheck=true`).

Se o navegador aceitar cookies de terceiros, a solicitação de redirecionamento vai inclui-los, e a oferta será retornada.

Alguns navegadores rejeitam cookies de terceiros. Se o cookie de terceiros for bloqueado, o cookie próprio ainda funcionará. [!DNL Target]O tenta instalar o cookie de terceiros e, caso não seja possível, [!DNL Target] poderá somente rastrear o domínio específico do cliente. O rastreamento de domínio cruzado não funciona se o terceiro estiver bloqueado, a menos que o `mboxSession` esteja anexado no link que cruza domínios. Nesse caso, outro cookie próprio é instalado e sincronizado com o cookie próprio do domínio anterior.

## Configurações de cookie

O cookie possui várias configurações padrão. Você pode alterar essas configurações, se necessário, exceto a duração do cookie. Entre em contato com seu representante de contas ao modificar as configurações de cookie.

| Configuração | Informações |
|--- |--- |
| Nome do cookie | mbox. |
| Domínio do cookie | Domínio de primeiro e segundo nível a partir de onde o conteúdo será disponibilizado. O cookie é sempre um cookie próprio porque é disponibilizado pelo domínio de sua companhia. Exemplo: `mycompany.com`. |
| Domínio do servidor | `clientcode.tt.omtrdc.net`, utilizando o código de cliente de sua conta. |
| Duração do cookie | O cookie permanece no navegador do visitante por dois anos a partir do último logon.<br>A  `deviceIdLifetime` configuração é substituível na  [at.js versão 2.3.1 ou posterior](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md). Para obter mais informações, consulte [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md). |
| Política P3P | O cookie é publicado com a política P3P, conforme requerido pela configuração padrão na maioria dos navegadores. Uma política P3P indica ao navegador quem está disponibilizando o cookie e como as informações serão utilizadas. |

O cookie mantém uma série de valores para gerenciar a experiência de seus visitantes nas campanhas:

| Valor | Definição |
|--- |--- |
| session ID | ID único para a sessão do usuário. A duração padrão é de 30 minutos. |
| pc ID | Um ID temporário para o navegador do visitante. Dura 14 dias. |
| check | Um simples valor de teste utilizado para determinar se o navegador do visitante tem suporte a cookies. Definido sempre que o usuário solicita uma página. |
| disable | Configurado se o tempo de carga do visitante ultrapassar o tempo limite configurado no arquivo [!DNL Adobe Experience Platform Web SDK] ou at.js. A duração padrão é de uma hora. |

## Impacto em [!DNL Target] para visitantes do Safari devido a alterações no rastreamento do Apple WebKit

Lembre-se do seguinte:

### Como funciona o Rastreamento de Adobe [!DNL Target]?

| Cookies | Detalhes |
|--- |--- |
| Domínios próprios | Esta é a implementação padrão para clientes-alvo. Os cookies &quot;mbox&quot; são definidos no domínio do cliente. |
| Rastreamento de terceiros | O rastreamento de terceiros é importante para anunciar e segmentar casos de uso no Target e no Adobe Audience Manager (AAM).  O rastreamento de terceiros requer técnicas de script entre sites.  O Target usa dois cookies, &quot;mboxSession&quot; e &quot;mboxPC&quot; configurados no domínio `clientcode.tt.omtrd.net`. |

### Qual é a abordagem da Apple?

Da Apple:

&quot;A Intelligent Tracking Prevention é um novo recurso do WebKit que reduz o rastreamento entre sites, limitando ainda mais os cookies e outros dados do site&quot;.

&quot;Isso é chamado de rastreamento entre sites e o cookie usado por `example-tracker.com` é chamado de cookie de terceiros. Em nossos testes, encontramos sites populares com mais de 70 desses rastreadores, todos coletando dados em silêncio sobre os usuários&quot;.

| Abordagem | Detalhes |
|--- |--- |
| Intelligent tracking prevention (Prevenção inteligente de rastreamento) | Para obter mais informações, consulte [Intelligent Tracking Prevention](https://webkit.org/blog/7675/intelligent-tracking-prevention/) no site WebKit Open Source Web Browser Engine. |
| Cookies | Como o Safari gerencia cookies:<ul><li>Cookies de terceiros que não estão em um domínio que o usuário acessa diretamente nunca são salvos. Esse comportamento não é novo. Cookies de terceiros já não são suportados no Safari.</li><li>Cookies de terceiros definidos em um domínio que o usuário acessa diretamente são removidos após 24 horas.</li><li>Os cookies próprios são removidos após 30 dias se o domínio próprio for classificado como rastreamento de usuários em todos os sites. Esse problema pode se aplicar a grandes empresas que enviam usuários para domínios diferentes online. A Apple não deixou claro como exatamente esses domínios serão classificados, ou como um domínio pode determinar se eles foram classificados como usuários de rastreamento entre sites.</li></ul> |
| Aprendizagem de máquina para identificar domínios que estão em todos os sites | Da Apple:<br>Classificador de aprendizagem de máquina: um modelo de aprendizagem de máquina é usado para classificar os principais domínios controlados de forma privada que podem controlar o usuário em todos os sites, com base nas estatísticas coletadas. Das várias estatísticas coletadas, três vetores mostraram forte sinal de classificação com base nas práticas de rastreamento atuais: sub-origem em número de domínios únicos, subestrutura em número de domínios únicos e número de domínios únicos redirecionados. Toda a coleta e classificação de dados acontece no dispositivo.<br>No entanto, se o usuário interagir com example.com como o domínio principal, geralmente chamado de domínio próprio, a Intelligent Tracking Prevention considera um sinal de que o usuário está interessado no site e ajusta temporariamente seu comportamento, conforme demonstrado na linha do tempo:<br>Se o usuário interagiu com example.com as últimas 24 horas, seus cookies estarão disponíveis quando `example.com` for um terceiro. Isso permite cenários de login &quot;Fazer login com minha conta X em Y&quot;.<ul><li>Os domínios visitados como domínio de nível superior não serão afetados. Sites como o OKTA, por exemplo</li><li>Identifica domínios que são subdomínios ou subestruturas da página atual em vários domínios únicos.</li></ul> |

### Como a Adobe será afetada?

| Funcionalidade afetada | Detalhes |
|--- |--- |
| Suporte para cancelamento | As alterações de rastreamento do WebKit da Apple interrompem o suporte ao cancelamento.<br>O cancelamento do Target usa um cookie no domínio `clientcode.tt.omtrdc.net`. Para obter mais detalhes, consulte [Privacidade](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md).<br>O Target suporta dois cancelamentos:<ul><li>Um por cliente (o cliente gerencia o link para opção de não participação).</li><li>Um via Adobe que cancela o usuário em todas as funcionalidades do Target para todos os clientes.</li></ul>Ambos os métodos usam o cookie de terceiros. |
| Atividades do Target | Os clientes podem escolher seus  [ciclo de vida do perfil](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md) para contas Target: até 90 dias. A preocupação é que, se a duração do perfil da conta for superior a 30 dias, e o cookie próprio for limpo porque o domínio do cliente foi marcado como usuários de rastreamento entre sites, o comportamento dos visitantes do Safari será afetado nas seguintes áreas no Target:<br>**Relatórios do Target**: Se um usuário do Safari entrar em uma atividade, retornar após 30 dias e depois se converter, o usuário contará como dois visitantes e uma conversão.<br>Esse comportamento é o mesmo para atividades que usam o Analytics como fonte de geração de relatórios (A4T).<br>**Associação de perfil e atividade**:<ul><li>Dados do perfil são apagados quando o cookie próprio expira.</li><li>Associação de atividade é apagada quando o cookie próprio expira.</li><li> O Target não funciona no Safari para contas que usam uma implementação de cookies de terceiros ou uma implementação de cookies próprios e de terceiros. Observe que esse comportamento não é novo. O Safari não permite cookies de terceiros por algum tempo.</li></ul><br>**Sugestões:** se houver uma preocupação de que o domínio do cliente possa ser marcado como uma sessão cruzada de visitantes de rastreamento, é mais seguro definir a duração do perfil para 30 dias ou menos no Target. Isso garante que os usuários sejam rastreados de forma semelhante no Safari e em todos os outros navegadores. |
