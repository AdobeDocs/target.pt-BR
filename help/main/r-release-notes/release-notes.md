---
keywords: notas de versão;novos recursos;versões;atualizações;atualizar;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações;atualizações atuais;release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates;current updates
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 860dd22fc4ec261a62869cb656d72bd49f2bd91c
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 51%

---

# Notas de versão do [!DNL Target] (atuais)

Explore os recursos, aprimoramentos e correções mais recentes no [!DNL Adobe Target]. Essas notas de versão também abrangem atualizações para APIs do [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outros componentes da plataforma, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## Atualizações sensíveis ao tempo que você precisa saber {#time-sensitive}

[!BADGE Importante]{type=Informative}

Para atualizações com limite de tempo relacionadas ao [!DNL Adobe Target] e à sua implementação, o [!DNL Adobe] fornece notas de versão detalhadas e documentação até [!UICONTROL Experience League]. Estes são alguns destaques importantes para sua implementação:

### Desativação da alternância de versão da interface do usuário [!DNL Target]

Para obter mais informações, consulte [[!DNL Target] Perguntas frequentes sobre atualização da interface](/help/main/c-intro/updated-ui-faq.md).

## [!DNL Target Standard/Premium] 26.5.1 (7 de maio de 2026)

**Integrações**

+++Ver detalhes

* Gerenciamento de **[!DNL Adobe Target]no Experimentation Accelerator.** Adição de suporte para atribuição de espaços de trabalho [!DNL Target] a sandboxes do Experimentation Accelerator para que as equipes possam exibir experimentos de [!DNL Adobe Target] no Experimentation Accelerator em um único local. [Saiba mais](../c-integrating-target-with-mac/experimentation-accelerator.md)

+++

**Atividades**

+++Ver detalhes

* **[!UICONTROL Graph View]fora de sincronia com a tabela e o download.** Correção de um problema em que os relatórios de atividade podiam mostrar métricas ausentes ou nulas em **[!UICONTROL Graph View]** para alguns intervalos de datas, mesmo que **[!UICONTROL Table View]** e o relatório baixado ainda mostrassem os valores corretos. (TGT-54998)

+++

**[!UICONTROL Audiences]**

+++Ver detalhes

* **A lista de uso do público-alvo não foi totalmente renderizada.** Correção de um problema em que a seção **[!UICONTROL Usage]** nos detalhes do público-alvo podia exibir apenas um subconjunto de atividades mapeadas, mesmo quando atividades adicionais estavam associadas a esse público-alvo. (TGT-55094)

+++

**[!UICONTROL Administration]**

+++Ver detalhes

* **Confirmação mais clara para ofuscação de IP de último octeto.** Ao alterar **[!UICONTROL Obfuscate Visitor IP addresses]** para **[!UICONTROL Last octet]** em **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**, a caixa de diálogo de confirmação agora explica que [!DNL Target] oculta o último octeto do endereço IP do visitante. (TGT-44821)

+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++Ver detalhes

* **Página em branco ou incompleta com o Enhanced Experience Composer (EEC).** Correção de um problema em que o [!UICONTROL Visual Experience Composer] não carregava o site no editor quando **[!UICONTROL Enhanced Experience Composer]** era habilitado. (TGT-54576)

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
