---
keywords: Visão geral e referência; webkit; cookies; originais; terceiros; próprios; terceiros
description: Saiba mais sobre o comportamento do cookie [!DNL Target] cookie (cookie próprio, cookie de terceiros com cookie próprio ou cookie de terceiros sozinho).
title: 'Onde posso encontrar informações sobre os cookies? [!DNL Target] '
feature: at.js
role: Developer
exl-id: 1c4e5b0b-8ae4-4526-aea0-318a33f4d247
source-git-commit: e773db20ac593108aa3e54aae1bcb2c0f713e387
workflow-type: tm+mt
source-wordcount: '1542'
ht-degree: 58%

---

# Cookies do Target

O comportamento de cookies depende do tipo do cookie, podendo ser um cookie próprio, um cookie de terceiros com um cookie próprio ou somente um cookie de terceiros.

>[!NOTE]
>
>Este tópico contém informações sobre `mboxSession` e `mboxPC`. As práticas recomendadas de implementação recomendam que você não vincule nem armazene informações confidenciais com os dados do cookie: `mboxSession` ou `mboxPC`.

Consulte também [Excluir o cookie do Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cookie-deleting.md).

## Quando utilizar cookies próprios ou de terceiros {#section_F71B29420C004A7FA3B1921E619B326E}

A configuração do site determina quais cookies você deseja utilizar. É útil entender como o [!DNL Target] funciona ao tentar entender cookies próprios e de terceiros. Consulte [Como [!DNL Adobe Target] Funciona](/help/c-intro/how-target-works.md#concept_459AB4DEE7364A9290C2FD405DC29584) para obter mais informações.

Há três casos de uso principais de cookies:

1. Um domínio.

   Todos os seus testes ocorrem dentro de um domínio de nível superior (`www.domain.com`, `store.domain.com`, `anysub.domain.com`, e assim por diante).

   Abordagem: Use somente cookies próprios (o padrão).

1. Os usuários navegam entre domínios e você deseja rastrear e testar seu comportamento nesses domínios.

   Exemplo: Um usuário acessa o seu site para efetuar uma compra, mas faz o pagamento utilizando a loja do Yahoo. Três abordagens (consulte seu representante de contas para determinar a melhor abordagem):

   * Habilitar cookies próprios e de terceiros.
   * Habilitar somente cookies de terceiros (raro, mas tem a vantagem de manter o cookie da mbox fora de seu domínio).
   * Permitir apenas cookies próprios e enviar o parâmetro `mboxSession` ao atravessar domínios.

      O parâmetro `mboxSession` deve ser passado para uma página de aterrissagem e referenciado da biblioteca de JavaScript (Adobe Experience Platform Web SDK ou at.js). Uma página intermediária de redirecionador não pode ser utilizada.

1. Você somente está utilizando adboxes ou Flashboxes em um site de terceiros.

   Duas abordagens (consulte seu representante de conta para determinar a melhor abordagem):

   * Habilitar cookies próprios e de terceiros.

      Cookies próprios e de terceiros são requeridos pelo Flashbox e anúncios dinâmicos.

   * Habilitar somente cookies de terceiros.

      Essa abordagem é apenas para casos raros em que as implementações AdBox são usadas sem definição de metas no site.

## Comportamento do cookie próprio {#section_CE6313D979EA4D0897D2F661E7A8AFA7}

O cookie próprio é armazenado em [!DNL clientdomain.com], onde `clientdomain` é o seu domínio.

A biblioteca do JavaScript gera um `mboxSession ID` e a armazena no cookie [!DNL Target]. A primeira resposta de mbox contém a oferta e o JavaScript armazena o `mboxPC ID` gerado pelo aplicativo, no cookie da mbox.

>[!NOTE]
>
>O [!DNL AMCV_###@AdobeOrg] cookie próprio sempre é definido com o [!DNL Experience Cloud Visitor ID].

## Comportamento do cookie de terceiros {#section_4C3A83990BF8415BB1806602D84AED48}

O cookie de terceiros é armazenado em [!DNL clientcode.tt.omtrdc.net] e o cookie próprio é armazenado em [!DNL clientdomain.com], onde `clientdomain` é o seu domínio.

A biblioteca do JavaScript gera um `mboxSession ID`. A primeira solicitação de local retorna cabeçalhos HTTP de resposta que tentam instalar cookies de terceiros chamados `mboxSession` e `mboxPC`. Uma solicitação de redirecionamento é enviada de volta com um parâmetro extra (`mboxXDomainCheck=true`).

Se o navegador aceitar cookies de terceiros, a solicitação de redirecionamento vai inclui-los, e a oferta será retornada.

Se o navegador rejeita cookies de terceiros, a solicitação de redirecionamento não vai inclui-los, e o conteúdo padrão será exibido em todos os locais da página. Como não existem cookies definidos, o mesmo processo descrito acima é repetido em cada solicitação de página.

>[!NOTE]
>
>O [!DNL demdex.net]cookie será configurado se os cookies de terceiros não estiverem bloqueados.

## Comportamento do cookie próprio e de terceiros {#section_F0C9AD8BFDF8457A999C4A07A0F7A981}

O cookie de terceiros é armazenado em [!DNL clientcode.tt.omtrdc.net] e o cookie próprio é armazenado em [!DNL clientdomain.com], onde `clientdomain` é o seu domínio.

A biblioteca do JavaScript gera um `mboxSession ID`. A primeira solicitação de local retorna cabeçalhos HTTP de resposta que tentam instalar cookies de terceiros chamados `mboxSession` e `mboxPC`. Uma solicitação de redirecionamento é enviada de volta com um parâmetro extra (`mboxXDomainCheck=true`).

Se o navegador aceitar cookies de terceiros, a solicitação de redirecionamento vai inclui-los, e a oferta será retornada.

Alguns navegadores rejeitam cookies de terceiros. Se o cookie de terceiros for bloqueado, o cookie próprio ainda funcionará. [!DNL Target]O tenta instalar o cookie de terceiros e, caso não seja possível, [!DNL Target] poderá somente rastrear o domínio específico do cliente. O rastreamento entre domínios não funciona se o cookie de terceiros estiver bloqueado, a menos que `mboxSession` esteja anexado no link que cruza domínios. Nesse caso, outro cookie próprio é instalado e sincronizado com o cookie próprio do domínio anterior.

## Configurações de cookie {#section_B498B8D1A34A444BBF84CC720EE9D87F}

O cookie possui várias configurações padrão. É possível alterar essas configurações, se necessário, exceto pela duração do cookie. Entre em contato com seu representante de contas ao modificar as configurações de cookie.

| Configuração | Informações |
|--- |--- |
| Nome do cookie | mbox. |
| Domínio do cookie | Domínio de primeiro e segundo nível a partir de onde o conteúdo será disponibilizado. Como ele é disponibilizado pelo domínio de sua empresa, o cookie é um cookie próprio.<br>Exemplo: `mycompany.com`. |
| Domínio do servidor | `clientcode.tt.omtrdc.net`, utilizando o código de cliente de sua conta. |
| Duração do cookie | O cookie permanece no navegador do visitante por duas semanas a partir do último logon. Não é possível alterar a duração do cookie. |
| Política P3P | O cookie é publicado com a política P3P, conforme requerido pela configuração padrão na maioria dos navegadores. Uma política P3P indica a um navegador quem está disponibilizando o cookie e como as informações são usadas. |

O cookie mantém vários valores para gerenciar a experiência de seus visitantes nas campanhas:

| Valor | Definição |
|--- |--- |
| session ID | ID único para a sessão do usuário. Por padrão, essa ID dura 30 minutos. |
| pc ID | Um ID temporário para o navegador do visitante. Dura 14 dias. |
| check | Um simples valor de teste utilizado para determinar se o navegador do visitante tem suporte a cookies. Definido sempre que o usuário solicita uma página. |
| disable | Configurado se o tempo de carga do visitante ultrapassar o tempo limite configurado no arquivo da biblioteca JavaScript. Por padrão, esse valor dura uma hora. |

## Impacto em [!DNL Target] para visitantes do Safari devido a alterações no rastreamento do Apple WebKit {#section_2A2E5730ED7D4A0985C904AFEA310AAE}

**Como funciona o  [!DNL Adobe Target] rastreamento?**

| Cookies | Detalhes |
|--- |--- |
| Domínios próprios | A implementação padrão para clientes [!DNL Target]. Os cookies &quot;mbox&quot; são definidos no domínio do cliente. |
| Rastreamento de terceiros | O rastreamento de terceiros é importante para anunciar e direcionar casos de uso em [!DNL Target] e em [!DNL Adobe Audience Manager] (AAM). O rastreamento de terceiros requer técnicas de script entre sites. [!DNL Target]O usa dois cookies, &quot;mboxSession&quot; e &quot;mboxPC&quot; configurados no domínio `clientcode.tt.omtrd.net`. |
**Qual é a abordagem da Apple?**

Da Apple:

&quot;A Intelligent Tracking Prevention é um novo recurso do WebKit que reduz o rastreamento entre sites, limitando ainda mais os cookies e outros dados do site&quot;.

&quot;Isso é chamado de rastreamento entre sites e o cookie usado por `example-tracker.com` é chamado de cookie de terceiros. Em nossos testes, encontramos sites populares com mais de 70 desses rastreadores, todos coletando dados em silêncio sobre os usuários&quot;.

| Abordagem | Detalhes |
|--- |--- |
| Intelligent tracking prevention (Prevenção inteligente de rastreamento) | Para obter mais informações, consulte [Intelligent Tracking Prevention](https://webkit.org/blog/7675/intelligent-tracking-prevention/) no site WebKit Open Source Web Browser Engine. |
| Cookies | Como o Safari gerencia cookies:<ul><li>Cookies de terceiros que não estão em um domínio que o usuário acessa diretamente nunca são salvos. Esse comportamento não é novo. Cookies de terceiros já não são suportados no Safari.</li><li>Cookies de terceiros definidos em um domínio que o usuário acessa diretamente são removidos após 24 horas.</li><li>Os cookies próprios são removidos após 30 dias se o domínio próprio for classificado como rastreamento de usuários em todos os sites. Esse problema pode se aplicar a grandes empresas que enviam usuários para domínios diferentes online. A Apple não deixou claro como exatamente esses domínios são classificados, ou como um domínio pode determinar se eles foram classificados como usuários de rastreamento entre sites.</li></ul> |
| Aprendizagem de máquina para identificar domínios que estão em todos os sites | Da Apple:<br>Classificador de Aprendizagem de Máquina: Um modelo de aprendizado de máquina é usado para classificar os principais domínios controlados de forma privada que podem rastrear o usuário em todos os sites, com base nas estatísticas coletadas. Das várias estatísticas coletadas, três vetores mostraram forte sinal de classificação com base nas práticas de rastreamento atuais: sub-origem em número de domínios únicos, subestrutura em número de domínios únicos e número de domínios únicos redirecionados. Toda a coleta e classificação de dados acontece no dispositivo.<br>No entanto, se o usuário interagir com o  `example.com` como o domínio principal, geralmente chamado de domínio próprio, a Intelligent Tracking Prevention considera um sinal de que o usuário está interessado no site e ajusta temporariamente seu comportamento, conforme descrito nesta linha do tempo:<br>Se o usuário interagiu com  `example.com` as últimas 24 horas, seus cookies estarão disponíveis quando  `example.com` for um terceiro. Essa prática permite cenários de login &quot;Fazer logon com minha conta X em Y&quot;.<ul><li>Os domínios visitados como domínio de nível superior não são afetados. Sites como o OKTA, por exemplo</li><li>Identifica domínios que são subdomínios ou subestruturas da página atual em vários domínios únicos.</li></ul> |

**Como o Adobe é afetado?**

| Funcionalidade afetada | Detalhes |
|--- |--- |
| Suporte para cancelamento | As alterações de rastreamento do WebKit da Apple interrompem o suporte ao cancelamento.<br>[!DNL Target]O cancelamento do usa um cookie no domínio `clientcode.tt.omtrdc.net`. Para obter mais detalhes, consulte [Privacidade](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md).<br>[!DNL Target] O suporta dois cancelamentos:<ul><li>Um por cliente (o cliente gerencia o link para opção de não participação).</li><li>Um via [!DNL Adobe] que recusa o usuário de toda a funcionalidade [!DNL Target] para todos os clientes.</li></ul>Ambos os métodos usam o cookie de terceiros. |
| [!DNL Target] atividades | Os clientes podem escolher sua [duração do perfil](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md) para suas contas [!DNL Target] (até 90 dias). A preocupação é que, se a duração do perfil da conta for superior a 30 dias e o cookie próprio for removido, pois o domínio do cliente foi marcado como rastreamento de usuários entre sites, o comportamento dos visitantes do Safari será afetado nas seguintes áreas em [!DNL Target]:<br>**[!DNL Target] reports **: Se um usuário do Safari entrar em uma atividade, retornar após 30 dias e, em seguida, converter, esse usuário contará como dois visitantes e uma conversão.<br>[!DNL Analytics]Esse comportamento é o mesmo para atividades que usam o como fonte de geração de relatórios (A4T).<br>** Associação **de perfil e atividade:<ul><li>Dados do perfil são apagados quando o cookie próprio expira.</li><li>Associação de atividade é apagada quando o cookie próprio expira.</li><li> [!DNL Target]O não funciona no Safari para contas que usam uma implementação de cookies de terceiros ou uma implementação de cookies próprios e de terceiros. Esse comportamento não é novo. O Safari não permite cookies de terceiros por algum tempo.</li></ul><br>**Sugestões**: Se houver uma preocupação de que o domínio do cliente possa ser marcado como uma sessão cruzada de visitantes de rastreamento, é mais seguro definir a duração do perfil para 30 dias ou menos no  [!DNL Target]. Esse limite garante que os usuários sejam rastreados de forma semelhante no Safari e em todos os outros navegadores. |
