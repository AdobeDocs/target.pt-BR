---
keywords: Notas de versão;novos recursos;versões;atualizações;atualização;versão;aprimoramento;aprimoramentos;correções;correções de bugs;atualizações
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do [!DNL Adobe Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: dd8c0f3781625985f53aeb3b659fb4498a3e10e8
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 49%

---

# Notas de versão do Target (atual)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium] Além disso, as notas de versão do [!DNL Target] APIs, SDKs, a variável [!DNL Adobe Experience Platform Web SDK], at.js e outras alterações da plataforma também são incluídas, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## [!DNL Target Standard/Premium] 22.3.1 (lançamento escalonado, data a determinar)

Esta versão contém as seguintes alterações e aprimoramentos:

* Correção de um problema que fazia com que as edições nos scripts de perfil fossem revertidas para o script original não editado após o script ser editado, ativado e depois desativado. O script de perfil agora permanece no seu estado editado. (TGT-43249)
* Correção de um problema que causava a seguinte mensagem de erro no [!DNL Target] Interface do usuário ao mover um público-alvo usado em uma atividade com o status de &quot;rascunho&quot;: &quot;Não podemos concluir sua solicitação. Entre em contato com o atendimento ao cliente do Adobe se o problema persistir.&quot; (TGT-43212)
* Correção de um problema que causava o [!UICONTROL Incluir] e [!UICONTROL Excluir] opções a serem desativadas para públicos-alvo combinados ao editar uma atividade. (TGT-43422)
* Correção de um problema que impedia que alguns clientes visualizassem a lista de públicos disponíveis ao editar uma atividade. (TGT-43404)
* Correção de um problema que impedia alguns clientes de excluir um endereço IP do &quot;[!UICONTROL IPs a serem excluídos [!DNL Target] dados de relatório]&quot; listar em [!UICONTROL Administração] > [!UICONTROL Relatório]. (TGT-43384)
* Correção de um problema que impedia o uso de números negativos no critério de público-alvo que verificavam se qualquer variável era &quot;maior que&quot;, &quot;maior que ou igual a&quot;, &quot;menor que&quot; ou &quot;menor que ou igual a&quot;. (TGT-43367)
* Correção de um problema que impedia que os clientes visualizassem a variável [!UICONTROL Detalhes do público-alvo] ao criar públicos-alvo combinados. (TGT-43303)
* Correção de um problema que causava o [!DNL Target] IU ou nova [!UICONTROL Públicos-alvo] IU para o tempo limite prematuro de alguns clientes. (TGT-42590 e TGT-43273)

## [!DNL Target] Versão da plataforma (30 de março)

Esta versão inclui os seguintes aprimoramentos:

* As métricas de rastreamento de cliques incluirão a carga de análise nas solicitações da API de entrega para atividades que usam o Analytics como fonte de geração de relatórios (A4T) e eventos de processo no lado do cliente. (TNT-43073)

## [!DNL Target Standard] Atualização de públicos-alvo (28 de março)

Esta versão contém a seguinte atualização:

* O novo [!UICONTROL Públicos-alvo] A interface do usuário será ativada para todos [!DNL Target Standard] clientes.

## Correções de engenharia do cliente Target Standard/Premium (22 de março de 2022)

Esta versão de manutenção contém os seguintes aprimoramentos:

* Funcionalidade adicionada para retornar [!DNL Analytics] dados de carga para `prefetch` exibições e `pageLoad` clique nas métricas ao usar a variável [!UICONTROL API de entrega] com atividades que usam [!UICONTROL Analytics como fonte de relatórios] (A4T). (TNT-43198)
* Atualização da lista de agentes do usuário da filtragem de bot para permitir um tipo de navegador comumente usado no Japão. (TNT-43867)

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da plataforma. |
| [Detalhes da versão da at.js](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Alterações na documentação, notas de versão anteriores e notas de versão da Experience Cloud

Além das notas para cada versão, os recursos a seguir oferecem informações adicionais:

| Recurso | Detalhes |
|--- |--- |
| Alterações de documentação | Veja informações detalhadas sobre atualizações neste manual que podem não estar incluídas nas notas de versão.<br>Para obter mais informações, consulte [Alterações de documentação](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de versão para versões anteriores | Veja informações sobre os novos recursos e aprimoramentos das versões anteriores do Target Standard e do Target Premium.<br>Para obter mais informações, consulte [Notas de versões anteriores](/help/main/r-release-notes/release-notes-for-previous-releases.md). |
| Notas de versão da Adobe Experience Cloud | Veja as notas de versão mais recentes para as soluções da Adobe Experience Cloud.<br>Para obter mais informações, consulte as [Notas de versão da Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR). |

## Informações de pré-lançamento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Os recursos a seguir permitem ver as novidades previstas para a próxima versão do Target.

| Recurso | Detalhes |
|--- |--- |
| Atualização de produtos prioritários da Adobe | Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Notas de versão futuras | Para obter informações sobre os lançamentos do Target do mês atual, incluindo informações de pré-lançamento, consulte a página [Notas de versão do Target - Pré-lançamento](/help/main/r-release-notes/target-release-notes.md). |
