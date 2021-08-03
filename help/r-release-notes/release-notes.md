---
keywords: Notas de versão;novos recursos;versões;atualizações;atualização;versão;aprimoramento;aprimoramentos;correções;correções de bugs;atualizações
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos incluídos na versão atual?
feature: Notas de versão
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 7badceff58e00f8406d24621534d24ea4067a224
workflow-type: tm+mt
source-wordcount: '739'
ht-degree: 88%

---

# Notas de versão do Target (atual)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium] Além disso, as notas de versão para APIs do Target, SDKs, a biblioteca de JavaScript (at.js) e outras alterações na plataforma também são incluídas, quando aplicável.

>[!IMPORTANT]
>
>**Fim da vida útil da mbox.js**: a partir de 31 de março de 2021, o [!DNL Adobe Target] não oferecerá mais suporte à biblioteca de mbox.js. Após 31 de março de 2021, todas as chamadas feitas da mbox.js vão resultar em falha e afetar suas páginas com atividades do [!DNL Target] em execução ao veicular conteúdo padrão.
>
>Migre para a versão mais recente do novo [!DNL Adobe Experience Platform Web SDK] ou para a biblioteca at.js JavaScript para evitar possíveis problemas com seus sites. Para obter mais informações, consulte [Visão geral: implementar o Target para Web do lado do cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe].)

## API de entrega do Target (3 de agosto de 2021)

Esta versão contém os seguintes aprimoramentos:

* O limite de parâmetros da mbox foi aumentado para 100 parâmetros. O limite anterior era de 50 parâmetros. (TNT-41717)
* O limite de `categoryId` foi aumentado para 256 caracteres. O limite anterior era de 128 caracteres.
* Os seguintes detalhes [!DNL Adobe Audience Manager] (AAM) foram adicionados à API de entrega:

   * UUID do AAM: A ID de AAM interna usada para identificar exclusivamente um usuário.
   * dataPartnerId: A ID de um parceiro de dados.
   * dataPartnerUserId: A ID de usuário fornecida por um parceiro de dados.

   Anteriormente, a API de entrega incluía somente `dcsLocationHint` e `blob`. (TNT-41644)

## at.js 2.6.0 (16 de julho de 2021)

* Adição do atributo seguro aos cookies sempre que as configurações `secureOnly` da at.js estiverem definidas como `true`.
* Os tokens de resposta agora estão disponíveis ao usar o `triggerView()`.
* Correção de um problema relacionado ao evento `CONTENT_RENDERING_NO_OFFERS`. Agora, esse evento é acionado corretamente sempre que não há conteúdo retornado do [!DNL Target].
* Os detalhes das métricas de clique do [!DNL Anlytics for Target] (A4T) são retornados corretamente ao usar solicitações `prefetch`.
* A geração UUID não usa mais `Math.random()`, mas depende de `window.crypto`.
* A expiração do cookie `sessionId` é estendida corretamente em cada chamada de rede.
* A inicialização do cache de visualização do [!UICONTROL Aplicativo de página única] (SPA) agora é manipulada corretamente e atende às configurações `viewsEnable`.

## [!DNL Target Standard/Premium] 21.6.1 (30 de junho de 2021)

Esta versão inclui os novos recursos e melhorias a seguir. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

| Recurso | Detalhes |
| --- | --- |
| [!UICONTROL Analytics for Target] (A4T) | Ao clicar no link &quot;[!UICONTROL Exibir no Analytics]&quot; na página [!UICONTROL Relatórios] de uma atividade que usa [!DNL Analytics] como fonte de relatórios (A4T), o [!DNL Analysis Workspace] agora é aberto. Anteriormente, o link abria os relatórios do [!DNL Analytics]. (TGT-36959) |

## Python SDK 1.0.0 (16 de junho de 2021)

Está disponível agora o novo [!DNL Adobe Target] Python SDK com recursos de decisão no dispositivo. Essa mais nova adição reforça o conjunto de SDKs do lado do servidor do [!DNL Target]. Esses SDKs ajudam na integração com o [!DNL Target] e agilizam a atribuição de valor, no idioma de sua escolha. As integrações do lado do servidor estão se tornando uma escolha popular, visto que o mercado está mudando para um mundo sem cookies, no qual os dados próprios são valiosos. Os SDKs do Target estão disponíveis nas linguagens de programação mais populares do mercado (Python, Java, JavaScript, C# e .Net).

Para obter mais informações, consulte a [documentação do Python SDK](https://adobetarget-sdks.gitbook.io/docs/sdk-reference-guides/python-sdk) no [Guia de SDKs do Adobe Target](https://adobetarget-sdks.gitbook.io/docs/).

## ![Selo do SDK da Web da Adobe Experience Platform](/help/assets/platform.png) [!DNL Adobe Experience Platform Web SDK] versão 2.5.0 (1º de junho de 2021)

Esta versão do [!DNL Platform Web SDK] inclui suporte para o seguinte:

| Recurso | Detalhes |
| --- | --- |
| Suporte de redirecionamento com [!UICONTROL Analytics for Target] (A4T) | O SDK da Web da Platform agora oferece suporte a [!DNL Target] redirecionamentos ao usar o [A4T](/help/c-integrating-target-with-mac/a4t/a4t.md).<br>Para obter mais informações, consulte [Implementação do Analytics for  [!DNL Target] ](/help/c-integrating-target-with-mac/a4t/a4timplementation.md). |

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
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
