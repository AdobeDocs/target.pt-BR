---
keywords: notas de versão;novos recursos;versões;atualizações;atualizar;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações;atualizações atuais;release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates;current updates
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: ada5803424b4930d91dda735901390fe5073932f
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 39%

---

# Notas de versão do [!DNL Target] (atuais)

Explore os recursos, aprimoramentos e correções mais recentes no [!DNL Adobe Target]. Essas notas de versão também abrangem atualizações para APIs do [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outros componentes da plataforma, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## Atualizações sensíveis ao tempo que você precisa saber {#time-sensitive}

[!BADGE Importante]{type=Informative}

Para atualizações com limite de tempo relacionadas ao [!DNL Adobe Target] e à sua implementação, o [!DNL Adobe] fornece notas de versão detalhadas e documentação até [!UICONTROL Experience League]. Estes são alguns destaques importantes para sua implementação:

### Desativação da alternância de versão da interface do usuário [!DNL Target]

Para obter mais informações, consulte [[!DNL Target] Perguntas frequentes sobre atualização da interface](/help/main/c-intro/updated-ui-faq.md).

<!--
## [!DNL Target Standard/Premium] 26.4.2 (April 7, 2026)

**Activities**

+++See details

* **Custom code preserved when applied to additional views.** Fixed an issue where custom code applied to one **[!UICONTROL View]** could be removed when adding or saving custom code for another **[!UICONTROL View]** in the same **[!UICONTROL Activity]**. (TGT-53933)

* **Reporting metrics column order.** The updated [!DNL Target] interface allows reporting metrics to be reordered without clearing the full selection and re-adding metrics in sequence. Previously, users were required to unselect all metrics and select them again in the desired order, which was time-consuming when many metrics were enabled and when adjusting column placement to limit horizontal scrolling. (TGT-53044)

+++

-->

## [!DNL Target Standard/Premium] 26.4.1 (sexta-feira, 2 de abril de 2026)

**Atividades**

+++Ver detalhes

* **Atributos de público-alvo visíveis na exibição Atividades.** Correção de um problema em que os detalhes da regra de público-alvo visualizados de um **[!UICONTROL Activity]** não exibiam determinados atributos exibidos ao abrir o mesmo público-alvo da seção **[!UICONTROL Audiences]**. (TGT-54742)

* **Exportar CSV nas páginas de lista de Atividades e Públicos.** Adicionada uma ação **[!UICONTROL Export CSV]** para que você possa exportar listas de atividades da interface do usuário, inclusive quando os filtros são aplicados, sem depender exclusivamente de APIs para exportações de rotina. (TGT-51466)

* **Modificações de experiência sinalizadas quando seletores não são encontrados.** Modificações de experiência agora executam uma verificação de existência de seletor; quando um seletor não é encontrado na página, a modificação é sinalizada como inválida. (TGT-54815)

* **[!UICONTROL Automated personalization]atividades.** Correção de problemas de interface e carregamento de atividade que impediam os usuários de criar, editar ou gerenciar com confiança as atividades de Personalização automatizada, o que bloqueava a configuração da campanha e atrasava os casos de uso de personalização. (TGT-54421)

+++

**Públicos-alvo**

+++Ver detalhes

* **Nome e descrição do público-alvo visíveis ao criar públicos-alvo de uma atividade.** Correção de um problema em que os campos de público-alvo **[!UICONTROL Name]** e **[!UICONTROL Description]** não se destacavam claramente ao criar ou editar um público-alvo a partir do fluxo de atividade, em comparação à criação do público-alvo diretamente em **[!UICONTROL Audiences]**. (TGT-54837)

+++

**Insights**

+++Ver detalhes

* **[!UICONTROL Live Activities]conta com Insights.** Correção de um problema em que a métrica **[!UICONTROL Live Activities]** no painel de Insights podia relatar um total maior do que o número de atividades que apareciam como ativas em **[!UICONTROL All Activities]**. (TGT-54788)

+++

**Recomendações**

+++Ver detalhes

* **Listas de ID longas em [!UICONTROL Global Exclusions].** Correção de um problema em que a colagem ou a inserção de uma longa lista de IDs em **[!UICONTROL Global Exclusions]** poderia ser truncada na interface atualizada em comparação com a herdada, causando uma lista de exclusão incompleta. (TGT-54422)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Ver detalhes

* **Indicador de status do Enhanced Experience Composer (EEC) no [!UICONTROL Visual Experience Composer].** O indicador EEC indica se o Enhanced Experience Composer está ativado. Sua apresentação foi revisada para não se parecer mais com um botão interativo, pois serve apenas como uma exibição de status não interativa. (TGT-54828)

* **Painel esquerdo recolhível em [!UICONTROL Visual Experience Composer].** O painel esquerdo agora pode ser recolhido enquanto uma atividade estiver aberta para edição. Isso melhora o acesso a **[!UICONTROL Components]** e **[!UICONTROL Properties]** para atividades que incluem vários públicos e páginas, inclusive em exibições menores. (TGT-54269)

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
