---
keywords: notas de versão, versões, atualizações, versão futura, melhorias, novos recursos, correções, atualizações, pré-lançamento
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na próxima versão do Adobe Target, incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais novos recursos serão incluídos na próxima versão?
feature: Notas de versão
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 7eb44049a954f1f18c1e4a52d455d352d0fcfdf0
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 36%

---

# Notas de versão do Target (pré-lançamento)

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização: 17 de maio de 2021**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do tempo das versões. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

>[!IMPORTANT]
>
>**Fim da vida útil** da mbox.js: A partir de 31 de março de 2021, o  [!DNL Adobe Target] não será mais compatível com a biblioteca mbox.js. Após 31 de março de 2021, todas as chamadas feitas da mbox.js normalmente falharão e afetarão suas páginas que têm [!DNL Target] atividades em execução ao veicular conteúdo padrão.
>
>Para evitar possíveis problemas com seus sites, migre para a versão mais recente da nova [!DNL Adobe Experience Platform Web SDK] ou da biblioteca at.js de JavaScript. Para obter mais informações, consulte [Visão geral: implementar o Target para Web do lado do cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## at.js versão 2.5.0 (13 de maio de 2021)

Essa versão da at.js inclui os seguintes aprimoramentos e alterações:

* [Suporte ao On-device ](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) Decisioning para at.js.
* [Visualizar ](/help/c-activities/c-activity-qa/activity-qa.md) links para suporte a atividades do  [!UICONTROL Automated Personalization]  (AP)

Esta versão também remove o suporte ao Microsoft Internet Explorer 10, Internet Explorer 11 e todas as versões mais antigas. O Microsoft Edge continua sendo compatível com a at.js 2.5.0 e posteriores. Para obter mais informações, consulte [Navegadores compatíveis](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md).

## [!DNL Adobe Experience Platform Web SDK] versão 2.5.0 (24 de maio de 2021)

Esta versão do [!DNL Platform Web SDK] inclui suporte para [!UICONTROL Analytics for Target] (A4T) para redirecionamentos [!DNL Target].

## [!DNL Target Standard/Premium] 21.5.1 (25 de maio de 2021)

O conteúdo será adicionado à medida que a data de lançamento se aproximar.

## [!DNL Target Standard/Premium] 21.5.2 (Data a determinar)

Esta versão contém os seguintes novos recursos e aprimoramentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

| Recurso | Detalhes |
| --- | --- |
| ![Premium](/help/assets/premium.png) [!DNL Recommendations] | Os seguintes aprimoramentos se aplicam aos algoritmos de popularidade [!DNL Recommendations]:<ul><li>Uma nova opção de &quot;janela de lookback&quot; (intervalo de dados) de seis horas estará disponível para todos os algoritmos de popularidade (Mais visualizados/Mais vendidos) quando [!DNL Target] for a fonte de dados comportamentais. (Essa janela de lookback é *not* disponível quando [!DNL Adobe Analytics] é a fonte de dados comportamentais.)</li><li>Quando selecionados, os seguintes algoritmos serão executados aproximadamente a cada três horas (em vez de a cada 12 horas).<ul><li>Mais visualizados</li><li>Mais comprados</li><li>Mais visualizados por categoria</li><li>Mais comprados por categoria</li><li>Mais exibido pelo atributo personalizado (usando o recurso groupBy)</li><li>Mais comprado pelo atributo personalizado (usando o recurso groupBy)</li></ul></ul>(TOP-1086) |

Esta versão contém as seguintes correções.

* O conteúdo será adicionado à medida que a data de lançamento se aproximar.

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
