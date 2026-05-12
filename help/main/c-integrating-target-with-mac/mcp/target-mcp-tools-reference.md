---
solution: Target
product: target
title: Referência de ferramentas do servidor do Adobe Target MCP
description: Referência completa do parâmetro para todas as 21 ferramentas somente leitura expostas pelo servidor MCP do Adobe Target.
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: Developer, User
level: Intermediate, Experienced
source-git-commit: 7b0c8b18abe2db4e07e3ef979d6d194f4c4c81d6
workflow-type: tm+mt
source-wordcount: '1698'
ht-degree: 11%

---

# Referência de ferramentas do servidor MCP [!DNL Adobe Target] {#target-mcp-tools-reference}


>[!AVAILABILITY]
>
>O servidor MCP [!DNL Adobe Target] está disponível para todos os clientes em **Beta Público**. Atualmente, ele tem suporte no **Claude Web**, **Claude Desktop**, **Claude Code**, **Cursor** e **ChatGPT**.

Esta página é uma referência completa para todas as ferramentas somente leitura expostas pelo servidor MCP [!DNL Adobe Target]. Para cada ferramenta, você encontrará uma descrição, detalhes do parâmetro, valor de retorno e um exemplo de prompt em linguagem natural. Para obter instruções de configuração e casos de uso, consulte [Introdução](target-mcp-get-started.md) e [Casos de uso e apresentações](target-mcp-use-cases.md).

>[!IMPORTANT]
>
>O protocolo de contexto de modelo (MCP) é um padrão de código aberto emergente e pode apresentar riscos de segurança ou confiabilidade. As integrações do servidor Adobe MCP e a documentação relacionada são fornecidas &quot;no estado em que se encontram&quot;, sem garantias de nenhum tipo.
>
>Conectar clientes ou servidores MCP a produtos Adobe é uma configuração escolhida pelo cliente, e os clientes são responsáveis por avaliar a segurança e a adequação de qualquer integração MCP. O Adobe não é responsável por problemas resultantes de configuração incorreta, uso incorreto do MCP, vulnerabilidades em implementações de terceiros ou ações não intencionais executadas por meio de fluxos de trabalho habilitados para MCP.
>
>Para reduzir os riscos, a Adobe incentiva o teste de integrações em um ambiente de sandbox antes do uso produtivo e a análise e validação cuidadosas de todas as ações e respostas iniciadas pelo MCP antes de confirmar ou confiar nelas.

## Pré-requisitos {#tools-prerequisites}

Sua função [!DNL Adobe Target] determina quais ferramentas estão disponíveis para você:

* Função de **Observador** ou superior: acesso a todas as ferramentas de leitura
* Função de **Editor**: acesso a ferramentas de leitura e gravação (criar)
* Função do **Aprovador**: acesso a ferramentas de leitura, gravação e ativação/desativação

Para obter instruções completas sobre a configuração, consulte [Introdução](target-mcp-get-started.md).

## Ferramentas de atividade {#tools-activities}

+++Listar atividades

**Ferramenta:** `list_target_activities`

Listar [!DNL Adobe Target] atividades com filtragem e classificação do lado do servidor.

Recupera uma lista paginada de atividades. Todos os filtros são aplicados no lado do servidor pela API de Administração [!DNL Target]. O servidor retorna no máximo 200 atividades por página.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `limit` | número inteiro | Não | Número máximo de atividades a serem retornadas (máx. do servidor: 200) |
| `offset` | número inteiro | Não | Número de atividades a serem ignoradas para paginação |
| `sort_by` | string | Não | Campo de acordo com o qual classificar. Prefixo com `-` para ordem decrescente (por exemplo, `-modifiedAt`). Opções: `id`, `name`, `state`, `priority`, `startsAt`, `endsAt`, `lifetimeStart`, `lifetimeEnd`, `createdAt`, `createdBy`, `modifiedAt`, `modifiedBy`, `type`, `thirdPartyId` |
| `state` | string | Não | Filtrar por estado de atividade: `approved` (ativo/ativo), `deactivated` (inativo), `paused`, `saved` (rascunho) |
| `activity_type` | string | Não | Filtrar por tipo: `ab` (Teste A/B), `xt` (Direcionamento de experiência), `abt` (Automated Personalization) |
| `name_contains` | string | Não | Filtrar atividades cujo nome contém esta cadeia de caracteres (não diferencia maiúsculas de minúsculas) |
| `starts_after` | string | Não | Data ISO 8601 — atividades que começam após esta data |
| `starts_before` | string | Não | Data ISO 8601 — atividades que começam antes desta data |
| `modified_after` | string | Não | Data ISO 8601 — atividades modificadas após esta data |
| `ends_after` | string | Não | Data ISO 8601 — atividades que terminam após esta data |
| `ends_before` | string | Não | Data ISO 8601 — atividades que terminam antes desta data |
| `workspace` | string | Não | Filtrar por ID de espaço de trabalho |
| `segment_id` | string | Não | Filtrar por ID de segmento de público |
| `profile_attribute_id` | string | Não | Filtrar por ID de atributo de perfil |
| `priority` | número inteiro | Não | Filtrar por valor de prioridade exato (0-999) |
| `mbox` | string | Não | Filtrar por nome de mbox/local |
| `offer_id` | string | Não | Filtrar por ID de oferta |
| `view_id` | string | Não | Filtrar por ID de exibição de SPA |

**Retorna:** objeto JSON com `activities` (lista de objetos incluindo `id`, `name`, `state`, `type`, `priority`, `modifiedAt`, `startsAt`, `endsAt`) e `total` (contagem total, pode exceder o tamanho da página retornada).

**Prompt de exemplo:** &quot;Lista todos os testes A/B ativos classificados pela última modificação.&quot;

+++

+++Obter uma atividade A/B

**Ferramenta:** `get_ab_activity`

Obtenha informações detalhadas sobre uma atividade A/B.

Recupera a configuração completa de um teste A/B específico, incluindo experiências, locais, métricas e regras de direcionamento.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `activity_id` | número inteiro | Sim | O identificador exclusivo da atividade A/B |

**Retorna:** Detalhes completos da atividade, incluindo metadados (nome, estado, prioridade, datas), experiências, locais e ofertas, metas e métricas, além das regras de direcionamento.

**Prompt de exemplo:** &quot;Obter detalhes da atividade A/B 12345&quot;.

+++

+++Obter uma atividade de direcionamento de experiência

**Ferramenta:** `get_xt_activity`

Obtenha informações detalhadas sobre uma atividade de Direcionamento de experiência (XT).

Recupera a configuração completa de uma atividade de XT específica, incluindo mapeamentos de experiência de público-alvo, locais e métricas.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `activity_id` | número inteiro | Sim | O identificador exclusivo da atividade de XT |

**Retorna:** detalhes completos da atividade, incluindo metadados, experiências com mapeamentos de público-alvo, locais e ofertas, metas e métricas.

**Prompt de exemplo:** &quot;Obter detalhes da atividade de Direcionamento de Experiência 12345&quot;.

+++

+++Obter uma atividade do Automated Personalization

**Ferramenta:** `get_abt_activity`

Obtenha informações detalhadas sobre uma atividade de Automated Personalization (AP).

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `activity_id` | número inteiro | Sim | O identificador exclusivo da atividade de AP |

**Retorna:** detalhes completos da atividade, incluindo metadados, experiências, locais e configurações algorítmicas.

**Prompt de exemplo:** &quot;Obter detalhes da atividade 12345 do Personalization Automático&quot;.

+++

<!--
+++Create an A/B activity

**Tool:** `create_ab_activity`

Create a new A/B test activity.

Creates a new A/B test with the specified configuration including experiences, offers, and targeting.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the activity |
| `state` | string | No | Initial state: `approved`, `deactivated`, or `saved` (default: `saved`) |
| `priority` | integer | No | Activity priority (0–999, default: 0) |
| `starts_at` | string | No | Activity start date (ISO 8601) |
| `ends_at` | string | No | Activity end date (ISO 8601) |
| `experiences` | array | Yes | List of experience configurations |
| `locations` | array | Yes | List of location/mbox configurations |
| `goals` | object | No | Primary and secondary goal metrics |
| `audiences` | array | No | Target audience configurations |
| `workspace_id` | string | No | Workspace ID for the activity |

**Returns:** The created activity object with its assigned ID.

**Example prompt:** "Create an A/B test called 'Homepage Hero Test' with two experiences testing different hero images on the homepage-hero mbox."

+++
-->

<!--
+++Create an Experience Targeting activity

**Tool:** `create_xt_activity`

Create a new Experience Targeting (XT) activity.

Creates an XT activity that delivers different experiences to different audiences based on targeting rules.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the activity |
| `state` | string | No | Initial state: `approved`, `deactivated`, or `saved` (default: `saved`) |
| `priority` | integer | No | Activity priority (0–999, default: 0) |
| `starts_at` | string | No | Activity start date (ISO 8601) |
| `ends_at` | string | No | Activity end date (ISO 8601) |
| `experiences` | array | Yes | List of experience configurations with audience mappings |
| `locations` | array | Yes | List of location/mbox configurations |
| `goals` | object | No | Primary and secondary goal metrics |
| `workspace_id` | string | No | Workspace ID for the activity |

**Returns:** The created activity object with its assigned ID.

**Example prompt:** "Create an Experience Targeting activity called 'Geo Personalization' that shows different content to visitors from different regions."

+++
-->

<!--
+++Update an A/B activity

**Tool:** `update_ab_activity`

Update an existing A/B activity.

Uses a read-modify-write pattern: fetches the current state, merges your changes, validates, and sends the update.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity to update |
| `activity` | object | Yes | Fields to update (name, priority, experiences, locations, goals, etc.) |

**Returns:** The updated activity object.

**Example prompt:** "Update activity 12345 to change the traffic allocation to 70/30."

+++
-->

<!--
+++Update an Experience Targeting activity

**Tool:** `update_xt_activity`

Update an existing Experience Targeting activity.

Uses a read-modify-write pattern.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the XT activity to update |
| `activity` | object | Yes | Fields to update |

**Returns:** The updated activity object.

**Example prompt:** "Update XT activity 12345 to add a new experience for mobile visitors."

+++
-->

<!--
+++Update an Automated Personalization activity

**Tool:** `update_abt_activity`

Update an existing Automated Personalization activity.

Uses a read-modify-write pattern.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the AP activity to update |
| `activity` | object | Yes | Fields to update |

**Returns:** The updated activity object.

**Example prompt:** "Update Auto-Personalization activity 12345 to change the optimization goal."

+++
-->

<!--
+++Update activity schedule

**Tool:** `update_activity_schedule`

Update activity start and end dates.

Updates the schedule for an activity without modifying other settings.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity |
| `activity_type` | string | Yes | Type of activity: `ab`, `xt`, or `abt` |
| `starts_at` | string | No | New start date (ISO 8601) |
| `ends_at` | string | No | New end date (ISO 8601) |

**Returns:** Confirmation of the schedule update.

**Example prompt:** "Update the schedule for A/B activity 12345 to run from May 1st to May 31st."

+++
-->

<!--
+++Change activity state

**Tool:** `update_activity_state`

Change activity state (activate, deactivate, or pause).

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity |
| `state` | string | Yes | New state: `approved` (live/active), `deactivated` (inactive), `paused`, or `saved` (draft) |

**Returns:** The updated activity state.

**Example prompt:** "Activate activity 12345" or "Pause the Homepage Hero Test."

+++
-->

<!--
+++Rename an activity

**Tool:** `update_activity_name`

Rename an activity.

Updates only the name without modifying the full configuration.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity |
| `name` | string | Yes | New activity name |

**Returns:** The updated activity object.

**Example prompt:** "Rename activity 12345 to 'Summer Campaign Hero Test'."

+++
-->

<!--
+++Change activity priority

**Tool:** `update_activity_priority`

Change activity priority.

Higher-priority activities take precedence when multiple activities target the same location.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity |
| `priority` | integer | Yes | New priority value (0–999; higher = higher priority) |

**Returns:** The updated activity object.

**Example prompt:** "Set the priority of activity 12345 to 100."

+++
-->

<!--
+++Add a variant to an activity

**Tool:** `add_activity_variant`

Add a new experience/variant to an activity.

Handles all structural coordination including creating options, mapping to locations, and rebalancing traffic.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The ID of the activity to modify |
| `activity_type` | string | Yes | Activity type: `ab`, `xt`, or `abt` |
| `variant_name` | string | Yes | Name for the new experience/variant |
| `offer_id` | integer | No | (Form-based) Existing offer ID to use |
| `offer_content` | string | No | (Form-based) HTML content for a new inline offer |
| `traffic_percentage` | integer | No | Traffic % for the new variant (1–99). If omitted, traffic is rebalanced evenly |
| `audience_id` | integer | No | Audience ID for the variant (XT activities) |
| `modifications` | array | No | (VEC) List of CSS selector-based modifications |

**Returns:** The updated activity object.

**Example prompt:** "Add a new variant called 'Holiday Theme' to A/B activity 12345 using offer 67890."

+++
-->

<!--
+++Update traffic split

**Tool:** `update_traffic_split`

Update traffic allocation across variants.

The percentages must sum to exactly 100.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The ID of the activity to modify |
| `activity_type` | string | Yes | Activity type: `ab` or `abt` (XT not supported — audience-targeted) |
| `splits` | object | Yes | Dictionary mapping experience name to percentage. Must include all experiences and sum to 100 |

**Returns:** The updated activity object.

**Example prompt:** "Change the traffic split for activity 12345 to 70% Control and 30% Variant A."

+++
-->

<!--
+++Change a variant's offer

**Tool:** `update_variant_offer`

Change the offer for a specific variant.

Works for both form-based activities (using `offer_id`) and VEC activities (using `modifications`).

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The ID of the activity to modify |
| `activity_type` | string | Yes | Activity type: `ab`, `xt`, or `abt` |
| `variant_name` | string | Yes | Name of the experience/variant to update |
| `offer_id` | integer | No | (Form-based) New offer ID |
| `offer_content` | string | No | (Form-based) HTML content for a new inline offer |
| `modifications` | array | No | (VEC) New list of CSS selector-based modifications |

**Returns:** The updated activity object.

**Example prompt:** "Update the 'Variant A' experience in activity 12345 to use offer 99999."

+++
-->

<!--
+++Remove a variant from an activity

**Tool:** `remove_activity_variant`

Remove an experience/variant from an activity.

Removes the experience, cleans up orphaned options, and rebalances traffic evenly across remaining variants.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The ID of the activity to modify |
| `activity_type` | string | Yes | Activity type: `ab`, `xt`, or `abt` |
| `variant_name` | string | Yes | Name of the experience/variant to remove |

**Returns:** The updated activity object.

**Example prompt:** "Remove the 'Test Variant' experience from A/B activity 12345."

+++
-->

## Ferramentas de oferta {#tools-offers}

+++Listar ofertas

**Ferramenta:** `list_target_offers`

Liste todas as ofertas em seu locatário do [!DNL Target].

Recupera uma lista paginada de ofertas de conteúdo com filtragem opcional.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `limit` | número inteiro | Não | Número máximo de ofertas a serem retornadas |
| `offset` | número inteiro | Não | Número de ofertas a serem ignoradas para paginação |
| `type` | string | Não | Filtrar por tipo de oferta: `content` (HTML), `json` ou `redirect` |
| `name` | string | Não | Filtrar por nome da oferta (correspondência parcial) |

**Retorna:** objeto JSON com `offers` (lista de objetos incluindo `id`, `name`, `type`, `content`, `modifiedAt`) e `total`.

**Prompt de exemplo:** &quot;Listar todas as ofertas JSON&quot;.

+++

+++Obter uma oferta

**Ferramenta:** `get_target_offer`

Obtenha informações detalhadas sobre uma oferta específica.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `offer_id` | número inteiro | Sim | O identificador exclusivo da oferta |

**Retorna:** Detalhes completos da oferta, incluindo `id`, `name`, `type`, `content`, `workspace` e `modifiedAt`.

**Exemplo de prompt:** &quot;Obter detalhes da oferta 67890&quot;.

+++

<!--
+++Create an HTML offer

**Tool:** `create_target_offer`

Create a new HTML content offer.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the offer |
| `content` | string | Yes | HTML or text content for the offer |
| `workspace_id` | string | No | Workspace ID for the offer |

**Returns:** The created offer with its assigned ID.

**Example prompt:** "Create an HTML offer called 'Summer Sale Banner' with a promotional banner."

+++

+++Create a JSON offer

**Tool:** `create_target_json_offer`

Create a new JSON offer for delivering structured data.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the offer |
| `content` | object | Yes | JSON content for the offer |
| `workspace_id` | string | No | Workspace ID for the offer |

**Returns:** The created offer with its assigned ID.

**Example prompt:** "Create a JSON offer called 'Feature Flags Config' with feature toggle settings."

+++

+++Update an offer

**Tool:** `update_target_offer`

Update an existing offer.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `offer_id` | integer | Yes | The unique identifier of the offer to update |
| `name` | string | No | Updated offer name |
| `content` | string or object | No | Updated offer content |

**Returns:** The updated offer object.

**Example prompt:** "Update offer 67890 with new promotional content."

+++
-->

## Ferramentas de público {#tools-audiences}

+++Listar públicos

**Ferramenta:** `list_target_audiences`

Liste todos os públicos do seu locatário do [!DNL Target].

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `limit` | número inteiro | Não | Número máximo de públicos-alvo a serem retornados |
| `offset` | número inteiro | Não | Número de públicos-alvo a serem ignorados para paginação |

**Retorna:** objeto JSON com `audiences` (lista de objetos incluindo `id`, `name`, `description`, `origin`, `modifiedAt`) e `total`.

**Exemplo de prompt:** &quot;Listar todos os públicos-alvo&quot;.

+++

<!--
+++Create an audience

**Tool:** `create_target_audience`

Create a new audience with targeting rules.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the audience |
| `description` | string | No | Description of the audience |
| `targetRule` | object | No | Targeting rules (geo, browser, custom attributes, etc.) |
| `workspace_id` | string | No | Workspace ID for the audience |

**Returns:** The created audience with its assigned ID.

**Example prompt:** "Create an audience called 'Mobile Visitors from California' targeting mobile users in CA."

+++
-->

## Ferramentas da mbox {#tools-mboxes}

+++Listar mboxes

**Ferramenta:** `list_target_mboxes`

Liste todas as mboxes em seu locatário do [!DNL Target].

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `limit` | número inteiro | Não | Número máximo de mboxes a serem retornadas |
| `offset` | número inteiro | Não | Número de mboxes a serem ignoradas para paginação |
| `name` | string | Não | Filtrar por nome de mbox (correspondência parcial) |
| `status` | string | Não | Filtrar por status |

**Retorna:** objeto JSON com `mboxes` (lista de objetos incluindo `name`, `status`, `lastRequestTime`) e `total`.

**Exemplo de prompt:** &quot;Listar todas as mboxes contendo &#39;homepage&#39;.&quot;

+++

+++Obter uma mbox

**Ferramenta:** `get_target_mbox`

Obtenha informações detalhadas sobre uma mbox específica.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `mbox_name` | string | Sim | O nome da mbox |

**Retorna:** detalhes da mbox, incluindo `name`, `status` e lista de atividades usando a mbox.

**Prompt de exemplo:** &quot;Obter detalhes da mbox &#39;homepage-hero&#39;.&quot;

+++

+++Listar atributos de perfil da mbox

**Ferramenta:** `list_target_mbox_profile_attributes`

Liste todos os atributos de perfil de mbox disponíveis para direcionamento.

Nenhum parâmetro é necessário.

**Retorna:** matriz JSON de objetos de atributo de perfil.

**Exemplo de prompt:** &quot;Quais atributos de perfil estão disponíveis para direcionamento?&quot;

+++

## Ferramentas de propriedade {#tools-properties}

+++Propriedades da lista

**Ferramenta:** `list_target_properties`

Liste todas as propriedades em seu locatário do [!DNL Target].

As propriedades organizam atividades e controlam o acesso.

Nenhum parâmetro é necessário.

**Retorna:** Lista de objetos de propriedade incluindo `id`, `name`, `description` e `channel`.

**Prompt de exemplo:** &quot;Listar todas as propriedades do Target&quot;.

+++

## Ferramentas de relatórios {#tools-reporting}

+++Obter um relatório de desempenho A/B

**Ferramenta:** `get_ab_performance_report`

Obtenha um relatório de desempenho para uma atividade A/B.

Recupera taxas de conversão, aumentos e níveis de confiança.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `activity_id` | número inteiro | Sim | O identificador exclusivo da atividade A/B |
| `report_interval` | string | Não | Período do relatório (por exemplo, `last7days`, `last30days` ou um intervalo de datas personalizado) |

**Retorna:** métricas de nível de experiência (visitantes, conversões, taxa de conversão), cálculos de aumento, níveis de confiança estatística e métricas de receita (se configuradas).

**Prompt de exemplo:** &quot;Mostrar o relatório de desempenho do teste A/B 12345 dos últimos 30 dias.&quot;

+++

+++Obter um relatório de pedidos A/B

**Ferramenta:** `get_ab_orders_report`

Obtenha um relatório de pedidos/receita para uma atividade A/B.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `activity_id` | número inteiro | Sim | O identificador exclusivo da atividade A/B |
| `report_interval` | string | Não | Período do relatório |

**Devoluções:** Contagens de pedidos, receita e valor médio de pedidos por experiência.

**Exemplo de prompt:** &quot;Obter o relatório de pedidos para a atividade 12345&quot;.

+++

+++Obter um relatório de desempenho de Direcionamento de experiência

**Ferramenta:** `get_xt_performance_report`

Obtenha um relatório de desempenho para uma atividade de Direcionamento de experiência.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `activity_id` | número inteiro | Sim | O identificador exclusivo da atividade de XT |
| `report_interval` | string | Não | Período do relatório |

**Retorna:** métricas de desempenho de nível de experiência.

**Prompt de exemplo:** &quot;Mostrar desempenho para minha atividade de Direcionamento de Experiência 54321&quot;.

+++

+++Obter um relatório de pedidos de direcionamento de experiência

**Ferramenta:** `get_xt_orders_report`

Obtenha um relatório de pedidos/receita para uma atividade de Direcionamento de experiência.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `activity_id` | número inteiro | Sim | O identificador exclusivo da atividade de XT |
| `report_interval` | string | Não | Período do relatório |

**Retorna:** Ordenar métricas por experiência.

**Exemplo de prompt:** &quot;Obter dados de pedidos para a atividade XT 54321&quot;.

+++

+++Obtenha um relatório de desempenho por nome de atividade

**Ferramenta:** `get_activity_report_by_name`

Procure uma atividade por nome e obtenha o relatório de desempenho.

Útil quando você sabe o nome da atividade, mas não a ID.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `activity_name` | string | Sim | Nome da atividade a ser pesquisada |
| `report_interval` | string | Não | Período do relatório |

**Retorna:** detalhes da atividade e métricas de desempenho.

**Prompt de exemplo:** &quot;Obter o relatório de desempenho da minha atividade &#39;Teste de Herói da Página Inicial&#39;.&quot;

+++

## Ferramentas de visualização {#tools-preview}

+++Visualizar uma atividade

**Ferramenta:** `preview_activity`

Gerar URLs de visualização de QA do navegador para uma atividade [!DNL Target].

Cria links de visualização clicáveis que forçam a exibição de experiências específicas, ignorando as regras de direcionamento de público-alvo. Funciona para atividades A/B, XT e Automated Personalization.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `activity_id` | número inteiro | Sim | A ID da atividade [!DNL Target] para visualizar |
| `experience_index` | número inteiro | Não | Índice de experiência com base em 0. Se omitido, retorna URLs para todas as experiências |
| `url` | string | Não | URL da página para visualização. Obrigatório para atividades baseadas em formulário. Para atividades do VEC, substitui o local criado, se fornecido |

**Retorna:** informações de atividade (nome, tipo, estado), URLs de visualização para cada experiência, além de nomes e índices de experiência.

**Prompt de exemplo:** &quot;Gerar URLs de visualização para a atividade 12345 para que eu possa testar cada experiência no meu navegador.&quot;

+++

## Ferramentas de token de resposta {#tools-response-tokens}

+++Listar tokens de resposta

**Ferramenta:** `list_target_response_tokens`

Liste todos os tokens de resposta em seu locatário do [!DNL Target].

Recupera todos os tokens de resposta configurados, incorporados e personalizados.

Nenhum parâmetro é necessário.

**Retorna:** matriz JSON de objetos de token de resposta com status `name`, `type` e `enabled`.

**Exemplo de prompt:** &quot;Listar todos os tokens de resposta&quot;.

+++

<!--
+++Create a response token

**Tool:** `create_target_response_token`

Create a new custom response token for collecting additional data in [!DNL Target] responses.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `token_name` | string | Yes | Name of the response token |
| `token_type` | string | Yes | Type of token: `SCRIPT`, `ACTIVITY`, `MBOX`, `GEO`, or `CRS` |

**Returns:** The created response token object.

**Example prompt:** "Create a custom response token called 'campaign_id' of type ACTIVITY."

+++
-->

## Ferramentas de revisão {#tools-revisions}

+++Obter o log de auditoria

**Ferramenta:** `get_target_revisions`

Obter o log de auditoria para um tipo de recurso.

Recupera alterações feitas em [!DNL Target] recursos com filtragem opcional por autor.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `revision_resource_type` | string | Sim | Tipo de recurso: `activity`, `offer` ou `audience` |
| `modified_by` | string | Não | Filtrar por usuário que fez alterações |
| `limit` | número inteiro | Não | Número máximo de revisões retornadas |
| `offset` | número inteiro | Não | Número de revisões a serem ignoradas para paginação |

**Retorna:** histórico de revisões com carimbos de data/hora, usuários e descrições de alterações.

**Prompt de exemplo:** &quot;Mostrar o log de auditoria para alterações de atividades&quot;.

+++

+++Obter revisões para uma entidade específica

**Ferramenta:** `get_target_entity_revisions`

Obtenha todas as revisões de uma entidade específica por ID.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `revision_resource_type` | string | Sim | Tipo de recurso: `activity`, `offer` ou `audience` |
| `entity_id` | número inteiro | Sim | O identificador exclusivo da entidade |

**Retorna:** a matriz JSON de todas as revisões da entidade especificada.

**Prompt de exemplo:** &quot;Mostrar todas as alterações feitas na atividade 12345.&quot;

+++

## Ferramentas de modelo {#tools-templates}

+++Listar modelos disponíveis

**Ferramenta:** `list_target_templates`

Liste os recursos e modelos do MCP disponíveis para criar atividades e ofertas.

Nenhum parâmetro é necessário.

**Retorna:** o objeto JSON está listando os modelos e recursos disponíveis.

**Exemplo de prompt:** &quot;Quais modelos estão disponíveis para criar atividades?&quot;

+++

## Resumo das ferramentas {#tools-summary}

| Categoria | Contagem | Ferramentas |
|---|---|---|
| Atividade | 4 | `list_target_activities`, `get_ab_activity`, `get_xt_activity`, `get_abt_activity` |
| Oferta | 2 | `list_target_offers`, `get_target_offer` |
| Público-alvo | 1 | `list_target_audiences` |
| Mbox | 3 | `list_target_mboxes`, `get_target_mbox`, `list_target_mbox_profile_attributes` |
| Propriedade | 1 | `list_target_properties` |
| Relatório | 5 | `get_ab_performance_report`, `get_ab_orders_report`, `get_xt_performance_report`, `get_xt_orders_report`, `get_activity_report_by_name` |
| Visualização | 1 | `preview_activity` |
| Token de resposta | 1 | `list_target_response_tokens` |
| Revisão | 2 | `get_target_revisions`, `get_target_entity_revisions` |
| Modelo | 1 | `list_target_templates` |
| **Total** | **21** | |

## Recursos relacionados {#tools-related}

* [Trabalhar com clientes MCP](target-mcp.md)
* [Referência da API de administração [!DNL Adobe Target]](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
