---
keywords: notas de versão, versões, atualizações, versão futura, melhorias, novos recursos, correções, atualizações, pré-lançamento
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na próxima versão do Adobe Target, incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais novos recursos serão incluídos na próxima versão?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 89b995f20491fe0a51c91f8a1fe7e6b1ccc7f974
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 100%

---

# Notas de versão do Target (pré-lançamento)

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização em: 28 outubro de 2021**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

>[!IMPORTANT]
>
>**Fim da vida útil da mbox.js**: a partir de 31 de março de 2021, o [!DNL Adobe Target] não oferecerá mais suporte à biblioteca de mbox.js. Após 31 de março de 2021, todas as chamadas feitas da mbox.js vão resultar em falha e afetar suas páginas com atividades do [!DNL Target] em execução ao veicular conteúdo padrão.
>
>Para evitar possíveis problemas com seus sites, migre para a versão mais recente do novo [!DNL Adobe Experience Platform Web SDK] ou para a biblioteca at.js de JavaScript. Para obter mais informações, consulte [Visão geral: implementar o Target para Web do lado do cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## at.js versão 2.7.0 (28 de outubro de 2021)

Esta versão inclui os seguintes aprimoramentos:

* Suporte adicionado para [Componentes da web](https://developer.mozilla.org/pt-BR/docs/Web/Web_Components). Esta versão da at.js é necessária para criar e testar experiências e ofertas personalizadas em elementos personalizados e em elementos dentro de elementos personalizados. Essa funcionalidade está incluída na versão 21.10.5 do [!DNL Target Standard/Premium].

## [!DNL Target Standard/Premium] 21.10.5 (28 de outubro de 2021)

Esta versão de manutenção contém o seguinte aprimoramento:

| Recurso | Detalhes |
| --- | --- |
| [!UICONTROL Visual Experience Composer] (VEC) | Suporte adicionado para [Componentes da web](https://developer.mozilla.org/en-US/docs/Web/Web_Components). Experiências e ofertas personalizadas podem ser criadas e testadas em elementos personalizados e em elementos dentro de elementos personalizados.<br>Para obter mais informações, consulte [opções do Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#custom). |

## [!DNL Target Standard/Premium] 21.10.4 (21 de outubro de 2021)

Esta versão de manutenção contém o seguinte aprimoramento:

| Recurso | Detalhes |
| --- | --- |
| Recomendações baseadas em carrinho | Uma nova família de algoritmos foi adicionada para fornecer recomendações com base no conteúdo do carrinho do visitante.<br>Para obter mais informações, consulte “Baseado em carrinho” na seção [Criar critérios](/help/c-recommendations/c-algorithms/create-new-algorithm.md) e “Inclusões/visualizações do carrinho e páginas de finalização” e “Excluir itens já presentes no carrinho do visitante” na seção [Planejar e implementar o Recommendations](/help/c-recommendations/plan-implement.md). |

## [!DNL Target Standard/Premium] 21.10.3 (19 de outubro de 2021)

Esta versão do inclui os seguintes aprimoramentos, correções e alterações:

* Correção de problemas que impediam os clientes de abrirem o painel do [!UICONTROL A4T] no [!DNL Analysis Workspace], ao clicar no botão [!UICONTROL Exibir no Analytics] no relatório de atividades do [!DNL Target]. (TGT-42099, TGT-42100)
* Correção de um problema que impedia a exibição do botão [!UICONTROL Editar design] durante a edição de atividades de [!UICONTROL Teste A/B] e [!UICONTROL Direcionamento de experiência] (XT), usando o [!UICONTROL Experience Composer baseado em formulário]. (TGT-41980)
* Correção de um problema que impedia a exibição da caixa de seleção [!UICONTROL Compatível] na seleção de critérios ao criar uma nova atividade do [!UICONTROL Recommendations]. (TGT-42053)
* Correção de uma mensagem de erro incorreta que era exibida quando não era possível selecionar o [!DNL Analytics] como fonte de relatórios (A4T), devido à falta de permissões do [!DNL Analytics]. (TGT-41954)
* Foram implementadas várias correções de acessibilidade para melhorar a navegação pelo teclado na interface do [!DNL Target].

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
