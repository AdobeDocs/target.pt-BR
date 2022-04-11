---
keywords: notas de versão, versões, atualizações, versão futura, melhorias, novos recursos, correções, atualizações, pré-lançamento
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na próxima versão do Adobe Target, incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais novos recursos e aprimoramentos serão incluídos na próxima versão?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: dd8c0f3781625985f53aeb3b659fb4498a3e10e8
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 37%

---

# Notas de versão do Target (pré-lançamento)

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização: 11 de abril de 2022**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## [!DNL Target Standard/Premium] 22.3.1 (lançamento escalonado, data a determinar)

Esta versão contém as seguintes alterações e aprimoramentos:

* Correção de um problema que fazia com que as edições nos scripts de perfil fossem revertidas para o script original não editado após o script ser editado, ativado e depois desativado. O script de perfil agora permanece no seu estado editado. (TGT-43249)
* Correção de um problema que causava a seguinte mensagem de erro no [!DNL Target] Interface do usuário ao mover um público-alvo usado em uma atividade com o status de &quot;rascunho&quot;: &quot;Não podemos concluir sua solicitação. Entre em contato com o atendimento ao cliente do Adobe se o problema persistir.&quot; (TGT-43212)
* Correção de um problema que causava o [!UICONTROL Incluir] e [!UICONTROL Excluir] opções a serem desativadas para públicos-alvo combinados ao editar uma atividade. (TGT-43422)
* Correção de um problema que impedia que alguns clientes visualizassem a lista de públicos disponíveis ao editar uma atividade. (TGT-43404)
* Correção de um problema que impedia alguns clientes de excluir um endereço IP do &quot;[!UICONTROL IPs a serem excluídos [!DNL Target] dados de relatório]&quot; listar em [!UICONTROL Administração] > [!UICONTROL Relatório]. (TGT-43384)
* Correção de um problema que impedia o uso de números negativos no critério de público-alvo que verificavam se qualquer variável era &quot;maior que&quot;, &quot;maior que ou igual a&quot;, &quot;menor que&quot; ou &quot;menor que ou igual a&quot;. (TGT-43367)
* Correção de um problema que impedia que os clientes visualizassem a variável [!UICONTROL Detalhes do público-alvo] ao criar públicos-alvo combinados. (TGT-43303)
* Correção de um problema que causava o [!DNL Target] IU ou nova [!UICONTROL Públicos-alvo] IU para o tempo limite prematuro de alguns clientes. (TGT-42590 e TGT-43273)

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
