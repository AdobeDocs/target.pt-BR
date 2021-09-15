---
keywords: Notas de versão;novos recursos;versões;atualizações;atualização;versão;aprimoramento;aprimoramentos;correções;correções de bugs;atualizações
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
title: Quais são os novos recursos incluídos na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 5a5b39db9b9b4ffd95573d643dcff52fe562c0c2
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 57%

---

# Notas de versão do Target (atual)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium] Além disso, as notas de versão para APIs do Target, SDKs, [!DNL Adobe Experience Platform Web SDK], at.js e outras alterações de plataforma também estão incluídas, quando aplicável.

>[!IMPORTANT]
>
>**Fim da vida útil da mbox.js**: a partir de 31 de março de 2021, o [!DNL Adobe Target] não oferecerá mais suporte à biblioteca de mbox.js. Após 31 de março de 2021, todas as chamadas feitas da mbox.js vão resultar em falha e afetar suas páginas com atividades do [!DNL Target] em execução ao veicular conteúdo padrão.
>
>Migre para a versão mais recente do novo [!DNL Adobe Experience Platform Web SDK] ou para a biblioteca at.js JavaScript para evitar possíveis problemas com seus sites. Para obter mais informações, consulte [Visão geral: implementar o Target para Web do lado do cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe].)

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

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da plataforma. |
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
