---
keywords: vec;visual experience composer; vec;iframe;extensão;navegador;perguntas frequentes
description: Descubra por que alguns sites podem não abrir de forma confiável no [!UICONTROL Visual Experience Composer] (VEC). A extensão de navegador [!UICONTROL Auxiliar de edição visual] permite carregar sites de maneira confiável no VEC.
title: Como usar a extensão [!UICONTROL Auxiliar de edição visual]?
feature: Visual Experience Composer (VEC)
exl-id: e5aeb8b9-fab5-4ad4-882e-2106d2c9daab
TQID: 'https://experienceleague.adobe.com/wUWUT-FvVIAo52PDaBMfmT7vxv8VOR71hSGhxFvylus'
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
source-wordcount: '829'
ht-degree: 4%
---
# Extensão [!UICONTROL Auxiliar de edição visual] {#visual-editing-helper}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba como a extensão de navegador **[!UICONTROL Auxiliar de edição visual]** carrega sites de maneira confiável no **[!UICONTROL Visual Experience Composer]** (VEC) e como instalá-lo e usá-lo.

>[!ENDSHADEBOX]

A extensão de navegador [!DNL Adobe Experience Cloud] **[!UICONTROL Auxiliar de edição visual]** para [!DNL Google Chrome] carrega sites de maneira confiável no [!DNL Adobe Target] **[!UICONTROL Visual Experience Composer]** (VEC), o que torna mais rápido criar e verificar experiências da web.

>[!IMPORTANT]
>
>Esta extensão substitui a [extensão de navegador Auxiliar do VEC do Target](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) anterior, conforme descrito na observação Importante na parte superior desse artigo. O Manifesto V3 apresenta aprimoramentos de segurança, portanto, o [!DNL Adobe] exige o download dessa nova extensão para continuar criando sites visualmente em [!DNL Target].

## Por que alguns sites não abrem de forma confiável no VEC

Um site pode não abrir de forma confiável no VEC pelos seguintes motivos:

* O site tem políticas de segurança estritas.
* O site está em um iframe.
* O site de controle de qualidade ou preparo do cliente é interno e não está disponível fora da rede.

A extensão soluciona esses problemas de carregamento de site, para os quais os clientes dependem do [Enhanced Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) ou de extensões de terceiros, como Requestly.

## Benefícios da extensão

* **Cabeçalhos de interrupção de Iframe removidos:** a extensão remove implicitamente cabeçalhos como `X-Frame-Options` e `Content-Security-Policy` do site, portanto, nenhuma regra Solicitável complicada é necessária.
* **injeção de at.js:** quando uma página da Web ainda não contém a biblioteca de at.js [!DNL Target], a extensão pode inseri-la. As experiências podem ser criadas para o site e as atividades podem ser criadas e verificadas com links de visualização. Com o [Enhanced Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) (EEC), a extensão não insere a at.js, mas a funcionalidade de cookie SameSite permanece. Para inserir a at.js na página da Web, desative o EEC.
* **Visores móveis:** [visores móveis](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) são suportados mesmo sem o **[!UICONTROL Enhanced Experience Composer]** (EEC).
* **Novos clientes do [!DNL Target]:** a extensão possibilita experimentar o [!DNL Target] mesmo quando os desenvolvedores de TI ainda não tiverem implementado o [!DNL Target] no site.
* **Parceiros:** parceiros que servem os sites e contas do [!DNL Target] de vários clientes obtêm um mecanismo para oferecer suporte ao carregamento do VEC, no lugar de várias regras em ferramentas de terceiros.

## Obter e instalar a extensão

A instalação da extensão no [!DNL Chrome] permite carregar sites de maneira confiável no VEC, incluindo sites que bloqueiam iframes ou que ainda não têm o at.js implementado.

1. Vá para a extensão de navegador [[!DNL Adobe Experience Cloud] **[!UICONTROL Auxiliar de Edição Visual ]**na Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}.
1. Clique em **[!UICONTROL Adicionar ao Chrome]** > **[!UICONTROL Adicionar Extensão]**.
1. Abra o VEC no [!DNL Target].
1. No VEC ou no Modo de controle de qualidade, clique no ícone da extensão de navegador **[!UICONTROL Auxiliar de edição visual]** ( ![ícone Auxiliar de edição visual](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png) ) na barra de ferramentas do [!DNL Chrome].

   A extensão é habilitada automaticamente quando um site é aberto no VEC do [!DNL Target] para habilitar a criação. Ele não tem configurações condicionais e trata todas as configurações automaticamente, incluindo as configurações de cookie SameSite. Para obter mais informações sobre a correção de navegador do atributo `SameSite=None`, consulte [Políticas de cookie SameSite do Google Chrome](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

## Notas de uso

* A extensão carrega a versão mais recente da at.js disponível na interface do usuário do [!DNL Target] em **[!UICONTROL Administração]** > **[!UICONTROL Implementação]**, e a at.js baixa as bibliotecas de criação.
* Para usar a extensão para inserir a at.js no [Modo de controle de qualidade](/help/main/c-activities/c-activity-qa/activity-qa.md), outra guia do Chrome deve estar aberta. Esta guia deve ser autenticada na mesma organização [!DNL Adobe Experience Cloud] em que a atividade foi criada.
* O VEC exibe mensagens que sugerem a instalação da extensão nos seguintes casos:

  * Falha ao carregar um site no VEC.
  * A at.js ou alloy.js ainda não está implementada no site.

* Se a nova extensão tiver sido tentada e a [extensão antiga](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) for usada novamente, mas o [!DNL Target] não carregar o site, apague todos os dados do navegador e desabilite a nova extensão.

## Últimas alterações na extensão do (17 de janeiro de 2026)

A extensão adiciona um recurso experimental de limpeza de cookie de inicialização ao VEC Helper. O recurso limpa cookies não particionados uma vez por guia ao iniciar a criação, em vez de continuamente, o que melhora o desempenho e a confiabilidade. Ele rastreia o histórico de cada guia para evitar limpeza redundante e limpa esse histórico quando a guia é fechada, de modo que a limpeza se comporta corretamente quando a guia é reaberta. Testes de unidade garantem comportamento consistente.

![Opções da extensão VEC Helper, incluindo os modos de processamento de cookies, a opção de log avançada e os recursos experimentais Atrasar carregamento da página da Web, Limpeza de cookies e Limpeza de cookies de inicialização](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper.png)

## Perguntas frequentes

+++ A extensão faz algo quando é usada fora do [!DNL Adobe Target] ou do [!UICONTROL Adobe Journey Optimizer] (AJO)?

A extensão é ativada somente quando o site é carregado dentro de um iFrame em [!DNL Adobe] produtos ([!DNL Target], [!DNL AJO]). Fora desse fluxo, a extensão não tenta adicionar, remover ou modificar nenhum cabeçalho e não tenta inserir nenhum código dentro do site.

+++

+++ O que a extensão faz quando está ativa no VEC do [!DNL Adobe Target]?

Quando um site é carregado dentro de um iFrame em [!DNL Adobe] produtos ([!DNL Target], [!DNL AJO]), a extensão injeta código que é fornecido com a extensão no site e baixa arquivos auxiliares da CDN [!DNL Adobe] para habilitar a criação visual.

+++
