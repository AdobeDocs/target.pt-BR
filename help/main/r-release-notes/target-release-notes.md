---
keywords: notas de versão;versões;atualizações;versão futura;melhorias;novos recursos;correções;atualizações;pré-lançamento
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na próxima versão do Adobe Target, incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos e melhorias que serão incluídos na próxima versão do  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 8cdf362d9e45153b26bca5a45ed59ef557adc016
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 44%

---

# Notas de versão do Target (pré-lançamento)

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização: 14 de março de 2023**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## [!DNL Target] Standard/Premium 22.15.1 (8 e 9 de março de 2023)

Esta versão estará disponível de acordo com o seguinte agendamento:

* **8 de março**: região das Américas
* **9 de março**: região da Europa, Oriente Médio e África (EMEA)
* **9 de março**: região Ásia-Pacífico (APAC)

Essa versão contém os seguintes novos recursos, aprimoramentos e correções:

| Recurso | Detalhes |
| --- | --- |
| Métricas otimizadas do A4T para [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] | [!DNL Target] permite escolher métricas baseadas em eventos binomiais ou métricas baseadas em eventos contínuos ao usar [!UICONTROL A4T] para [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] atividades.<P>Esteja ciente da seguinte alteração nas métricas compatíveis:<ul><li>[!DNL Target] preservado o comportamento anterior para atividades existentes até (DATA A SER DETERMINADA). Após essa data, as atividades que usam métricas não compatíveis serão descontinuadas para forçar a migração de atividades existentes para o novo comportamento.</li></ul>Para obter mais informações, consulte [Métricas de meta compatíveis](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#supported) in *Suporte do A4T para atividades de Alocação automática e Direcionamento automático*. |
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


## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
