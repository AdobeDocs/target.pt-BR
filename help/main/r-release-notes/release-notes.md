---
keywords: notas de versão;novos recursos;versões;atualizações;atualizar;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações;atualizações atuais;release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates;current updates
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
TQID: https://experienceleague.adobe.com/-Unx6cVsw3wch2LJgPtvBYPe-10rdpiJ4v9F7tMSP08
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2: id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 327891a5a9112dfacfca1c049adaef54b218676e
workflow-type: tm+mt
source-wordcount: 719
ht-degree: 37%

---

# Notas de versão do [!DNL Target] (atuais)

Explore os recursos, aprimoramentos e correções mais recentes no [!DNL Adobe Target]. Essas notas de versão também abrangem atualizações para APIs do [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outros componentes da plataforma, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## [!DNL Target Standard/Premium] 26.6.8 (24 de junho de 2026)

**Atividades**

+++Ver detalhes

* **O filtro Source para API e MCP criou recursos.** Correção de um problema em que a filtragem por [!UICONTROL API do Adobe Target] ou [!UICONTROL MCP do Adobe Target] não funcionava nas páginas de listagem de atividades, públicos e ofertas. (TGT-55236)

+++

**[!UICONTROL Analytics para Target] (A4T)**

+++Ver detalhes

* **Relatórios do A4T não visíveis.** Correção de um problema em que os relatórios do [!UICONTROL Analytics for Target] (A4T) não eram exibidos. (TGT-55432)

+++

**[!DNL Adobe Target]servidor MCP**

+++Ver detalhes

* **Ferramentas de atividade consolidadas.** As ferramentas de atividade do servidor MCP [!DNL Adobe Target] foram consolidadas para reduzir a sobrecarga de seleção de ferramentas e estender a cobertura de leitura e relatórios a todos os tipos de atividades. Seis ferramentas por tipo foram substituídas por quatro ferramentas unificadas:

   * `get_activity` substitui `get_ab_activity`, `get_xt_activity` e `get_abt_activity`. Recupera detalhes completos da atividade para todos os tipos: Teste A/B, Direcionamento de experiência, Automated Personalization, Alocação automática, Teste multivariado (MVT) e Recommendations. O tipo de atividade é detectado automaticamente a partir da ID.
   * `update_activity` substitui `update_ab_activity`, `update_xt_activity` e `update_abt_activity`. Oferece suporte a atividades de Teste A/B, Direcionamento de experiência e Automated Personalization; as atividades de Alocação automática, MVT e Recommendations são somente leitura.
   * `get_activity_performance_report` substitui `get_ab_performance_report` e `get_xt_performance_report`. Recupera métricas de conversão, aumento e confiança para todos os tipos de atividades.
   * `get_activity_orders_report` substitui `get_ab_orders_report` e `get_xt_orders_report`. Recupera métricas de pedido e receita para todos os tipos de atividades.

  Para obter mais informações, consulte [[!DNL Adobe Target] Referência de ferramentas do servidor MCP](../c-integrating-target-with-mac/mcp/target-mcp-tools-reference.md).

+++

## [!DNL Target Standard/Premium] 26.6.4 (16 de junho de 2026)

**Atividades**

+++Ver detalhes

* **[!UICONTROL Salvar e fechar] na interface atualizada [!DNL Target].** Restaurada a opção **[!UICONTROL Salvar e fechar]** na interface atualizada [!DNL Target]. (TGT-55152)

* **URLs de garantia da qualidade na interface do usuário [!DNL Target] atualizada.** Correção de um problema em que as URLs de garantia da qualidade não funcionavam corretamente na interface do usuário atualizada [!DNL Target]. ([TGT-55110](https://jira.corp.adobe.com/browse/TGT-55110))

+++

**Localização**

+++Ver detalhes

* **Cadeias de caracteres não localizadas no modal [!UICONTROL Criar Oferta JSON].** Correção de um problema em que as cadeias de caracteres no modal [!UICONTROL Criar Oferta JSON], incluindo [!UICONTROL Nome] e [!UICONTROL Workspace], não eram localizadas durante a criação da atividade. (TGT-50084)

* **Mensagem de notificação do sistema não localizada em uma atividade [!UICONTROL Recommendations].** Correção de um problema em que uma mensagem em caixa de informações não localizada aparecia ao adicionar recomendações em uma atividade [!UICONTROL Recommendations] baseada em formulário. (TGT-50463)

* **Sequência de caracteres não localizada nas [!UICONTROL Coleções] e [!UICONTROL Exclusões].** Correção de um problema em que a sequência de caracteres &quot;Carga do item&quot; não estava localizada nas caixas de diálogo [!UICONTROL Coleções] e [!UICONTROL Exclusões] em [!UICONTROL Recomendações]. (TGT-51542)

* **Cadeia de caracteres &quot;Aprovador&quot; deslocalizada na guia [!UICONTROL Públicos-alvo].** Correção de um problema em que a cadeia de caracteres &quot;Aprovador&quot; não estava localizada na coluna [!UICONTROL Workspace] da página [!UICONTROL Biblioteca de público-alvo]. (TGT-51751)

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
