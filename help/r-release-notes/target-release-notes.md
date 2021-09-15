---
keywords: notas de versão, versões, atualizações, versão futura, melhorias, novos recursos, correções, atualizações, pré-lançamento
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na próxima versão do Adobe Target, incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais novos recursos serão incluídos na próxima versão?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 5a5b39db9b9b4ffd95573d643dcff52fe562c0c2
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 41%

---

# Notas de versão do Target (pré-lançamento)

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização em 14 de setembro de 2021**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

>[!IMPORTANT]
>
>**Fim da vida útil da mbox.js**: a partir de 31 de março de 2021, o [!DNL Adobe Target] não oferecerá mais suporte à biblioteca de mbox.js. Após 31 de março de 2021, todas as chamadas feitas da mbox.js vão resultar em falha e afetar suas páginas com atividades do [!DNL Target] em execução ao veicular conteúdo padrão.
>
>Para evitar possíveis problemas com seus sites, migre para a versão mais recente do novo [!DNL Adobe Experience Platform Web SDK] ou para a biblioteca at.js de JavaScript. Para obter mais informações, consulte [Visão geral: implementar o Target para Web do lado do cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## [!DNL Target Standard/Premium] 21.9.1 (14 de setembro de 2021)

Esta versão de manutenção inclui os seguintes aprimoramentos, correções e alterações.

* Correção de problemas que impedia os clientes de fazer logon no [!UICONTROL Visual Experience Composer] (VEC) devido a novas políticas de segurança para cookies de terceiros em alguns navegadores da Web. Esse problema foi discutido em &quot;Páginas que não carregam no Visual Experience Composer (VEC) ou no Enhanced Experience Composer (EEC) ao usar o Google Chrome versão 80+&quot; em [Solução de problemas relacionados ao Visual Experience Composer e ao Enhanced Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md).
* Correção de um problema que fazia com que os nomes das ofertas no VEC exibissem o caminho da oferta em vez do nome amigável da oferta. (TGT-41300)
* Os nomes de experiência agora são refletidos em [!DNL Analysis Workspace] para atividades do A4T (TGT-38674)
* Correção de um problema em [!DNL Recommendations] que aplicava incorretamente as alterações de ID da entidade em uma promoção em uma atividade duplicada à atividade original. (TGT-41482)
* Correção de um problema que impedia que o botão &quot;Editar critérios&quot; fosse exibido corretamente na página [!UICONTROL Experiências] para atividades [!DNL Recommendations] no VEC. (TGT-39512)
* Correção de um problema que impedia a sincronização de atividades quando duplicadas e copiadas para um espaço de trabalho de teste. (TGT-40686)
* Correção de um problema que impedia modificações em um seletor com [fragmentos de experiência](/help/c-experiences/c-manage-content/aem-experience-fragments.md) ao usar &quot;[!UICONTROL Inserir após]&quot; no VEC. (TGT-41802)
* Correção de um problema que impedia o envio de conteúdo JSON vazio em uma oferta para o back-end. [!DNL Target] agora envia o objeto JSON, mesmo que esteja vazio. (TGT-41555)
* Correção de um problema que fazia com que os relatórios herdados [!DNL Analytics] fossem abertos em vez de [!DNL Analysis Workspace] quando os clientes clicavam em &quot;[!UICONTROL Exibir no Analytics]&quot; ao visualizar um relatório. (TGT-41867)
* Foi adicionado um esclarecimento adicional à mensagem de interface do usuário exibida quando um cliente tenta selecionar [!DNL Analytics] como fonte de relatórios (A4T) para uma atividade [!UICONTROL Automated Personalization]. A mensagem declara que &quot;[!DNL Target] é a única fonte compatível para as atividades [!UICONTROL Automated Personalization].&quot; (TGT-41954)
* Foi adicionado um esclarecimento adicional à mensagem de erro quando os clientes tentam separar hosts com &quot;nova linha&quot; em vez de vírgulas. (TGT-40671)
* Correção de um problema que fazia com que as datas &quot;[!UICONTROL Última atualização]&quot; de algumas atividades fossem diferentes da interface do usuário em inglês para clientes espanhóis e japoneses (ao visualizar a interface do usuário em espanhol e japonês). (TGT-38980)

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
