---
keywords: notas de versão;versões;atualizações;versão futura;melhorias;novos recursos;correções;atualizações;pré-lançamento
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na próxima versão do Adobe Target, incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais novos recursos e melhorias serão incluídos na próxima versão?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 57030f8f3c1758c60ef00184b4b6d3dee30731fa
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 90%

---

# Notas de versão do Target (pré-lançamento)

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização: 26 de janeiro de 2023**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## [!DNL Target] Standard/Premium 22.13.3 (25 e 26 de janeiro de 2023)

Esta versão estará disponível de acordo com o seguinte agendamento:

* **25 de janeiro**: Europa, Oriente Médio e África (EMEA)
* **25 de janeiro**: Região Ásia-Pacífico (APAC)
* **26 de janeiro**: Região das Américas

Essa versão contém os seguintes novos recursos, aprimoramentos e correções:

| Recurso | Detalhes |
| --- | --- |
| [Oferta JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md) suporte no Automated Personalization (AP) | Adição de suporte para ofertas JSON em atividades do [!UICONTROL Automated Personalization] (AP) usando o Experience Composer baseado em formulário. (TGT-41460) |
| [Fragmentos de experiência do AEM](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) | Adição da capacidade de distinguir entre [!DNL Adobe Experience Manager] tipos de fragmento (AEM XF) exportados para o [!DNL Target]. Em vez da opção &quot;Fragmento de experiência&quot;, [!DNL Target] agora permite filtrar e pesquisar por &quot;HTML XF&quot; e &quot;JSON XF.&quot; (TGT-44132) |

* Correção de um problema que causava um &quot;erro 500&quot; no [!UICONTROL Teste A/B] e em atividades de [!UICONTROL Direcionamento de experiência] (XT) que contêm recomendações. Esse problema era causado quando o [!DNL Target] falhava ao excluir corretamente os objetos de critérios da interface do [!DNL Target] e do back-end do [!DNL Recommendations] que não estão mais em uso. (TGT-44383)
* Remoção do local do nome de oferta exibido no relatório de [!UICONTROL Nível da oferta] das atividades em [!UICONTROL Automated Personalization]. Essa alteração torna o relatório mais legível. (TGT-44294)
* As opções de calendário de 45 dias e 90 dias foram removidas do AP e dos relatórios de [!UICONTROL Direcionamento automático], [!UICONTROL Insights de personalização] e [!UICONTROL Atributos importantes] na interface do [!DNL Target]. Devido aos padrões de uso e para melhorar o desempenho, esses intervalos de datas foram removidos. A interface será atualizada para refletir os intervalos permitidos no momento: 15, 30 e 60 dias. (TGT-39357)
* Remoção da capacidade de alterar a configuração [!UICONTROL Igual à meta de otimização] na página [!UICONTROL Metas e configurações] após a ativação da atividade. (TGT-43923)
* Correção de um problema que causava problemas com o local de trabalho padrão no back-end do [!DNL Target] ao atualizar do [!DNL Target Standard] para o [!DNL Target Premium]. (TGT-44081 e TGT-44306)
* Alteração do link na página de [!UICONTROL Implementação] ([!UICONTROL Administração] > [!UICONTROL Implementação]) para os &quot;Métodos de implementação com decisão no dispositivo&quot; para apontar para a página que explica como usar a decisão no dispositivo para todos os SDKs compatíveis: Node.js, Java, .NET e Python. Para obter mais informações, consulte [Introdução aos SDKs de Target](https://developer.adobe.com/target/implement/server-side/sdk-guides/getting-started/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.
* Correção de um problema que causava problemas de upload de arquivo ao usar o [!DNL Scene7] e o [!DNL Target].
* Aprimoramento da acessibilidade da interface do [!DNL Target] para pessoas com deficiência usando resultados de uma auditoria interna de usabilidade. Essas melhorias de acessibilidade incluem recursos que antes não eram acessíveis por meio do teclado, melhorias no texto alternativo, a capacidade de ampliar partes da interface para serem mais utilizáveis, foco do teclado aprimorado e muito mais.   (TGT-42759)
* Várias correções de localização foram feitas na interface do [!DNL Target].

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da Platform. |
| [Detalhes da versão da at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |


## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
