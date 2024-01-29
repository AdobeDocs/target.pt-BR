---
keywords: notas de versão;novos recursos;versões;atualizações;atualização;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 99152f66217f66174e8b6a5a7319f11b22c74b8e
workflow-type: ht
source-wordcount: '575'
ht-degree: 100%

---

# Notas de versão do [!DNL Target] (atuais)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium]. Além disso, as notas de versão para APIs [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outras alterações de plataforma também estão incluídas, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## Descontinuação do iPad e iPhone do atributo de público-alvo do navegador (30 de abril de 2024)

| Descontinuação | Detalhes |
|--- |--- |
| [!DNL iPad] e [!DNL iPhone] serão descontinuados do [atributo do navegador](/help/main/c-target/c-audiences/c-target-rules/browser.md) usado ao criar públicos-alvo.<p>Data da descontinuação:<P>30 de abril de 2024 | O [!DNL Adobe Target] permite [segmentar qualquer um dos vários atributos de categoria](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), incluindo usuários que usam um [navegador específico ou opções de navegador](/help/main/c-target/c-audiences/c-target-rules/browser.md) quando visitam sua página.<P><B>A partir de 30 de abril de 2024, o iPad e o iPhone serão removidos da lista suspensa do tipo [!UICONTROL Navegador] disponível ao criar categorias para públicos-alvo.</b><P>Se você tiver públicos-alvo que visam iPads ou iPhones usando o atributo [!UICONTROL Navegador], será necessário alterar essas configurações antes de 30 de abril de 2024 para garantir que esses públicos-alvo continuem funcionando conforme o esperado.<p>Para obter exemplos de configurações alternativas, consulte [Descontinuação do iPad e do iPhone do atributo de público-alvo do navegador (30 de abril de 2024)](/help/main/c-target/c-audiences/c-target-rules/browser.md#deprecation). |

## [!DNL Target] Standard/Premium 24.1.1 (22, 23 e 25 de janeiro de 2024)

Este lançamento está previsto para os seguintes dias:

* **22 de janeiro**: regiões da Europa, Oriente Médio e África (EMEA)
* **23 de janeiro**: região da Ásia-Pacífico (APAC)
* **25 de janeiro**: região das Américas

Essa versão conta com os seguintes aprimoramentos e correções:

* As atividades do [!UICONTROL Analytics for Target] (A4T) com métricas de meta de receita não exibiam “Receita” como o nome da coluna e a métrica de receita não era exibida no formato ($) no relatório. Era um problema superficial que foi corrigido. (TGT-46995)
* Correção de um problema que fazia com que os intervalos de datas do relatório não funcionassem corretamente. (TGT-47396)
* Correção de um problema que fazia com que um status incorreto fosse exibido na página [!UICONTROL Todas as atividades] depois que os clientes ativavam ou desativavam uma atividade usando o ícone [!UICONTROL Mais ações]. (TGT-47367)
* Correção de um problema que fazia com que o relatório [!UICONTROL Atributos importantes] não fosse exibido para um cliente. (TGT-47272)
* Correção de um problema que fazia com que uma mensagem “Conteúdo inválido” fosse exibida quando um único cliente tentava habilitar a opção “Exigir autenticação”. (TGT-47195)
* Atualização de várias strings localizadas na interface do [!DNL Target].

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da Platform. |
| [Detalhes da versão da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

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
