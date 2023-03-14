---
keywords: notas de versão;novos recursos;versões;atualizações;atualização;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 8cdf362d9e45153b26bca5a45ed59ef557adc016
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 56%

---

# Notas de versão do [!DNL Target] (atuais)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium]. Além disso, as notas de versão para APIs [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outras alterações de plataforma também estão incluídas, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## [!DNL Target] Standard/Premium 22.15.1 (8 e 9 de março de 2023)

Esta versão estará disponível de acordo com o seguinte agendamento:

* **8 de março**: região das Américas
* **9 de março**: região da Europa, Oriente Médio e África (EMEA)
* **9 de março**: região Ásia-Pacífico (APAC)

Esta versão inclui os novos recursos e melhorias a seguir:

| Recurso | Detalhes |
| --- | --- |
| Métricas otimizadas do A4T para [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] | [!DNL Target] permite escolher métricas baseadas em eventos binomiais ou métricas baseadas em eventos contínuos ao usar [!UICONTROL A4T] para [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] atividades.<P>Esteja ciente da seguinte alteração sensível ao tempo nas métricas compatíveis:<ul><li>[!DNL Target] O preservou o comportamento anterior para atividades existentes até 9 de setembro de 2023. Após essa data, as atividades que usam métricas não compatíveis serão descontinuadas para forçar a migração de atividades existentes para o novo comportamento.</li></ul>Para obter mais informações, consulte [Métricas de meta compatíveis](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#supported) in *Suporte do A4T para atividades de Alocação automática e Direcionamento automático*. |
| [!UICONTROL Alocação automática] usar [!UICONTROL Analytics for Target] (A4T) | Novo tutorial:<ul><li>[Configuração de relatórios do A4T no [!DNL Analysis Workspace] para [!UICONTROL Alocação automática] atividades](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank}</li></ul> |
| [!UICONTROL Direcionamento automático] usar [!UICONTROL Analytics for Target] (A4T) | Novo tutorial:<ul><li>[Configuração de relatórios do A4T no [!DNL Analysis Workspace] para [!UICONTROL Direcionamento automático] atividades](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html){target=_blank}</li></ul> |

Esta versão inclui as seguintes correções:

* Atualizações de componentes da Web personalizados criados com o [!UICONTROL Visual Experience Composer] (VEC):

   * Correção da seleção de elementos DOM de sombra no VEC, melhorando o processo de criação para que não houvesse dependência no [!DNL Target] tipo de implementação ao criar a raiz de sombra. Agora, selecionar elementos DOM de sombra no VEC deve funcionar para qualquer site.
   * Correção de um problema que impedia o carregamento de elementos HTML usando #Shadow DOM no VEC. (TGT-35801)
   * Correção de problemas do VEC com sites SPA usando o ShadowDOM. (TGT-43169)
   * Correção de um problema com a Meta de otimização: &quot;clicou em um elemento&quot; que não identificava corretamente o seletor de CSS no ShadowDOM.

>[!NOTE]
>
>Para garantir a entrega das alterações criadas no VEC, verifique se você está usando um [!DNL Target] SDK ([at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} or [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html){target=_blank} (alloy.js)) com uma versão superior a 2.8.

**Problema conhecido**: rastreamento de cliques em um elemento raiz de sombra ao usar [!DNL Adobe Experience Platform Web SDK] O não está funcionando corretamente. (TNT-47012)

## at.js versão 2.10.2 (7 de março de 2023)

* Correção de um problema que causava a `trackEvent` para sempre retornar um erro.

Para obter informações sobre todas as versões da at.js, consulte [Detalhes da versão da at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da Platform. |
| [Detalhes da versão da at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Alterações na documentação, notas de versão anteriores e notas de versão da Experience Cloud

Além das notas para cada versão, os recursos a seguir oferecem informações adicionais:

| Recurso | Detalhes |
|--- |--- |
| Alterações de documentação | Veja informações detalhadas sobre atualizações neste manual que podem não estar incluídas nas notas de versão.<br>Para obter mais informações, consulte [Alterações de documentação](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de versão para versões anteriores | Veja informações sobre os novos recursos e aprimoramentos das versões anteriores do Target Standard e do Target Premium.<br>Para obter mais informações, consulte [Notas de versões anteriores](/help/main/r-release-notes/release-notes-for-previous-releases.md). |
| Notas de versão da Adobe Experience Cloud | Veja as notas de versão mais recentes para as soluções da Adobe Experience Cloud.<br>Para obter mais informações, consulte as [Notas de versão da Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR). |

## Informações de pré-lançamento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Os recursos a seguir permitem ver as novidades previstas para a próxima versão do Target.

| Recurso | Detalhes |
|--- |--- |
| Atualização de produtos prioritários da Adobe | Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Notas de versão futuras | Para obter informações sobre os lançamentos do Target do mês atual, incluindo informações de pré-lançamento, consulte a página [Notas de versão do Target - Pré-lançamento](/help/main/r-release-notes/target-release-notes.md). |
