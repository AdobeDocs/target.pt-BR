---
solution: Target
product: target
title: Visão geral do servidor Adobe Target MCP
description: Saiba o que é o servidor MCP do Adobe Target, seus principais recursos e como ele se conecta ao seu assistente de IA.
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: User, Developer
level: Beginner, Intermediate
source-git-commit: d5d7a57ce6a3188f02e680c24849d773cb53457a
workflow-type: tm+mt
source-wordcount: '1002'
ht-degree: 0%

---

# [!DNL Adobe Target] servidor MCP {#target-mcp}

A integração do MCP [!DNL Adobe Target] permite inspecionar e analisar testes A/B, atividades de personalização e critérios do Recommendations diretamente do seu assistente de IA. Transforme os dados de experimentação e personalização do [!DNL Target] em fluxos de trabalho em linguagem simples: audite seu portfólio de experimentos, revise relatórios de desempenho e explore públicos e ofertas sem navegar na interface do usuário ou gravar chamadas de API.

>[!AVAILABILITY]
>
>O servidor MCP [!DNL Adobe Target] está disponível para todos os clientes em **Beta Público**. Atualmente, ele tem suporte no **Claude Web**, **Claude Desktop**, **Claude Code**, **Cursor** e **ChatGPT**. O suporte para outros aplicativos compatíveis com MCP será adicionado em versões futuras.


## O que é o protocolo de contexto de modelo? {#mcp-overview}

As equipes de marketing e otimização dependem cada vez mais de aplicativos baseados em bate-papo e ferramentas de desenvolvedor — como Anthropic Claude, OpenAI ChatGPT, Cursor e Microsoft Copilot Studio — para simplificar seu trabalho diário. Esses aplicativos oferecem suporte ao **Protocolo de Contexto de Modelo (MCP)**, um padrão aberto que permite que os aplicativos exponham ferramentas de back-end a grandes modelos de idioma (LLMs) de maneira uniforme.

[!DNL Adobe Target] agora fornece um servidor MCP que supera operações de experimentação, personalização e recomendações diretamente dentro de qualquer aplicativo compatível com MCP. O [!DNL Adobe Target] atua como a camada de decisão e execução enquanto o assistente de IA lida com raciocínio e explicação, oferecendo às equipes acesso mais rápido a insights de otimização sem navegar por várias telas de produtos ou gravar consultas na API REST do [!DNL Adobe Target].


>[!IMPORTANT]
>
>O protocolo de contexto de modelo (MCP) é um padrão de código aberto emergente e pode apresentar riscos de segurança ou confiabilidade. As integrações do servidor Adobe MCP e a documentação relacionada são fornecidas &quot;no estado em que se encontram&quot;, sem garantias de nenhum tipo.
>
>Conectar clientes ou servidores MCP a produtos Adobe é uma configuração escolhida pelo cliente, e os clientes são responsáveis por avaliar a segurança e a adequação de qualquer integração MCP. O Adobe não é responsável por problemas resultantes de configuração incorreta, uso incorreto do MCP, vulnerabilidades em implementações de terceiros ou ações não intencionais executadas por meio de fluxos de trabalho habilitados para MCP.
>
>Para reduzir os riscos, a Adobe incentiva o teste de integrações em um ambiente de sandbox antes do uso produtivo e a análise e validação cuidadosas de todas as ações e respostas iniciadas pelo MCP antes de confirmar ou confiar nelas.

## Principais recursos {#mcp-capabilities}

O servidor MCP [!DNL Adobe Target] fornece acesso de leitura a atividades, públicos, ofertas, recomendações e configuração de implementação. Com a integração do, você pode:

* **Inspecionar e auditar experimentos** - Obtenha status, desempenho, histórico de alterações e links de visualização de QA para qualquer atividade sem navegar na interface do usuário.
* **Analisar resultados** - Recupere relatórios de desempenho, receita e A4T para atividades A/B, XT, AP e de Direcionamento automático.
* **Explorar atividades** - Listar, inspecionar e analisar atividades A/B e XT.
* **Explorar públicos-alvo e ofertas** - Liste e inspecione públicos-alvo, ofertas da HTML e ofertas JSON.
* **Explorar critérios do Recommendations** - Lista e inspeciona critérios e algoritmos baseados no carrinho.
* **Implementação de auditoria** - Revise as configurações da at.js, os tokens de resposta e o histórico de revisão por entidade.

>[!NOTE]
>
>As ferramentas de gravação (criar, atualizar, ativar, desativar) não são expostas por meio do catálogo MCP público em **Beta Público**. Todas as ferramentas disponíveis no momento são somente leitura. O acesso de gravação estará disponível em uma versão futura.

O servidor MCP [!DNL Adobe Target] expõe 23 ferramentas somente leitura em 10 categorias — da inspeção e geração de relatórios de atividades à exploração de público-alvo e visualizações de controle de qualidade. Para obter a referência completa do parâmetro, consulte [Referência de ferramentas do servidor MCP](target-mcp-tools-reference.md).

Para explorar o que você pode fazer com o servidor MCP [!DNL Adobe Target] — incluindo apresentações passo a passo de prompt — consulte [Casos de uso e apresentações](target-mcp-use-cases.md).

Para conectar o servidor MCP do [!DNL Adobe Target] ao seu assistente de IA, incluindo pré-requisitos, configuração específica do cliente e solução de problemas, consulte [Introdução](target-mcp-get-started.md).

## Perguntas frequentes {#mcp-faq}

+++Quais clientes MCP são compatíveis?

O servidor MCP [!DNL Adobe Target] está disponível atualmente para **Claude Web**, **Claude Desktop**, **Claude Code**, **Cursor** e **ChatGPT**. O suporte para aplicativos adicionais compatíveis com MCP poderá ser adicionado em versões futuras.
+++

+++Quais objetos do [!DNL Adobe Target] posso acessar via MCP?

Você pode acessar atividades (A/B, XT, AP), públicos-alvo, ofertas, propriedades, mboxes, critérios do Recommendations, tokens de resposta, configuração do at.js, relatórios do A4T e histórico de revisão de entidade. Todas as 23 ferramentas disponíveis no momento são somente leitura.
+++

+++O servidor MCP pode criar ou modificar atividades?

Não no Beta público. O catálogo MCP público atualmente expõe 23 ferramentas somente leitura. As operações de gravação (criar, atualizar, ativar, desativar) ainda não estão disponíveis por meio do servidor MCP público. O acesso de gravação estará disponível em uma versão futura.
+++

+++Preciso de acesso de desenvolvedor para usar o servidor MCP?

Não. O servidor MCP foi projetado para personas técnicas e de marketing. Os profissionais de marketing podem interagir com ele usando prompts de linguagem natural em qualquer cliente MCP compatível, enquanto os desenvolvedores podem usá-lo em ferramentas como o Claude Code ou o Cursor.
+++

+++Meus dados [!DNL Adobe Target] são enviados ao provedor do cliente MCP?

Ao enviar um prompt, o cliente MCP pode enviar o contexto relevante (incluindo os dados [!DNL Adobe Target] retornados pelo servidor MCP) ao seu modelo para processamento. Analise as políticas de privacidade e manuseio de dados do seu provedor de cliente MCP antes de se conectar aos dados de produção. A manipulação de dados da Adobe é regida pela [Política de Privacidade da Adobe](https://www.adobe.com/privacy.html) e pelos [Termos de Proteção de Dados](https://www.adobe.com/go/dpt-ww).
+++

+++As operações de gravação podem causar alterações não intencionais em atividades ativas?

As ferramentas de gravação não estão disponíveis por meio do catálogo MCP público no Beta público — todas as 23 ferramentas atualmente expostas são somente leitura. Quando as ferramentas de gravação forem introduzidas em uma versão futura, elas incluirão anotações de segurança e portas de confirmação para que nenhuma ação de alteração de estado seja executada sem a confirmação explícita do usuário.
+++

+++Quais permissões são necessárias para o [!DNL Adobe Target]?

A função **Observador** ou superior concede acesso a todas as 23 ferramentas somente leitura disponíveis no Beta Público. As ferramentas de gravação ainda não estão expostas por meio do catálogo MCP público, portanto, os privilégios de função de Editor e Aprovador não desbloqueiam ferramentas MCP adicionais no momento. Entre em contato com o administrador do [!DNL Adobe Target] se não tiver certeza sobre o seu nível de acesso atual.
+++

+++Posso usar o servidor MCP em várias organizações ou propriedades do Target?

O servidor MCP define o escopo das operações para a organização associada às suas credenciais autenticadas do Adobe IMS. Se você tiver acesso a várias propriedades nessa organização, poderá consultar por propriedade usando a ferramenta `list_target_properties` e filtrar as solicitações subsequentes de acordo.
+++

## Recursos relacionados {#mcp-related}

* [Introdução](target-mcp-get-started.md)
* [Casos de uso e apresentações](target-mcp-use-cases.md)
* [Referência de ferramentas do servidor MCP](target-mcp-tools-reference.md)
* [Documentação do protocolo de contexto do modelo](https://modelcontextprotocol.io/introduction){target="_blank"}
* [Referência da API de administração [!DNL Adobe Target]](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
* [Documentação do cursor](https://docs.cursor.com/){target="_blank"}
