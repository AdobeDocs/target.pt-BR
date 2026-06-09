---
keywords: notas de versão;novos recursos;versões;atualizações;atualizar;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações;atualizações atuais;release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates;current updates
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
TQID: https://experienceleague.adobe.com/-Unx6cVsw3wch2LJgPtvBYPe-10rdpiJ4v9F7tMSP08
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 391653c7a45a48c311c6a6cff358bd077f8c47b7
workflow-type: tm+mt
source-wordcount: 652
ht-degree: 41%

---

# Notas de versão do [!DNL Target] (atuais)

Explore os recursos, aprimoramentos e correções mais recentes no [!DNL Adobe Target]. Essas notas de versão também abrangem atualizações para APIs do [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outros componentes da plataforma, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## [!DNL Target Standard/Premium] 26.6.1 (4 de junho de 2026)

**Atividades**

+++Ver detalhes

* **URL de atividade incompleta em [!UICONTROL Visão geral da atividade].** Correção de um problema em que a [!UICONTROL Visão geral da atividade] não exibia a URL completa de uma atividade. (TGT-54029)

* **Formato de data não localizado nos Relatórios de atividade.** Correção de um problema em que o formato de data não estava localizado na guia **[!UICONTROL Relatórios]** ao escolher a opção **Últimos X dias** na lista suspensa **[!UICONTROL Intervalo de datas predefinido]**. (TGT-51637)

* **Não é possível salvar a Atividade baseada em Formulário com determinados caracteres GB18030 no [!UICONTROL Local].** Correção de um problema em que não era possível salvar uma atividade baseada em formulário quando o campo **[!UICONTROL Local]** continha caracteres GB18030 específicos. (TGT-46980)

+++

**[!UICONTROL Públicos-alvo]**

+++Ver detalhes

* **Calendário não localizado em Criar fluxo de público-alvo para chinês simplificado e tradicional.** Correção de um problema em que o calendário nos campos **[!UICONTROL Início]** e **[!UICONTROL Fim]** dos atributos **[!UICONTROL Intervalo de tempo]** não era localizado nas localidades do chinês simplificado (CHS) e do chinês tradicional (CHT) durante o fluxo Criar público. (TGT-50619)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Ver detalhes

* **Dicas de ferramenta não localizadas no Criador de atividades atualizado.** Correção de problemas de localização em que as dicas de ferramentas de informações de **[!UICONTROL Refinamentos]** e **[!UICONTROL Conteúdo]** não foram localizadas no construtor de atividades atualizado do [!UICONTROL Visual Experience Composer]. (TGT-53721)

* **Deslocalizou [!UICONTROL Todos os Visitantes] em [!UICONTROL Públicos-alvo].** Correção de um problema em que a sequência de caracteres **[!UICONTROL Todos os visitantes]** em **[!UICONTROL Públicos-alvo de experiência]** no painel esquerdo não estava localizada no [!UICONTROL Visual Experience Composer]. (TGT-50086)

+++

**[!UICONTROL Relatórios]**

+++Ver detalhes

* **Formato de data não localizado na janela [!UICONTROL Criar Predefinição].** Correção de um problema em que o formato de data no campo **[!UICONTROL Intervalo de datas]** da janela **[!UICONTROL Criar predefinição]** não foi localizado. (TGT-49239)

+++

**Localização**

+++Ver detalhes

* Exibição de caracteres **GB18030 em várias áreas.** Correção de problemas em que alguns caracteres da Área de Uso Privada eram exibidos incorretamente como letras na interface do usuário do **[!UICONTROL Público]**, **[!UICONTROL Administração]** > **[!UICONTROL Propriedades]**, configuração de visor móvel e notificações do sistema. (TGT-49622, TGT-49623, TGT-49624, &amp; TGT-49625)

+++

<!--
* **Blank page or CORS errors with Enhanced Experience Composer.** Fixed an issue where the [!UICONTROL Visual Experience Composer] could fail to load when Enhanced Experience Composer (EEC) was enabled. (TGT-54576)

**[!UICONTROL Visual Experience Composer] (VEC)**

+++See details

* **Click tracking for Experience B.** Fixed an issue where click tracking was not saved for **[!UICONTROL Experience B]** in the [!UICONTROL Visual Experience Composer]. (TGT-54843)

+++
-->

## Atualizações sensíveis ao tempo que você precisa saber {#time-sensitive}

[!BADGE Importante]{type=Informative}

Para atualizações com limite de tempo relacionadas ao [!DNL Adobe Target] e à sua implementação, o [!DNL Adobe] fornece notas de versão e documentação detalhadas por meio do [!UICONTROL Experience League]. Estes são alguns destaques importantes para sua implementação:

### Desativação da alternância de versão da interface do usuário [!DNL Target]

Para obter mais informações, consulte [[!DNL Target] Perguntas frequentes sobre atualização da interface](/help/main/c-intro/updated-ui-faq.md).

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
| [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR){target=_blank} | Veja as notas de versão mais recentes das soluções da Adobe Experience Cloud. |

## Informações de pré-lançamento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Os recursos a seguir permitem ver as novidades previstas para a próxima versão do Target.

| Recurso | Detalhes |
|--- |--- |
| [Atualização de produtos prioritários da Adobe](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Receba notificações antecipadas sobre futuros aprimoramentos de produtos para o [!DNL Target] e outras soluções da [!DNL Adobe Experience Cloud]. |
| [Notas de versão do Target - Pré-lançamento](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Informações sobre os lançamentos do Target no mês atual, incluindo informações de pré-lançamento. |
