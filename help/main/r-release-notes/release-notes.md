---
keywords: notas de versão;novos recursos;versões;atualizações;atualizar;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações;atualizações atuais;release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates;current updates
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 7976d43e43baeabdb68509373f1b0b72bbe723b3
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 49%

---

# Notas de versão do [!DNL Target] (atuais)

Explore os recursos, aprimoramentos e correções mais recentes no [!DNL Adobe Target]. Essas notas de versão também abrangem atualizações para APIs do [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outros componentes da plataforma, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## Atualizações sensíveis ao tempo que você precisa saber {#time-sensitive}

[!BADGE Importante]{type=Informative}

Para atualizações com limite de tempo relacionadas ao [!DNL Adobe Target] e à sua implementação, o [!DNL Adobe] fornece notas de versão detalhadas e documentação até [!UICONTROL Experience League]. Estes são alguns destaques importantes para sua implementação:

### Desativação da alternância de versão da interface do usuário [!DNL Target]

Para obter mais informações, consulte [[!DNL Target] Perguntas frequentes sobre atualização da interface](/help/main/c-intro/updated-ui-faq.md).

## [!DNL Target Standard/Premium] 26.4.4 (28 de abril de 2026)

**Atividades**

+++Ver detalhes

* **Erro com o filtro de Público-alvo nos Relatórios.** Correção de um problema em que a alteração do filtro de público-alvo em **[!UICONTROL Goals & Settings]** causava um erro na seção Relatório da interface do usuário [!DNL Target]. (TGT-55006)

* **Classificar atividades por prioridade.** Foi adicionada a classificação por prioridade na lista de atividades usando o cabeçalho da coluna **[!UICONTROL Priority]**, com ordem crescente e decrescente consistente com outras colunas classificáveis. (TGT-54948)

* **Propriedades de atividade adicionais não retidas após salvar.** Correção de um problema em que determinadas **[!UICONTROL Properties]** seleções não persistiam após salvar e reabrir uma atividade. (TGT-53889)

+++

**Localização**

+++Ver detalhes

* **Rótulos japoneses para [!UICONTROL Page Delivery] operadores de regra.** Correção de cadeias de caracteres ilegíveis ou corrompidas para rótulos de operador de regra de entrega de página na interface do usuário japonesa. (TGT-53097)

+++

**APIs**

+++Ver detalhes

* **Suporte à API [!DNL GraphQL] de relatórios para `segmentId`.** Adição de `segmentId` à API [!DNL GraphQL] de relatórios. (TGT-55021)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Ver detalhes

* **Modificações mostradas na experiência errada no editor.** Correção de um problema em que uma exclusão ou outra modificação poderia aparecer na experiência errada após alternar entre experiências no [!UICONTROL Visual Experience Composer]. (TGT-54955)

* **Modificações removidas ao excluir HTML de inserção.** Correção de um problema em que a exclusão do bloco **[!UICONTROL HTML]** extra adicionado com **[!UICONTROL Insert before]** ou **[!UICONTROL Insert after]** também removia uma modificação vinculada que não tinha seletor CSS. (TGT-54530)

+++

<!--
* **Blank page or CORS errors with Enhanced Experience Composer.** Fixed an issue where the [!UICONTROL Visual Experience Composer] could fail to load when Enhanced Experience Composer (EEC) was enabled. (TGT-54576)




**[!UICONTROL Visual Experience Composer] (VEC)**

+++See details

* **Click tracking for Experience B.** Fixed an issue where click tracking was not saved for **[!UICONTROL Experience B]** in the [!UICONTROL Visual Experience Composer]. (TGT-54843)

+++
-->

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
