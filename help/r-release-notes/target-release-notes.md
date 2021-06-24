---
keywords: notas de versão, versões, atualizações, versão futura, melhorias, novos recursos, correções, atualizações, pré-lançamento
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na próxima versão do Adobe Target, incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais novos recursos serão incluídos na próxima versão?
feature: Notas de versão
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: b897829595ef1cdda28a995481fa1d2d5d1616f4
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 79%

---

# Notas de versão do Target (pré-lançamento)

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização: 24 de junho de 2021**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

>[!IMPORTANT]
>
>**Fim da vida útil da mbox.js**: a partir de 31 de março de 2021, o [!DNL Adobe Target] não oferecerá mais suporte à biblioteca de mbox.js. Após 31 de março de 2021, todas as chamadas feitas da mbox.js vão resultar em falha e afetar suas páginas com atividades do [!DNL Target] em execução ao veicular conteúdo padrão.
>
>Para evitar possíveis problemas com seus sites, migre para a versão mais recente do novo [!DNL Adobe Experience Platform Web SDK] ou para a biblioteca at.js de JavaScript. Para obter mais informações, consulte [Visão geral: implementar o Target para Web do lado do cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## [!DNL Target Standard/Premium] 21.6.1 (30 de junho de 2021)

Esta versão inclui os novos recursos e melhorias a seguir. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

| Recurso | Detalhes |
| --- | --- |
| Analytics for Target (A4T) | Clicando no link &quot;[!UICONTROL Exibir no Analytics]&quot; na página [!UICONTROL Relatórios] de uma atividade que usa [!DNL Analytics] como fonte de relatórios (A4T), [!DNL Analysis Workspace] agora abre. Anteriormente, o link abria os relatórios [!DNL Analytics]. (TGT-36959) |
| ![Premium](/help/assets/premium.png) [!DNL Recommendations] | Os seguintes aprimoramentos se aplicam aos algoritmos de popularidade do [!DNL Recommendations]:<ul><li>Uma nova opção de &quot;janela de lookback&quot; (intervalo de dados) de seis horas está disponível para todos os algoritmos de popularidade (Mais visualizados/Mais vendidos) quando [!DNL Target] é a fonte de dados comportamentais. (Essa janela de lookback *não* está disponível quando o [!DNL Adobe Analytics] é a fonte de dados comportamentais.)</li><li>Quando selecionados, os seguintes algoritmos são executados aproximadamente a cada três horas (em vez de a cada 12 horas).<ul><li>Mais visualizados</li><li>Mais comprados</li><li>Mais visualizados por categoria</li><li>Mais comprados por categoria</li><li>Mais visualizados pelo atributo personalizado (usando o recurso groupBy)</li><li>Mais comprados pelo atributo personalizado (usando o recurso groupBy)</li></ul></ul>Data de lançamento a ser anunciada. (TOP-1086) |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
