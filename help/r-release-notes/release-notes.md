---
keywords: Notas de versão;novos recursos;versões;atualizações;atualização;versão;aprimoramento;aprimoramentos;correções;correções de bugs;atualizações
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual de [!DNL Adobe Target].
title: Quais são os novos recursos incluídos na versão atual?
feature: Notas de versão
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 14a1755bf3f3e47baea3a2105679c9d2951948a4
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 62%

---

# Notas de versão do Target (atual)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium] Além disso, as notas de versão para APIs do Target, SDKs, [!DNL Adobe Experience Platform Web SDK], at.js e outras alterações da plataforma também são incluídas, quando aplicável.

>[!IMPORTANT]
>
>**Fim da vida útil da mbox.js**: a partir de 31 de março de 2021, o [!DNL Adobe Target] não oferecerá mais suporte à biblioteca de mbox.js. Após 31 de março de 2021, todas as chamadas feitas da mbox.js vão resultar em falha e afetar suas páginas com atividades do [!DNL Target] em execução ao veicular conteúdo padrão.
>
>Migre para a versão mais recente do novo [!DNL Adobe Experience Platform Web SDK] ou para a biblioteca at.js JavaScript para evitar possíveis problemas com seus sites. Para obter mais informações, consulte [Visão geral: implementar o Target para Web do lado do cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe].)

## [!DNL Target] node.js SDK 2.1.8 (11 de agosto de 2021)

* Coleta de dados de telemetria do SDK adicionada
* Codegen do openapi do cliente da API de entrega automatizada

Para obter mais informações sobre esta versão e versões anteriores, consulte o [Change log](https://github.com/adobe/target-nodejs-sdk/blob/main/CHANGELOG.md) na [Target node.js SDK documentation](https://github.com/adobe/target-nodejs-sdk) no Github.

## [!DNL Target Standard/Premium] 21.8.1 (Data a ser determinada)

>[!NOTE]
>
>A versão [!DNL Target Standard/Premium] 21.8.1 foi adiada. Em vez de ser lançado em 4 de agosto de 2021, a versão 21.8.1 será lançada nos próximos dias. Mais detalhes quando disponíveis.

Esta versão de manutenção contém vários aprimoramentos de backend, incluindo a seguinte alteração voltada para o cliente:

* Correção de um problema que fazia com que os relatórios das atividades de [!UICONTROL Personalização automática] criadas no [!UICONTROL Experience Composer baseado em formulário] referenciassem ofertas excluídas em relatórios. Esse erro gerou a seguinte mensagem de erro: &quot;Estamos tendo problemas para recuperar dados para esse relatório. Entre em contato com o Atendimento ao cliente do Adobe se o problema persistir.&quot; (TGT-41028)

## [!DNL Target Delivery API] (3 de agosto de 2021)

Esta versão contém os seguintes aprimoramentos:

* O limite de parâmetros da mbox foi aumentado para 100 parâmetros. O limite anterior era de 50 parâmetros. (TNT-41717)
* O limite de `categoryId` foi aumentado para 256 caracteres. O limite anterior era de 128 caracteres.
* Os seguintes detalhes [!DNL Adobe Audience Manager] (AAM) foram adicionados à API de entrega:

   * UUID do AAM: A ID de AAM interna usada para identificar exclusivamente um usuário.
   * dataPartnerId: A ID de um parceiro de dados.
   * dataPartnerUserId: A ID de usuário fornecida por um parceiro de dados.

   Anteriormente, a API de entrega incluía somente `dcsLocationHint` e `blob`. (TNT-41644)

## at.js 2.6.0 (27 de julho de 2021)

* Adição do atributo seguro aos cookies sempre que as configurações `secureOnly` da at.js estiverem definidas como `true`.
* Os tokens de resposta agora estão disponíveis ao usar o `triggerView()`.
* Correção de um problema relacionado ao evento `CONTENT_RENDERING_NO_OFFERS`. Agora, esse evento é acionado corretamente sempre que não há conteúdo retornado do [!DNL Target].
* Os detalhes das métricas de clique do [!DNL Anlytics for Target] (A4T) são retornados corretamente ao usar solicitações `prefetch`.
* A geração UUID não usa mais `Math.random()`, mas depende de `window.crypto`.
* A expiração do cookie `sessionId` é estendida corretamente em cada chamada de rede.
* A inicialização do cache de visualização do [!UICONTROL Aplicativo de página única] (SPA) agora é manipulada corretamente e atende às configurações `viewsEnable`.

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Detalhes sobre alterações em cada versão do SDK da Web da plataforma. |
| [Detalhes da versão da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Alterações na documentação, notas de versão anteriores e notas de versão da Experience Cloud

Além das notas para cada versão, os recursos a seguir oferecem informações adicionais:

| Recurso | Detalhes |
|--- |--- |
| Alterações de documentação | Veja informações detalhadas sobre atualizações neste manual que podem não estar incluídas nas notas de versão.<br>Para obter mais informações, consulte [Alterações de documentação](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de versão para versões anteriores | Veja informações sobre os novos recursos e aprimoramentos das versões anteriores do Target Standard e do Target Premium.<br>Para obter mais informações, consulte [Notas de versões anteriores](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Notas de versão da Adobe Experience Cloud | Veja as notas de versão mais recentes para as soluções da Adobe Experience Cloud.<br>Para obter mais informações, consulte as [Notas de versão da Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR). |

## Informações de pré-lançamento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Os recursos a seguir permitem ver as novidades previstas para a próxima versão do Target.

| Recurso | Detalhes |
|--- |--- |
| Atualização de produtos prioritários da Adobe | Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Notas de versão futuras | Para obter informações sobre os lançamentos do Target do mês atual, incluindo informações de pré-lançamento, consulte a página [Notas de versão do Target - Pré-lançamento](/help/r-release-notes/target-release-notes.md). |
