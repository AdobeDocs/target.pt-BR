---
keywords: Direcionamento, visual experience composer, lista branca, lista de permissões, lista de permissões, lista de permissões, enhanced visual experience composer, vec, solucionar problemas do visual experience composer, solução de problemas, eec, enhanced experience composer, tls, tls 1.2
description: Saiba como solucionar problemas que às vezes ocorrem no Adobe [!DNL Target] Visual Experience Composer (VEC) e o Enhanced Experience Composer (EEC) sob determinadas condições.
title: Como soluciono problemas relacionados ao Visual Experience Composer e ao Enhanced Experience Composer?
feature: Visual Experience Composer (VEC)
exl-id: d829cd63-950f-4bb4-aa58-0247f85de383
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1421'
ht-degree: 52%

---

# Solução de problemas relacionados ao Visual Experience Composer e ao Enhanced Experience Composer

Problemas de exibição e outros problemas às vezes ocorrem na [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) e a [!UICONTROL Enhanced Experience Composer] (CEE) em determinadas condições.

## Como as políticas de imposição de cookie SameSite do Google Chrome afetam o VEC e o EEC? {#samesite}

Esteja ciente das alterações que afetam o VEC e o EEC ao usar as seguintes versões do Chrome:

>[!NOTE]
>
>A seguinte alteração afeta todas as três atualizações descritas abaixo:
>
> * Will *not* ser capaz de usar o VEC sem a extensão VEC Helper instalada e ativada para páginas protegidas por senha de seus sites. Os cookies de logon do site são considerados cookies de terceiros e não são enviados com solicitações de logon dentro do editor de VEC no modo Procurar. A única exceção é quando os cookies de logon do site já têm a variável `SameSite=None` e `Secure` conjunto de atributos.


**Chrome 94 (21 de setembro de 2021)**: Com as alterações iminentes planejadas para a versão do Chrome 94 (21 de setembro de 2021), a seguinte alteração afeta todos os usuários com as versões do navegador Chrome 94+:

* O sinalizador de linha de comando `--disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure` serão removidas.

**Chrome 91 (25 de maio de 2021)**: Com as alterações implementadas para a versão do Chrome 91 (25 de maio de 2021), a seguinte alteração afeta todos os usuários com as versões do navegador Chrome 91+:

* Os sinalizadores `#same-site-by-default-cookies` e `#cookies-without-same-site-must-be-secure` foram removidas de `chrome://flags`. Esse comportamento agora é ativado por padrão.

**Chrome 80 (agosto de 2020)**: Com as alterações implementadas em agosto de 2020, todos os usuários com as versões do navegador Chrome 80+:

* Will *not* ser capaz de baixar [!DNL Target] bibliotecas ao editar uma atividade (quando elas ainda não estiverem no site). Isso ocorre porque a chamada de download é feita do domínio do cliente para um [!DNL Adobe] e é rejeitado como não autenticado.
* A CEE *not* para todos os usuários, pois não é possível definir o atributo SameSite para cookies em `adobemc.com domain`. Sem esse atributo, o navegador rejeita esses cookies, causando a falha do EEC.

### Determine quais cookies estão bloqueados

Para determinar quais cookies estão bloqueados por causa das políticas de imposição de cookies do SameSite, use as Ferramentas do desenvolvedor no Chrome.

1. Para acessar as Ferramentas do desenvolvedor, enquanto exibe o VEC no Chrome, clique no link **[!UICONTROL elipse]** ícone no canto superior direito do Chrome > **[!UICONTROL Mais ferramentas]** > **[!UICONTROL Ferramentas do desenvolvedor]**.
1. Clique no botão **[!UICONTROL Rede]** guia > em seguida, procure cookies bloqueados.

   >[!NOTE]
   >
   >Use o **[!UICONTROL Bloqueou cookies]** caixa de seleção para facilitar a localização de cookies bloqueados.

   A ilustração a seguir mostra um cookie bloqueado:

   ![Ferramentas do desenvolvedor > Guia Rede mostrando um cookie bloqueado](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/chrome-developer-tools.png)

### [!DNL Adobe Target] Extensão do VEC Helper

A partir da versão 0.7.1, a variável [!DNL Adobe Target] A extensão do navegador VEC Helper adiciona a variável `SameSite=None` e `Secure` atributos para todos os cookies em respostas de páginas da Web editadas no VEC quando a opção &quot;Cookies&quot; estiver ativada na interface do usuário da extensão:

![Extensão do Adobe Target VEC Helper UIAnterface do Adobe Target VEC Helper UI](assets/cookies-vec-helper.png)

### Alternativas e soluções alternativas

Use uma das seguintes opções para garantir que seu VEC e EEC continuem a funcionar conforme esperado:

* Baixe e use o arquivo atualizado [Extensão do VEC Helper](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak?hl=en).
* Use o navegador Mozilla Firefox. O Firefox ainda não está aplicando essa política.
* Use os seguintes sinalizadores para executar o Google Chrome a partir da linha de comando até 21 de setembro de 2021. Após 21 de setembro, os recursos que exigem cookies não funcionarão mais no VEC, como pop-ups de logon ou de consentimento de cookies. Se você atualizar para o Chrome 94, deverá gerar cookies manualmente com `SameSite=none` e `Secure` em seus sites.

   ```
   --disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure
   ```

## Does [!DNL Target] suporta iframes de vários níveis?

[!DNL Target]O não oferece suporte para iframes de vários níveis. Se o site carregar um iframe que tenha um iframe secundário, a at.js interage somente com o iframe principal. [!DNL Target]As bibliotecas do não interagem com o iframe secundário.

Como solução, você pode adicionar uma página na experiência com o URL do iframe secundário.

## Quando eu tento editar uma página, só vejo um ponteiro, em vez da minha página. (VEC e EEC) {#section_313001039F79446DB28C70D932AF5F58}

Essa situação pode ocorrer se o URL contiver um caractere #. Para corrigir o problema, alterne para o modo de navegação no Visual Experience Composer e depois alterne de novo para o modo Compor. O ponteiro deverá sumir e a página deverá ser carregada.

## Os cabeçalhos da Política de segurança de conteúdo (CSP) bloqueiam o [!DNL Target] bibliotecas no meu site. (VEC e EEC) {#section_89A30C7A213D43BFA0822E66B482B803}

Se os cabeçalhos de CSP do seu site bloquearem as Bibliotecas do Target e carregarem o site, mas impedirem a edição, verifique se as bibliotecas do Target não estão bloqueadas.

>[!NOTE]
>
>Além das seguintes informações, você pode usar a extensão de navegador [Adobe Target VEC Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) para Google Chrome.

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

## Quando eu altero um elemento na página, vários elementos são alterados. (VEC e EEC) {#section_309188ACF34942989BE473F63C5710AF}

Se a mesma ID de elemento DOM for usada em vários elementos na página, a alteração desses elementos modificará todos os elementos com essa ID. Para evitar que isso aconteça, uma ID só deverá ser usada uma vez em cada página. Essa prática é uma prática recomendada de HTML. Para obter mais informações, consulte [Cenários de modificação da página](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## Não consigo editar experiências para um site do iFrame. (VEC e EEC) {#section_9FE266B964314F2EB75604B4D7047200}

Esse problema pode ser resolvido ativando o Enhanced Experience Composer. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Visual Experience Composer]**, marque a caixa de seleção que ativa o Enhanced Experience Composer. O Enhanced Experience Composer usa um proxy gerenciado pela Adobe para carregar sua página para edição. Esse proxy permite a edição em sites do iFrame e permite a edição em sites e páginas em que você ainda não adicionou o código do Adobe Target. As atividades não são entregues ao site antes de o código ser adicionado. Alguns sites talvez não sejam carregados no Enhanced Experience Composer, nesse caso, você poderá desmarcar essa opção para carregar o Visual Experience Composer via um iFrame. 

>[!NOTE]
>
>As páginas hospedadas localmente ou as páginas que não podem ser acessadas fora da sua rede não podem ser acessadas pelo servidor proxy da Adobe e não podem ser abertas no EEC. Essas páginas podem incluir URLs de preparação, URLs de Teste de aceitação do usuário (UAT) ou páginas hospedadas localmente.

## Quero configurar testes nas páginas que ainda não têm a implementação de mbox/direcionamento. (VEC e EEC) {#section_DE63BCCB5B124E10A71FA579B582A80A}

Consulte &quot;Não consigo editar experiências para um site do iFrame&quot;.

## Os estilos de texto negrito e itálico com Editar texto/HTML ou Alterar texto/HTML não são exibidos na minha página. Às vezes, o texto desaparece após aplicar essas alterações de estilo. (VEC e EEC) {#section_7A71D6DF41084C58B34C18701E8774E5}

Se você usar **[!UICONTROL Editar texto/HTML]** no Visual Experience Composer para atividades A/B ou de Direcionamento de experiência ou **[!UICONTROL Alterar texto/HTML]** para atividades de Personalização automatizada ou Teste multivariado para formatar o texto em negrito ou itálico, esses estilos poderão não ser aplicados na página ou o texto poderá desaparecer da página no Visual Experience Composer. Isso acontece devido à maneira como o editor de rich text aplica esses estilos, que pode interferir na marcação do site.

Caso veja esse problema:

1. Clique no botão **[!UICONTROL HTML]** no editor de rich text para entrar no modo de edição de fonte.
1. Encontre os elementos de texto de estilos.

   * Para texto em negrito, altere os elementos `<strong>` para `<b>`.

   * Para texto em itálico, altere os elementos `<em>` para `<i>`.

## Para atividades de Personalização automatizada, a troca de imagem aparece quebrada no VEC ou no EEC. (VEC e EEC) {#section_88AABFDFE6A3420299B0D508B12A3994}

A adição de uma oferta de imagem a um local obtém a dimensão completa do espaço de imagem original no VEC ou no EEC. Na entrega, a imagem não é expandida e é mostrada como está, de modo que não há impacto na entrega.
