---
keywords: notas de versão, versões, atualizações, versão futura, melhorias, novos recursos, correções, atualizações, pré-lançamento
description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na próxima versão do Adobe Target, incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais novos recursos serão incluídos na próxima versão?
feature: ' Notas de versão '
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
translation-type: tm+mt
source-git-commit: 2e678fa8a4826f6bfdaef1a04b89b8da7de48d12
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 22%

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

Esta versão contém os seguintes novos recursos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

| Recurso | Detalhes |
| --- | --- |
| Suporte ao On-device Decisioning para at.js | A tomada de decisão no dispositivo permite que profissionais de marketing e desenvolvedores forneçam experiência e personalização no navegador de um usuário com latência próxima de zero. |

Esta versão contém os seguintes aprimoramentos, correções e alterações.

* Correção de um problema que impedia a sincronização de uma atividade após alterar o público-alvo para [!UICONTROL Todos os visitantes]. (TGT-40259)
* Correção de um problema que impedia a duplicação de ofertas quando usadas em locais diferentes nas atividades [!UICONTROL Automated Personalization], mesmo que a opção [!UICONTROL Não permitir duplicatas] estivesse habilitada. (TGT-39567)
* Correção de um problema que impedia o carregamento correto da página [!UICONTROL Administration] > [!UICONTROL Scene7 configuration]. (TGT-39918)
* Correção de um problema que fazia com que as propriedades fossem mapeadas para o espaço de trabalho incorreto. (TGT-39869)
* [!DNL Target Recommendations] O suporta novos operadores baseados em lista para regras de filtragem de entidade. (TGT-39234)

   Os operadores recém-adicionados incluem:

   * Está Contido Na Lista
   * Não Está Contido Na Lista
   * A Lista Contém Um Item Em
   * A Lista Não Contém Um Item Em
   * A Lista Contém Todos Os Itens Em
   * A Lista Não Contém Todos Os Itens Em

* Correção de um problema que causava o carregamento infinito se a solicitação falhasse após alterar o ambiente ao criar uma exclusão de recomendações. (TGT-39948)

## at.js versão 2.5.0 (19 de abril de 2021)

Essa versão da at.js inclui os seguintes aprimoramentos:

* Suporte ao On-device Decisioning para at.js
* Suporte a links de visualização para atividades do Automated Personalization

Esta versão também remove o suporte ao Microsoft Internet Explorer 10 e versões posteriores.

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
