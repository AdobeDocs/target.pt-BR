---
keywords: notas de versão, versões, atualizações, versão futura, melhorias, novos recursos, correções, atualizações, pré-lançamento
description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na próxima versão do Adobe Target, incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais novos recursos serão incluídos na próxima versão?
feature: ' Notas de versão '
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
translation-type: tm+mt
source-git-commit: dba3044c94502ea9e25b21a3034dc581de10f431
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 20%

---

# Notas de versão do Target (pré-lançamento)

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização: 16 de abril de 2021**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do tempo das versões. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

>[!IMPORTANT]
>
>**Fim da vida útil** da mbox.js: A partir de 31 de março de 2021, o  [!DNL Adobe Target] não será mais compatível com a biblioteca mbox.js. Após 31 de março de 2021, todas as chamadas feitas da mbox.js normalmente falharão e afetarão suas páginas que têm [!DNL Target] atividades em execução ao veicular conteúdo padrão.
>
>Para evitar possíveis problemas com seus sites, migre para a versão mais recente da nova [!DNL Adobe Experience Platform Web SDK] ou da biblioteca at.js de JavaScript. Para obter mais informações, consulte [Visão geral: implementar o Target para web do lado do cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## Target Standard/Premium 21.4.1 (19 de abril de 2021)

Esta versão contém os seguintes novos recursos e aprimoramentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

| Recurso | Detalhes |
| --- | --- |
| Suporte ao On-device Decisioning para at.js | A tomada de decisão no dispositivo permite que profissionais de marketing e desenvolvedores forneçam experiência e personalização no navegador de um usuário com latência próxima de zero.<br>Para obter mais informações, consulte Decisão  [no dispositivo para at.js.](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md)<br>(Data a anunciar) |
| ![](/help/assets/premium.png) Operadores baseados em PremiumList para regras de filtragem de entidade | [!DNL Target Recommendations] O suporta novos operadores baseados em lista para regras de filtragem de entidade. (TGT-39234)<br>Os operadores recém-adicionados incluem:<br><ul><li>Está Contido Na Lista</li><li>Não Está Contido Na Lista</li><li>A Lista Contém Um Item Em</li><li>A Lista Não Contém Um Item Em</li><li>A Lista Contém Todos Os Itens Em</li><li>A Lista Não Contém Todos Os Itens Em</li></ul>Para obter mais informações, consulte &quot;Operadores disponíveis&quot; em [Usar regras de inclusão estática e dinâmica](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#operators). |

Esta versão contém as seguintes correções.

* Correção de um problema que impedia a sincronização de uma atividade após alterar o público-alvo para [!UICONTROL Todos os visitantes]. (TGT-40259)
* Correção de um problema que impedia a duplicação de ofertas quando usadas em locais diferentes nas atividades [!UICONTROL Automated Personalization], mesmo que a opção [!UICONTROL Não permitir duplicatas] estivesse habilitada. (TGT-39567)
* Correção de um problema que impedia o carregamento correto da página [!UICONTROL Administration] > [!UICONTROL Scene7 configuration]. (TGT-39918)
* Correção de um problema que fazia com que as propriedades fossem mapeadas para o espaço de trabalho incorreto. (TGT-39869)
* Correção de um problema que causava o carregamento infinito se a solicitação falhasse após alterar o ambiente ao criar uma exclusão de recomendações. (TGT-39948)

## at.js versão 2.5.0 (Data de anúncio)

Essa versão da at.js inclui os seguintes aprimoramentos e alterações:

* [Suporte ao On-device ](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) Decisioning para at.js.
* [Visualizar ](/help/c-activities/c-activity-qa/activity-qa.md) links suporte para atividades do Automated Personalization

Esta versão também remove o suporte ao Microsoft Internet Explorer 10 e versões posteriores.

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
