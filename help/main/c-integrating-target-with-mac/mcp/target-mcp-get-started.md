---
solution: Target
product: target
title: Introdução ao servidor MCP do Adobe Target
description: Saiba como conectar o servidor MCP do Adobe Target ao seu assistente de IA, incluindo pré-requisitos, configuração de cliente e solução de problemas.
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: User, Developer
level: Beginner, Intermediate
source-git-commit: d5d7a57ce6a3188f02e680c24849d773cb53457a
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 0%

---

# Introdução ao servidor MCP [!DNL Adobe Target] {#target-mcp-get-started}

>[!AVAILABILITY]
>
>O servidor MCP [!DNL Adobe Target] está disponível para todos os clientes em **Beta Público**. Atualmente, ele tem suporte no **Claude Web**, **Claude Desktop**, **Claude Code**, **Cursor** e **ChatGPT**.

Esta página aborda tudo o que você precisa para conectar o servidor MCP do [!DNL Adobe Target] ao seu assistente de IA e verificar sua configuração.

>[!IMPORTANT]
>
>O protocolo de contexto de modelo (MCP) é um padrão de código aberto emergente e pode apresentar riscos de segurança ou confiabilidade. As integrações do servidor Adobe MCP e a documentação relacionada são fornecidas &quot;no estado em que se encontram&quot;, sem garantias de nenhum tipo.
>
>Conectar clientes ou servidores MCP a produtos Adobe é uma configuração escolhida pelo cliente, e os clientes são responsáveis por avaliar a segurança e a adequação de qualquer integração MCP. O Adobe não é responsável por problemas resultantes de configuração incorreta, uso incorreto do MCP, vulnerabilidades em implementações de terceiros ou ações não intencionais executadas por meio de fluxos de trabalho habilitados para MCP.
>
>Para reduzir os riscos, a Adobe incentiva o teste de integrações em um ambiente de sandbox antes do uso produtivo e a análise e validação cuidadosas de todas as ações e respostas iniciadas pelo MCP antes de confirmar ou confiar nelas.

## Pré-requisitos {#mcp-prerequisites}

Antes de conectar o servidor MCP [!DNL Adobe Target] ao seu cliente MCP, verifique o seguinte:

* Você tem uma licença [!DNL Adobe Target] ativa (assinatura da Adobe Experience Cloud) com uma organização da Adobe Experience Platform.
* Você tem um aplicativo compatível com MCP (atualmente Claude Web, Claude Desktop, Claude Code, Cursor ou ChatGPT).
* Você tem [!DNL Adobe Target] permissões configuradas no Adobe Admin Console. No Beta público, todas as 23 ferramentas disponíveis são somente leitura. A função de **Observador** ou superior é suficiente para usar o servidor MCP.

>[!NOTE]
>
>As ferramentas de gravação (criar, atualizar, ativar, desativar) não são expostas por meio do catálogo MCP público no Public Beta. Os privilégios de função de Editor e Aprovador não desbloqueiam ferramentas adicionais no momento. O acesso de gravação estará disponível em uma versão futura.

## Conectar o servidor MCP [!DNL Adobe Target] {#mcp-connect}

>[!NOTE]
>
>O servidor MCP [!DNL Adobe Target] usa OAuth 2.0 para autenticação. Ao usar uma ferramenta MCP do Target pela primeira vez, você é redirecionado para a Adobe Experience Cloud para fazer logon, selecionar sua organização e conceder as permissões solicitadas. Nenhuma credencial estática é necessária.

**Para se conectar a partir do Claude Desktop ou do Claude Web:**

1. Abra as configurações do cliente MCP e adicione um novo servidor MCP.
1. Digite a URL do servidor: `https://targetmcp.adobe.io/mcp`
1. Quando solicitado, conclua o logon no Adobe IMS OAuth com suas credenciais da Adobe Experience Cloud.
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
>Se atividades ou dados da organização errada forem exibidos, faça logout completo da Adobe Experience Cloud, reconecte o servidor MCP e selecione cuidadosamente a organização correta durante a reautenticação.

## Solução de problemas {#mcp-troubleshooting}

+++O fluxo do OAuth falha ou redireciona incorretamente

1. Faça logout da Adobe Experience Cloud completamente.
1. Limpe os cookies do navegador para domínios do adobe.com.
1. Tente novamente o fluxo de autenticação.
1. Quando solicitado, certifique-se de selecionar a organização correta.
+++

+++Atividades ou dados da organização errada aparecem

1. Faça logout da Adobe Experience Cloud completamente.
1. Desconecte e reconecte o servidor MCP nas configurações do cliente.
1. Selecione a organização correta cuidadosamente durante a reautenticação.
+++

+++Uma ferramenta retorna uma mensagem de erro

1. Verifique se você tem a função **Observador** ou superior em [!DNL Adobe Target] (consulte [Pré-requisitos](#mcp-prerequisites)).
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

## Recursos relacionados {#mcp-get-started-related}

* [Visão geral](target-mcp.md)
* [Casos de uso e apresentações](target-mcp-use-cases.md)
* [Referência de ferramentas do servidor MCP](target-mcp-tools-reference.md)
* [Documentação do protocolo de contexto do modelo](https://modelcontextprotocol.io/introduction){target="_blank"}
* [Referência da API de administração [!DNL Adobe Target]](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
