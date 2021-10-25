---
keywords: notas de versão, versões, atualizações, versão futura, melhorias, novos recursos, correções, atualizações, pré-lançamento
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na próxima versão do Adobe Target, incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais novos recursos serão incluídos na próxima versão?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 5850e9b94d1e188b86f50092f30a6de9cfea9855
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 53%

---

# Notas de versão do Target (pré-lançamento)

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização em: 25 outubro de 2021**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

>[!IMPORTANT]
>
>**Fim da vida útil da mbox.js**: a partir de 31 de março de 2021, o [!DNL Adobe Target] não oferecerá mais suporte à biblioteca de mbox.js. Após 31 de março de 2021, todas as chamadas feitas da mbox.js vão resultar em falha e afetar suas páginas com atividades do [!DNL Target] em execução ao veicular conteúdo padrão.
>
>Para evitar possíveis problemas com seus sites, migre para a versão mais recente do novo [!DNL Adobe Experience Platform Web SDK] ou para a biblioteca at.js de JavaScript. Para obter mais informações, consulte [Visão geral: implementar o Target para Web do lado do cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## [!DNL Target Standard/Premium] 21.10.5 (26 de outubro de 2021)

Esta versão de manutenção contém as seguintes melhorias:

| Recurso | Detalhes |
| --- | --- |
| [!UICONTROL Visual Experience Composer] (VEC) | Adição de suporte para Componentes da Web. Experiências e ofertas personalizadas podem ser criadas e testadas em Elementos personalizados e em elementos dentro de Elementos personalizados. |

## [!DNL Target Standard/Premium] 21.10.4 (21 de outubro de 2021)

Esta versão de manutenção contém as seguintes melhorias:

| Recurso | Detalhes |
| --- | --- |
| Recommendations baseado em carrinho | Uma nova família de algoritmos foi adicionada para fornecer recomendações com base no conteúdo do carrinho do visitante.<br>Para obter mais informações, consulte &quot;Baseado em carrinho&quot; em [Criar critérios](/help/c-recommendations/c-algorithms/create-new-algorithm.md) e &quot;Páginas de finalização/exibições/finalização do carrinho&quot; e &quot;Excluir itens já no carrinho do visitante&quot; em [Planejar e implementar o Recommendations](/help/c-recommendations/plan-implement.md). |

## [!DNL Target Standard/Premium] 21.10.3 (19 de outubro de 2021)

Esta versão do inclui os seguintes aprimoramentos, correções e alterações:

* Correção de problemas que impedia os clientes de abrir o [!UICONTROL A4T] no painel [!DNL Analysis Workspace] clicando no botão [!UICONTROL Exibir no Analytics] botão em [!DNL Target] relatório de atividades. (TGT-42099, TGT-42100)
* Correção de um problema que causava o [!UICONTROL Editar design] botão para não ser exibido durante a edição [!UICONTROL Teste A/B] e [!UICONTROL Direcionamento de experiência] (XT) usando o [!UICONTROL Experience Composer baseado em formulário]. (TGT-41980)
* Correção de um problema que impedia o [!UICONTROL Compatível] da exibição da caixa de seleção na seleção de critérios ao criar um novo [!UICONTROL Recommendations] atividade . (TGT-42053)
* Correção de uma mensagem de erro incorreta que era exibida quando não era possível selecionar [!DNL Analytics] como fonte de relatórios (A4T) devido à falta de [!DNL Analytics] permissões. (TGT-41954)
* Implementamos várias correções de acessibilidade para melhorar a navegação pelo teclado na [!DNL Target] IU.

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
