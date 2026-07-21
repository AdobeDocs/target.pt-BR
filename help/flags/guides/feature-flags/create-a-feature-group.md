---
title: Criar um grupo de recursos
description: Saiba como criar um grupo de recursos em Sinalizadores para gerenciar vários sinalizadores de recursos entre aplicativos em sua equipe como uma única unidade.
hide: true
exl-id: 58148df1-84ee-4a78-a4b4-71f74cd8ce0a
source-git-commit: eeba7af62ab101e687852ce993a001832ce4a83b
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 0%

---

# Criar um grupo de recursos {#create-feature-group}

## Pré-requisitos {#prerequisites}

Antes de criar um grupo de recursos, faça o seguinte:

* Você tem acesso ao console de Sinalizadores — consulte [Fazer logon no console](../console/log-in-to-the-console.md)
* Seu aplicativo está integrado — consulte [Integrar seu aplicativo](../applications/onboard-your-application.md)
* Você tem a função **Proprietário da versão do produto**
* Você criou os sinalizadores de recursos que deseja adicionar ao grupo — consulte [Criar seu primeiro sinalizador de recursos](create-your-first-feature-flag.md)

Para obter uma introdução aos grupos de recursos, consulte [Grupos de recursos para controlar vários recursos](../../concepts/feature-groups-to-control-multiple-features.md).

## Etapa 1: criar o grupo de recursos {#create}

Abra o console e inicie um novo grupo de recursos:

1. Faça logon no **console Sinalizadores**, vá para o painel esquerdo e selecione **Grupos de Recursos**.
2. Selecione **Novo Grupo de Recursos**.

## Etapa 2: Detalhes básicos {#basic-details}

Defina as configurações gerais para o grupo de recursos:

1. Forneça um título, chave, descrição e, opcionalmente, uma tag.
2. Defina uma **porcentagem de implantação** para o grupo de recursos.
3. Para executar um teste A/B, selecione mais de uma variante. Caso contrário, deixe-a em uma variante. Consulte [Teste A/B com sinalizadores de recursos](a-b-testing.md) para obter detalhes.

## Etapa 3: Público-alvo {#audience}

Defina quem receberá os recursos neste grupo:

1. Na guia **Público-alvo**, adicione critérios de público-alvo para definir quais usuários receberão o recurso.
2. Em **Aplicativos**, adicione um ou mais aplicativos da sua equipe. Os grupos de recursos podem abranger vários aplicativos, desde que todos pertençam à mesma equipe.

## Etapa 4: recursos {#features}

Atribua os sinalizadores de recursos que serão controlados por este grupo:

1. Na guia **Recursos**, você verá uma caixa para cada aplicativo selecionado.
2. Adicione sinalizadores de recursos para cada aplicativo.
3. Se você selecionou várias variantes (para teste A/B), verá guias para cada variante. Adicione os sinalizadores de recursos apropriados a cada um.

>[!IMPORTANT]
>
>Um sinalizador de recurso só pode ser distribuído por meio de um método — diretamente como um sinalizador de recurso, por meio de um grupo de recursos ou por meio de uma versão. Quando você adiciona um sinalizador de recurso a um grupo de recursos, qualquer público-alvo ou implantação em porcentagem definida no sinalizador é removida. Sinalizadores de recursos já atribuídos a outra versão ou grupo de recursos não aparecerão na lista.

>[!IMPORTANT]
>
>Quando você **remove** um sinalizador de recurso de um grupo de recursos, o sinalizador retorna a um estado **desabilitado** e seu público-alvo é **não** restaurado — trate-o como um sinalizador novo. Um sinalizador **desabilitado** dentro de um grupo sempre é avaliado como `false`. A habilitação de um grupo de recursos **não** habilita seus sinalizadores de membro; habilita explicitamente cada sinalizador.
>
>Os grupos de recursos são uma **camada de gerenciamento**. No tempo de execução, você sempre avalia no **nível de recurso (sinalizador)**, nunca no nível de grupo; a resposta inclui a variante na qual o usuário se enquadrou.

## Consulte também {#see-also}

* [Definir um grupo de recursos para implantação gradual](set-feature-group-gradual-rollout.md)
* [Teste A/B com sinalizadores de recursos](a-b-testing.md)
* [Grupos de recursos para controlar vários recursos](../../concepts/feature-groups-to-control-multiple-features.md)

<!-- -->
