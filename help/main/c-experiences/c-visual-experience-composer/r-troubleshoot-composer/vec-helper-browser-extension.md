---
keywords: vec;visual experience composer; vec;iframe;extensão;navegador
description: Descubra por que alguns sites podem não abrir de forma confiável no [!UICONTROL Visual Experience Composer] (VEC). A extensão de navegador VEC Helper permite carregar sites de maneira confiável no VEC.
title: Como usar a extensão de ajuda do [!UICONTROL Visual Experience Composer] (VEC)?
feature: Visual Experience Composer (VEC)
exl-id: 3f38db69-046d-42c9-8c09-eca11d404b12
TQID: 'https://experienceleague.adobe.com/lqZGGWG1NVtKDzNGPq5k2bDPzxDfNWqPtJ-bYfLCr3Q'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: e9001ce2-5245-4a8e-8601-dd958009072f
    internal-label: Web experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '1119'
ht-degree: 5%
---
# Extensão auxiliar do [!UICONTROL Visual Experience Composer] {#vec-helper-extension}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba como a extensão de navegador VEC Helper herdada carrega sites no **[!UICONTROL Visual Experience Composer]** (VEC) e como instalá-lo e usá-lo.

>[!ENDSHADEBOX]

A extensão de navegador do [!DNL Adobe Target] **[!UICONTROL Visual Experience Composer]** (VEC) Helper para [!DNL Google Chrome] carrega sites de maneira confiável no VEC, o que torna mais rápido criar e verificar experiências da Web. A extensão não é necessária em [!DNL Mozilla Firefox].

>[!IMPORTANT]
>
>* A extensão auxiliar do VEC [!DNL Target] herdada documentada neste artigo foi criada com Manifest V2. [!DNL Google] anunciou que deixaria de permitir extensões criadas com o Manifest V2 a partir de junho de 2024. Para obter mais informações, consulte o [anúncio da linha do tempo de suporte do Manifest V2](https://developer.chrome.com/docs/extensions/develop/migrate/mv2-deprecation-timeline){target=_blank} de [!DNL Google] no site *Chrome para desenvolvedores*.
>
>* A partir de junho de 2024, o [!DNL Google] desabilitará as extensões criadas com o Manifesto V2, incluindo a extensão documentada neste artigo. A [!DNL Adobe] recomenda mudar para a [extensão Auxiliar de Edição Visual](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) mais recente assim que possível.

## Por que alguns sites não abrem de forma confiável no VEC

Um site pode não abrir de forma confiável no VEC pelos seguintes motivos:

* O site tem políticas de segurança estritas.
* O site está em um iframe.
* A biblioteca do at.js ainda não está implementada no site.
* O site de controle de qualidade ou preparo do cliente é interno e não está disponível fora da rede.
* O site usa o [Service Workers](https://developer.mozilla.org/pt-BR/docs/Web/API/Service_Worker_API){target=_blank} (SW), que o VEC suporta atualmente apenas com limitações. Consulte a seção a seguir.
* O site foi aberto em [!DNL Chrome] 80 ou posterior, o que impõe as políticas de cookies SameSite. Para obter mais informações, consulte [Políticas de cookies do Google Chrome SameSite](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

A extensão de navegador VEC Helper para [!DNL Chrome] resolve os problemas de carregamento de site para os quais os clientes dependem do [!DNL Target] [Enhanced Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) ou de extensões de terceiros, como Requestly.

### Trabalhadores do serviço

Um service worker (SW) é uma tecnologia da Web que uma página da Web instala para interceptar as solicitações de seu domínio. O SW se mantém na visita da página e se ativa em visitas subsequentes. Ele decide quais solicitações são passadas e quais são interceptadas e fornecidas a partir de um cache.

Um SW pode armazenar em cache a própria página da Web, recursos estáticos, como solicitações JS, CSS, IMG e AJAX, seu conteúdo e seus cabeçalhos de resposta. Esses cabeçalhos incluem aqueles que a [extensão auxiliar do VEC do Target](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) tenta remover, como `X-Frame-Options: SAMEORIGIN`, CSP (`Content-Security-Policy`) e `Set-Cookie`.

As APIs de extensão [!DNL Chrome] que interceptam solicitações da Web não recebem as solicitações interceptadas e tratadas por um SW. Quando um SW serve a solicitação da página da Web de um cache, a extensão não pode corrigir os cabeçalhos e os cookies e a página não é carregada dentro do VEC devido aos cabeçalhos em cache `X-Frame-Options` ou CSP.

Como uma possível solução alternativa, desabilite o Service Workers na guia [!DNL Chrome] Ferramentas do Desenvolvedor > **Aplicativo** e, em seguida, habilite a caixa de seleção &quot;Ignorar rede&quot; na seção Service Workers.

## Benefícios da extensão VEC Helper

* **Cabeçalhos de interrupção de Iframe removidos:** a extensão remove implicitamente cabeçalhos como `X-Frame-Options` e `Content-Security-Policy` do site, portanto, nenhuma regra Solicitável complicada é necessária.
* **injeção de at.js:** quando uma página da Web ainda não contém a biblioteca de JavaScript at.js [!DNL Target], a extensão pode inseri-la. As experiências podem ser criadas para o site e as atividades podem ser criadas e verificadas com links de visualização. Com o Enhanced Experience Composer (EEC), a extensão não insere a at.js, mas a funcionalidade de cookie SameSite permanece. Para inserir a at.js na página da Web, desative o EEC.
* **Visores móveis:** [visores móveis](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) são suportados mesmo sem o **[!UICONTROL Enhanced Experience Composer]** (EEC).
* **Novos clientes do [!DNL Target]:** a extensão possibilita experimentar o [!DNL Target] mesmo quando os desenvolvedores de TI ainda não tiverem implementado o [!DNL Target] no site.
* **Parceiros:** parceiros que servem os sites e contas do [!DNL Target] de vários clientes obtêm um mecanismo para oferecer suporte ao carregamento do VEC, no lugar de várias regras em ferramentas de terceiros.

## Obter e instalar a extensão do navegador VEC Helper

A instalação da extensão no [!DNL Chrome] permite carregar sites de maneira confiável no VEC, incluindo sites que bloqueiam iframes ou que ainda não têm o at.js implementado.

1. Vá para a [extensão de navegador do Adobe Target VEC Helper na Chrome Web Store](https://chromewebstore.google.com/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca).
1. Clique em **[!UICONTROL Adicionar ao Chrome]** > **[!UICONTROL Adicionar Extensão]**.
1. Abra o VEC no [!DNL Target].
1. No VEC ou no [Modo de controle de qualidade](/help/main/c-activities/c-activity-qa/activity-qa.md), clique no ícone de extensão de navegador do VEC Helper ( ![ícone do VEC Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png) ) na barra de ferramentas do [!DNL Chrome].
1. (Condicional) Se a página da Web ainda não contiver a biblioteca at.js de JavaScript [!DNL Target], ative a opção **[!UICONTROL Inserir bibliotecas do Target]**.

   A ilustração a seguir mostra o VEC Helper com a configuração **[!UICONTROL Inserir bibliotecas do Target]** ativada:

   O painel de extensão do ![VEC Helper com a opção Inserir bibliotecas do Target ativada e a opção Cookies desativada, mostrando que a configuração Cookies define SameSite=None e sinalizadores Seguros em todos os cookies para solicitações dentro do VEC](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   O VEC Helper pergunta se deve inserir as bibliotecas do [!DNL Target] na página para habilitar a criação:

   ![Insira o prompt Bibliotecas do Target informando que a extensão Auxiliar do VEC do Target deseja inserir bibliotecas do Target na página para habilitar a criação, com os botões Cancelar e Permitir](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. (Condicional) Ative a opção **[!UICONTROL Cookies]** para adicionar a correção de navegador de atributo `SameSite=None` automaticamente.

   ![Painel de extensão do VEC Helper com a opção Cookies ativada e realçada, sobre o Visual Experience Composer mostrando uma página de exemplo](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   Para obter mais informações sobre a correção de navegador do atributo `SameSite=None`, consulte [Políticas de cookie SameSite do Google Chrome](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

## Notas de uso

* O sinalizador **[!UICONTROL Inserir bibliotecas de destino]** na extensão está desativado por padrão. Ative-o para usar o VEC em um site no qual o [!DNL Target] ainda não está implementado.

  O sinalizador é uma configuração global, portanto, está ativado ou desativado para todos os sites abertos no VEC. Por exemplo, com o sinalizador ativado, abrir um site que já tem a at.js implementada exibe uma mensagem de que a at.js já está carregada. O [!DNL Adobe] espera que a maioria dos clientes já tenha o at.js implementado em suas páginas e use a configuração padrão de desativado.

* A extensão carrega a versão mais recente da at.js disponível na interface do usuário do [!DNL Target] em **[!UICONTROL Administração]** > **[!UICONTROL Implementação]**.
* Para usar a extensão para inserir a at.js no [Modo de controle de qualidade](/help/main/c-activities/c-activity-qa/activity-qa.md), outra guia do Chrome deve estar aberta. Esta guia deve ser autenticada na mesma organização [!DNL Adobe Experience Cloud] em que a atividade foi criada.
* O VEC exibe mensagens nos seguintes casos:

  * Falha ao carregar um site no VEC. A mensagem sugere instalar a extensão de navegador VEC Helper.
  * A at.js ainda não está implementada no site. A mensagem sugere instalar a extensão.
  * A extensão é ativada e habilita o carregamento. As mensagens são exibidas quando a extensão injeta a biblioteca at.js, se necessário, ou ajuda a abrir o site de forma confiável no VEC.
