---
keywords: notas de versão, versões, atualizações, versão futura, melhorias, novos recursos, correções, atualizações, pré-lançamento
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na próxima versão do Adobe Target, incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais novos recursos serão incluídos na próxima versão?
feature: Notas de versão
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 0271c55efba15071e67101ffdb6448f4f4e3b77a
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 74%

---

# Notas de versão do Target (pré-lançamento)

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização: 3 de agosto de 2021**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

>[!IMPORTANT]
>
>**Fim da vida útil da mbox.js**: a partir de 31 de março de 2021, o [!DNL Adobe Target] não oferecerá mais suporte à biblioteca de mbox.js. Após 31 de março de 2021, todas as chamadas feitas da mbox.js vão resultar em falha e afetar suas páginas com atividades do [!DNL Target] em execução ao veicular conteúdo padrão.
>
>Para evitar possíveis problemas com seus sites, migre para a versão mais recente do novo [!DNL Adobe Experience Platform Web SDK] ou para a biblioteca at.js de JavaScript. Para obter mais informações, consulte [Visão geral: implementar o Target para Web do lado do cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## API de entrega do Target (Data a ser determinada)

Esta versão contém os seguintes aprimoramentos:

* O limite de parâmetros da mbox foi aumentado para 100 parâmetros. O limite anterior era de 50 parâmetros.
* O limite de `categoryId` foi aumentado para 256 caracteres. O limite anterior era de 128 caracteres.
* Os seguintes detalhes [!DNL Adobe Audience Manager] (AAM) foram adicionados à API de entrega:

   * UUID do AAM (ID de usuário exclusiva do Adobe Audience Manager)
   * dataPartnerId
   * dataPartnerUserId

   Anteriormente, a API de entrega incluía somente `dcsLocationHint` e `blob`. (TNT-41644)

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
