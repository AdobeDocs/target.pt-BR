---
keywords: notas de versão;novos recursos;versões;atualizações;atualizar;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações,atualizações atuais
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: fe370f57978ace161ca2ba2b9f6b11ae8f9b4cfa
workflow-type: tm+mt
source-wordcount: '1669'
ht-degree: 19%

---

# Notas de versão do [!DNL Target] (atuais)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium]. Além disso, as notas de versão para APIs [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outras alterações de plataforma também estão incluídas, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## [!DNL Target Standard/Premium] 25.3.1 (3 de março de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Um público-alvo combinado pode incluir subgrupos, cada um contendo vários públicos-alvo. Esta versão corrigiu um problema que impedia que públicos-alvo de subgrupos fossem exibidos na caixa de diálogo [!UICONTROL Rules]. (TGT-51813)
* Solução de um problema em que alguns públicos-alvo de experiência eram substituídos por [!UICONTROL All Visitors] ao abrir atividades mais antigas. (TGT-51812)
* Solução de um problema que impedia a edição de atividades com públicos somente atividade. (TGT-51807)
* Solução de um problema que impedia a edição de modificações no cabeçalho da página na interface atualizada do usuário do [!DNL Target]. (TGT-51797)
* Correção de um erro nulo que ocorria ao duplicar uma experiência, excluir outra experiência e tentar salvar a atividade. (TGT-51796)
* Correção de um problema que impedia a exibição de regras de exclusão de público-alvo no painel de informações do público-alvo durante a etapa [!UICONTROL Targeting] da criação de atividades. (TGT-51579)
* Mensagens de erro atualizadas localizadas em coreano. (TGT-51701 e TGT-51699)

## [!DNL Target Standard/Premium] 25.2.3 (26 de fevereiro de 2025)

Esta versão do inclui as seguintes atualizações:

* Solução de um problema que impedia as atualizações de atividade após a versão [!DNL Target] 25.2.1 para algumas atividades. (TGT-51781)
* Solução de um problema em que todas as alterações de público-alvo no estado eram removidas ao cancelar o processo de criação de atividade (selecionando [!UICONTROL Cancel] em vez de [!UICONTROL Add Audience]). (TGT-51769 e TGT-51770)
* Solução de um problema em que o [!UICONTROL Visual Experience Composer] (VEC) não era carregado para algumas atividades, principalmente quando um código personalizado era usado.  O problema fez com que o VEC exibisse uma tela em branco ou a interface do usuário do [!DNL Target] revertesse para sua versão mais antiga. (TGT-51758)
* Correção de um problema em que as modificações eram descartadas após a edição da entrega de página para públicos-alvo. (TGT-51756)
* Solução de um problema em que todos os públicos-alvo não métricos (públicos-alvo de página e experiência) eram removidos das atividades ao alterar um tipo de métrica na página [!UICONTROL Goals & Settings]. (TGT-51753)
* Solução de um problema em que clicar em [!UICONTROL Cancel] ao editar uma atividade navegava pela interface do usuário de Destino para [!UICONTROL Activities List] em vez da página [!UICONTROL Activity Details]. (TGT-51731)
* Solução de um problema que impedia os clientes de baixar relatórios por meio da opção [!UICONTROL Export Reports to CSV]. (TGT-51708)
* Solução de um problema no Experience Composer baseado em formulário, no qual [!DNL Target Standard] clientes eram exibidos incorretamente como usando [!UICONTROL Properties], um recurso [!DNL Target Premium]. (TGT-51678)
* Correção de um problema que impedia a exibição de atributos do [!DNL Adobe Experience Platform] ao criar novas ofertas. (TGT-51665)
* Todos os filtros ativos do inventário [!DNL Recommendations] foram movidos para a pesquisa rápida, alinhando a interface com [!UICONTROL Catalog Search] em vez do painel [!UICONTROL Filter]. (TGT-50723)

## at.js versão 2.11.7 (26 de fevereiro de 2025)

Esta versão inclui a seguinte atualização:

* Log de Telemetria Corrigida quando `localStorage` não está disponível. A telemetria estava causando um problema para alguns clientes que tinham o `localStorage` desativado nos navegadores.

Para obter informações sobre esta versão e versões anteriores da at.js, consulte [detalhes de versão da at.js](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions){target=_blank}.

## Target Standard/Premium 25.2.1 (terça-feira, 17 de fevereiro de 2025)

Esta versão do inclui as seguintes atualizações:

* [!UICONTROL Activities] atualização da interface do usuário
* [!DNL Recommendations] atualização da interface do usuário

### [!UICONTROL Activities] atualização da interface do usuário

Conforme o esforço de modernização da interface do usuário do [!DNL Adobe Target] continua, temos o prazer de anunciar a disponibilidade geral da interface do usuário do [!UICONTROL Activities] atualizada.

>[!NOTE]
>
>A partir de 17 de fevereiro, os clientes terão acesso gradual à nova interface do usuário do [!UICONTROL Activities]. Para garantir uma implantação perfeita para todos os clientes, esta versão será implantada em estágios controlados. O primeiro estágio atualizará o grupo inicial de clientes [!DNL Target] para a nova interface do usuário [!UICONTROL Activities]. Os estágios subsequentes atualizarão os clientes restantes.

Com base no sistema de design [!DNL Adobe Spectrum] mais recente, a atualização padroniza padrões de design anteriormente inconsistentes, além de adicionar novas melhorias, como:

* [Relatórios reprojetados](/help/main/administrating-target/reporting.md) para obter melhores insights sobre os resultados da atividade.
* Página [[!UICONTROL Updated Change Log]](/help/main/c-activities/change-log.md), obtendo agora as informações de [[!DNL Audit Query API]](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/audit-logs/audit-api/overview){target=_blank} para insights em tempo real.
* [Exibições de lista personalizáveis](/help/main/c-activities/activities.md) para oferecer mais flexibilidade entre diferentes necessidades de equipe.
* [Triagens de detalhes e informações rápidas](/help/main/c-activities/activities.md) aprimoradas para facilitar o acesso às informações.
* [Opções de filtro e pesquisa persistentes em sessão](/help/main/c-activities/activities.md).
* O [recriou completamente o [!UICONTROL Visual Editing Composer]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) com suporte para as últimas atualizações de segurança de provedores de navegador e uma interface de usuário moderna.

  Para obter informações sobre como o VEC atualizado difere da versão anterior, consulte:

   * [Alterações no Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)
   * [Opções do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)

* [Atualização [!DNL Chrome] extensão](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) com suporte para Manifest V3 para maior segurança e suporte aprimorado para cookies próprios.

![Atividades atualizadas](/help/main/r-release-notes/assets/activities-refresh.png)

### [!DNL Recommendations] atualização da interface do usuário

Conforme o esforço de modernização da interface do usuário do [!DNL Adobe Target] continua, temos o prazer de anunciar a disponibilidade geral da interface do usuário do [!DNL Recommendations] atualizada.

>[!NOTE]
>
>A partir de 17 de fevereiro, os clientes terão acesso gradual à nova interface do usuário do [!UICONTROL Recommendations]. Para garantir uma implantação perfeita para todos os clientes, esta versão será implantada em estágios controlados. O primeiro estágio atualizará o grupo inicial de clientes [!DNL Target] para a nova interface do usuário [!UICONTROL Activities]. Os estágios subsequentes atualizarão os clientes restantes.

Com base no sistema de design [!DNL Adobe Spectrum] mais recente, a atualização padroniza padrões de design anteriormente inconsistentes, além de adicionar novas melhorias, como:

* A [pesquisa no catálogo de produtos](/help/main/c-recommendations/c-products/catalog-search.md) agora apresenta um banco de dados atualizado que permite a sincronização de produtos em tempo real.
* [!UICONTROL Recommendations] objetos ([!UICONTROL Criteria], [!UICONTROL Designs], [!UICONTROL Collections] e [!UICONTROL Exclusions]) [criados através da API agora estão disponíveis na interface](/help/main/c-recommendations/c-recommendations-faq/recommendations-faq.md).
* [As configurações do Recommendations](/help/main/administrating-target/recommendations-settings.md) foram consolidadas na seção [!UICONTROL Administration].
* Exibições de lista personalizáveis para maior flexibilidade entre diferentes necessidades da equipe.
* Editores de código HTML e JSON atualizados com [realce de sintaxe e numeração de linha](/help/main/c-experiences/c-manage-content/create-json-offer.md).
* Melhorias nas telas de detalhes e informações rápidas para facilitar o acesso às informações.
* Opções de filtro e pesquisa persistentes na sessão.

![Atualização da interface do usuário do Recommendations](/help/main/r-release-notes/assets/recs-ui-refresh.png)

## Target Standard/Premium 25.1.1 (sexta-feira, 9 de janeiro de 2025)

Esta versão do inclui as seguintes atualizações:

### [!UICONTROL Offers Library] atualização da interface do usuário

Para aprimorar a experiência do usuário para [!DNL Adobe Target] usuários, esta versão atualiza a interface do usuário [!UICONTROL Offers Library].

>[!NOTE]
>
>Para garantir uma implantação perfeita para todos os clientes, esta versão será implantada em estágios controlados. O primeiro estágio atualizou o grupo inicial de clientes do Target para a nova interface do usuário de ofertas. Os estágios subsequentes atualizarão os clientes restantes.

Usando o sistema de design [!DNL Adobe Spectrum] mais recente, esta atualização padroniza padrões de design inconsistentes e introduz novas melhorias, incluindo as seguintes:

* **Gerenciamento de ofertas em massa**: selecione e exclua ou mova várias ofertas simultaneamente.

* **[!UICONTROL Code Editor]atualizações**: editores HTML e JSON atualizados com realce de sintaxe e numeração de linha.

* **Cartões de oferta aprimorados**: cartões de informações e detalhes rápidos aprimorados para facilitar o acesso às informações.

* **Pesquisa e filtros persistentes**: adiciona opções de pesquisa e filtro persistentes na sessão.

Para obter mais informações, consulte [Ofertas](/help/main/c-experiences/c-manage-content/manage-content.md) e os subartigos desta seção. Todos os artigos de Ofertas nesta seção foram atualizados para refletir essas alterações na interface.

Este é um vídeo curto que destaca as alterações nesta versão:

![Vídeo de atualização da interface do usuário das ofertas](/help/main/r-release-notes/assets/offers-video-v2.gif)

## [!DNL Adobe Experience Platform Web SDK] Otimização de escopo do `__view__` (22 de outubro de 2024)

Entre 22 de julho de 2024 e 15 de agosto de 2024, a equipe do [!DNL Target] otimizou o escopo do `__view__`, melhorando a precisão da impressão da atividade, da visita e dos relatórios de visitantes. Essa otimização tem como objetivo capturar automaticamente dados de relatórios para apresentações renderizadas automaticamente e deve ser transparente para a maioria das contas.

Todos os novos clientes do [!DNL Adobe Experience Platform Web SDK] terão essa otimização habilitada. No entanto, os clientes que migraram da at.js e não seguiram as etapas de implementação abaixo têm a otimização desativada. Recomendamos que esses clientes analisem suas implementações até 3 de fevereiro de 2025. Após essa data, habilitaremos a otimização para todos os clientes. Falhas ao revisar e ajustar as implementações até lá podem afetar os relatórios, conforme mencionado abaixo. Entre em contato com [!DNL Adobe Customer Care] se precisar confirmar se a implementação foi afetada ou se precisar de mais tempo para ajustar a implementação.

>[!IMPORTANT]
>
>Se não conseguir concluir sua análise de implementação e resolver qualquer problema até 3 de fevereiro de 2025, você poderá solicitar uma extensão única de seis meses. Verifique se sua solicitação foi enviada até 31 de janeiro de 2025. O Adobe analisará e decidirá sua solicitação.

Para se beneficiar dessa otimização em caso de renderização manual de propostas, revise seu [[!DNL Platform Web SDK implementation]](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank} para garantir que você esteja enviando notificações após renderizar experiências manualmente ou ao usar o método `applyPropositions` (ou a ação [!DNL Launch] correspondente como auxiliar) para renderizar experiências.

Os cenários mais comuns quando as experiências são renderizadas manualmente incluem:

* Uso de ofertas JSON
* Usando um escopo de decisão personalizado em uma atividade criada no [[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md)
* Não está usando `renderDecisions: true` ao buscar uma atividade criada com o [!UICONTROL Form-Based Experience Composer] que usa o escopo global `__view__`

Se as notificações não forem implementadas conforme documentado em [Renderizar conteúdo personalizado](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/personalization/rendering-personalization-content){target=_blank} no guia *Coleta de dados*, os dados de relatório poderão estar ausentes em [!DNL Target] e em [Relatórios do Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Em determinados cenários, você pode notar uma divisão de tráfego incorreta, pois os dados de relatório não são capturados. Ou, em outros cenários, relatar o mesmo evento repetidamente.

Dependendo da sua implementação, verifique se há [!DNL Analytics] e impactos dos relatórios do A4T.

O [!DNL Platform Web SDK] oferece suporte a dois tipos de implementação para renderização de experiências e personalizações:

* **Chamada única para personalização e medição.**

  Inicialmente recomendada, a abordagem de chamada única para [!DNL Platform Web SDK] está agendada para ser descontinuada em favor da abordagem de chamada dividida. A Adobe aconselha todas as novas implementações a usarem a nova abordagem de chamada dividida e recomenda que os clientes existentes também façam a transição para o método de chamada dividida.

  Se você continuar usando a abordagem de chamada única, poderá observar as seguintes alterações inesperadas em seus relatórios do [!DNL Analytics]:

   * Um declínio nas rejeições.
   * As ocorrências do A4T e do [!UICONTROL Page View] não são compiladas, tornando desafiador executar determinados detalhamentos e correlações dos relatórios do A4T usando eVars e eventos do [!DNL Analytics].

* **Dividir chamadas (também conhecido como eventos da parte superior e inferior da página).**

  Este tipo de implementação é a nova [abordagem de implementação de split-call](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/use-cases/top-bottom-page-events){target=_blank} recomendada por [!DNL Adobe]. Com esta abordagem, a nova otimização não afeta os relatórios do [!DNL Analytics] ou do A4T.

Em caso de dúvidas, entre em contato com o [Atendimento ao cliente da Adobe](/help/main/cmp-resources-and-contact-information.md##reference_ACA3391A00EF467B87930A450050077C). (KB-2179)

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
