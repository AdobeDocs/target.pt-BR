---
title: Criar e usar conjuntos de regras
description: Saiba como criar um Conjunto de regras de critérios de contexto de público-alvo reutilizável em sinalizadores e importá-lo para sinalizadores de recursos e grupos de recursos.
badge: label="Beta" type="Informative"
hide: true
source-git-commit: 8fffd619232b2cae2f5dd0aa1e0a55183c4be698
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 1%

---

# Criar e usar conjuntos de regras {#creating-and-using-rule-sets}

Um conjunto de regras é uma coleção reutilizável de critérios de contexto de público-alvo. Crie um Conjunto de regras quando vários sinalizadores ou grupos de recursos precisarem do mesmo público-alvo. Em seguida, você pode importar o Conjunto de regras em vez de recriar os critérios de público-alvo para cada recurso.

## Requisitos do conjunto de regras {#requirements}

| Rótulo da interface | Usar | Obrigatório |
| --- | --- | --- |
| **Inserir Conjunto de Regras** | Informe um nome para o Conjunto de Regras. | Sim |
| **Descrição do Conjunto de Regras** | Descreva a finalidade do conjunto de regras. | Não |
| **Contexto** | Defina pelo menos um critério de público-alvo. Os atributos de contexto são campos nomeados, como camada de assinatura, versão do aplicativo ou região. | Sim |

## Criar um conjunto de regras {#create-rule-set}

### Etapa 1: iniciar um novo conjunto de regras {#step-1-start}

Em Sinalizadores, selecione **Conjunto de regras** na navegação à esquerda e selecione **Novo Conjunto de Regras**.

A guia **Meu Conjunto de Regras** exibe os Conjuntos de Regras que você criou. A guia **Conjunto de regras da equipe** exibe os Conjuntos de regras disponíveis para a sua equipe.

![Lista de Conjuntos de Regras sem Conjuntos de Regras criados ainda](assets/rule-set-list-empty.png)

### Etapa 2: adicionar os detalhes e critérios do Conjunto de regras {#step-2-details}

1. Informe um nome para o Conjunto de Regras.
1. Opcionalmente, informe uma descrição.
1. Em **Context**, defina os critérios de público-alvo que deseja reutilizar.
1. Use **And** ou **Or** para combinar vários critérios.
1. Para criar uma expressão mais complexa, selecione **Habilitar Lógica Aninhada**.

![Formulário de criação do Conjunto de Regras com exemplos de critérios de contexto](assets/rule-set-create-context.png)

### Etapa 3: salvar o conjunto de regras {#step-3-save}

Selecione **Salvar configurações**. O Conjunto de Regras salvo aparece em **Meu Conjunto de Regras**.

![Lista de Conjuntos de Regras mostrando um Conjunto de Regras recém-salvo](assets/rule-set-list-created.png)

## Usar um Conjunto de Regras em um sinalizador de recurso ou grupo de recursos {#use-rule-set}

### Etapa 1: abrir e habilitar as configurações de público {#step-1-open}

Abra o sinalizador de recurso ou o grupo de recursos no qual deseja usar o Conjunto de Regras, selecione a guia **Público-alvo** e ative a **Regra de Público-alvo** para habilitar os critérios de público-alvo.

### Etapa 2: Selecionar o Conjunto de Regras {#step-2-select}

Abra a lista suspensa **Selecionar Conjunto de Regras**. Escolha o Conjunto de Regras de **Meu Conjunto de Regras** ou **Meu Conjunto de Regras da Equipe**.

![Selecionar lista suspensa de Conjunto de Regras aberta na guia Público-alvo](assets/rule-set-select-in-audience.png)

### Etapa 3: revise os critérios importados {#step-3-review}

Os critérios de contexto do Conjunto de regras selecionado são importados para o público-alvo. Revise os critérios e salve o sinalizador de recurso ou o grupo de recursos.

![Guia de público-alvo do sinalizador de recurso mostrando os critérios importados do Conjunto de Regras](assets/rule-set-imported-audience.png)

Você pode usar o mesmo Conjunto de regras em vários sinalizadores de recursos e grupos de recursos que exigem o mesmo público-alvo.

### Etapa 4: salvar o sinalizador de recurso ou o grupo de recursos {#step-4-save}

Depois de revisar os critérios de público-alvo importados, selecione **Salvar configurações**.

>[!NOTE]
>
>A importação de um conjunto de regras copia seus critérios de público-alvo para o sinalizador de recurso ou grupo de recursos. Se os critérios de público-alvo precisarem ser atualizados posteriormente, atualize-os separadamente em cada sinalizador de recurso e grupo de recursos em que o conjunto de regras foi importado. A atualização do Conjunto de regras original não atualiza automaticamente os públicos importados anteriormente.

## Criar um conjunto de regras a partir de um sinalizador de recurso ou grupo de recursos {#create-from-feature}

Você também pode criar um Conjunto de regras diretamente na tela Público-alvo de um sinalizador de recurso ou grupo de recursos:

1. Abra o sinalizador de recurso ou o grupo de recursos e selecione a guia **Público**.
1. Ative a **Regra de público-alvo**.
1. Defina os critérios de contexto que deseja reutilizar.
1. Selecione o botão **+** no canto superior direito, ao lado da lista suspensa **Selecionar Conjunto de Regras**.
1. Na caixa de diálogo **Salvar Conjunto de Regras**, digite um nome para o Conjunto de Regras.
1. Selecione **Salvar Conjunto de Regras**.

## Consulte também {#see-also}

* [Criar atributos de contexto](creating-your-context-attributes.md)
* [Usar contexto nas regras de público](using-context-in-audience-rules.md)
* [Público-alvo em sinalizadores e grupos de recursos](audience-in-feature-flags-and-feature-groups.md)

<!-- -->
