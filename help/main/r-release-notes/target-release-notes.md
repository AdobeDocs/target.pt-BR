---
keywords: notas de versão;versões;atualizações;versão futura;melhorias;novos recursos;correções;atualizações;pré-lançamento
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na próxima versão do Adobe Target, incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais novos recursos e melhorias serão incluídos na próxima versão?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 80481a149d436f13bd510c4c4287d447799afbb4
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 54%

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
| Métricas contínuas | Foi adicionada a capacidade de usar métricas contínuas, como receita, em [!UICONTROL Direcionamento automático] e [!UICONTROL Alocação-Alocação] atividades.<br>Anteriormente, [!UICONTROL Direcionamento automático] e [!UICONTROL Alocação automática] foram otimizados para funcionar somente com métricas binárias (baseadas em conversão). (TGT-43649 e TGT-43649)<BR>Observe que esse recurso está disponível somente para clientes selecionados. Esse recurso estará disponível para todos os clientes em uma versão futura. |
| [!DNL Recommendations] nomes amigáveis | Nomes amigáveis adicionados em [!UICONTROL Analytics para Target] Relatórios do A4T. Anteriormente, [!DNL Target] somente as IDs de experiência listadas. Esse aprimoramento alinha os relatórios entre [!DNL Adobe Analytics] e [!DNL Target] e ajuda os clientes a simplificarem a criação de relatórios no A4T. (TGT-41853 |

* Adição de dicas de ferramentas no [!DNL Target] Interface do usuário para ajudar os clientes a navegar no construtor de público-alvo com mais eficiência e aprender a usar recursos que podem não ser familiares. (TGT-44139)
* Adição da funcionalidade para impedir que os clientes editem uma atividade que foi desativada por [!DNL Target] porque usa métricas não suportadas. Uma mensagem na interface do usuário direciona os clientes para duplicarem a atividade e, em seguida, atualizarem a métrica de conversão.

   Com esta versão `averagetimespentonsite`, `bouncerate`e `entries` métricas em [!DNL Target] as atividades serão descontinuadas para novas atividades. As atividades existentes podem continuar usando essas métricas até 6 de fevereiro de 2023. (TGT-43860, TGT-43861, &amp; TGT-43650)

* Adição de uma dica de ferramenta na [!DNL Target] Interface do usuário para ajudar os clientes a selecionar um critério de otimização ao criar ou editar uma [!UICONTROL Direcionamento automático] atividade que usa o A4T. (TGT-43713)

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da Platform. |
| [Detalhes da versão da at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |


## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
