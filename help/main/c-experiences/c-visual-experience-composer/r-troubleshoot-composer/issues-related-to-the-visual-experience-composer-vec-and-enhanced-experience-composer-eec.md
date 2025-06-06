---
keywords: Incluir na lista de permissões Direcionamento;visual experience composer;whitelist;lista branca;de experiência visual aprimorada;lista de permissões;enhanced visual experience composer;vec;solucionar problemas do visual experience composer;solução de problemas;eec;enhanced experience composer;tls;tls 1.2
description: Saiba como solucionar problemas que às vezes ocorrem no  [!DNL Target] [!UICONTROL Visual Experience Composer] (VEC) e no [!UICONTROL Enhanced Experience Composer] (EEC) sob determinadas condições.
title: Como soluciono problemas relacionados ao [!UICONTROL Visual Experience Composer] e ao [!UICONTROL Enhanced Experience Composer]?
feature: Visual Experience Composer (VEC)
exl-id: d829cd63-950f-4bb4-aa58-0247f85de383
source-git-commit: ef5df0ae37ca1d07c0e51c06ed78739b2d2983fc
workflow-type: tm+mt
source-wordcount: '1181'
ht-degree: 26%

---

# Solução de problemas relacionados ao [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] e [!UICONTROL Enhanced Experience Composer]

Problemas de exibição e outros problemas ocorrem às vezes no [!DNL Target] [!UICONTROL Visual Experience Composer] (VEC) e no [!UICONTROL Enhanced Experience Composer] (EEC) sob determinadas condições.

## Como as políticas de imposição de cookie SameSite do Google Chrome afetam o VEC e o EEC? {#samesite}

+++Detalhes
Esteja ciente das alterações que afetam o VEC e o EEC ao usar as seguintes versões do [!DNL Chrome]:

>[!NOTE]
>
>A alteração a seguir afeta todas as três atualizações descritas abaixo:
>
> * *não* poderá usar o VEC sem a [extensão auxiliar do VEC](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) instalada e habilitada para páginas protegidas por senha de seus sites. Os cookies de logon do site são considerados cookies de terceiros e não são enviados com solicitações de logon no editor do VEC no modo [!UICONTROL Browse]. A única exceção ocorre quando os cookies de logon do site já têm os atributos `SameSite=None` e `Secure` definidos.

**Chrome 94 (21 de setembro de 2021)**: com as alterações iminentes planejadas para a versão do Chrome 94 (21 de setembro de 2021), a seguinte alteração afetará todos os usuários com versões do navegador Chrome 94+:

* O sinalizador de linha de comando `--disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure` será removido.

**Chrome 91 (25 de maio de 2021)**: com as alterações implementadas para a versão do Chrome 91 (25 de maio de 2021), a seguinte alteração afetará todos os usuários com versões de navegador do Chrome 91+:

* Os sinalizadores `#same-site-by-default-cookies` e `#cookies-without-same-site-must-be-secure` foram removidos de `chrome://flags`. Esse comportamento agora está ativado por padrão.

**Chrome 80 (agosto de 2020)**: com as alterações implementadas em agosto de 2020, todos os usuários com versões do navegador Chrome 80+:

* *não* poderá baixar bibliotecas [!DNL Target] ao editar uma atividade (quando elas ainda não estiverem no site). Isso ocorre porque a chamada de download é feita do domínio do cliente para um domínio [!DNL Adobe] seguro e é rejeitada como não autenticada.

* O EEC *não* funcionará para todos os usuários porque não é possível definir o atributo SameSite para cookies em `adobemc.com domain`. Sem esse atributo, o navegador rejeita esses cookies, causando falha no EEC.

+++

### Determinar quais cookies estão bloqueados

+++Detalhes
Para determinar quais cookies estão bloqueados devido às políticas de imposição de cookies SameSite, use o [!DNL Developer Tools] em [!DNL Chrome].

1. Para acessar o [!DNL Developer Tools], ao exibir o VEC em [!DNL Chrome], clique no ícone **[!UICONTROL ellipsis]** no canto superior direito do Chrome > **[!UICONTROL More Tools]** > **[!UICONTROL Developer Tools]**.
1. Clique na guia **[!UICONTROL Network]** > e procure por cookies bloqueados.

   >[!NOTE]
   >
   >Use a caixa de seleção **[!UICONTROL Has blocked cookies]** para facilitar a localização de cookies bloqueados.

+++

## O [!DNL Target] suporta iframes de vários níveis?

+++Detalhes
[!DNL Target] não dá suporte a iframes de vários níveis. Se o site carregar um iframe que tenha um iframe secundário, a at.js interagirá somente com o iframe principal. As bibliotecas [!DNL Target] não interagem com o iframe secundário.

Como solução, você pode adicionar uma página na experiência com o URL do iframe secundário.

+++

## Quando eu tento editar uma página, só vejo um ponteiro, em vez da minha página. (VEC e EEC) {#section_313001039F79446DB28C70D932AF5F58}

+++Detalhes
Essa situação pode acontecer se o URL contiver um caractere #. Para corrigir o problema, alterne para o modo [!UICONTROL Browse] no VEC ou no EEC e alterne de volta para o modo [!UICONTROL Compose]. O ponteiro deverá sumir e a página deverá ser carregada.

+++

## Os cabeçalhos da Política de Segurança de Conteúdo (CSP) bloqueiam as bibliotecas do [!DNL Target] no meu site. (VEC e EEC) {#section_89A30C7A213D43BFA0822E66B482B803}


+++Detalhes
Se os cabeçalhos CSP do seu site bloquearem as bibliotecas do [!DNL Target] e carregarem o site, mas impedirem a edição, verifique se as bibliotecas do [!DNL Target] não estão bloqueadas.

>[!NOTE]
>
>Além das seguintes informações, você pode usar a [extensão de navegador Auxiliar do Adobe Target VEC](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) para [!DNL Google Chrome].

![imagem cps_headers](assets/cps_headers.png)

Como solução alternativa, você pode configurar uma regra [!DNL Requestly] para remover cabeçalhos CSP, conforme mostrado abaixo:

![imagem cps_headers_2](assets/cps_headers_2.png)

Você pode configurar uma regra [!DNL Requestly] semelhante para qualquer cabeçalho que faça com que um recurso não seja carregado dentro do VEC.

Para [!DNL Requestly], sempre que houver necessidade de remover cabeçalhos, você deve seguir um destes procedimentos:

* Adicione regras de URL ao URL que você deseja abrir no VEC, para que os cabeçalhos sejam removidos apenas para esses URLs.
* Habilite a regra quando estiver editando no VEC e desabilite a regra quando não estiver usando o VEC.

+++

## O VEC ou o EEC aparecem interrompidos ou não inicializam ao editar novamente uma atividade salva. (VEC e EEC) {#section_5AC3BA8F8FBB451EA814F298D0645E54}

+++Detalhes
Se o site tiver sido alterado fora do VEC após a definição da experiência, os seletores nos quais as ações foram executadas anteriormente não poderão ser encontrados quando a atividade for aberta para reedição. A página parece quebrada e nenhum aviso é exibido.

+++

## O VEC ou EEC não exibem meus banners rotativos e outros conteúdos contendo JavaScript. (VEC e EEC) {#section_8B5BE6EB050B42D6A14A054724C41330}

+++Detalhes
Por padrão, o VEC bloqueia elementos do JavaScript. Você pode trabalhar com esses elementos se desativar o JavaScript. Dependendo do modo como o site estiver configurado, alguns itens poderão continuar sendo exibidos incorretamente ou permanecer indisponíveis.

+++

## Quando eu altero um elemento na página, vários elementos são alterados. (VEC e EEC) {#section_309188ACF34942989BE473F63C5710AF}

+++Detalhes
Se a mesma ID do elemento DOM for usada em vários elementos da página, alterar um desses elementos alterará todos os elementos com essa ID. Para evitar que isso aconteça, uma ID só deverá ser usada uma vez em cada página. Esta é uma prática recomendada padrão do HTML. Para obter mais informações, consulte [Cenários de modificação da página](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

+++

## Não consigo editar experiências para um site do iFrame. (VEC e EEC) {#section_9FE266B964314F2EB75604B4D7047200}

+++Detalhes
Esse problema pode ser resolvido habilitando o [!UICONTROL Enhanced Experience Composer] (EEC). Clique em **[!UICONTROL Administation]** > **[!UICONTROL Visual Experience Composer]** e marque a caixa de seleção que habilita a [!UICONTROL Enhanced Experience Composer]. O EEC usa um proxy gerenciado por [!DNL Adobe] para carregar sua página para edição. Esse proxy permite a edição em sites com interrupção de iFrame e permite a edição em sites e páginas nos quais você ainda não adicionou o código [!DNL Adobe Target]. As atividades não são entregues ao site antes de o código ser adicionado. Alguns sites podem não ser carregados pelo EEC, nesse caso, você poderá desmarcar essa opção para carregar o EEC por meio de um iFrame.

>[!NOTE]
>
>As páginas hospedadas localmente ou as páginas que não podem ser acessadas fora da sua rede não podem ser acessadas pelo servidor proxy [!DNL Adobe] e não podem ser abertas no EEC. Essas páginas podem incluir URLs de preparação, URLs de Teste de aceitação do usuário (UAT) ou páginas hospedadas localmente.

+++

## Quero configurar testes em páginas que ainda não têm a implementação da mbox/[!DNL Target] concluída. (VEC e EEC) {#section_DE63BCCB5B124E10A71FA579B582A80A}

+++Detalhes
Consulte &quot;Não consigo editar experiências para um site de intermitência de iFrame&quot; acima.

+++

## Os estilos de texto em negrito e itálico com [!UICONTROL Edit Text]/[!UICONTROL Edit HTML] ou [!UICONTROL Change Text]/[!DNL Change HTML] não aparecem na minha página. Às vezes, o texto desaparece após aplicar essas alterações de estilo. (VEC e EEC) {#section_7A71D6DF41084C58B34C18701E8774E5}

+++Detalhes
Se você usar o **[!UICONTROL Edit Text]/[!UICONTROL Edit HTML]** no VEC para atividades [!UICONTROL A/B Test] ou [!UICONTROL Experience Targeting] ou **[!UICONTROL Change Text]/[!UICONTROL Change HTML]** para atividades [!UICONTROL Automated Personalization] ou [!UICONTROL Multivariate Test] para formatar o texto em negrito ou itálico, esses estilos poderão não ser aplicados na página ou o texto poderá desaparecer da página no VEC. Isso acontece por causa da forma como o editor de rich text aplica esses estilos pode interferir na marcação do site.

Caso veja esse problema:

1. Clique no botão **[!UICONTROL HTML]** no editor de rich text para entrar no modo de edição de origem.
1. Encontre os elementos de texto de estilos.

   * Para texto em negrito, altere os elementos `<strong>` para `<b>`.

   * Para texto em itálico, altere os elementos `<em>` para `<i>`.

+++

## Para atividades de Personalização automatizada, a troca de imagem aparece quebrada no VEC ou no EEC. (VEC e EEC) {#section_88AABFDFE6A3420299B0D508B12A3994}

+++Detalhes
A adição de uma oferta de imagem a um local utiliza a dimensão completa do espaço da imagem original no VEC ou no EEC. Na entrega, a imagem não é expandida e é mostrada como está, de modo que não há impacto na entrega.

+++
