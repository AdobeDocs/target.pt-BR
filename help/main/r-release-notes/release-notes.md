---
keywords: notas de versão;novos recursos;versões;atualizações;atualização;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Learn about the new features, enhancements, and fixes included in the current release of [!DNL Adobe Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: a791fbe805735b278f650ff1f087b85898a66a07
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 56%

---

# Notas de versão do [!DNL Target] (atuais)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium]. Além disso, as notas de versão para APIs [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outras alterações de plataforma também estão incluídas, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## [!DNL Target] Standard/Premium 23.3.1 (30 de março de 2023)

Esta versão está disponível de acordo com o seguinte agendamento:

* **28 de março**: regiões da Europa, Oriente Médio e África (EMEA)
* **29 de março**: região da Ásia-Pacífico (APAC)
* **30 de março**: região das Américas

Essa versão contém os seguintes novos recursos, aprimoramentos e correções:

| Recurso | Detalhes |
|--- |--- |
| Métricas otimizadas do A4T para [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático]<p>(Data de lançamento: 30 de março de 2023) | O [!DNL Target] permite escolher métricas baseadas em eventos binomiais ou em eventos contínuos ao usar o [!UICONTROL A4T] para as atividades de [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático].<P>Esteja ciente da seguinte alteração nas métricas compatíveis:<ul><li>O [!DNL Target] preservará o comportamento anterior para as atividades já existentes até 9 de setembro de 2023. Após essa data, as atividades usando métricas incompatíveis serão descontinuadas para forçar a migração de atividades existentes para o novo comportamento.</li></ul>Para obter mais informações, consulte &quot;Métricas de meta compatíveis&quot; em [Suporte a A4T para [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] atividades](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#supported).<br>Com esse recurso, os seguintes tutoriais foram atualizados:<ul><li>[Configuração de relatórios do A4T no [!DNL Analysis Workspace] para as atividades de [!UICONTROL Alocação automática]](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=pt-BR){target=_blank}</li><li>[Configuração de relatórios do A4T no [!DNL Analysis Workspace] para as atividades de [!UICONTROL Direcionamento automático]](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=pt-BR){target=_blank}</li></ul> |

* Sincronização aprimorada de público-alvo e atividade para que os itens criados em [!DNL Adobe Experience Platform] e [!DNL Adobe Audience Manager] estão disponíveis no [!DNL Target] Interface do usuário mais rápida. (TGT-44568)
* Interface do usuário aprimorada para permitir que os usuários removam o [!UICONTROL URL padrão] under [!UICONTROL Administração] > [!UICONTROL Visual Experience Composer] > [!UICONTROL URL padrão]. Essa alteração permite que os clientes alterem o URL padrão de volta para uma string vazia, o que anteriormente não era possível após a configuração inicial. (TGT-44577)
* Remoção de restrições que impedia clientes de editar ou excluir públicos-alvo prontos para uso (públicos-alvo com nomes reservados). (TGT-44655)
* Desativado o &quot;[!UICONTROL Concluído]&quot; ao carregar os giradores, a opção estava visível no [!DNL Target] IU ao criar [públicos-alvo combinados](/help/main/c-target/combining-multiple-audiences.md). (TGT-44079)
* Correção do [!UICONTROL Idioma] na parte inferior do [!UICONTROL Públicos-alvo] para que ele vincule corretamente ao &quot;[!UICONTROL Preferências de comunicação da conta]&quot;. (TGT-43562)
* Solução de um problema que, ocasionalmente, impedia que os clientes criassem [!UICONTROL Teste A/B] depois de selecionar a variável [!UICONTROL Adobe Analytics] opção em [!UICONTROL Administração] > [!UICONTROL Relatório] > [!UICONTROL Solução de relatório do Experience Cloud]. (TGT-44844)
* Correção de um problema que impedia que os clientes visualizassem a última experiência em um [!UICONTROL Teste multivariado] com muitas experiências dentro da variável [!UICONTROL Visual Experience Composer] (VEC). O [Caminho DOM](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) na parte inferior do VEC, às vezes, impedia que os clientes visualizassem a última experiência. (TGT-44578)
* Correção de um problema que fazia com que o URL de navegação no VEC não refletisse a página atual que está visível em uma sessão normal do navegador se a página requer autorização ou chama redirecionamentos. (TGT-44350)
* Correção de um problema que impedia que os clientes alterassem a configuração [!UICONTROL Filtrar critérios incompatíveis] definição em [!UICONTROL Recommendations] > [!UICONTROL Configurações]. (TGT-44398)
* Correção de um problema que fazia com que solicitações POST fossem criadas [!DNL Recommendations] os feeds falham ao usar [!UICONTROL Classificações do Analytics] com conjuntos de relatórios com pontos em seus nomes. (TGT-44598)
* Links atualizados na [!DNL Target] IU para apontar para a nova [Extensão do Visual Editing Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). (TGT-44459)
* Segurança aprimorada para impedir tentativas de falsificação de solicitação do lado do servidor (SSRF) em [!DNL Recommendations] feeds. (TGT-43769)
* Várias correções de localização foram feitas na interface do [!DNL Target].

## at.js versão 2.10.2 (7 de março de 2023)

* Correção de um problema que fazia com que a função `trackEvent` sempre retornasse um erro.

Para obter informações sobre todas as versões da at.js, consulte [Detalhes da versão da at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão do SDK da Web da Platform. |
| [Detalhes da versão da at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Alterações na documentação, notas de versão anteriores e notas de versão da Experience Cloud

Além das notas para cada versão, os recursos a seguir oferecem informações adicionais:

| Recurso | Detalhes |
|--- |--- |
| [Alterações de documentação](/help/main/r-release-notes/doc-change.md) | Veja informações detalhadas sobre atualizações neste manual que podem não estar incluídas nas notas de versão. |
| [Notas de versão para versões anteriores](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Veja informações sobre os novos recursos e aprimoramentos das versões anteriores do Target Standard e do Target Premium. |
| [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR){target=_blank} | Veja as notas de versão mais recentes para as soluções da Adobe Experience Cloud. |

## Informações de pré-lançamento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Os recursos a seguir permitem ver as novidades previstas para a próxima versão do Target.

| Recurso | Detalhes |
|--- |--- |
| [Atualização de produtos prioritários da Adobe](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Receba notificações antecipadas sobre aprimoramentos futuros de produtos para [!DNL Target] e outros [!DNL Adobe Experience Cloud] soluções. |
| [Notas de versão do Target - Pré-lançamento](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Informações sobre os lançamentos do Target do mês atual, incluindo informações de pré-lançamento. |
