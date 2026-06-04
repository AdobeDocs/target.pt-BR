---
solution: Target
product: target
title: Hospede automaticamente o servidor MCP do Adobe Target
description: Saiba como executar sua própria instância do servidor MCP do Adobe Target usando Python, Docker ou um ambiente de desenvolvimento local.
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: Developer
level: Experienced
source-git-commit: 7b0c8b18abe2db4e07e3ef979d6d194f4c4c81d6
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 2%

---

# Hospede automaticamente o servidor MCP [!DNL Adobe Target] {#target-mcp-self-hosted}


>[!AVAILABILITY]
>
>O servidor MCP [!DNL Adobe Target] está disponível para todos os clientes em **Beta Público**. Atualmente, ele tem suporte no **Claude Web**, **Claude Desktop**, **Claude Code**, **Cursor** e **ChatGPT**.

Esta página explica como clonar, configurar e executar sua própria instância do servidor MCP [!DNL Adobe Target]. A hospedagem própria é útil quando você precisa de um ambiente de desenvolvimento local, de uma configuração de rede personalizada ou quer contribuir com a base de código do servidor.

>[!AVAILABILITY]
>
>A implantação auto-hospedada destina-se a desenvolvedores e usuários avançados que precisam de controle total sobre o tempo de execução do servidor MCP [!DNL Adobe Target]. Para a maioria dos usuários, o ponto de extremidade hospedado (`https://targetmcp.adobe.io/mcp`) é recomendado. Consulte [Trabalhar com clientes MCP](target-mcp.md).



## Pré-requisitos {#self-hosted-prereqs}

Antes de começar, verifique se você tem o seguinte:

* **Python 3.13 ou posterior**
* **[uv](https://github.com/astral-sh/uv){target="_blank"}** — pacote Python rápido e gerente de projetos

  ```bash
  curl -LsSf https://astral.sh/uv/install.sh | sh
  ```

* Uma licença ativa do [!DNL Adobe Target] com acesso à Adobe Experience Cloud
* **Credenciais artificiais** (somente usuários internos do Adobe) — necessárias para instalar dependências internas

## Instalação {#self-hosted-install}

**1. Clonar o repositório:**

```bash
git clone https://github.com/Adobe-TnT/target-mcp.git
cd target-mcp
```

**2. Criar e ativar um ambiente virtual:**

```bash
uv venv --python 3.13
source .venv/bin/activate
```

**3. Configurar variáveis de ambiente:**

```bash
cp env.example .env
```

Abra `.env` e substitua os valores de espaço reservado pelas suas credenciais e configurações da organização.

**4. Instalar dependências:**

```bash
make uv-install
```

**5. Iniciar o servidor:**

Escolha o modo que corresponde ao seu caso de uso:

| Modo | Comando | Usar quando |
|---|---|---|
| StreamableHTTP (servidor de API) | `make run-api-server` | Conectando um cliente MCP via HTTP |
| STDIO (cliente MCP local) | `make run-mcp-stdio` | Uso da comunicação direta do processo |

## Conectar um cliente MCP a um servidor local {#self-hosted-connect}

### Cursor

Adicione o seguinte à configuração de MCP do cursor. Substitua os valores de espaço reservado pelo seu token IMS real e ID da organização:

```json
{
  "mcpServers": {
    "target-local": {
      "url": "http://localhost:8080/mcp",
      "headers": {
        "Authorization": "Bearer {IMS_USER_TOKEN}",
        "x-gw-ims-org-id": "{IMS_ORGANIZATION_ID}"
      }
    }
  }
}
```

### código Claude

Adicione uma entrada ao seu arquivo de configuração de MCP Claude Code apontando para o servidor local:

```json
{
  "mcpServers": {
    "target-local": {
      "url": "http://localhost:8080/mcp"
    }
  }
}
```

>[!NOTE]
>
>Ao conectar-se a um servidor local, os cabeçalhos de autenticação devem ser passados manualmente (como mostrado no exemplo de Cursor acima). O fluxo do navegador OAuth só está disponível com o ponto de extremidade `https://targetmcp.adobe.io/mcp` hospedado.

## Implantação do Docker {#self-hosted-docker}

O repositório inclui uma configuração de composição do Docker para implantações em containers.

**Executar com Composição do Docker:**

```bash
make run-dc
```

**Crie e execute a imagem do Docker diretamente:**

```bash
make build
make run-docker
```

## Endpoints de API {#self-hosted-endpoints}

O servidor auto-hospedado expõe os seguintes pontos de extremidade HTTP:

| Endpoint | Descrição |
|---|---|
| `/mcp` | Endpoint do protocolo MCP para clientes de IA |
| `/ping` | Verificação da vida útil — retorna `"Pong"` |
| `/health` | Verificação de integridade — retorna `{"status": "healthy"}` |
| `/validate` | Endpoint de validação de entrada |
| `/authorize` | Ponto de acesso de autorização OAuth |
| `/token` | Ponto de extremidade do token OAuth |

**Exemplo de verificação de integridade:**

```bash
curl http://localhost:8080/health
# Response: {"status": "healthy"}
```

## Solução de problemas {#self-hosted-troubleshoot}

+++Falha ao iniciar o servidor

1. Verifique se o Python 3.13+ está instalado: `python --version`
1. Confirme se o ambiente virtual está ativado: `source .venv/bin/activate`
1. Verifique se todas as variáveis de ambiente em `.env` estão definidas corretamente.
1. Execute `make uv-install` novamente para garantir que todas as dependências estejam presentes.

+++

+++Não é possível conectar-se do cliente MCP

1. Confirme se o servidor está em execução e se a porta está acessível: `curl http://localhost:8080/ping`
1. Verifique se o URL do servidor na configuração do cliente MCP corresponde ao endereço do servidor em execução.
1. Para o Cursor, verifique se o cabeçalho `Authorization` contém um token IMS válido e não expirado.

+++

+++Falha na instalação de dependências (usuários internos do Adobe)

1. Confirme se as credenciais do Artifatory estão configuradas corretamente.
1. Verifique sua conexão de rede com a instância interna do Artifatory.
1. Entre em contato com o DevOps da sua equipe ou com o departamento de engenharia da plataforma para obter acesso ao Artifatory.

+++

## Recursos relacionados {#self-hosted-related}

* [Trabalhar com clientes MCP](target-mcp.md) — configuração de ponto de extremidade hospedado e referência de ferramenta
* [Documentação do protocolo de contexto do modelo](https://modelcontextprotocol.io/introduction){target="_blank"}
* [Referência da API de administração [!DNL Adobe Target]](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
