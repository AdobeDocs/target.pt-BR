---
keywords: notas de versão;versões;atualizações;versão futura;melhorias;novos recursos;correções;atualizações;pré-lançamento
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na próxima versão do Adobe Target, incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais novos recursos e melhorias serão incluídos na próxima versão?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 145f4bd2b3353e429ce968622e47653170a60fda
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---

# Notas de versão do Target (pré-lançamento)

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização: 19 de outubro de 2022**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## [!DNL Target] Standard/Premium 22.10.3 (lançamento escalonado de 25 a 27 de outubro de 2022)

Esta versão estará disponível de acordo com o seguinte agendamento:

* **25 de outubro**: região da Europa, Oriente Médio e África (EMEA)
* **26 de outubro**: região da Ásia-Pacífico (APAC)
* **27 de outubro**: região das Américas

Essa versão contém os seguintes novos recursos, aprimoramentos e correções:

| Recurso | Detalhes |
| --- | --- |
| Métricas otimizadas do A4T para [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático]<br> (Disponível para clientes selecionados para teste. Estará disponível para todos os clientes em uma versão futura.) | Esteja ciente das seguintes alterações:<ul><li>Adição de suporte para métricas binárias e de maximização nos relatórios do [!UICONTROL Analytics for Target] (A4T) para as atividades de [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático]</li><li>O comportamento será preservado para atividades existentes até fevereiro de 2023. Após essa data, as atividades serão descontinuadas para forçar a migração de atividades existentes para um novo comportamento</li><li>A partir de 20 de fevereiro de 2023, o suporte para as métricas `averagetimespentonsite`, `bouncerate` e `entries` em atividades de [!DNL Target] será descontinuado.</li></ul> |

* Adição de dicas de ferramentas na interface do [!DNL Target] para ajudar os clientes a navegar pelo construtor de públicos com mais eficiência e aprender a usar recursos que eles possam não conhecer. (TGT-44139)
* Adição da funcionalidade de impedir que os clientes editem uma atividade que foi desativada pelo [!DNL Target] devido ao uso de métricas não compatíveis. Uma mensagem na interface orienta os clientes a duplicar a atividade e, em seguida, atualizar as métricas de conversão.

   Com esta versão, as métricas `averagetimespentonsite`, `bouncerate` e `entries` do [!DNL Target] serão descontinuadas em novas atividades. As atividades existentes podem continuar usando essas métricas até maio de 2023.

* Adição de uma dica de ferramenta na interface do [!DNL Target] para ajudar os clientes a selecionar um critério de otimização ao criar ou editar uma atividade de [!UICONTROL Direcionamento automático] que usa o A4T.

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da Platform. |
| [Detalhes da versão da at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |


## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
