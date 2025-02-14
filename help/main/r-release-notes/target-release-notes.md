---
keywords: notas de versão;versões;atualizações;versão futura;aprimoramentos;novos recursos;correções;atualizações;pré-lançamento;acesso antecipado;release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease;Early access
description: Saiba mais sobre os novos recursos, melhorias e correções adicionados na próxima versão do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos e melhorias que serão incluídos na próxima versão do  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 3aeac3344c2bbc2a44da80b5a359e55c9419b59b
workflow-type: tm+mt
source-wordcount: '1152'
ht-degree: 15%

---

# Notas de versão do [!DNL Target] (pré-lançamento)

Este artigo contém informações de pré-lançamento das próximas versões do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.

**Última atualização: sexta-feira, 13 de fevereiro de 2025**

>[!NOTE]
>
>As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.
>
>Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

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

Para obter mais informações, consulte [Ofertas](/help/main/c-experiences/c-manage-content/manage-content.md) e os subartigos desta seção.

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

<!-- 
## [!DNL Target Standard/Premium] 24.10.2 (October 21, 2024)

This release contains the following fixes:

* Fixed an issue that prevented [!UICONTROL Recommendations] activities from loading in [!UICONTROL Compose] and [!UICONTROL Browse] modes. (TGT-50709)
* Fixed an issue with the new [[!DNL Google Chrome] [!UICONTROL Visual Editing Helper] extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) that caused a redirect from the [!UICONTROL Visual Experience Composer] (VEC) to the [!UICONTROL Activities Library] after clicking Cancel. Before this fix, customers needed to refresh the [!UICONTROL Activities Library] before being able to create new activities. (TGT-49980)-->

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da Platform. |
| [Detalhes da versão da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
