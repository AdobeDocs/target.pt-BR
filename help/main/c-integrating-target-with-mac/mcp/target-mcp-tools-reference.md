---
solution: Target
product: target
title: Referência de ferramentas do servidor do Adobe Target MCP
description: Referência completa de parâmetro para todas as ferramentas expostas pelo servidor MCP do Adobe Target, incluindo operações de leitura e gravação.
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: Developer, User
level: Intermediate, Experienced
source-git-commit: aa7a47b00b86a47c97996b667ee0d73db52650aa
workflow-type: tm+mt
source-wordcount: '3046'
ht-degree: 14%

---

# Referência de ferramentas do servidor MCP [!DNL Adobe Target] {#target-mcp-tools-reference}

>[!AVAILABILITY]
>
>O servidor MCP [!DNL Adobe Target] está disponível para todos os clientes em **Beta Público**. Atualmente, ele tem suporte no **Claude Web**, **Claude Desktop**, **Claude Code**, **Cursor** e **ChatGPT**.

Esta página é uma referência completa para todas as ferramentas expostas pelo servidor MCP [!DNL Adobe Target]. Para cada ferramenta, você encontrará uma descrição, detalhes do parâmetro, valor de retorno e um exemplo de prompt em linguagem natural. Para obter instruções de configuração e casos de uso, consulte [Introdução](target-mcp-get-started.md) e [Casos de uso e apresentações](target-mcp-use-cases.md).

>[!IMPORTANT]
>
>O protocolo de contexto de modelo (MCP) é um padrão de código aberto emergente e pode apresentar riscos de segurança ou confiabilidade. As integrações do servidor Adobe MCP e a documentação relacionada são fornecidas &quot;no estado em que se encontram&quot;, sem garantias de nenhum tipo.
>
>Conectar clientes ou servidores MCP a produtos Adobe é uma configuração escolhida pelo cliente, e os clientes são responsáveis por avaliar a segurança e a adequação de qualquer integração MCP. O Adobe não é responsável por problemas resultantes de configuração incorreta, uso incorreto do MCP, vulnerabilidades em implementações de terceiros ou ações não intencionais executadas por meio de fluxos de trabalho habilitados para MCP.
>
>Para reduzir os riscos, a Adobe incentiva o teste de integrações em um ambiente de sandbox antes do uso produtivo e a análise e validação cuidadosas de todas as ações e respostas iniciadas pelo MCP antes de confirmar ou confiar nelas.

## Pré-requisitos {#tools-prerequisites}

Sua função [!DNL Adobe Target] determina quais ferramentas estão disponíveis para você:

* Função de **Observador** ou superior: acesso a todas as ferramentas somente leitura
* Função do **Editor** ou superior: acesso a ferramentas de leitura mais ferramentas de gravação (criar, atualizar)
* Função do **Aprovador**: acesso a todas as ferramentas, incluindo ativação e desativação

Para obter instruções completas sobre a configuração, consulte [Introdução](target-mcp-get-started.md).

## Ferramentas de atividade {#tools-activities}

>[!NOTE]
>
>As operações de leitura e gravação têm escopo diferente. `get_activity` recupera atividades de todos os tipos (Teste A/B, Direcionamento de experiência, Automated Personalization, Alocação automática, Teste multivariado, Recommendations). O `update_activity` é compatível com testes A/B, direcionamento de experiência e Automated Personalization; as atividades de Alocação automática, Teste multivariado e Recommendations são somente leitura por meio do servidor MCP.

| Recurso | Teste A/B | Direcionamento de experiência | Automated Personalization | Alocação automática | Teste multivariado | Recomendações |
|---|---|---|---|---|---|---|
| `get_activity` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| `list_target_activities` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| `get_activity_performance_report` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| `get_activity_orders_report` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| `update_activity` | ✓ | ✓ | ✓ | — | — | — |
| Edições de ciclo de vida (estado, prioridade, nome, agendamento) | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Edições de variante e tráfego | ✓ | ✓ | ✓ | — | — | — |
| Criar | ✓ | ✓ | — | — | — | — |

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
| `activity_type` | string | Não | Filtrar por tipo: `ab` (Teste A/B), `xt` (Direcionamento de experiência), `abt` (Automated Personalization), `auto_allocate` (Alocação automática), `mvt` (Teste multivariado), `recs` (Recomendações) |
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

+++Obter uma atividade

**Ferramenta:** `get_activity`

Obtenha informações detalhadas sobre uma atividade de qualquer tipo.

Recupera a configuração completa de uma atividade específica, detectando automaticamente o tipo de atividade. Suporta atividades de Teste A/B, Direcionamento de experiência, Automated Personalization, Alocação automática, Teste multivariado e Recommendations.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `activity_id` | número inteiro | Sim | O identificador exclusivo da atividade |

**Retorna:** Detalhes completos da atividade, incluindo metadados (nome, estado, prioridade, datas), experiências, locais e ofertas, metas e métricas, além das regras de direcionamento.

**Prompt de exemplo:** &quot;Obter detalhes da atividade 12345&quot;.

+++

+++Criar uma atividade A/B

**Ferramenta:** `create_ab_activity`

Crie uma nova atividade de teste A/B.

Cria um novo teste A/B com a configuração especificada, incluindo experiências, ofertas e direcionamento.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `name` | string | Sim | Nome da atividade |
| `state` | string | Não | Estado inicial: `approved`, `deactivated` ou `saved` (padrão: `saved`) |
| `priority` | número inteiro | Não | Prioridade de atividade (0-999, padrão: 0) |
| `starts_at` | string | Não | Data de início da atividade (ISO 8601) |
| `ends_at` | string | Não | Data final da atividade (ISO 8601) |
| `experiences` | matriz | Sim | Lista de configurações de experiência |
| `locations` | matriz | Sim | Lista de configurações de local/mbox |
| `goals` | objeto | Não | Métricas de meta primária e secundária |
| `audiences` | matriz | Não | Configurações do público-alvo |
| `workspace_id` | string | Não | Workspace ID da atividade |

**Retorna:** o objeto de atividade criado com sua ID atribuída.

**Prompt de exemplo:** &quot;Crie um teste A/B chamado &#39;Teste de Herói da Página Inicial&#39; com duas experiências testando imagens herói diferentes na mbox homepage-hero.&quot;

+++

+++Criar uma atividade de direcionamento de experiência

**Ferramenta:** `create_xt_activity`

Crie uma nova atividade de Direcionamento de experiência (XT).

Cria uma atividade de XT que fornece experiências diferentes para públicos-alvo diferentes com base nas regras de direcionamento.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `name` | string | Sim | Nome da atividade |
| `state` | string | Não | Estado inicial: `approved`, `deactivated` ou `saved` (padrão: `saved`) |
| `priority` | número inteiro | Não | Prioridade de atividade (0-999, padrão: 0) |
| `starts_at` | string | Não | Data de início da atividade (ISO 8601) |
| `ends_at` | string | Não | Data final da atividade (ISO 8601) |
| `experiences` | matriz | Sim | Lista de configurações de experiência com mapeamentos de público |
| `locations` | matriz | Sim | Lista de configurações de local/mbox |
| `goals` | objeto | Não | Métricas de meta primária e secundária |
| `workspace_id` | string | Não | Workspace ID da atividade |

**Retorna:** o objeto de atividade criado com sua ID atribuída.

**Prompt de exemplo:** &quot;Crie uma atividade de Direcionamento de Experiência chamada &#39;Geo Personalization&#39; que mostre conteúdo diferente para visitantes de regiões diferentes.&quot;

+++

+++Atualizar uma atividade

**Ferramenta:** `update_activity`

Atualize uma atividade existente de Teste A/B, Direcionamento de experiência ou Automated Personalization.

Usa um padrão de leitura-modificação-gravação: busca o estado atual, mescla as alterações, valida e envia a atualização. Oferece suporte a atividades de Teste A/B, Direcionamento de experiência e atividades do Automated Personalization; as atividades de Alocação automática, Teste multivariado e Recommendations são somente leitura. Os parâmetros `goal`, `audience_ids` e `additional_metrics` estruturados são suportados apenas para Teste A/B e Direcionamento de experiência; as atividades do Automated Personalization aceitam atualizações de mesclagem de campo simples.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `activity_id` | número inteiro | Sim | O identificador exclusivo da atividade a ser atualizada |
| `activity` | objeto | Sim | Campos a serem atualizados (nome, prioridade, experiências, locais, metas etc.) |

**Retorna:** O objeto de atividade atualizado.

**Prompt de exemplo:** &quot;Atualize a atividade 12345 para alterar a alocação de tráfego para 70/30.&quot;

+++

+++Atualizar programação de atividades

**Ferramenta:** `update_activity_schedule`

Atualize as datas de início e término da atividade.

Atualiza o agendamento de uma atividade sem modificar outras configurações.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `activity_id` | número inteiro | Sim | O identificador exclusivo da atividade |
| `starts_at` | string | Não | Nova data de início (ISO 8601) |
| `ends_at` | string | Não | Nova data final (ISO 8601) |

**Retorna:** Confirmação da atualização da agenda.

**Prompt de exemplo:** &quot;Atualize o agendamento da atividade A/B 12345 para execução de 1º de maio a 31 de maio&quot;.

+++

+++Alterar estado da atividade

**Ferramenta:** `update_activity_state`

Alterar o estado da atividade (ativar, desativar ou pausar).

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `activity_id` | número inteiro | Sim | O identificador exclusivo da atividade |
| `state` | string | Sim | Novo estado: `approved` (ativo/ativo), `deactivated` (inativo), `paused` ou `saved` (rascunho) |

**Retorna:** O estado de atividade atualizado.

**Prompt de exemplo:** &quot;Ativar atividade 12345&quot; ou &quot;Pausar o Teste Herói da Página Inicial&quot;.

+++

+++Renomear uma atividade

**Ferramenta:** `update_activity_name`

Renomeie uma atividade.

Atualiza somente o nome sem modificar a configuração completa.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `activity_id` | número inteiro | Sim | O identificador exclusivo da atividade |
| `name` | string | Sim | Nome da nova atividade |

**Retorna:** O objeto de atividade atualizado.

**Prompt de exemplo:** &quot;Renomeie a atividade 12345 para &#39;Teste de Herói da Campanha de Verão&#39;.&quot;

+++

+++Alterar prioridade da atividade

**Ferramenta:** `update_activity_priority`

Alterar prioridade da atividade.

Atividades de prioridade mais alta têm prioridade quando várias atividades têm como alvo o mesmo local.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `activity_id` | número inteiro | Sim | O identificador exclusivo da atividade |
| `priority` | número inteiro | Sim | Novo valor de prioridade (0-999; maior = prioridade mais alta) |

**Retorna:** O objeto de atividade atualizado.

**Prompt de exemplo:** &quot;Definir a prioridade da atividade 12345 para 100&quot;.

+++

+++Adicionar uma variante a uma atividade

**Ferramenta:** `add_activity_variant`

Adicionar uma nova experiência/variante a uma atividade.

Lida com toda a coordenação estrutural, incluindo a criação de opções, mapeamento para locais e reequilíbrio do tráfego.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `activity_id` | número inteiro | Sim | A ID da atividade a ser modificada |
| `activity_type` | string | Sim | Tipo de atividade: `ab`, `xt` ou `abt` |
| `variant_name` | string | Sim | Nome da nova experiência/variante |
| `offer_id` | número inteiro | Não | (Baseado em formulário) ID de oferta existente para usar |
| `offer_content` | string | Não | (Baseado em formulário) Conteúdo do HTML para uma nova oferta em linha |
| `traffic_percentage` | número inteiro | Não | % de tráfego da nova variante (1-99). Se omitido, o tráfego será rebalanceado uniformemente |
| `audience_id` | número inteiro | Não | ID de público-alvo da variante (atividades de XT) |
| `modifications` | matriz | Não | (VEC) Lista de modificações baseadas no seletor de CSS |

**Retorna:** O objeto de atividade atualizado.

**Prompt de exemplo:** &quot;Adicione uma nova variante chamada &#39;Tema de Feriado&#39; à atividade A/B 12345 usando a oferta 67890.&quot;

+++

+++Atualizar divisão de tráfego

**Ferramenta:** `update_traffic_split`

Atualizar alocação de tráfego entre variantes.

As porcentagens devem somar exatamente 100.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `activity_id` | número inteiro | Sim | A ID da atividade a ser modificada |
| `activity_type` | string | Sim | Tipo de atividade: `ab` ou `abt` (XT não suportado — direcionado ao público) |
| `splits` | objeto | Sim | Nome da experiência de mapeamento de dicionário para porcentagem. Deve incluir todas as experiências e somar até 100 |

**Retorna:** O objeto de atividade atualizado.

**Prompt de exemplo:** &quot;Alterar a divisão de tráfego da atividade 12345 para 70% de Controle e 30% de Variante A&quot;.

+++

+++Alterar a oferta de uma variante

**Ferramenta:** `update_variant_offer`

Alterar a oferta de uma variante específica.

Funciona para atividades baseadas em formulário (usando `offer_id`) e atividades de VEC (usando `modifications`).

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `activity_id` | número inteiro | Sim | A ID da atividade a ser modificada |
| `activity_type` | string | Sim | Tipo de atividade: `ab`, `xt` ou `abt` |
| `variant_name` | string | Sim | Nome da experiência/variante a ser atualizada |
| `offer_id` | número inteiro | Não | (Baseado em formulário) Nova ID de oferta |
| `offer_content` | string | Não | (Baseado em formulário) Conteúdo do HTML para uma nova oferta em linha |
| `modifications` | matriz | Não | (VEC) Nova lista de modificações baseadas em seletor de CSS |

**Retorna:** O objeto de atividade atualizado.

**Prompt de exemplo:** &quot;Atualize a experiência &#39;Variante A&#39; na atividade 12345 para usar a oferta 99999.&quot;

+++

+++Remover uma variante de uma atividade

**Ferramenta:** `remove_activity_variant`

Remover uma experiência/variante de uma atividade.

Remove a experiência, limpa opções órfãs e redistribui o tráfego de maneira uniforme entre as variantes restantes.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `activity_id` | número inteiro | Sim | A ID da atividade a ser modificada |
| `activity_type` | string | Sim | Tipo de atividade: `ab`, `xt` ou `abt` |
| `variant_name` | string | Sim | Nome da experiência/variante a ser removida |

**Retorna:** O objeto de atividade atualizado.

**Prompt de exemplo:** &quot;Remover a experiência &#39;Variante de Teste&#39; da atividade A/B 12345.&quot;

+++

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

+++Criar uma oferta do HTML

**Ferramenta:** `create_target_offer`

Crie uma nova oferta de conteúdo do HTML.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `name` | string | Sim | Nome da oferta |
| `content` | string | Sim | Conteúdo de texto ou HTML para a oferta |
| `workspace_id` | string | Não | Workspace ID da oferta |

**Retorna:** a oferta criada com sua ID atribuída.

**Exemplo de prompt:** &quot;Crie uma oferta do HTML chamada &#39;Banner de Vendas de Verão&#39; com um banner promocional.&quot;

+++

+++Criar uma oferta JSON

**Ferramenta:** `create_target_json_offer`

Crie uma nova oferta JSON para fornecer dados estruturados.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `name` | string | Sim | Nome da oferta |
| `content` | objeto | Sim | Conteúdo JSON para a oferta |
| `workspace_id` | string | Não | Workspace ID da oferta |

**Retorna:** a oferta criada com sua ID atribuída.

**Exemplo de prompt:** &quot;Crie uma oferta JSON chamada &#39;Configuração de Sinalizadores de Recurso&#39; com configurações de alternância de recurso.&quot;

+++

+++Atualizar uma oferta

**Ferramenta:** `update_target_offer`

Atualizar uma oferta existente.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `offer_id` | número inteiro | Sim | O identificador exclusivo da oferta a ser atualizada |
| `name` | string | Não | Nome da oferta atualizado |
| `content` | string ou objeto | Não | Conteúdo de oferta atualizado |

**Retorna:** O objeto de oferta atualizado.

**Prompt de exemplo:** &quot;Atualizar oferta 67890 com novo conteúdo promocional.&quot;

+++

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

+++Obter um público

**Ferramenta:** `get_target_audience`

Obtenha detalhes do público-alvo, incluindo regras de direcionamento.

Recupera a configuração completa de um público-alvo específico, incluindo suas regras de direcionamento e condições.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `audience_id` | número inteiro | Sim | O identificador exclusivo do público-alvo |

**Retorna:** detalhes completos sobre o público-alvo, incluindo `id`, `name`, `description`, `origin`, regras de direcionamento e contagem de atividades associada.

**Prompt de exemplo:** &quot;Obter detalhes do público-alvo 12345 e mostrar suas regras de direcionamento para mim.&quot;

+++

+++Criar um público-alvo

**Ferramenta:** `create_target_audience`

Crie um novo público com regras de direcionamento.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `name` | string | Sim | Nome do público |
| `description` | string | Não | Descrição do público |
| `targetRule` | objeto | Não | Regras de direcionamento (localização geográfica, navegador, atributos personalizados etc.) |
| `workspace_id` | string | Não | Workspace ID para o público |

**Retorna:** o público-alvo criado com sua ID atribuída.

**Exemplo de prompt:** &quot;Crie um público chamado &#39;Visitantes móveis da Califórnia&#39; direcionado a usuários móveis na CA.&quot;

+++

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

+++Obter um relatório de desempenho de atividade

**Ferramenta:** `get_activity_performance_report`

Obtenha um relatório de desempenho para uma atividade de qualquer tipo.

Recupera taxas de conversão, aumentos e níveis de confiança. Suporta atividades de Teste A/B, Direcionamento de experiência, Automated Personalization, Alocação automática, Teste multivariado e Recommendations.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `activity_id` | número inteiro | Sim | O identificador exclusivo da atividade |
| `report_interval` | string | Não | Período do relatório (por exemplo, `last7days`, `last30days` ou um intervalo de datas personalizado) |

**Retorna:** métricas de nível de experiência (visitantes, conversões, taxa de conversão), cálculos de aumento, níveis de confiança estatística e métricas de receita (se configuradas).

**Prompt de exemplo:** &quot;Mostrar o relatório de desempenho da atividade 12345 dos últimos 30 dias.&quot;

+++

+++Obter um relatório de ordens de atividade

**Ferramenta:** `get_activity_orders_report`

Obtenha um relatório de pedidos/receita para qualquer atividade.

Suporta atividades de Teste A/B, Direcionamento de experiência, Automated Personalization, Alocação automática, Teste multivariado e Recommendations.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `activity_id` | número inteiro | Sim | O identificador exclusivo da atividade |
| `report_interval` | string | Não | Período do relatório |

**Devoluções:** Contagens de pedidos, receita e valor médio de pedidos por experiência.

**Exemplo de prompt:** &quot;Obter o relatório de pedidos para a atividade 12345&quot;.

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

+++Obter um relatório do Analytics for Target (A4T)

**Ferramenta:** `get_a4t_report`

Buscar um relatório do Analytics for Target (A4T) para uma atividade [!DNL Target].

Valida a configuração A4T da atividade e executa consultas GraphQL em [!DNL Adobe Analytics] para recuperar métricas do lado do Analytics. Disponível somente para atividades com relatórios do A4T configurados.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `activity_id` | número inteiro | Sim | O identificador exclusivo da atividade [!DNL Target] |
| `report_interval` | string | Não | Período do relatório (por exemplo, `last7days`, `last30days` ou um intervalo de datas personalizado) |

**Retorna:** métricas do lado analítico da atividade, incluindo contagens de visitantes, conversões, receita e aumento por experiência, originadas diretamente de [!DNL Adobe Analytics].

**Prompt de exemplo:** &quot;Puxe o relatório do A4T para meu teste de otimização de check-out e resuma os dados de conversão do lado do Analytics.&quot;

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

+++Criar um token de resposta

**Ferramenta:** `create_target_response_token`

Crie um novo token de resposta personalizado para coletar dados adicionais em [!DNL Target] respostas.

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `token_name` | string | Sim | Nome do token de resposta |
| `token_type` | string | Sim | Tipo de token: `SCRIPT`, `ACTIVITY`, `MBOX`, `GEO` ou `CRS` |

**Retorna:** o objeto de token de resposta criado.

**Exemplo de prompt:** &quot;Criar um token de resposta personalizado chamado &#39;campaign_id&#39; do tipo ACTIVITY.&quot;

+++

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
| Atividade | 13 | `list_target_activities`, `get_activity`, `create_ab_activity`, `create_xt_activity`, `update_activity`, `update_activity_schedule`, `update_activity_state`, `update_activity_name`, `update_activity_priority`, `add_activity_variant`, `update_traffic_split`, `update_variant_offer`, `remove_activity_variant` |
| Oferta | 5 | `list_target_offers`, `get_target_offer`, `create_target_offer`, `create_target_json_offer`, `update_target_offer` |
| Público | 4 | `list_target_audiences`, `get_target_audience`, `create_target_audience`, `update_target_audience` |
| Mbox | 3 | `list_target_mboxes`, `get_target_mbox`, `list_target_mbox_profile_attributes` |
| Propriedade | 1 | `list_target_properties` |
| Relatório | 4 | `get_activity_performance_report`, `get_activity_orders_report`, `get_activity_report_by_name`, `get_a4t_report` |
| Visualização | 1 | `preview_activity` |
| Token de resposta | 2 | `list_target_response_tokens`, `create_target_response_token` |
| Revisão | 2 | `get_target_revisions`, `get_target_entity_revisions` |
| AT.js | 2 | `get_atjs_settings`, `get_atjs_versions` |
| Modelo | 1 | `list_target_templates` |
| **Total** | **38** | |

## Recursos relacionados {#tools-related}

* [Trabalhar com clientes MCP](target-mcp.md)
* [Referência da API de administração [!DNL Adobe Target]](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
