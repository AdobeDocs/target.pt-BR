---
keywords: notas de versão;novos recursos;versões;atualizações;atualização;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: dbf9a51044f317d02a705f2331d6dc58b6549606
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 100%

---

# Notas de versão do [!DNL Target] (atuais)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium]. Além disso, as notas de versão para APIs [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outras alterações de plataforma também estão incluídas, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## [!DNL Target] Standard/Premium 23.9.4 (4 a 6 de outubro de 2023)

Esta versão estará disponível de acordo com o seguinte cronograma:

* **4 de outubro**: região da Ásia-Pacífico (APAC)
* **5 de outubro**: região da Europa, Oriente Médio e África (EMEA)
* **6 de outubro**: região das Américas

Essa versão conta com os seguintes aprimoramentos e correções:

| Recurso | Detalhes |
| --- | --- |
| Atualização da interface de [!UICONTROL Atividades]<P>e<P>Atualização da interface de [!UICONTROL Feeds] | Como parte do esforço contínuo da equipe do [!DNL Adobe Target] em aprimorar a experiência para usuários do [!DNL Target], esta versão atualiza as páginas [!UICONTROL Atividades] e [!DNL Recommendations] [!UICONTROL Feeds] na interface do [!DNL Target]. Essa atualização unifica e uniformiza padrões de design que eram inconsistentes, além de adicionar novas melhorias.<P>Para obter mais informações, consulte [Atividades](/help/main/c-activities/activities.md) e [Feeds](/help/main/c-recommendations/c-products/feeds.md). |
| Padrão de implementação do [!DNL Recommendations] | Os artigos da seção *Padrão de implementação do Recommendations com o uso da at.js* ajudam você a entender e criar uma implementação do [!DNL Adobe Target Recommendations] usando a biblioteca JavaScript da at.js.<P>Para obter mais informações, consulte a visão geral do [Padrão de implementação do Recommendations com o uso da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/recs-implementation-pattern-atjs.html?lang=pt-BR){target=_blank} no *Guia de desenvolvimento do Adobe Target*. |

* Adição de aprimoramentos do [!UICONTROL Visual Experience Composer] (VEC) para estruturas dinâmicas. (TGT-44064)
* Correção de um problema que atualizava incorretamente a data selecionada na solicitação `getViewInAnalyticsId`. Essa correção ajuda a recalcular o link do [!DNL Analytics] nos relatórios quando as configurações de intervalo de datas e métricas do relatório são alteradas. (TGT-46246)

## [!DNL Target] Standard/Premium 23.9.3 (18 de setembro de 2023)

Essa versão conta com os seguintes aprimoramentos e correções:

* Aprimoramento do [!UICONTROL Visual Experience Composer] (VEC) para oferecer suporte a componentes Lightning Web (DOM de luz). (TGT-45422)
* Correção de um problema que fazia com que as ações do VEC fossem aplicadas na ordem incorreta. Em alguns casos, o VEC aplicava algumas modificações de forma assíncrona e adicionar modificações extras a um elemento causava erros se esse elemento fosse exibido após uma ação [!UICONTROL Inserir]. Também corrige o URL do VEC que agora é atualizado ao clicar em links de âncora. (TGT-45983)
* Correção de um problema com o recurso [!UICONTROL Sobreposição] do VEC, que agora oferece suporte a elementos em DOMs de sombra. (TGT-45202 e TGT-45262)
* Correção de um problema ao abrir uma página de Aplicativo de página única (SPA) no VEC e acessar o modo [!UICONTROL Procurar] que fazia com que as setas Voltar e Avançar não funcionassem corretamente. (TGT-45956)
* Correção de um problema que impedia o carregamento de algumas páginas da Web no VEC. (TGT-45983)

## [!DNL Target] Standard/Premium 23.9.2 (12 a 14 de setembro de 2023)

Esta versão estará disponível de acordo com o seguinte cronograma:

* **12 de setembro**: região das Américas
* **13 de setembro**: região Ásia-Pacífico (APAC)
* **14 de setembro**: regiões da Europa, Oriente Médio e África (EMEA)

Essa versão conta com os seguintes aprimoramentos e correções:

* Alteração da API do [!DNL Analytics] para a nova API versão 2.0 do [!DNL Analytics]. (TGT-45345)
* Correção de problemas que afetavam atividades da [!UICONTROL Automated Personalization] (AP) para alguns clientes, incluindo a sincronização oportuna da atividade no back-end do [!DNL Target] e a entrega da experiência esperada nos links de visualização. (TGT-46202)

## [!DNL Target] Standard/Premium 23.9.1 (6 a 11 de setembro de 2023)

Esta versão estará disponível de acordo com o seguinte cronograma:

* **6 de setembro**: região das Américas
* **7 de setembro**: regiões da Europa, Oriente Médio e África (EMEA)
* **11 de setembro**: região Ásia-Pacífico (APAC)

Essa versão conta com os seguintes aprimoramentos e correções:

* Correção de um problema que causava inconsistência nos dados de relatórios na interface do [!DNL Target] e do [!DNL Adobe Analytics] para atividades de [!UICONTROL Alocação automática] que usam o [!UICONTROL Analytics for Target] (A4T) como fonte de relatórios. (TGT-46112)
* O tempo limite das chamadas de PUT para a API de entrega do Target foi aumentado para 15 segundos para evitar erros de tempo limite. (TGT-46091)
* Correção de um problema que impedia a atualização consistente do URL ao navegar por um site de aplicativo de página única (SPA). (TGT-45417)

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
