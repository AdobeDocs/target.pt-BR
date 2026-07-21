---
title: Criar atributos de contexto
description: Saiba como criar e organizar atributos de contexto e grupos de contexto em Sinalizadores para que você possa usá-los em critérios de público-alvo.
hide: true
source-git-commit: 9c6f2b72f964b06da51e1f3655545147d7240a93
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 5%

---

# Criar atributos de contexto {#creating-your-context-attributes}

Atributos de contexto são campos de dados personalizados que descrevem o contexto do usuário, da sessão ou do aplicativo (por exemplo, camada de assinatura, versão do aplicativo ou região). Use atributos de contexto para definir critérios de público-alvo para sinalizadores de recursos.

Os grupos de contexto organizam atributos de contexto relacionados em uma hierarquia lógica. Use grupos de contexto para facilitar a localização e o gerenciamento de atributos durante a configuração do recurso.

| Termo | Descrição | Usado em |
| --- | --- | --- |
| **Atributo de contexto** | Um campo nomeado com um tipo de dados e valores predefinidos opcionais. | Critérios de público-alvo, configuração de recursos |
| **Grupo de contexto** | Uma categoria que organiza atributos de contexto relacionados. | Seleção de contexto ao criar um recurso |
| **Rótulo da interface do usuário** | O nome de exibição mostrado na interface do usuário. | Páginas de critérios e administração de público-alvo |
| **ID** | Um identificador técnico exclusivo. | Solicitações de aplicativos |
| **Valores predefinidos** | Uma lista opcional de valores permitidos com rótulos de exibição. | Listas suspensas e construtores de regras de público-alvo |

## Pré-requisitos {#prerequisites}

Antes de gerenciar atributos de contexto e grupos de contexto, faça o seguinte:

* Você tem acesso ao **console Sinalizadores** na sandbox correta.
* Você tem a função de **Administrador** necessária para criar e gerenciar atributos de contexto e grupos de contexto.

## Navegar até Atributos de Contexto {#navigate}

1. Faça logon no **console Sinalizadores**.
1. Na navegação à esquerda, em **Painéis**, selecione **Atributos de Contexto**.

Agora você está na página **Atributos de Contexto**. Use esta página para criar grupos de contexto e atributos de contexto.

## Criar um grupo de contexto {#create-group}

Todo atributo de contexto deve pertencer a um grupo.

1. Na navegação à esquerda, em **Painéis**, selecione **Atributos de Contexto**.
1. Na guia **Meus atributos de contexto**, selecione **Adicionar grupo**.
1. Preencha os campos obrigatórios
1. Selecione **Criar**.

### Agrupar campos {#group-fields}

| Campo | Descrição |
| --- | --- |
| **Nome do grupo** | Informe um nome exclusivo para o grupo. |
| **Criar um subgrupo de** | Selecione um grupo pai para organizar a hierarquia. Você também pode criar um grupo ao criar um atributo. |

## Criar um atributo de contexto {#create-attribute}

1. Na guia **Meus Atributos de Contexto**, selecione **Novo Atributo de Contexto**.
1. Preencha os campos obrigatórios
1. Selecione **Enviar**.

### Campos de atributo {#attribute-fields}

| Campo | Descrição |
| --- | --- |
| **Rótulo da IU** | Insira o nome de exibição usado nos critérios de público-alvo. |
| **ID** | Insira um identificador técnico exclusivo usado em solicitações de aplicativo. |
| **Grupo de contexto** | Selecione um grupo ou crie um novo grupo em linha. |
| **Tipo de dados** | Selecione o tipo que corresponde aos dados enviados pelo aplicativo. |

| Tipo de dado | Exemplo |
| --- | --- |
| STRING | `gold` |
| INTEIRO | `42` |
| BOOLEANO | `true` |
| DECIMAL | `9.99` |
| DATA | `2026-07-17` |
| VERSÃO | `1.2.0` |

### Valores predefinidos (opcional) {#predefined-values}

Use valores predefinidos para limitar um atributo a um conjunto fixo de valores. Selecione **Adicionar Valores Predefinidos**.

| Campo | Descrição |
| --- | --- |
| **Rótulo da IU** | Insira o nome de exibição. |
| **Valor** | Insira o valor técnico enviado pelo aplicativo. |

Selecione **Salvar** para aplicar as alterações.

## Solução de problemas {#troubleshooting}

| Problema | Resolução |
| --- | --- |
| **Criar** está desabilitado | Conclua o **Nome do grupo** e o **Criar um subgrupo de**. |
| Não é possível enviar um atributo | Concluir **ID** e **Grupo de Contexto**. |
| Grupo não visível na lista suspensa | Atualize a página ou crie o grupo em linha a partir do formulário de atributo. |
| Valores predefinidos não salvos | Selecione **Salvar** no modal antes de enviar o atributo. |

## Consulte também {#see-also}

* [Criar e usar conjuntos de regras](creating-and-using-rule-sets.md)
* [Usar contexto nas regras de público](using-context-in-audience-rules.md)
* [Público-alvo em sinalizadores e grupos de recursos](audience-in-feature-flags-and-feature-groups.md)

<!-- -->
