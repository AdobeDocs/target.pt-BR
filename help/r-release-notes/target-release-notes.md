---
keywords: notas de versão, versões, atualizações, versão futura, melhorias, novos recursos, correções, atualizações, pré-lançamento
description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na próxima versão do Adobe Target, incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais novos recursos serão incluídos na próxima versão?
feature: ' Notas de versão '
translation-type: tm+mt
source-git-commit: ddc357197f6a182865c5f06930de747c143c7c38
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 21%

---


# Notas de versão do Target (pré-lançamento)

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização: 1 de março de 2021**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do tempo das versões. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

>[!IMPORTANT]
>
>**Fim da vida útil** da mbox.js: Em 31 de março de 2021, o não  [!DNL Adobe Target] será mais compatível com a biblioteca mbox.js. Após 31 de março de 2021, todas as chamadas feitas da mbox.js normalmente falharão e afetarão suas páginas que têm [!DNL Target] atividades em execução ao veicular conteúdo padrão.
>
>A Adobe recomenda que todos os clientes migrem para a versão mais recente da nova [!DNL Adobe Experience Platform Web SDK] ou da biblioteca at.js de JavaScript antes dessa data para evitar possíveis problemas com seus sites. Para obter mais informações, consulte [Visão geral: implementar o Target para web do lado do cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## Target Standard/Premium 21.2.1 (9 e 10 de março de 2021)

Esta versão de manutenção contém os seguintes aprimoramentos, correções e alterações.

Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

* Aumento do tamanho permitido da oferta (TGT-38304):

   | Tipo | Limite anterior | Novo limite |
   | --- | --- | --- |
   | HTML | 256 KB | 1024 KB |
   | Ofertas visuais da interface do usuário do Target | 64 KB | 1024 KB para cada experiência |
   | Via API | 512 KB | 1024 KB |

* [!UICONTROL Os relatórios de ] Insights de personalização para atividades de Direcionamento  [!UICONTROL automático]  (AT) e Personalização  [!UICONTROL automatizada]  (AP) agora são produzidos diariamente. Você pode escolher um relatório que fornece [!UICONTROL Segmentos automatizados] ou [!UICONTROL Atributos importantes] para os últimos 15, 30 e 60 dias. As opções de 45 e 90 dias foram removidas para permitir que as outras configurações da janela de lookback sejam executadas diariamente. (TGT-39472)
* Correção de um problema que fazia com que a dependência atual não fosse exibida quando os clientes clicavam em [!UICONTROL Editar dependência] na página [!UICONTROL Metas e configurações] de uma atividade. (TGT-39340)
* Correção de um problema ao atualizar a [!UICONTROL Biblioteca de público-alvo] de um espaço de trabalho. Antes da atualização, os públicos-alvo do espaço de trabalho selecionado no momento eram exibidos. Após a atualização, o [!UICONTROL Espaço de trabalho padrão] e seus públicos-alvo eram exibidos. O espaço de trabalho atual e seus públicos-alvo agora persistem após a atualização. (TGT-38871)
* Correção de um problema ao copiar uma atividade [!UICONTROL Recommendations] e editar posteriormente a atividade original alterando sua sequência de critérios. A alteração na sequência de critérios na atividade original também foi aplicada incorretamente à atividade copiada. (TGT-39155)
* Correção de um problema que fazia com que o número incorreto de produtos fosse exibido para exclusões [!UICONTROL Recommendations] . (TGT-39599)

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
