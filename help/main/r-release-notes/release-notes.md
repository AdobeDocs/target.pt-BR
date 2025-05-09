---
keywords: notas de versão;novos recursos;versões;atualizações;atualizar;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações,atualizações atuais
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: b1fb49d78b3a159c16e8ebb855ff175c26681da6
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 36%

---

# Notas de versão do [!DNL Target] (atuais)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium]. Além disso, as notas de versão para APIs [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outras alterações de plataforma também estão incluídas, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## [!DNL Target Standard/Premium] 25.5.2 (8 de maio de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* [!DNL Target] usuários com direitos de [!UICONTROL Product Administrator] e [!UICONTROL System Administrator] agora podem editar todas as configurações nas páginas [!UICONTROL Administration], independentemente de sua função no [!DNL Target]. Os usuários sem essas permissões têm acesso somente leitura a essas configurações. Esta atualização garante um controle de acesso mais rigoroso sobre [Configurações de administração](/help/main/administrating-target/administrating-target.md). (TGT-48179)
* Correção de um problema de cache que impedia salvar a atividade [Preferências do site](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#settings). (TGT-52213)
* Correção de um problema em que os clientes não podiam habilitar a seleção por ID e classe na seção [!UICONTROL Site Preferences] após carregar o site no VEC. A configuração [!UICONTROL Site Preferences] foi automaticamente revertida para desabilitada mesmo depois de ser habilitada. (TGT-52207)
* Correção de um problema em que o [!UICONTROL Visual Experience Composer] (VEC) não exibia a página correta quando as URLs de [entrega de página](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#settings) terminavam com uma barra (/). (TGT-52237)
* Correção de um problema que impedia a remoção de modificações de código personalizadas ao alterar experiências. (TGT-52240)
* Correção de um problema em que as modificações do HTML no VEC sobrepunham elementos de página existentes. (TGT-52265)
* Correção de um problema que impedia a edição do código personalizado no VEC atualizado porque o código personalizado existente não estava visível no editor. (TGT-52272)
* Correção de um problema que causava uma mensagem de erro &quot;Nomes duplicados não são permitidos&quot; ao salvar uma atividade do Recommendations. (TGT-52318)
* Correção de um problema no VEC atualizado que impedia os clientes de editar elementos de texto ou remover objetos de contêiner. (TGT-52348)
* Correção de um problema que impedia a exibição correta de [!DNL Customer Journey Analytics] em uma página de atividade [!UICONTROL Overview]. (TGT-52359)
* Correção de um problema que impedia que os grupos de relatórios persistissem nas atividades de [!UICONTROL Automated Personalization] (AP). (TGT-52368)
* Correção de um problema que impedia o salvamento de atividades que incluíam o Offer Decisioning. (TGT-52390)
* Correção de um problema em que a oferta padrão era selecionada, mas o outro conteúdo de oferta era exibido nas atividades [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Multivariate Test] (MVT). (TGT-52372)
* Correção da lógica de permissões do GET para verificar com OU entre o acesso completo à organização e o acesso específico à organização + usuário. (TGT-52374)
* Correção de um problema em que os nomes de público-alvo não eram exibidos após a seleção de um público-alvo para [!UICONTROL Managed Content] e [!UICONTROL Reporting Audiences], mesmo que [!UICONTROL Show Only Selected] estivesse habilitado. (TGT-52393)

## [!DNL Target Standard/Premium] 25.5.1 (5 de maio de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Correção de um problema que impedia que refinamentos de público-alvo fossem exibidos para determinadas atividades na interface atualizada. (TGT-52057)
* Correção de um problema que impedia o uso de públicos-alvo combinados em atividades do. (TGT-52346)
* Correção de um problema que impedia a criação de uma nova atividade em um espaço de trabalho não padrão usando um público somente atividade do mesmo espaço de trabalho. (TGE-52349)
* Correção de um problema que fazia com que os públicos-alvo somente de atividades desaparecessem da interface atualizada após criar e selecionar um novo público-alvo. (TGT=52091)
* Correção de um problema que impedia o uso de públicos-alvo duplicados em atividades do. (TGT-51200 e TGT-52057)
* Correção de um problema que fazia com que refinamentos de público-alvo e públicos-alvo de atividades fossem revertidos na interface do usuário atualizada. (TGT-52158)
* Correção de um problema que impedia a criação de uma nova atividade devido ao erro de entrada do usuário: &quot;espaço de trabalho não padrão não permitido para este usuário&quot;. (TGT-52267)
* Correção de um problema que impedia a exibição de ofertas na interface atualizada para espaços de trabalho padrão e não padrão. [!DNL Target] agora exibe ofertas de ambos os espaços de trabalho. (TGT-52339)
* Correção de um problema em que [!DNL Target] não avisava os clientes ao editar uma atividade e alterar um elemento de site modificado. (TGT-52100)
* Correção de um problema em que a edição de uma oferta com ofertas ad-hoc criava uma nova oferta em vez de atualizar a existente. (TGT-52135)
* Correção de um problema que causava um erro de carga inválida ao mover ofertas para pastas. (TGT-52325)
* Correção de um problema que causava um erro de entrada do usuário ao mover ofertas para pastas. (TGT-52296)
* Adicionado um campo `audienceMetadata` para cada atividade, e verificado se ele é lido e atualizado ao editar a atividade. (TGT-51004)

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da plataforma. |
| [Detalhes da versão da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Alterações na documentação, notas de versão anteriores e notas de versão da Experience Cloud

Além das notas para cada versão, os recursos a seguir oferecem informações adicionais:

| Recurso | Detalhes |
|--- |--- |
| [Alterações de documentação](/help/main/r-release-notes/doc-change.md) | Veja informações detalhadas sobre atualizações neste manual que podem não estar incluídas nas notas de versão. |
| [Notas de versões anteriores](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Veja informações sobre os novos recursos e aprimoramentos das versões anteriores do Target Standard e do Target Premium. |
| [Notas de versão do Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR){target=_blank} | Veja as notas de versão mais recentes das soluções da Adobe Experience Cloud. |

## Informações de pré-lançamento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Os recursos a seguir permitem ver as novidades previstas para a próxima versão do Target.

| Recurso | Detalhes |
|--- |--- |
| [Atualização de produtos prioritários da Adobe](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Receba notificações antecipadas sobre futuros aprimoramentos de produtos para o [!DNL Target] e outras soluções da [!DNL Adobe Experience Cloud]. |
| [Notas de versão do Target - Pré-lançamento](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Informações sobre os lançamentos do Target no mês atual, incluindo informações de pré-lançamento. |
