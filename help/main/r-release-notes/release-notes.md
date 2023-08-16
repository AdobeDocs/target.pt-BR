---
keywords: notas de versão;novos recursos;versões;atualizações;atualização;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: e130c68c838e799228956c598c583038a2f68ecf
workflow-type: ht
source-wordcount: '494'
ht-degree: 100%

---

# Notas de versão do [!DNL Target] (atuais)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium]. Além disso, as notas de versão para APIs [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outras alterações de plataforma também estão incluídas, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## Atualização planejada da infraestrutura de borda do [!DNL Adobe Target] {#edge}

A atualização planejada da infraestrutura de borda requer que IP ou domínios adicionais sejam incluídos na lista de permissões. Revise e inclua na lista de permissões o NAT e IP/domínios para implantações de borda 41-48. As atualizações da infraestrutura começam em 9 de agosto de 2023.

Para obter mais informações, consulte [Lista de permissões de nós de borda no Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html?lang=pt-BR){target=_blank} no *Manual do desenvolvedor do Adobe Target*.

## [!DNL Target] Standard/Premium 23.8.1 (9 de agosto de 2023)

Essa versão conta com os seguintes aprimoramentos e correções:

* Correção de um problema que, ocasionalmente, impedia a sincronização correta das atividades, como mostrado na coluna “[!UICONTROL Status]”, na página da lista de [!UICONTROL Atividades]. (TGT-46010 e TGT-44831)
* Correção de um problema que, ocasionalmente, impedia que o link “[!UICONTROL Exibir no Analytics]” fosse visualizado na página de atividades [!UICONTROL Relatórios], que usa o [!UICONTROL Analytics for Target] (A4T) como fonte de relatórios. (TGT-45808)
* Ajuste da apresentação de valores em tabelas para exibir como porcentagens, em vez de números com decimais. Por exemplo, 8% em vez de 0,08. (TGT-45548)
* Correção de um problema que impedia clientes de usar o foco do teclado na movimentação para o próximo elemento na página [!UICONTROL Metas e configurações] em atividades de [!UICONTROL Direcionamento de experiência] (XT). (TGT-44526)
* Correção de um problema que causava perda do foco do teclado após abrir a caixa de diálogo “[!UICONTROL Adicionar públicos]” ao criar uma atividade. (TGT-44525)

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da Platform. |
| [Detalhes da versão da at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Alterações na documentação, notas de versão anteriores e notas de versão da Experience Cloud

Além das notas para cada versão, os recursos a seguir oferecem informações adicionais:

| Recurso | Detalhes |
|--- |--- |
| [Alterações de documentação](/help/main/r-release-notes/doc-change.md) | Veja informações detalhadas sobre atualizações neste manual que podem não estar incluídas nas notas de versão. |
| [Notas de versões anteriores](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Veja informações sobre os novos recursos e aprimoramentos das versões anteriores do Target Standard e do Target Premium. |
| [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR){target=_blank} | Veja as notas de versão mais recentes das soluções da Adobe Experience Cloud. |

## Informações de pré-lançamento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Os recursos a seguir permitem ver as novidades previstas para a próxima versão do Target.

| Recurso | Detalhes |
|--- |--- |
| [Atualização de produtos prioritários da Adobe](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Receba notificações antecipadas sobre futuros aprimoramentos de produtos para o [!DNL Target] e outras soluções da [!DNL Adobe Experience Cloud]. |
| [Notas de versão do Target - Pré-lançamento](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Informações sobre os lançamentos do Target no mês atual, incluindo informações de pré-lançamento. |
