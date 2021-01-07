---
keywords: Targeting;visual experience composer;whitelist;white list;allowlist;allow list;enhanced visual experience composer;vec;troubleshoot visual experience composer;troubleshooting;eec;enhanced experience composer;tls;tls 1.2
description: Às vezes, ocorrem problemas de exibição no Adobe Target Visual Experience Composer (VEC) e no Enhanced Experience Composer (EEC) sob determinadas condições.
title: Solução de problemas relacionados ao Visual Experience Composer e ao Enhanced Experience Composer
feature: Visual Experience Composer (VEC)
translation-type: tm+mt
source-git-commit: 8110807a73e4d6d9848a52224db04faba033c98c
workflow-type: tm+mt
source-wordcount: '1370'
ht-degree: 67%

---


# Solução de problemas relacionados ao Visual Experience Composer e ao Enhanced Experience Composer

Problemas de exibição e outros problemas às vezes ocorrem no [!DNL Adobe Target] Visual Experience Composer (VEC) e no Enhanced Experience Composer (EEC) sob determinadas condições.

## Como as políticas de aplicação de cookies do Google Chrome SameSite, recentemente anunciadas, afetam o VEC e o EEC? {#samesite}

Com as alterações mais recentes (agosto de 2020), todos os usuários com as versões do navegador Chrome 80+:

* *not* poderá usar o VEC (com ou sem a extensão VEC Helper instalada e ativada) em páginas protegidas por senha de seus sites. Isso ocorre porque os cookies de logon do site serão considerados cookies de terceiros e não serão enviados com a solicitação de logon. A única exceção é quando o cookie de logon do site do cliente já tem o parâmetro SameSite definido como &quot;none&quot;.
* *not* poderá baixar as bibliotecas [!DNL Target] ao editar uma atividade (quando elas ainda não estiverem no site). Isso ocorre porque a chamada de download é feita do domínio do cliente para um domínio de Adobe protegido e é rejeitada como não autenticada.
* O EEC funcionará *não* para todos os usuários porque não é possível definir o atributo SameSite para cookies em `adobemc.com domain`. Sem esse atributo, o navegador rejeitará esses cookies, fazendo com que a CEE falhe.

A Adobe enviou uma extensão do VEC Helper atualizada para a Google Chrome Store. Essa extensão substitui os atributos do cookie para definir o atributo `SameSite="none"`, quando necessário. A extensão [atualizada pode ser encontrada aqui](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak?hl=en). Para obter mais informações sobre como instalar e usar a Extensão Auxiliar VEC, consulte [Extensão auxiliar do Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md).

Para seus próprios cookies de site, você deve especificar os cookies por nome. Alterne o controle deslizante [!UICONTROL Cookie] para a posição ligada e especifique o cookie pelo nome e o domínio do cookie. O nome do cookie é &quot;mbox&quot; e o domínio do cookie é o segundo e o mais alto nível dos domínios dos quais você serve a mbox. O cookie é sempre um cookie próprio porque é disponibilizado pelo domínio de sua companhia. Exemplo: `mycompany.com`. Para obter mais informações, consulte [Adobe Target Cookies](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-target.html) no *Guia do Usuário da Interface do Experience Cloud*.

![Os cookies alternam na extensão auxiliar VEC](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

### Alternativas e alternativas

Use uma das seguintes opções para garantir que sua VEC e EEC continuem funcionando como esperado:

* Baixe e use a [extensão do Auxiliar VEC](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak?hl=en) atualizada.
* Use o navegador Mozilla Firefox. O Firefox ainda não está aplicando essa política.
* Continue usando o Chrome, mas defina o sinalizador `chrome://flags/#same-site-by-default-cookies` como &quot;Desativado&quot;.

   >[!NOTE]
   >
   >Isso *não* será suficiente se os cookies já tiverem o atributo SameSite definido como &quot;Lax&quot; ou &quot;Strict&quot; do servidor.

## O Target suporta iframes de vários níveis?

O Target não oferece suporte para iframes de vários níveis. Se o site carregar um iframe que tenha um iframe secundário, as bibliotecas do Target (at.js e mbox.js) vão interagir somente com o iframe principal. As bibliotecas do Target não interagem com o iframe secundário.

Como solução, você pode adicionar uma página na experiência com o URL do iframe secundário.

## Quando eu tento editar uma página, só vejo um ponteiro, em vez da minha página. (VEC e EEC) {#section_313001039F79446DB28C70D932AF5F58}

Isso poderá ocorrer se o URL contiver um caractere #. Para corrigir o problema, alterne para o modo de navegação no Visual Experience Composer e depois alterne de novo para o modo Compor. O ponteiro deverá sumir e a página deverá ser carregada.

## Os cabeçalhos da Política de segurança do conteúdo (CSP) bloqueiam as bibliotecas do Target no meu site. (VEC e EEC) {#section_89A30C7A213D43BFA0822E66B482B803}

Se os cabeçalhos de CSP do seu site bloquearem as Bibliotecas do Target e carregarem o site, mas impedirem a edição, verifique se as bibliotecas do Target não estão bloqueadas.

>[!NOTE]
>
>Além das seguintes informações, você pode usar a extensão de navegador [Adobe Target VEC Helper](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) para Google Chrome.

![](assets/cps_headers.png)

Como solução alternativa, é possível configurar uma regra do Requestly para remover cabeçalhos de CSP, conforme mostrado abaixo:

![](assets/cps_headers_2.png)

É possível configurar uma regra Requestly semelhante para qualquer cabeçalho que faça com que um recurso não seja carregado dentro do VEC.

Para Requestly, sempre que houver a necessidade de remover cabeçalhos, você deve fazer o seguinte:

* Adicione regras de URL ao URL que você deseja abrir no VEC, para que os cabeçalhos sejam removidos apenas para esses URLs.
* Habilite a regra quando estiver editando no VEC e desabilite a regra quando não estiver usando o VEC.

## O VEC ou o EEC aparecem interrompidos ou não inicializam ao editar novamente uma atividade salva. (VEC e EEC) {#section_5AC3BA8F8FBB451EA814F298D0645E54}

Se o site tiver sido alterado fora do Visual Experience Composer após a definição da experiência, os seletores nos quais ações foram executadas antes não poderão ser encontradas quando a atividade for aberta para reedição. A página parece quebrada e nenhum aviso é exibido.

## O VEC ou EEC não exibem meus banners rotativos e outros conteúdos contendo JavaScript. (VEC e EEC) {#section_8B5BE6EB050B42D6A14A054724C41330}

Por padrão, o Visual Experience Composer bloqueia elementos de JavaScript. Você poderá trabalhar com esses elementos se desativar o JavaScript nas configurações do Visual Experience Composer. Dependendo do modo como o site estiver configurado, alguns itens poderão continuar sendo exibidos incorretamente ou permanecer indisponíveis.

## Meu arquivo target.js hospedado falha ao carregar em recarregamentos de páginas subsequentes. (VEC e EEC) {#section_87F6418C2CD142A7B4D1E7037935F81F}

Esse problema ocorre quando os clientes têm uma versão da mbox.js anterior à versão 57 (ou seja, versão 56 ou anterior).

Recomendamos que todos os usuários da sala de aula virtual atualizem para a [versão mais recente do mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A) o pelo menos atualizem para a versão 57. Considere também [fazer a transição para o at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17).

## Quando eu altero um elemento na página, vários elementos são alterados. (VEC e EEC) {#section_309188ACF34942989BE473F63C5710AF}

Se a mesma ID de elemento DOM for usada em vários elementos na página, a alteração desses elementos modificará todos os elementos com essa ID. Para evitar que isso aconteça, uma ID só deverá ser usada uma vez em cada página. Essa é uma prática recomendada de HTML padrão. Para obter mais informações, consulte  [Cenários de modificação da página](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## Não consigo editar experiências para um site do iFrame. (VEC e EEC) {#section_9FE266B964314F2EB75604B4D7047200}

Esse problema pode ser resolvido ativando o Enhanced Experience Composer. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Visual Experience Composer]** e marque a caixa de seleção que ativa o Enhanced Experience Composer. O Enhanced Experience Composer usa um proxy gerenciado pela Adobe para carregar sua página para edição. Isso permite a edição de sites no iFrame e a edição de sites e páginas em que ainda não adicionou código do Adobe Target. As atividades não são entregues ao site antes de o código ser adicionado. Alguns sites talvez não sejam carregados no Enhanced Experience Composer, nesse caso, você poderá desmarcar essa opção para carregar o Visual Experience Composer via um iFrame.   []

>[!NOTE]
>
>As páginas hospedadas localmente ou as páginas que não podem ser acessadas fora da sua rede não podem ser acessadas pelo servidor proxy da Adobe e não podem ser abertas no EEC. Essas páginas podem incluir URLs de preparação, URLs de Teste de aceitação do usuário (UAT) ou páginas hospedadas localmente.

## Quero configurar testes nas páginas que ainda não têm a implementação de mbox/direcionamento. (VEC e EEC) {#section_DE63BCCB5B124E10A71FA579B582A80A}

Consulte &quot;Não consigo editar experiências para um site do iFrame&quot;.

## Os estilos de texto negrito e itálico com Editar texto/HTML ou Alterar texto/HTML não são exibidos na minha página. Às vezes, o texto desaparece após aplicar essas alterações de estilo. (VEC e EEC) {#section_7A71D6DF41084C58B34C18701E8774E5}

Se você usar **[!UICONTROL Editar texto/HTML]** no Visual Experience Composer para atividades A/B ou de Direcionamento de experiência ou **[!UICONTROL Alterar texto/HTML]** para atividades de Personalização automatizada ou Teste multivariado para formatar o texto em negrito ou itálico, esses estilos poderão não ser aplicados na página ou o texto poderá desaparecer da página no Visual Experience Composer. Isso ocorre porque a maneira como o editor de rich text aplica esses estilos pode interferir na marcação do site.

Caso veja esse problema:

1. Clique no botão **[!UICONTROL HTML]** no editor de rich text para entrar no modo de edição de fonte.
1. Encontre os elementos de texto de estilos.

   * Para texto em negrito, altere os elementos `<strong>` para `<b>`.

   * Para texto em itálico, altere os elementos `<em>` para `<i>`.

## Para atividades de Personalização automatizada, a troca de imagem aparece quebrada no VEC ou no EEC. (VEC e EEC) {#section_88AABFDFE6A3420299B0D508B12A3994}

A adição de uma oferta de imagem a um local obtém a dimensão completa do espaço de imagem original no VEC ou no EEC. Na entrega, a imagem não é expandida e é mostrada como está, de modo que não há impacto na entrega.
