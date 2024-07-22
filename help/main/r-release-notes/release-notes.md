---
keywords: notas de versão;novos recursos;versões;atualizações;atualização;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 44445f269a69a3ac3e3bc88bab8abf9fc4d51663
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 58%

---

# Notas de versão do [!DNL Target] (atuais)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium]. Além disso, as notas de versão para APIs [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outras alterações de plataforma também estão incluídas, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## [!DNL Target] relatórios em [!DNL Adobe Customer Journey Analytics] (8 de maio de 2024)

A integração entre o [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/customer-journey-analytics){target=_blank} e o [!DNL Target] fornece ferramentas poderosas de análise e economia de tempo para o seu programa de otimização.

Os principais benefícios de usar o [!DNL Customer Journey Analytics] como fonte de relatórios para o [!DNL Target] são:

* Profissionais de marketing podem aplicar dinamicamente as métricas de sucesso do [!DNL Customer Journey Analytics] nos relatórios de atividades do [!DNL Target] a qualquer momento. Não há necessidade de especificar tudo antes de executar a atividade.
* Os profissionais de marketing podem aproveitar os recursos do [!DNL Customer Journey Analytics], como o [Painel de experimentação](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation){target=_blank}, para analisar ainda mais a personalização do site.
* Os profissionais de marketing podem ter uma única fonte de relatórios para [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/reporting/cja-ajo){target=_blank} e [!DNL Target]. Ambos os produtos de personalização podem ser conectados ao [!DNL Customer Journey Analytics] para obter uma visão mais completa da personalização na Web.

Para obter mais informações, consulte [Relatórios do Target no Adobe Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md).

## Extensão auxiliar do [!UICONTROL Visual Experience Composer] (23 de abril de 2024)

A extensão auxiliar herdada [!DNL Target] do Visual Experience Composer foi criada usando Manifest V2. [!DNL Google] anunciou que não permitirá mais extensões criadas usando o Manifest V2 a partir de junho de 2024. Para obter mais informações, consulte [[!UICONTROL Visual Experience Composer] extensão auxiliar](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md).

A [!DNL Adobe] recomenda que os clientes mudem para a [extensão Auxiliar de edição visual](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) mais recente assim que possível.

## Atualizações para `Browser:iPad` e `Browser:iPhone` em [!UICONTROL Browser] atributos de público (30 de abril de 2024)

| Atualizações | Detalhes |
|--- |--- |
| [!UICONTROL Browser:iPad] e [!UICONTROL Browser:iPhone] atualizados em [Atributos do navegador](/help/main/c-target/c-audiences/c-target-rules/browser.md) usados ao criar públicos. | O [!DNL Adobe Target] permite [segmentar qualquer um dos vários atributos de categoria](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), incluindo visitantes que usam [opções específicas de navegador ou navegador](/help/main/c-target/c-audiences/c-target-rules/browser.md) quando visitam sua página.<P>A partir do [!DNL Target] Standard/Premium 24.3.1 (4-6 de março de 2024), os públicos-alvo internos criados usando a interface do usuário do Target, como `Browser:iPad` e `Browser:iPhone`, serão atualizados para executar o direcionamento adequado para [!DNL iPad] e [!DNL iPhone] usando `profile.mobile.deviceVendor`, `profile.mobile.isMobilePhone` e `profile.mobile.isTablet`.<P>Esta atualização não requer nenhuma ação por parte dos clientes.<p><B>Importante</b>: para que os clientes executem o direcionamento adequado para [!DNL iPad] e [!DNL iPhone] em scripts de perfil (e segmentos do JavaScript), as alterações manuais devem ser feitas pelo cliente até **30 de abril de 2024**. Para obter exemplos de configurações alternativas que devem ser alteradas manualmente, consulte [Atualizações para [!DNL iPad] e [!DNL iPhone] em [!UICONTROL Browser] atributos de público-alvo](/help/main/c-target/c-audiences/c-target-rules/browser.md#updates). |

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da Platform. |
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
