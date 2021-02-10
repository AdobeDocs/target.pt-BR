---
keywords: notas de versão;versões;atualizações;versão futura;melhorias;novos recursos;correções;atualizações;pré-lançamento;notas de versão;notas;versões;atualizações;versão futura;melhorias;novos recursos;correções;atualizações;pré-lançamento
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na próxima versão do Adobe Target, incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais novos recursos estão incluídos na próxima versão?
feature: Release Notes
translation-type: tm+mt
source-git-commit: e0d61de20501f40ea6b61db83be346072df997f0
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 25%

---


# Notas de versão do Target (pré-lançamento)

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização: 10 de fevereiro de 2021**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do tempo das versões. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

>[!IMPORTANT]
>
>**Fim da vida útil** do mbox.js: Em 31 de março de 2021, não  [!DNL Adobe Target] será mais compatível com a biblioteca mbox.js. Após 31 de março de 2021, todas as chamadas feitas a partir do mbox.js falharão e afetarão suas páginas que possuem [!DNL Target] atividades sendo executadas com o conteúdo padrão.
>
>Recomendamos que todos os clientes migrem para a versão mais recente da nova [!DNL Adobe Experience Platform Web SDK] ou da biblioteca JavaScript at.js antes dessa data para evitar possíveis problemas com seus sites. Para obter mais informações, consulte [Visão geral: implemente o Público alvo para Web do lado do cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## Target Standard/Premium 21.2.1 (2 de março de 2021) 

Esta versão de manutenção contém os seguintes aprimoramentos, correções e alterações.

Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

* Aumento do tamanho de oferta permitido pela API de 512 KB para 1 MB. (TGT-38304)
* Correção de um problema que fazia com que a dependência atual não fosse exibida quando os clientes clicavam em [!UICONTROL Editar dependência] em uma página [!UICONTROL Metas e configurações] do atividade. (TGT-39340)
* Correção de um problema ao atualizar a [!UICONTROL Biblioteca de Audiências] de um espaço de trabalho. Antes da atualização, as audiências para o espaço de trabalho selecionado no momento eram exibidas. Após a atualização, a área de trabalho padrão [!UICONTROL e suas audiências eram exibidas. ] O espaço de trabalho atual e suas audiências agora persistem após a atualização. (TGT-38871)
* Correção de um problema ao copiar uma atividade [!UICONTROL Recommendations] e editar posteriormente a atividade original alterando sua sequência de critérios. A alteração na sequência de critérios na atividade original também foi aplicada incorretamente à atividade copiada. (TGT-39155)

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
