---
keywords: notas de versão;novos recursos;versões;atualizações;atualizar;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações;atualizações atuais;release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates;current updates
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do [!DNL Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
TQID: 'https://experienceleague.adobe.com/-Unx6cVsw3wch2LJgPtvBYPe-10rdpiJ4v9F7tMSP08'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
  - id: c5abb976-5170-45d6-bcac-66d15d10a4d4
    internal-label: Release notes
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: ece061af0f50ec45e07b9710d355a9c91731578e
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 42%
---
# Notas de versão do [!DNL Target] (atuais)

Explore os recursos, aprimoramentos e correções mais recentes no [!DNL Adobe Target]. Essas notas de versão também abrangem atualizações para APIs do [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outros componentes da plataforma, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## [!DNL Target Standard/Premium] 26.10.2 (15 de outubro de 2026)

**[!UICONTROL Atividades]**

+++Ver detalhes

* **Configurações de meta incorretas exibidas na Visão Geral da Atividade**. Correção de um problema em que as configurações da meta mostradas na página **[!UICONTROL Visão geral]** de uma atividade estavam incorretas. Por exemplo, `https://` foi adicionado à URL da página, e a condição **[!UICONTROL URL contém]** não foi exibida, mesmo que a configuração de meta real estivesse correta. (TGT-56326)

+++

**[!UICONTROL Recomendações]**

+++Ver detalhes

* **Recomendações de backup exibidas após uma promoção ser atualizada em uma atividade online**. Correção de um problema em que a edição de uma promoção em uma atividade [!DNL Recommendations] em tempo real fazia com que [!DNL Target] criasse novas promoções e unidades de recomendação, mesmo que nada mudasse em sua definição. (TGT-56369)

+++

**[!UICONTROL Relatórios]**

+++Ver detalhes

* **Predefinições de relatório excluídas após duas semanas**. Correção de um problema em que as predefinições de relatório salvas pelos usuários em uma atividade eram excluídas automaticamente após aproximadamente duas semanas. (TGT-56374)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Ver detalhes

* **Suporte ao Safari adicionado a[!DNL Adobe Target]**. Agora há suporte para [!DNL Target] no navegador [!DNL Safari]. Observe que o Visual Experience Composer e [!DNL Enhanced Experience Composer] não são suportados no [!DNL Safari]. Como resultado, uma sobreposição agora aparece no [!DNL VEC] para notificar os usuários que eles devem alternar para [!DNL Chrome] para usar o editor. (TGT-55853)
  [Saiba mais](../c-experiences/c-visual-experience-composer/visual-experience-composer.md#browser-requirements)
+++


## [!DNL Target Standard/Premium] 26.10.1 (13 de outubro de 2026)

**[!UICONTROL Análises para Destino]**

+++Ver detalhes

* **Falha no relatório do A4T com um erro &quot;Algo deu errado&quot;**. Correção de um problema em que as atividades [!DNL A4T] usando um conjunto de relatórios recém-adicionado exibiam o erro &quot;Algo deu errado&quot; no relatório [!DNL Target] em vez dos resultados. Clicar em **[!UICONTROL Exibir no Analytics]** também exibiu uma mensagem &quot;Conjunto de relatórios incompatível&quot; com informações de classificação [!DNL Analytics for Target] ausentes. (TGT-56389)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Ver detalhes

* **Raw HTML exibido em vez do nome da oferta para [!DNL Experience Fragments] entregue através de uma mbox**. Correção de um problema em que o painel **[!UICONTROL Modificações]** exibia HTML/código bruto em vez do nome da oferta quando uma [!DNL Experience Fragment] era entregue por meio de uma mbox. (TGT-56241)

+++

## Atualizações sensíveis ao tempo que você precisa saber {#time-sensitive}

[!BADGE Importante]{type=Informative}

Para atualizações com limite de tempo relacionadas ao [!DNL Adobe Target] e à sua implementação, o [!DNL Adobe] fornece notas de versão e documentação detalhadas por meio do [!UICONTROL Experience League]. Estes são alguns destaques importantes para sua implementação:

### Desativação da alternância de versão da interface do usuário [!DNL Target]

Para obter mais informações, consulte [[!DNL Target] Perguntas frequentes sobre atualização da interface](/help/main/c-intro/updated-ui-faq.md).

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da plataforma. |
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
