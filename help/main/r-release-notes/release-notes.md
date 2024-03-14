---
keywords: notas de versão;novos recursos;versões;atualizações;atualização;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 5df9ba6eb249dfc690279177ecb5936aaefa7bdd
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 57%

---

# Notas de versão do [!DNL Target] (atuais)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium]. Além disso, as notas de versão para APIs [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outras alterações de plataforma também estão incluídas, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## Atualizações para `Browser:iPad` e `Browser:iPhone` in [!UICONTROL Browser] atributos do público-alvo (30 de abril de 2024)

| Atualizações | Detalhes |
|--- |--- |
| [!UICONTROL Browser:iPad] e [!UICONTROL Browser:iPhone] atualizado em [Atributos do navegador](/help/main/c-target/c-audiences/c-target-rules/browser.md) usado ao criar públicos. | [!DNL Adobe Target] permite [direcionar em qualquer um dos vários atributos de categoria](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), incluindo visitantes que usam um [opções do navegador ou do navegador](/help/main/c-target/c-audiences/c-target-rules/browser.md) quando visitarem sua página.<P>Começando com o [!DNL Target] Standard/Premium 24.3.1 (4-6 de março de 2024), públicos-alvo integrados criados usando a interface do usuário do Target, como `Browser:iPad` e `Browser:iPhone` será atualizado para executar o direcionamento adequado para [!DNL iPad] e [!DNL iPhone] usar `profile.mobile.deviceVendor`, `profile.mobile.isMobilePhone` e `profile.mobile.isTablet`.<P>Esta atualização não requer nenhuma ação por parte dos clientes.<p><B>Importante</b>: para que os clientes executem o direcionamento adequado para [!DNL iPad] e [!DNL iPhone] em scripts de perfil (e segmentos JavaScript), as alterações manuais devem ser feitas pelo cliente até **30 de abril de 2024**. Para obter exemplos de configurações alternativas que devem ser alteradas manualmente, consulte [Atualizações para [!DNL iPad] e [!DNL iPhone] in [!UICONTROL Browser] atributos de público](/help/main/c-target/c-audiences/c-target-rules/browser.md#updates). |

## [!UICONTROL Visual Editing Helper] extensão (14 de março de 2023)

Esta versão inclui os seguintes aprimoramentos e correções para o [[!DNL Adobe Experience Cloud Editing Helper]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) extensão para [!DNL Google Chrome]:

* O mecanismo de carregamento do iFrame foi aprimorado ao executar a criação nos sites dos clientes.
* Correção de um problema que fazia com que a extensão duplicasse cookies ao executar a criação no [!UICONTROL Visual Experience Composer] (VEC).
* Remoção da dependência para baixar a at.js para clientes que estão usando o [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank}.

## [!DNL Target] Standard/Premium 24.3.1 (4-6 de março de 2024)

Este lançamento está previsto para os seguintes dias:

* **4 de março**: regiões da Europa, Oriente Médio e África (EMEA)
* **5 de março**: região da Ásia-Pacífico (APAC)
* **6 de março**: região das Américas

Essa versão conta com os seguintes aprimoramentos e correções:

* Correção da lógica que calcula o número de seletores únicos em uma atividade. (TGT-47878)
* Correção de um problema que causava [!UICONTROL Multivariate] (MVT) atividades configuradas com [!UICONTROL Analytics for Target] (A4T) para não exibir corretamente. (TGT-47490)
* Mensagem de aviso exibida nos relatórios quando uma experiência sem tráfego é usada como a experiência de controle. (TGT-47537)
* Adição de muitas correções de back-end e localização.

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
