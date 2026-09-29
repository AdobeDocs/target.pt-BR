---
title: Recursos e grupos de recursos
description: Saiba mais sobre as diferenças entre sinalizadores de recursos e grupos de recursos em Sinalizadores e quando usar cada um.
badge: label="Beta" type="Informative"
hide: true
exl-id: 852aa777-6f8a-47c9-bf54-e645a5ee2f3e
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
source-git-commit: ed3d4b67c78791454c55a2cad4908a37a4d60e26
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 3%
---
# Recursos e grupos de recursos {#features-feature-groups}

Os sinalizadores fornecem dois artefatos para gerenciar implantações de recursos. Escolher a opção certa depende do escopo da implantação e do número de recursos envolvidos.

## Os dois artefatos {#artifacts}

**Sinalizador de recurso**
A unidade mais atômica. Controla um único recurso para um único aplicativo. Pode ser ativado ou desativado para um público-alvo definido.

**Grupo de recursos**
Uma coleção de sinalizadores de recursos pertencentes à mesma equipe. Permite gerenciar vários sinalizadores em vários aplicativos como uma única unidade.

## Comparação {#comparison}

| | Sinalizador de recurso | Grupo de recursos |
|---|---|---|
| **Função necessária para gerenciar a audiência** | Proprietário da versão do produto | Proprietário da versão do produto |
| **Aplicativos** | Única | Múltiplos (mesma equipe) |
| **Critérios avançados de público-alvo** | ✓ | ✓ |
| **porcentagem de implantação** | Combinado com qualquer critério de público-alvo | Combinado com qualquer critério de público-alvo |
| **Teste A/B** | ✓ | ✓ |
| **Autoatendimento** | ✓ | ✓ |
| **Trilha de auditoria** | ✓ | ✓ |

## Quando usar cada {#when-to-use}

| Cenário | Usar |
|---|---|
| Teste ou implantação de um único recurso para um aplicativo | **Sinalizador de recurso** |
| Coordenação de vários recursos na mesma equipe, entrando em funcionamento ao mesmo tempo | **Grupo de recursos** |

## Consulte também {#see-also}

* [Criar o primeiro sinalizador de recurso](create-your-first-feature-flag.md)
* [Criar um grupo de recursos](create-a-feature-group.md)

<!-- -->
