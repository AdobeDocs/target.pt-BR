---
keywords: notas de versão;versões;atualizações;versão futura;melhorias;novos recursos;correções;atualizações;pré-lançamento
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na próxima versão do Adobe Target, incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais novos recursos e melhorias serão incluídos na próxima versão?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: c12df34c9c7392a0ea50e8d1dea32147e8b7b165
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 37%

---

# Notas de versão do Target (pré-lançamento)

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização: 12 de janeiro de 2023**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## [!DNL Target] Standard/Premium 22.13.3 (25-26 de janeiro de 2023)

Essa versão contém os seguintes novos recursos, aprimoramentos e correções:

* Adição de suporte para ofertas JSON em [!UICONTROL Automated Personalization] (AP) usando o Experience Composer baseado em formulário. (TGT-41460)
* Implementado [Modo de controle de qualidade](/help/main/c-activities/c-activity-qa/activity-qa.md) para atividades de AP. (TGT-44341)
* Nomes de experiência em [!DNL Recommendations] agora são exibidas com nomes amigáveis para que os clientes possam correlacionar melhor os dados em [!DNL Adobe Analytics] com isso no [!DNL Target] IU. (TGT-41853)
* Correção de um problema que causava um &quot;erro 500&quot; em [!UICONTROL Teste A/B] e [!UICONTROL Direcionamento de experiência] (XT) atividades que contêm recomendações. Esse problema foi causado quando [!DNL Target] falha ao excluir corretamente os objetos de critérios do [!DNL Target] Interface do usuário e [!DNL Recommendations] backend que não está mais em uso. (TGT-44383)
* Remoção do local do nome de oferta exibido no [!UICONTROL Nível da oferta] relatório de [!UICONTROL Automated Personalization] atividades. Essa alteração torna o relatório mais legível. (TGT-44294)
* &quot; renomeado[!UICONTROL Fragmento de experiência]&quot; na [!UICONTROL Visual Experience Composer] Fluxo de trabalho (VEC). A opção agora é &quot;[!UICONTROL HTML XF].&quot; (TGT-44132)
* Adição da capacidade de exibir metadados da oferta do fragmento de experiência na dica de ferramenta de informações da oferta. (TGT-43838)
* Remoção das opções de calendário de 45 dias e 90 dias da API e [!UICONTROL Direcionamento automático] [!UICONTROL Insights de personalização] e [!UICONTROL Atributos importantes] nos relatórios do [!DNL Target] IU. Devido aos padrões de uso e para melhorar o desempenho, esses intervalos de datas foram descontinuados. A interface do usuário foi atualizada para refletir os intervalos permitidos no momento: 15, 30 e 60 dias. (TGT-39357)
* Não permitido alterar a [!UICONTROL Igual à meta de otimização] na configuração do [!UICONTROL Metas e configurações] página após a atividade estar ativa. (TGT-43923)
* Correção de um problema que causava problemas com o local de trabalho padrão no [!DNL Target] backend ao atualizar de [!DNL Target Standard] para [!DNL Target Premium]. (TGT-44081 e TGT-44306)
* Alteração do link no [!UICONTROL Implementação] página ([!UICONTROL Administração] > [!UICONTROL Implementação]) para &quot;Métodos de implementação com o On-Device Decisioning&quot;, para apontar para a página que explica como usar a decisão no dispositivo para todos os SDKs compatíveis: Node.js, Java, .NET e Python. Para obter mais informações, consulte [Introdução aos SDKs do Target](https://developer.adobe.com/target/implement/server-side/sdk-guides/getting-started/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.
* Correção de um problema que causava problemas de upload de arquivo ao usar o [!DNL Scene7] e [!DNL Target].
* Aprimoramento da acessibilidade do [!DNL Target] Interface do usuário para pessoas com deficiência usando resultados de uma auditoria interna de usabilidade. Essas melhorias de acessibilidade incluem o acesso a recursos que antes não eram acessíveis por meio do teclado, melhorias no texto alternativo, a capacidade de ampliar partes da interface do usuário para serem mais utilizáveis, o foco do teclado aprimorado e muito mais.   (TGT-42759)
* Várias correções de localização foram feitas no [!DNL Target] IU.

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da plataforma. |
| [Detalhes da versão da at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |


## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
