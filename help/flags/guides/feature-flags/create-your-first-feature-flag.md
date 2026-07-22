---
title: Criar o primeiro sinalizador de recurso
description: Saiba como criar um sinalizador de recurso em Sinalizadores, definir um público-alvo e testá-lo antes de implantar para os usuários.
badge: label="Beta" type="Informative"
hide: true
exl-id: ae115120-8da9-465e-a556-c17591ea7054
source-git-commit: 8fffd619232b2cae2f5dd0aa1e0a55183c4be698
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 2%

---

# Criar o primeiro sinalizador de recurso {#create-feature-flag}

## Pré-requisitos {#prerequisites}

Antes de criar um sinalizador de recurso, conclua o seguinte:

* Você tem acesso ao console de Sinalizadores — consulte [Fazer logon no console](../console/log-in-to-the-console.md)
* Seu aplicativo está integrado — consulte [Integrar seu aplicativo](../applications/onboard-your-application.md)
* Você tem a função **Proprietário da versão do produto**

## Etapa 1: criar o sinalizador de recurso {#create}

Para criar um novo sinalizador de recurso, siga estas etapas no console:

1. Faça logon no **console Sinalizadores**, vá para o painel esquerdo e selecione **Sinalizadores de Recursos**.
1. Selecione seu aplicativo no menu suspenso **Aplicativo**.
1. Selecione **Novos Sinalizadores De Recursos**.
1. Preencha os campos do formulário:

   | Campo | Descrição |
   | --- | --- |
   | **Nome** | Um rótulo de exibição para o sinalizador de recurso. Não usado no código. |
   | **Chave** * | O identificador usado no código para avaliar o sinalizador. Não é possível alterar após a criação. |
   | **Descrição** | Descrição opcional para fins de documentação. |
   | **Metadados** | Opcional. Até 1.024 caracteres. Use esse campo para qualquer metadado adicional associado ao sinalizador. |
   | **Tags** | Tags opcionais para fins de documentação. |
   | **Identidade** * | A identidade com a qual o sinalizador é avaliado (por exemplo, ECID). Esta é a identidade transmitida na solicitação de recurso. |
   | **porcentagem de implantação** | A porcentagem do público-alvo definido que é fornecida com esse recurso. O padrão é 100%. Consulte [Definir um recurso para implantação gradual](set-feature-gradual-rollout.md). |

   Os campos marcados com * são obrigatórios.

>[!IMPORTANT]
>
>A **Chave** é o identificador usado em seu código e não pode ser alterada após a criação. As chaves **não podem conter espaços** e diferenciam maiúsculas de minúsculas **3&rbrace;.** O **Name** é apenas um rótulo de exibição e não é usado no código; os dois são independentes (o Name não é convertido na Key). Inserir um espaço no campo Chave produz o erro: _&quot;Valor inválido para chave de recurso.&quot;_

1. Opcionalmente, adicione um critério de público-alvo (consulte Etapa 2).
1. Salve as configurações do sinalizador de recurso.

## Etapa 2: adicionar um critério de público {#audience}

Os critérios de público-alvo controlam quais usuários veem o recurso. Você pode direcionar usuários com **atributos de contexto** — valores que seu site ou aplicativo envia na solicitação de recurso (por exemplo, `locale` ou `platform`). Combine-os com **AND**, **OR** e **NOT**. Consulte [Usar contexto nas regras de audiência](../audience/using-context-in-audience-rules.md).

Para adicionar critérios de público-alvo, vá para a guia **Público-alvo** ao criar ou editar um sinalizador de recurso.

## Consulte também {#see-also}

* [Definir um recurso para implantação gradual](set-feature-gradual-rollout.md)
* [Criar um grupo de recursos](create-a-feature-group.md)

<!-- -->
