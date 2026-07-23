---
keywords: notas de versão;novos recursos;versões;atualizações;atualizar;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações;atualizações atuais;release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates;current updates
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
TQID: https://experienceleague.adobe.com/-Unx6cVsw3wch2LJgPtvBYPe-10rdpiJ4v9F7tMSP08
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: c74d8b09fba181fcded2f982d99a03f1e7f3a07a
workflow-type: tm+mt
source-wordcount: 927
ht-degree: 29%

---

# Notas de versão do [!DNL Target] (atuais)

Explore os recursos, aprimoramentos e correções mais recentes no [!DNL Adobe Target]. Essas notas de versão também abrangem atualizações para APIs do [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outros componentes da plataforma, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## [!DNL Target Standard/Premium] 26.7.4 (23 de julho de 2026)

**Relatório**

+++Ver detalhes

* **O gráfico de taxas de conversão não está disponível para o público móvel específico.** Correção de um problema em que o gráfico [!UICONTROL Taxa de conversão] não era renderizado para determinados públicos móveis. (TGT-55611)

* **A meta de conversão &quot;Visualizou uma mbox&quot; não está funcionando quando selecionada na lista suspensa.** Correção de um problema em que selecionar uma mbox na lista suspensa em [!UICONTROL Metas e configurações] para uma meta de conversão &quot;Visualizou uma mbox&quot; salvava o nome da mbox incorretamente, impedindo que as conversões fossem gravadas. (TGT-55588)

+++

**Públicos-alvo**

+++Ver detalhes

* **Problema de layout na página Biblioteca de público-alvo.** Correção de um problema de layout que ocorria quando os filtros eram ativados na página [!UICONTROL Biblioteca de público-alvo] enquanto a navegação lateral era recolhida. (TGT-55502)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Ver detalhes

* **A versão móvel não é carregada corretamente.** Correção de um problema em que o [!UICONTROL Visual Experience Composer] não oferecia uma maneira de atualizar, impedindo que a exibição móvel fosse carregada corretamente. (TGT-54408)

* **Editar ou excluir ações de modificação que não funcionam.** Correção de um problema em que a edição ou exclusão de uma modificação da exibição [!UICONTROL Editar experiência] não funcionava. (TGT-55250)

* **Modo de navegação sem resposta após o carregamento da atividade.** Correção de um problema em que o modo [!UICONTROL Procurar] não respondia em experiências que continham uma modificação, impedindo navegação e criação futuras. (TGT-55306)

* **Não é possível selecionar elementos dentro do Salesforce LWC (DOM Sombra).** Correção de um problema em que o [!UICONTROL Visual Experience Composer] não podia selecionar elementos aninhados nos Componentes Web do Salesforce Lightning usando o DOM de sombra, resultando em um erro de &quot;seletor não encontrado&quot;. (TGT-54956)

* **Ofertas duplicadas apareceram no [!UICONTROL Visual Experience Composer].** Correção de um problema em que as modificações e ofertas apareciam duplicadas intermitentemente na interface do usuário da criação de atividades. (TGT-55685)

+++

**Administração**

+++Ver detalhes

* **O assistente de geração de conteúdo foi renomeado para [!UICONTROL Gerar conteúdo].** O recurso de geração de conteúdo &quot;Assistente de IA&quot; foi renomeado para [!UICONTROL Gerar conteúdo] pelas superfícies de interface do usuário [!DNL Target]. (TGT-55689)

+++

**Recomendações**

+++Ver detalhes

* **Recomendações baseadas em popularidade usando atributos de perfil.** O [!DNL Target] agora oferece suporte ao agrupamento de recomendações de popularidade, Mais Visualizados e Mais Vendidos, dinamicamente por atributos de perfil do visitante, como país, idioma preferencial ou nível de associação. (TAPER-7614)

* **Incompatibilidade de coleção de recomendação entre [!UICONTROL Coleções] e a configuração de atividade.** Correção de um problema em que uma coleção [!UICONTROL Recommendations] retornava entidades adicionais não qualificadas quando visualizadas a partir da configuração da atividade em comparação à exibição [!UICONTROL Recommendations] > [!UICONTROL Coleções]. (TGT-55554)

+++

## [!DNL Target Standard/Premium] 26.7.2 (16 de julho de 2026)

**Atividades**

+++Ver detalhes

* **Informações de meta incorretas na página [!UICONTROL Visão geral da atividade].** Correção de um problema em que a página [!UICONTROL Visão geral da atividade] para atividades [!DNL Automated Personalization] mostrava metas adicionais em vez da meta de otimização. (TGT-55553)

* **Tela sem resposta ao navegar pelas páginas no modo [!UICONTROL Procurar].** Correção de um problema em que a tela ficava sem resposta ao navegar entre páginas no modo [!UICONTROL Procurar]. (TGT-55565)

+++

**Página inicial**

+++Ver detalhes

* **Alteração na interface do usuário de [!UICONTROL Principais executores] e [!UICONTROL Salvamentos].** Atualização da interface do usuário para os melhores desempenhos e salva a experiência. (TGT-54975)

+++

**Públicos-alvo**

+++Ver detalhes

* **Cadeias de caracteres não localizadas na caixa de diálogo [!UICONTROL Criar Script de Perfil].** Correção de um problema em que as cadeias de caracteres na caixa de diálogo [!UICONTROL Criar Script de Perfil] não eram localizadas. (TGT-51527)

+++

## [!DNL Target Standard/Premium] 26.7.1 (9 de julho de 2026)

**Atividades**

+++Ver detalhes

* **Exibição de origem inconsistente em [!UICONTROL Atividades], [!UICONTROL Públicos-alvo] e [!UICONTROL Ofertas] páginas.** Correção de um problema em que a origem era exibida de forma inconsistente nas [!UICONTROL Atividades], [!UICONTROL Públicos-alvo] e [!UICONTROL Ofertas] páginas. (TGT-55247)

* **A origem da atividade é alterada durante a edição via interface.** Correção de um problema em que a edição de uma atividade por meio da interface alterava a fonte da atividade original. (TGT-55248)

+++

**Públicos-alvo**

+++Ver detalhes

* **Espaço de trabalho padrão incorreto ao editar um público-alvo.** Correção de um problema em que o espaço de trabalho padrão estava incorreto após você editar um público. (TGT-55510)

+++

**Relatório**

+++Ver detalhes

* **Falha no download do CSV para os relatórios de maio.** Correção de um problema em que o download de um relatório CSV para maio falhava. (TGT-55524)

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
