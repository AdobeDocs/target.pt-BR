---
solution: Target
product: target
title: Servidor MCP Adobe Target — casos de uso e apresentações
description: Explore casos de uso comuns e apresentações de prompt passo a passo para o servidor MCP do Adobe Target.
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: User, Developer
level: Beginner, Intermediate
source-git-commit: 216b1103f501a3fcf955523d4bcc8254a8ea418d
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 0%

---

# Servidor MCP [!DNL Adobe Target] — casos de uso e apresentações {#target-mcp-use-cases}

>[!AVAILABILITY]
>
>O servidor MCP [!DNL Adobe Target] está disponível para todos os clientes em **Beta Público**. Atualmente, ele tem suporte no **Claude Web**, **Claude Desktop**, **Claude Code**, **Cursor** e **ChatGPT**.

Esta página mostra o que você pode fazer com o servidor MCP [!DNL Adobe Target] usando prompts em linguagem natural, desde pesquisas rápidas até tarefas de gerenciamento de atividades em várias etapas.

>[!IMPORTANT]
>
>O protocolo de contexto de modelo (MCP) é um padrão de código aberto emergente e pode apresentar riscos de segurança ou confiabilidade. As integrações do servidor Adobe MCP e a documentação relacionada são fornecidas &quot;no estado em que se encontram&quot;, sem garantias de nenhum tipo.
>
>Conectar clientes ou servidores MCP a produtos Adobe é uma configuração escolhida pelo cliente, e os clientes são responsáveis por avaliar a segurança e a adequação de qualquer integração MCP. O Adobe não é responsável por problemas resultantes de configuração incorreta, uso incorreto do MCP, vulnerabilidades em implementações de terceiros ou ações não intencionais executadas por meio de fluxos de trabalho habilitados para MCP.
>
>Para reduzir os riscos, a Adobe incentiva o teste de integrações em um ambiente de sandbox antes do uso produtivo e a análise e validação cuidadosas de todas as ações e respostas iniciadas pelo MCP antes de confirmar ou confiar nelas.

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
&quot;Crie um teste A/B chamado de &#39;Teste de imagem de herói de página inicial&#39; com duas experiências: &#39;Controle&#39; mostrando o herói atual e &#39;Variante&#39; mostrando uma nova imagem de herói com tema de verão. Direcione a mbox da página inicial.&quot;

O assistente de IA usa a ferramenta `create_ab_activity` para criar a atividade com a configuração descrita. A ferramenta retorna a nova ID de atividade e uma confirmação das experiências criadas.

+++

+++Verificar o desempenho da atividade

**Aviso:**
&quot;Mostrar as métricas de desempenho da minha atividade &#39;Otimização do Fluxo de Check-out&#39; dos últimos 30 dias.&quot;

O assistente de IA usa `get_ab_performance_report` ou `get_xt_performance_report` (dependendo do tipo de atividade) para recuperar taxas de conversão, contagens de visitantes e outras métricas para a janela de tempo especificada.

+++

+++Gerenciamento de ofertas

**Aviso:**
&quot;Crie uma oferta do HTML chamada &#39;Banner de Vendas de Verão&#39; com um banner promocional que diz &#39;20% de desconto em todos os itens de verão&#39;.&quot;

O assistente de IA usa a ferramenta `create_target_offer` para criar a oferta com o conteúdo HTML especificado e retorna uma confirmação com a nova ID da oferta.

+++

+++Criação de um público

**Aviso:**
&quot;Crie um público-alvo chamado &#39;Visitantes móveis da Califórnia&#39; que segmente os usuários em dispositivos móveis localizados na Califórnia.&quot;

O assistente de IA usa a ferramenta `create_target_audience` com as regras de direcionamento apropriadas derivadas da sua descrição.

+++

+++Gerar links de visualização de QA

**Aviso:**
&quot;Gere URLs de visualização para a atividade 12345 para que eu possa testar cada experiência.&quot;

O assistente de IA usa a ferramenta `preview_activity` para gerar URLs clicáveis que ignoram o direcionamento do público-alvo, permitindo que você visualize cada experiência diretamente no navegador.

+++

+++Criação de uma atividade de direcionamento de experiência

**Aviso:**
&quot;Crie uma atividade de Direcionamento de Experiência chamada &#39;Geo Personalization&#39; que mostra banners herói diferentes para visitantes de diferentes regiões.&quot;

O assistente de IA usa o `create_xt_activity` para criar a atividade com mapeamento de experiência baseado em público-alvo de acordo com as regiões que você descreve.

+++

+++Agendamento de uma atividade

**Aviso:**
&quot;Atualize a programação da atividade 12345 para iniciar em 1º de maio e terminar em 31 de maio.&quot;

O assistente de IA usa a ferramenta `update_activity_schedule` para aplicar as novas datas de início e término à atividade.

+++

## Recursos relacionados {#mcp-use-cases-related}

* [Visão geral](target-mcp.md)
* [Introdução](target-mcp-get-started.md)
* [Referência de ferramentas do servidor MCP](target-mcp-tools-reference.md)
* [Documentação do protocolo de contexto do modelo](https://modelcontextprotocol.io/introduction){target="_blank"}
* [Referência da API de administração [!DNL Adobe Target]](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
