---
title: Criar o primeiro sinalizador de recurso
description: Saiba como criar um sinalizador de recurso em Sinalizadores, definir um público-alvo e testá-lo antes de implantar para os usuários.
hide: true
exl-id: ae115120-8da9-465e-a556-c17591ea7054
source-git-commit: 045bd3321fd4041fe7f723ce300a400102ed7274
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 1%

---

# Criar o primeiro sinalizador de recurso {#create-feature-flag}

## Pré-requisitos {#prerequisites}

Antes de criar um sinalizador de recurso, conclua o seguinte:

* Você tem acesso ao console de Sinalizadores — consulte [Fazer logon no console](../console/log-in-to-the-console.md)
* Seu aplicativo está integrado — consulte [Integrar seu aplicativo](../applications/onboard-your-application.md)
* Você tem a função **Desenvolvedor** ou **Proprietário da Versão do Produto**

## Etapa 1: criar o sinalizador de recurso {#create}

Para criar um novo sinalizador de recurso, siga estas etapas no console:

1. Faça logon no console Sinalizadores e navegue até **Recursos e Versões > Sinalizadores de Recursos**.
1. Selecione seu aplicativo no menu suspenso **Aplicativo**.
1. Selecione **Novo Recurso**.
1. Preencha os campos do formulário:

   | Campo | Descrição |
   | --- | --- |
   | **Nome** | Um rótulo de exibição para o sinalizador de recurso. Não usado no código. |
   | **Chave** * | O identificador usado no código para avaliar o sinalizador. Não é possível alterar após a criação. |
   | **Descrição** | Descrição opcional para fins de documentação. |
   | **Metadados** | Opcional. Até 1.024 caracteres. Use esse campo para qualquer metadado adicional associado ao sinalizador. |
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

>[!NOTE]
>
>A função de **Desenvolvedor** está em modo seguro. Os desenvolvedores só podem expor um recurso a si mesmos adicionando sua própria ID de usuário em **Público-alvo > Perfil > ID de usuário**. Para expor um recurso a usuários externos, você precisa da função **Proprietário da Versão do Produto**.

## Etapa 3: Calcular tamanho do público {#audience-size}

Depois de adicionar os critérios de público-alvo, selecione **Calcular** na barra inferior para obter uma contagem estimada de usuários que se qualificam para o recurso. Isso ajuda a validar seu direcionamento antes de entrar em funcionamento.

## Etapa 4: programação (opcional) {#schedule}

Você pode agendar um sinalizador de recurso para ativação em uma data e hora futuras usando a opção **Agendar** nas configurações de sinalizador de recurso.

## Perguntas frequentes: não consigo adicionar um sinalizador de recurso como Desenvolvedor {#faq}

A função de **Desenvolvedor** está em modo seguro. Os desenvolvedores podem testar os recursos de forma privada adicionando a ID do usuário ao público-alvo. Eles não podem expor recursos do a usuários externos. Use a função **Proprietário da Versão do Produto** para liberar recursos para usuários externos. Entre em contato com o administrador para atualizar sua função.

## Consulte também {#see-also}

* [Definir um recurso para implantação gradual](set-feature-gradual-rollout.md)
* [Criar um grupo de recursos](create-a-feature-group.md)

<!-- -->
