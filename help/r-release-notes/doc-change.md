---
keywords: target documentation change log;documentation updates;new topics;edits;updates
description: Esta página lista alterações importantes feitas na documentação do Público alvo da Adobe, ordenadas por versões.
title: Alterações na documentação do produto Adobe Target.
topic: Standard
uuid: 6fba75e2-0a93-488d-9010-fffa423600c0
translation-type: tm+mt
source-git-commit: c22f2c375c15c5827f5c9884fbf948b99424c760
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 34%

---


# Alterações de documentação{#documentation-changes}

This page lists important changes made to the [!DNL Adobe Target] product documentation.

## Adobe Target Standard/Premium 20.4.1 (6 de maio de 2020) 

| Data | Tópico | Alterações |
| --- | --- | --- |
| Maio de 28 | [Perguntas frequentes de geração de relatórios](/help/c-reports/reporting-frequently-asked-questions.md) | Adicionadas as seguintes perguntas frequentes: <ul><li>Como as métricas Novos Visitantes e Visitantes de Retorno são contadas?</li></ul> |
| Maio de 27 | [Notas de versão do Target (pré-lançamento)](/help/r-release-notes/target-release-notes.md) | Foram adicionadas informações sobre o suporte do Analytics para Públicos alvos (A4T) para alocação automática de atividades. |
| Maio de 26 | [Atributos do perfil](/help/c-target/c-visitor-profile/profile-parameters.md) | Foram adicionadas as seguintes informações: &quot;O parâmetro permanece no perfil após desativar o script. Os usuários cujos perfis já contenham um parâmetro que seja usado em uma audiência de atividade se qualificarão nessa atividade.&quot; |
| Maio de 21 | [Nós de borda do Público alvo da lista de permissões](/help/c-implementing-target/c-considerations-before-you-implement-target/white-list-edges.md) | Adicionado `mboxedge30.tt.omtrdc.net` à lista. |
| Maio de 20 | [Notas de versão do Target (pré-lançamento)](/help/r-release-notes/target-release-notes.md) | Foram adicionadas informações sobre a próxima versão do Público alvo Standard/Premium 20.6.1 (10 de junho de 2020). |
|  | [Hosts](/help/administrating-target/hosts.md) | Foi adicionada uma observação à seção &quot;Práticas recomendadas de segurança&quot;. |
| Maio de 14 | [Notas de versão do Target (atual)](/help/r-release-notes/release-notes.md) | Foram adicionadas informações sobre alterações na API v2 de status de lote de Perfis. |
| Maio de 13 | [CNAME e Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | Adicionada a seção &quot;Limitações conhecidas&quot;. |
| Maio de 11 | [Hosts](/help/administrating-target/hosts.md) | Foram adicionadas informações sobre o uso da funcionalidade de ubox com redirecionamentos e listas brancas. |
|  | [Trabalhar com redirecionadores](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) | Foram adicionadas informações sobre o uso de hosts para evitar vulnerabilidades de redirecionamento aberto. |
|  | [Integração do Recommendations ao email](/help/c-recommendations/c-recommendations-faq/integrating-recs-email.md) | Foram adicionadas informações sobre o uso de hosts para evitar vulnerabilidades de redirecionamento aberto. |
|  | [Email: implementação do Target](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md) | Foram adicionadas informações sobre o uso de hosts para evitar vulnerabilidades de redirecionamento aberto. |
| Maio de 7 | [Notas de versão do Target (atual)](/help/r-release-notes/release-notes.md) | Com a próxima desaprovação do mbox.js em 30 de agosto de 2020, David Son, o gerente de produtos do Público alvo da Adobe lançou recentemente um bate-papo para o desenvolvedor discutir os benefícios da migração do mbox.js para o at.js. Há um link no qual você pode assistir ao webinar pelos próximos 30 dias. |
|  | [Controle de qualidade da atividade ](/help/c-activities/c-activity-qa/activity-qa.md) | Atualização da seção &quot;Considerações&quot;. |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | A linha &quot;overrideMboxEdgeServer&quot; foi atualizada em &quot;Configurações&quot;. |
| Maio de 6 | [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md) | Foram adicionadas informações sobre o ITP 2.3. |
|  | [Notas de versão](/help/r-release-notes/release-notes.md): 20.4.1 | Essa versão inclui aprimoramentos e correções. Você pode ler sobre eles e acessar a documentação a partir das notas de versão. Esta versão também inclui muitas atualizações da documentação na seção de ajuda. |

## Adobe Target Standard/Premium 20.2.1 (19 de fevereiro de 2020)

| Data | Tópico | Alterações |
| --- | --- | --- |
| Maio de 4 | [Perguntas frequentes de geração de relatórios](/help/c-reports/reporting-frequently-asked-questions.md#uneven) | Novas perguntas frequentes adicionadas: &quot;Por que o tráfego é dividido entre minhas experiências de forma irregular na minha atividade A/B ou MVT?&quot; |
| Abril de 29 | [Problemas conhecidos e problemas resolvidos](/help/r-release-notes/known-issues-resolved-issues.md) | Foi adicionado um problema conhecido para o relatórios com pedidos extremos. |
| Abril de 28 | [Glossário de variáveis e perfis](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md) | Foram removidas informações sobre o uso `user.header('x-forwarded-for')` com bordas AWS mais recentes para recuperar os endereços IP dos usuários. Esse comando agora funciona com bordas AWS mais recentes. |
|  | [Notas de versão do Target (pré-lançamento)](/help/r-release-notes/target-release-notes.md) | Data alterada da versão Público alvo Standard/Premium (20.4.1) para 6 de maio. |
| Abril de 23 | [CNAME e Adobe Target](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | Tópico atualizado. |
| Abril de 22 | [Notas de versão do Target (pré-lançamento)](/help/r-release-notes/target-release-notes.md) | Nova seção adicionada: *Alterações na API de status de lote de Perfis v2 (4 de maio de 2020).* |
| Abril de 20 | [Notas de versão do Target (atual)](/help/r-release-notes/release-notes.md) | Nova seção adicionada: *Construtor de habilidades do Público alvo da Adobe: Bate-papo no desenvolvedor, migre o mbox.js do Público alvo da Adobe para o at.js.* |
| Abril de 14 | [Hosts de borda do Público alvo da lista de permissões](/help/c-implementing-target/c-considerations-before-you-implement-target/white-list-edges.md) | Novo tópico. |
| Abril de 10 | [Implementação do aplicativo de página única](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md#bp) | Nova seção adicionada: &quot;Práticas recomendadas de implementação.&quot; |
| Abril de 7 | [Aumento e Confiança - Perguntas frequentes sobre o A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-lift-and-confidence.md#lift-condidence) | Texto atualizado para &quot;Por que não consigo ver incentivo e confiança nas métricas calculadas?&quot; |
| Abril de 2 | [Glossário de variáveis e perfis](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md) | Foram adicionadas informações sobre como usar `user.header('x-forwarded-for')` as bordas AWS mais recentes para recuperar os endereços IP dos usuários. |
|  | [Atualização do at.js 1.*x* para o at.js 2.*x *](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md) | Adição da seguinte observação:<ul><li>Depois de instalar a biblioteca da ECID v4.3.0+ e o at.js 2.*x*, você poderá criar atividades que abrangem domínios exclusivos e rastrear usuários. É importante observar que essa funcionalidade funciona somente após a sessão expirar.</li></ul> |
| 30 de março | [Problemas conhecidos e problemas resolvidos](/help/r-release-notes/known-issues-resolved-issues.md#atjs) | Adicionados problemas conhecidos que afetam as versões do at.js anteriores ao at.js 2.2.0. Esse problema fazia com que o rastreamento de cliques não relatasse conversões no Analytics para Público alvo (A4T) quando o código do Adobe Analytics não estava presente nos elementos da página. |
|  | [Detalhes da versão da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Foram adicionadas as seguintes informações aos detalhes da versão 2.2.0 do at.js:<ul><li>Correção de um problema que fazia com que o rastreamento de cliques não relatasse conversões no Analytics para Públicos alvos (A4T) quando o código do Adobe Analytics não estava presente nos elementos da página.</li></ul> |
| 25 de março | [Detalhes da versão da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Foram adicionadas informações sobre as seguintes novas versões do at.js:<ul><li>at.js versão 2.3.0</li><li>at.js versão 1.8.1</li></ul> |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Foram adicionadas as novas linhas a seguir na seção &quot;Configurações&quot;:<ul><li>cspScriptNonce</li><li>cspStyleNonce</li></ul>Adição da seguinte nova seção:<ul><li>Política de segurança de conteúdo</li></ul> |
| 24 de março | [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md#impact) | Foram adicionadas informações sobre os impactos para o seguinte:<ul><li>Scripts de Perfil com base em 3rdPartyID</li><li>URLs de QA/Pré-visualização em dispositivos iOS</li></ul> |
| 20 de março | [Notas de versão (atuais)](/help/r-release-notes/release-notes.md) | Indicado que a versão Público alvo Standard/Premium 20.2.1 será 23 de março de 2020. |
| 13 de março | [Limites](/help/r-troubleshooting-target/target-limits.md) | Número de &quot;Audiências reutilizáveis por conta&quot; atualizado. |
| 12 de março | [Notas de versão (atuais)](/help/r-release-notes/release-notes.md#summit) | Foram adicionadas informações de registro para acesso gratuito à conferência online do Digital Summit. |
| 9 de março | [Privacidade](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md) | Foram adicionadas mais informações na seção &quot;Substituição do último octeto de endereços IP&quot;. |
|  | [Trabalhar com atributos de vários valores](/help/c-recommendations/c-algorithms/work-with-multi-value-attributes.md) | Amostra de código atualizada em *Transmitir um parâmetro de vários valores em JavaScript*. |
|  | [Atributos de entidade personalizados](/help/c-recommendations/c-products/custom-entity-attributes.md) | Adição de amostra de código em *Uso de APIs* em *Implementação de atributos* de vários valores. |
| 4 de março | [Atributos do perfil](/help/c-target/c-visitor-profile/profile-parameters.md) | Atualização de todo o tópico, com revisões extensas para a seção &quot;Práticas recomendadas&quot;. |
| 21 de fevereiro | [Notas de versão (atuais)](/help/r-release-notes/release-notes.md) | Foram adicionadas informações sobre a nova navegação da Adobe Experience Cloud. |
| 20 de fevereiro | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Updated the description for the `enabled` setting. Foram adicionadas informações para as seguintes configurações: `pageLoadEnabled` e `viewsEnabled`. |
| 19 de fevereiro | [Notas de versão](/help/r-release-notes/release-notes.md) | Foram adicionadas informações sobre a futura desaprovação da biblioteca mbox.js. |
|  | [Geografia](/help/c-target/c-audiences/c-target-rules/geo.md) | Foi adicionada uma observação que `mboxOverride.browserIp` é suportada em at.js 1.somente *x.* |
|  | [Detalhes da versão da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Texto esclarecido explicando quais versões do at.js a equipe do Público alvo suporta. |
|  | [Notas de versão](/help/r-release-notes/release-notes.md): 20.2.1 | Essa versão inclui aprimoramentos e correções. Você pode ler sobre eles e acessar a documentação a partir das notas de versão. Esta versão também inclui muitas atualizações da documentação na seção de ajuda. |

## Adobe Target Standard/Premium 20.1.1 (4 de fevereiro de 2020)

| Data | Tópico | Alterações |
| --- | --- | --- |
| 4 de fevereiro | [Notas de versão](/help/r-release-notes/release-notes.md): 20.1.1 | Essa versão inclui aprimoramentos e correções. Você pode ler sobre eles e acessar a documentação a partir das notas de versão. Esta versão também inclui muitas atualizações da documentação na seção de ajuda. |
