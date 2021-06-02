---
keywords: Notas de versão; novos recursos; versões; atualizações; atualização; versão; aprimoramento; aprimoramentos; correções; correções de bugs; atualizações
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do Adobe Target, incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos incluídos na versão atual?
feature: Notas de versão
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: ea5a451e71f390ddacc6ccea583112dd831184dc
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 84%

---

# Notas de versão do Target (atual)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium] Além disso, as notas de versão para APIs do Target, SDKs, a biblioteca de JavaScript (at.js) e outras alterações na plataforma também são incluídas, quando aplicável.

>[!IMPORTANT]
>
>**Fim da vida útil da mbox.js**: a partir de 31 de março de 2021, o [!DNL Adobe Target] não oferecerá mais suporte à biblioteca de mbox.js. Após 31 de março de 2021, todas as chamadas feitas da mbox.js vão resultar em falha e afetar suas páginas com atividades do [!DNL Target] em execução ao veicular conteúdo padrão.
>
>Migre para a versão mais recente da nova [!DNL Adobe Experience Platform Web SDK] ou da biblioteca at.js de JavaScript para evitar possíveis problemas com seus sites. Para obter mais informações, consulte [Visão geral: implementar o Target para Web do lado do cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe].)

## ![Adobe Experience Platform Web SDK ](/help/assets/platform.png) [!DNL Adobe Experience Platform Web SDK] badgeversion 2.6.0 (1 de junho de 2021)

Esta versão do [!DNL Platform Web SDK] inclui suporte para o seguinte:

| Recurso | Detalhes |
| --- | --- |
| Suporte de redirecionamento com [!UICONTROL Analytics for Target] (A4T) | O SDK da Web da plataforma agora oferece suporte a redirecionamentos [!DNL Target] ao usar [A4T](/help/c-integrating-target-with-mac/a4t/a4t.md).<br>Para obter mais informações, consulte  [Analytics  [!DNL Target] para implementação](/help/c-integrating-target-with-mac/a4t/a4timplementation.md). |
| Tokens de resposta | O SDK da Web da plataforma agora suporta tokens de resposta [!DNL Target].<br>Para obter mais informações, consulte Tokens  [de resposta](/help/administrating-target/response-tokens.md). |

## at.js versão 2.5.0 (13 de maio de 2021)

Essa versão da at.js inclui os seguintes aprimoramentos e alterações:

* [Suporte à decisão no dispositivo ](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) para at.js.
* [Suporte a links de pré-visualização](/help/c-activities/c-activity-qa/activity-qa.md) para atividade de Automated Personalization

Esta versão também remove o suporte ao Microsoft Internet Explorer 10, Internet Explorer 11 e todas as versões mais antigas. O Microsoft Edge continua sendo compatível com a at.js 2.5.0 e posteriores.

## Target Standard/Premium 21.4.1 (19 de abril de 2021)

Esta versão inclui os novos recursos e melhorias a seguir. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

| Recurso | Detalhes |
| --- | --- |
| Suporte para decisão no dispositivo para at.js<br>(Data a ser anunciada) | A decisão no dispositivo permite que profissionais de marketing e desenvolvedores forneçam experiência e personalização no navegador do usuário com latência próxima de zero.<br>Para obter mais informações, consulte [Decisão no dispositivo para at.js.](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) |
| ![Premium](/help/assets/premium.png) Operadores baseados em lista para regras de filtragem de entidade | O [!DNL Target Recommendations] oferece suporte a novos operadores baseados em lista para regras de filtragem de entidade. (TGT-39234)<br>Os operadores recém-adicionados incluem:<br><ul><li>Está contido na lista</li><li>Não está contido na lista</li><li>A lista contém um item em</li><li>A lista não contém um item em</li><li>A lista contém todos os itens em</li><li>A lista não contém todos os itens em</li></ul>Para obter mais informações, consulte &quot;Operadores disponíveis&quot; em [Usar regras de inclusão dinâmicas e estáticas](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#operators). |

Esta versão inclui as seguintes correções.

* Correção de um problema que impedia a sincronização de uma atividade após alterar o público-alvo para [!UICONTROL Todos os visitantes]. (TGT-40259)
* Correção de um problema que impedia a duplicação de ofertas quando usadas em locais diferentes nas atividades [!UICONTROL Automated Personalization], mesmo que a opção [!UICONTROL Não permitir duplicatas] estivesse habilitada. (TGT-39567)
* Correção de um problema que impedia o carregamento correto da página [!UICONTROL Administração] > [!UICONTROL Configuração do Scene7]. (TGT-39918)
* Correção de um problema que fazia com que as propriedades fossem mapeadas para o espaço de trabalho incorreto. (TGT-39869)
* Correção de um problema que causava o carregamento infinito se a solicitação falhasse após alterar o ambiente ao criar uma exclusão de recomendações. (TGT-39948)

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
