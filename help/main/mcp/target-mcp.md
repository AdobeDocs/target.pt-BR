---
solution: Target
product: target
title: Trabalhar com clientes MCP
description: Saiba como conectar o Adobe Target a clientes MCP usando o servidor MCP
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: User, Developer
level: Beginner, Intermediate
hide: true
source-git-commit: 17804b5f8cfce7033bffcad826e5510bfc42a832
workflow-type: tm+mt
source-wordcount: '2267'
ht-degree: 1%

---

# Trabalhar com clientes MCP {#target-mcp}

>[!BEGINSHADEBOX]

Índice:

* **[Trabalhar com clientes MCP](target-mcp.md)**
* [Referência de ferramentas do servidor MCP](target-mcp-tools-reference.md)
* [Auto-hospedar o servidor MCP](target-mcp-self-hosted.md)

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>O servidor MCP [!DNL Adobe Target] está disponível atualmente no **Claude Web**, **Claude Desktop**, **Claude Code** e **Cursor**. O suporte para outros aplicativos compatíveis com MCP será adicionado em versões futuras.

A integração do MCP [!DNL Adobe Target] permite inspecionar, analisar e gerenciar testes A/B, atividades de personalização e critérios do Recommendations diretamente do assistente de IA. Transforme as APIs de leitura e gravação do [!DNL Target] em fluxos de trabalho em linguagem simples — faça uma auditoria do seu portfólio de experimentos, revise relatórios de desempenho, gerencie públicos e ofertas e execute ações controladas sem navegar na interface do usuário ou gravar chamadas de API. Esta página explica como a integração funciona, o que você pode fazer com ela e como começar.

## O que é o protocolo de contexto de modelo? {#mcp-overview}

As equipes de marketing e otimização dependem cada vez mais de aplicativos baseados em bate-papo e ferramentas de desenvolvedor — como Anthropic Claude, OpenAI ChatGPT, Cursor e Microsoft Copilot Studio — para simplificar seu trabalho diário. Esses aplicativos oferecem suporte ao **Protocolo de Contexto de Modelo (MCP)**, um padrão aberto que permite que os aplicativos exponham ferramentas de back-end a grandes modelos de idioma (LLMs) de maneira uniforme.

[!DNL Adobe Target] agora fornece um servidor MCP que supera operações de experimentação, personalização e recomendações diretamente dentro de qualquer aplicativo compatível com MCP. O [!DNL Adobe Target] atua como a camada de decisão e execução enquanto o assistente de IA lida com raciocínio e explicação, oferecendo às equipes acesso mais rápido a insights de otimização sem navegar por várias telas de produtos ou gravar consultas na API REST do [!DNL Adobe Target].

## Principais recursos {#mcp-capabilities}

O servidor MCP [!DNL Adobe Target] fornece acesso de leitura e gravação a atividades, públicos, ofertas, recomendações e configuração de implementação. Com a integração do, você pode:

* **Inspecionar e auditar experimentos** - Obtenha status, desempenho, histórico de alterações e links de visualização de QA para qualquer atividade sem navegar na interface do usuário.
* **Analisar resultados** - Recupere relatórios de desempenho, receita e A4T para atividades A/B, XT, AP e de Direcionamento automático.
* **Gerenciar atividades** - Crie, atualize e ative atividades A/B e XT; ajuste as divisões de tráfego, variantes, agendas e prioridades.
* **Gerenciar públicos e ofertas** - Listar, inspecionar e criar públicos, ofertas do HTML e ofertas JSON.
* **Explorar critérios do Recommendations** - Lista e inspeciona critérios e algoritmos baseados no carrinho.
* **Implementação de auditoria** - Revise as configurações da at.js, os tokens de resposta e o histórico de revisão por entidade.

>[!NOTE]
>
>As operações de gravação (criar, atualizar, ativar, desativar) incluem anotações de segurança. Nenhuma alteração é executada sem confirmação explícita do usuário.

## Ferramentas disponíveis {#mcp-tools}

O servidor MCP [!DNL Adobe Target] expõe 52 ferramentas. As ferramentas de leitura estão disponíveis para todos os usuários conectados com permissões de Exibição; as ferramentas de gravação exigem a função de Editor ou Aprovador.

### Ferramentas de atividade - ler

| Ferramenta | Descrição |
|---|---|
| `list_target_activities` | Listar atividades com filtragem do lado do servidor por estado, tipo, nome, data, prioridade, mbox e espaço de trabalho |
| `list_all_target_activities` | Buscar todas as atividades que correspondem a filtros, paginação automática pelos resultados |
| `get_ab_activity` | Obter detalhes completos de uma atividade A/B específica |
| `get_xt_activity` | Obter detalhes completos de uma atividade específica de Direcionamento de experiência (XT) |
| `get_abt_activity` | Obter detalhes completos de uma atividade específica do Automated Personalization (AP) |

### Ferramentas de atividade - gravação

| Ferramenta | Descrição |
|---|---|
| `create_ab_activity` | Criar uma nova atividade de teste A/B |
| `create_xt_activity` | Criar uma nova atividade de Direcionamento de experiência (XT) |
| `create_activity_from_modifications` | Criar uma atividade de XT a partir de modificações do JavaScript |
| `update_ab_activity` | Atualizar uma atividade A/B existente |
| `update_xt_activity` | Atualizar uma atividade XT existente |
| `update_abt_activity` | Atualizar uma atividade existente do Automated Personalization |
| `update_activity_state` | Ativar, desativar, pausar ou arquivar uma atividade |
| `update_activity_schedule` | Atualizar datas de início e término de uma atividade |
| `update_activity_priority` | Atualizar a prioridade de uma atividade |
| `update_activity_name` | Renomear uma atividade |
| `add_activity_variant` | Adicionar uma nova variante (experiência) a uma atividade |
| `update_traffic_split` | Atualizar alocação de tráfego entre variantes |
| `update_variant_offer` | Alterar a oferta ou as modificações do VEC para uma variante |
| `remove_activity_variant` | Remover uma variante de uma atividade |

### Ferramentas de oferta

| Ferramenta | Descrição |
|---|---|
| `list_target_offers` | Listar ofertas com filtragem e classificação do lado do servidor |
| `list_all_target_offers` | Buscar todas as ofertas que correspondem aos filtros, paginação automática |
| `get_target_offer` | Obter detalhes de uma oferta específica |
| `create_target_offer` | Criar uma nova oferta do HTML |
| `create_target_json_offer` | Criar uma nova oferta JSON |
| `update_target_offer` | Atualizar uma oferta existente do HTML |

### Ferramentas de público

| Ferramenta | Descrição |
|---|---|
| `list_target_audiences` | Listar públicos-alvo com filtragem e classificação do lado do servidor |
| `create_target_audience` | Crie um público-alvo com regras de direcionamento opcionais |

### Ferramentas de mbox e localização

| Ferramenta | Descrição |
|---|---|
| `list_target_mboxes` | Listar mboxes com filtragem e classificação |
| `list_all_target_mboxes` | Buscar todas as mboxes que correspondem aos filtros, paginação automática |
| `get_target_mbox` | Obter detalhes de uma mbox específica por nome |
| `list_target_mbox_profile_attributes` | Listar todos os atributos de perfil associados às mboxes |

### Propriedades

| Ferramenta | Descrição |
|---|---|
| `list_target_properties` | Listar todas as propriedades do Target |

### Ferramentas de relatórios e insights

| Ferramenta | Descrição |
|---|---|
| `get_ab_performance_report` | Obter relatório de desempenho para uma atividade A/B, Alocação automática ou Direcionamento automático |
| `get_ab_orders_report` | Obter relatório de pedidos e receita para uma atividade A/B ou de Direcionamento automático |
| `get_xt_performance_report` | Obter relatório de desempenho de uma atividade de XT |
| `get_xt_orders_report` | Obter relatório de pedidos e receita para uma atividade de XT |
| `get_apt_performance_report` | Obter relatório de desempenho para uma atividade de AP ou de Direcionamento automático |
| `get_activity_insights` | Procure uma atividade por nome e obtenha insights detalhados sobre desempenho |
| `get_a4t_report` | Obter o relatório Analytics for Target (A4T) para uma atividade |

### Ferramentas do Recommendations

| Ferramenta | Descrição |
|---|---|
| `list_target_criteria` | Listar todos os critérios do Recommendations |
| `get_target_criteria` | Obter detalhes de um critério específico do Recommendations |
| `update_target_criteria_cart` | Atualizar os critérios baseados no carrinho do Recommendations |

### Ferramentas de implementação e configuração

| Ferramenta | Descrição |
|---|---|
| `get_atjs_settings` | Obter configurações do AT.js |
| `get_atjs_versions` | Obter versões da AT.js disponíveis |
| `list_target_response_tokens` | Listar todos os tokens de resposta no seu locatário do Target |
| `create_target_response_token` | Criar um novo token de resposta personalizado |

### Ferramentas de auditoria e revisão

| Ferramenta | Descrição |
|---|---|
| `get_target_revisions` | Obter log de auditoria para um tipo de recurso, filtrado pelo autor |
| `get_target_entity_revisions` | Obter todas as revisões de uma entidade específica por ID |

### Utilitários

| Ferramenta | Descrição |
|---|---|
| `preview_activity` | Gerar URLs de visualização de controle de qualidade para uma atividade do Target |
| `create_page_delivery_segment` | Criar um segmento de entrega de página para direcionamento de atividade do VEC |
| `list_target_templates` | Listar recursos e modelos de MCP disponíveis |
| `debug_token_info` | Inspecionar os escopos e declarações atuais do token OAuth |

## Casos de uso {#mcp-use-cases}

Os seguintes exemplos mostram como interagir com o servidor MCP [!DNL Adobe Target] usando linguagem natural:

| Meta | Exemplo de prompt |
|---|---|
| **Auditoria de status de experimento** | &quot;Quais testes A/B estão ativos atualmente na página inicial? Mostre-me o status, a alocação de tráfego e por quanto tempo cada um está em execução.&quot; |
| **Análise de desempenho** | &quot;Mostre-me todos os testes ativos que atingiram significância estatística — quais experiências estão ganhando?&quot; |
| **Análise de receita** | &quot;Obtenha o relatório de pedidos e receita da atividade AT4821 e resuma qual experiência está gerando mais receita por visitante.&quot; |
| **Relatórios do A4T** | &quot;Obtenha o relatório do A4T para meu teste de otimização de check-out e resuma os dados de conversão do lado do Analytics.&quot; |
| **Gerenciamento de atividades** | &quot;Pausar a atividade 98765 e atualizar a prioridade da atividade 1111 para 200.&quot; |
| **Insights de atividade** | &quot;Obtenha insights sobre meu teste &#39;Banner de vendas de verão&#39; — como o desempenho se parece e há anomalias?&quot; |
| **Gerenciamento de público-alvo** | &quot;Lista todos os públicos-alvo direcionados a usuários móveis e mostra a quais atividades eles estão associados.&quot; |
| **Controle de qualidade e visualização** | &quot;Gere URLs de visualização de controle de qualidade para a atividade 12345 para que eu possa revisar todas as variantes antes de ativar.&quot; |
| **Revisão das recomendações** | &quot;Lista todos os critérios do Recommendations configurados nesta conta e resume os tipos de algoritmo em uso.&quot; |
| **Auditoria de implementação** | &quot;Qual versão da at.js está configurada e quais tokens de resposta estão ativos no momento?&quot; |
| **Alterar auditoria** | &quot;Mostre-me todas as alterações feitas na atividade 98765 nos últimos 30 dias e quem as fez.&quot; |

## Apresentação do caso de uso {#mcp-use-case-walkthroughs}

As apresentações a seguir mostram como executar tarefas comuns usando prompts em linguagem natural com o servidor MCP [!DNL Adobe Target].

+++Criação de um teste A/B

**Aviso:**
> &quot;Crie um teste A/B chamado de &#39;Teste de imagem de herói de página inicial&#39; com duas experiências: &#39;Controle&#39; mostrando o herói atual e &#39;Variante&#39; mostrando uma nova imagem de herói com tema de verão. Direcione a mbox da página inicial.&quot;

O assistente de IA usa a ferramenta `create_ab_activity` para criar a atividade com a configuração descrita. A ferramenta retorna a nova ID de atividade e uma confirmação das experiências criadas.

+++

+++Verificar o desempenho da atividade

**Aviso:**
> &quot;Mostrar as métricas de desempenho da minha atividade &#39;Otimização do Fluxo de Check-out&#39; dos últimos 30 dias.&quot;

O assistente de IA usa `get_ab_performance_report` ou `get_xt_performance_report` (dependendo do tipo de atividade) para recuperar taxas de conversão, contagens de visitantes e outras métricas para a janela de tempo especificada.

+++

+++Gerenciamento de ofertas

**Aviso:**
> &quot;Crie uma oferta do HTML chamada &#39;Banner de Vendas de Verão&#39; com um banner promocional que diz &#39;20% de desconto em todos os itens de verão&#39;.&quot;

O assistente de IA usa a ferramenta `create_target_offer` para criar a oferta com o conteúdo HTML especificado e retorna uma confirmação com a nova ID da oferta.

+++

+++Criação de um público

**Aviso:**
> &quot;Crie um público-alvo chamado &#39;Visitantes móveis da Califórnia&#39; que segmente os usuários em dispositivos móveis localizados na Califórnia.&quot;

O assistente de IA usa a ferramenta `create_target_audience` com as regras de direcionamento apropriadas derivadas da sua descrição.

+++

+++Gerar links de visualização de QA

**Aviso:**
> &quot;Gere URLs de visualização para a atividade 12345 para que eu possa testar cada experiência.&quot;

O assistente de IA usa a ferramenta `preview_activity` para gerar URLs clicáveis que ignoram o direcionamento do público-alvo, permitindo que você visualize cada experiência diretamente no navegador.

+++

+++Criação de uma atividade de direcionamento de experiência

**Aviso:**
> &quot;Crie uma atividade de Direcionamento de Experiência chamada &#39;Geo Personalization&#39; que mostra banners herói diferentes para visitantes de diferentes regiões.&quot;

O assistente de IA usa o `create_xt_activity` para criar a atividade com mapeamento de experiência baseado em público-alvo de acordo com as regiões que você descreve.

+++

+++Agendamento de uma atividade

**Aviso:**
> &quot;Atualize a programação da atividade 12345 para iniciar em 1º de maio e terminar em 31 de maio.&quot;

O assistente de IA usa a ferramenta `update_activity_schedule` para aplicar as novas datas de início e término à atividade.

+++

## Pré-requisitos {#mcp-prerequisites}

Antes de conectar o servidor MCP [!DNL Adobe Target] ao seu cliente MCP, verifique o seguinte:

* Você tem uma licença [!DNL Adobe Target] ativa (assinatura do Adobe Experience Cloud) com uma organização da Adobe Experience Platform.
* Você tem um aplicativo compatível com MCP (atualmente Claude Web, Claude Desktop, Claude Code ou Cursor).
* Você tem [!DNL Adobe Target] permissões configuradas no Adobe Admin Console:
   * Função de **Observador**: ferramentas somente leitura
   * Função do **Editor**: ler + criar ferramentas
   * Função do **Aprovador**: ler + criar + ativar/desativar ferramentas

## Conectar o servidor MCP [!DNL Adobe Target] {#mcp-connect}

>[!NOTE]
>
>O servidor MCP [!DNL Adobe Target] usa OAuth 2.0 para autenticação. Ao usar uma ferramenta MCP do Target pela primeira vez, você é redirecionado ao Adobe Experience Cloud para fazer logon, selecionar sua organização e conceder as permissões solicitadas. Nenhuma credencial estática é necessária.

**Para se conectar a partir do Claude Desktop ou do Claude Web:**

1. Abra as configurações do cliente MCP e adicione um novo servidor MCP.
1. Digite a URL do servidor: `https://targetmcp.adobe.io/mcp`
1. Quando solicitado, conclua o logon do Adobe IMS OAuth com suas credenciais do Adobe Experience Cloud.
1. Depois de autenticadas, todas as ferramentas ficam disponíveis imediatamente. Tente &quot;Listar todas as atividades ativas do Target&quot; para verificar a conexão.

**Para se conectar a partir do Código Claude:**

Adicione o seguinte à configuração do MCP do Claude Code:

```json
{
  "mcpServers": {
    "adobe-target": {
      "url": "https://targetmcp.adobe.io/mcp"
    }
  }
}
```

Complete o fluxo do navegador OAuth quando solicitado na primeira utilização.

**Para se conectar a partir do Cursor:**

1. Abra **Cursor** e navegue até **Configurações** → **MCP** → **Adicionar novo servidor MCP global**.
1. Adicione a seguinte configuração:

```json
{
  "mcpServers": {
    "target": {
      "type": "streamable-http",
      "url": "https://targetmcp.adobe.io/mcp"
    }
  }
}
```

1. Salve a configuração. O servidor MCP [!DNL Target] aparecerá nos servidores MCP disponíveis.

>[!TIP]
>
>Se atividades ou dados da organização errada forem exibidos, faça logout completo do Adobe Experience Cloud, reconecte o servidor MCP e selecione cuidadosamente a organização correta durante a reautenticação.

## Solução de problemas {#mcp-troubleshooting}

+++O fluxo do OAuth falha ou redireciona incorretamente

1. Faça logout do Adobe Experience Cloud completamente.
1. Limpe os cookies do navegador para domínios do adobe.com.
1. Tente novamente o fluxo de autenticação.
1. Quando solicitado, certifique-se de selecionar a organização correta.
+++

+++Atividades ou dados da organização errada aparecem

1. Faça logout do Adobe Experience Cloud completamente.
1. Desconecte e reconecte o servidor MCP nas configurações do cliente.
1. Selecione a organização correta cuidadosamente durante a reautenticação.
+++

+++Uma ferramenta retorna uma mensagem de erro

1. Verifique se você tem as permissões necessárias em [!DNL Adobe Target] para a operação (consulte [Pré-requisitos](#mcp-prerequisites)).
1. Verifique se os recursos referenciados — atividades, ofertas, públicos-alvo — existem em sua organização.
1. Confirme se as IDs de atividade e outros identificadores estão corretos.
+++

+++Não é possível conectar-se ao servidor MCP

1. Verifique sua conexão com a Internet.
1. Verifique se o URL do servidor MCP foi inserido corretamente na configuração do cliente.
1. Tente remover e adicionar novamente o servidor nas configurações do cliente MCP.
+++

## Segurança e permissões {#mcp-security}

O servidor MCP [!DNL Adobe Target] só pode acessar dados que sua conta de usuário do Adobe tenha permissão para exibir ou modificar. Todas as operações respeitam suas atribuições de função e permissões de espaço de trabalho do [!DNL Target].

O servidor solicita os seguintes escopos OAuth:

* `AdobeID` — Identidade básica do Adobe
* `openid` — Autenticação OpenID Connect
* `additional_info.projectedProductContext` — Descoberta de locatário
* `read_organizations` — Operações no nível da organização
* `additional_info.roles` — Controle de acesso baseado em função

Os tokens OAuth são validados em relação ao Adobe IMS em cada solicitação, não são armazenados de forma persistente pelo servidor MCP e todas as comunicações usam HTTPS.

## Perguntas frequentes {#mcp-faq}

+++Quais clientes MCP são compatíveis?

O servidor MCP [!DNL Adobe Target] está disponível atualmente para **Claude Web**, **Claude Desktop**, **Claude Code** e **Cursor**. O suporte para aplicativos adicionais compatíveis com MCP poderá ser adicionado em versões futuras.
+++

+++Quais objetos do [!DNL Adobe Target] posso acessar via MCP?

Você pode acessar atividades (A/B, XT, AP), públicos-alvo, ofertas, propriedades, mboxes, critérios do Recommendations, tokens de resposta, configuração do at.js, relatórios do A4T e histórico de revisão de entidade. As operações de leitura e gravação são suportadas em 52 ferramentas — as operações de gravação exigem a função apropriada e a confirmação explícita.
+++

+++O servidor MCP pode criar ou modificar atividades?

Sim. Além das operações de leitura, o servidor expõe as operações de gravação que permitem criar atividades, pausá-las, atualizar prioridades, ajustar divisões de tráfego e muito mais. As operações de gravação seguem o mesmo modelo de permissão da interface do usuário [!DNL Adobe Target]. Você precisa da função apropriada para fazer alterações e nenhuma ação é executada sem a confirmação explícita do usuário.
+++

+++Preciso de acesso de desenvolvedor para usar o servidor MCP?

Não. O servidor MCP foi projetado para personas técnicas e de marketing. Os profissionais de marketing podem interagir com ele usando prompts de linguagem natural em qualquer cliente MCP compatível, enquanto os desenvolvedores podem usá-lo em ferramentas como o Claude Code ou o Cursor.
+++

+++Meus dados [!DNL Adobe Target] são enviados ao provedor do cliente MCP?

Ao enviar um prompt, o cliente MCP pode enviar o contexto relevante (incluindo os dados [!DNL Adobe Target] retornados pelo servidor MCP) ao seu modelo para processamento. Analise as políticas de privacidade e manuseio de dados do seu provedor de cliente MCP antes de se conectar aos dados de produção. A manipulação de dados da Adobe é regida pela [Política de Privacidade da Adobe](https://www.adobe.com/br/privacy.html) e pelos [Termos de Proteção de Dados](https://www.adobe.com/go/dpt-ww).
+++

+++As operações de gravação podem causar alterações não intencionais em atividades ativas?

As ferramentas de gravação incluem anotações de segurança e portas de confirmação. Antes de qualquer ação de alteração de estado — como ativar uma atividade, alterar a prioridade ou atualizar a alocação de tráfego — o servidor apresenta uma confirmação estruturada mostrando o objeto afetado, o impacto do tráfego estimado e uma etapa de aprovação explícita necessária. Nenhuma alteração é feita até a confirmação.
+++

+++Quais permissões são necessárias para o [!DNL Adobe Target]?

No mínimo, a função **Observador** concede acesso a todas as ferramentas de leitura. A função de **Editor** habilita a criação de atividades, públicos e ofertas. A função de **Aprovador** é necessária para ativar, desativar ou arquivar atividades. Entre em contato com o administrador do [!DNL Adobe Target] se não tiver certeza sobre o seu nível de acesso atual.
+++

+++Posso usar o servidor MCP em várias organizações ou propriedades do Target?

O servidor MCP define o escopo das operações para a organização associada às suas credenciais autenticadas do Adobe IMS. Se você tiver acesso a várias propriedades nessa organização, poderá consultar por propriedade usando a ferramenta `list_target_properties` e filtrar as solicitações subsequentes de acordo.
+++

## Recursos relacionados {#mcp-related}

* [Referência de ferramentas do servidor MCP](target-mcp-tools-reference.md)
* [Hospedar automaticamente o servidor MCP [!DNL Adobe Target] ](target-mcp-self-hosted.md)
* [Documentação do Model Context Protocol](https://modelcontextprotocol.io/introduction){target="_blank"}
* [[!DNL Adobe Target] Referência da API de administração](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
* [Documentação do cursor](https://docs.cursor.com/){target="_blank"}
