---
keywords: notas de versão;novos recursos;versões;atualizações;atualizar;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações;atualizações atuais;release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates;current updates
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
hold: true
source-git-commit: 44d9cd4de7ff2064e6005a4d7ece7f37194fbf2f
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 41%

---

# Notas de versão do [!DNL Target] (atuais)

Explore os recursos, aprimoramentos e correções mais recentes no [!DNL Adobe Target]. Essas notas de versão também abrangem atualizações para APIs do [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outros componentes da plataforma, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## Atualizações sensíveis ao tempo que você precisa saber {#time-sensitive}

[!BADGE Importante]{type=Informative}

Para atualizações com limite de tempo relacionadas ao [!DNL Adobe Target] e à sua implementação, o [!DNL Adobe] fornece notas de versão detalhadas e documentação até [!UICONTROL Experience League]. Estes são alguns destaques importantes para sua implementação:

### Desativação da alternância de versão da interface do usuário [!DNL Target]

Para obter mais informações, consulte [[!DNL Target] Perguntas frequentes sobre atualização da interface](/help/main/c-intro/updated-ui-faq.md).

## [!DNL Target Standard/Premium] 26.3.2 (10 de março de 2026)

**Atividades**

+++Ver detalhes

* **As alterações da oferta direta na experiência não foram salvas.** Essa correção resolve um problema em que as modificações feitas nas ofertas diretas em uma experiência de atividade não eram salvas. Anteriormente, quando os usuários abriam uma oferta direta, faziam alterações e as salvavam, as alterações apareciam refletidas inicialmente, mas eram perdidas ao reabrir a oferta. A correção garante que as alterações nas ofertas diretas sejam salvas corretamente e persistam quando a oferta for reaberta. (TGT-54653)

+++

**Implementação**

+++Ver detalhes

* **Adicionar alternância de gerenciamento de cintilação na tela de Implementação.** Um novo botão de alternância foi adicionado à tela [!UICONTROL Implementation] para controlar a habilitação da configuração de gerenciamento de cintilação. Essa opção permite que os administradores configurem o gerenciamento de cintilação diretamente na tela de Implementação. (TGT-52247)

+++

**Visão geral**

+++Ver detalhes

* **Mostrar nome completo do público-alvo e da experiência na página Visão geral.** Esse aprimoramento atualiza a página [!UICONTROL Overview] para exibir o nome completo dos públicos-alvo e experiências. Anteriormente, os nomes longos eram truncados e não eram totalmente visíveis, exigindo que os usuários clicassem três vezes para selecionar todo o texto e ver o nome completo. A atualização garante que os nomes completos de público-alvo e experiência estejam visíveis, facilitando para os usuários a identificação e a análise das configurações de atividade. (TGT-53323)

+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++Ver detalhes

* **As alterações do VEC não são refletidas nos sites que usam o DOM de Sombra (Salesforce Lightning Web Components).** Essa correção resolve um problema em que as alterações feitas no Adobe Target (como alterações de cor do CTA) não eram salvas ou refletidas no site ativo de sites baseados no Salesforce usando o LWC (Componentes Web Lightning). O CMS não aceitava atualizações de atividades do Target e esse problema ocorria consistentemente em testes A/B e outros tipos de atividades. (TGT-54059)

+++

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
