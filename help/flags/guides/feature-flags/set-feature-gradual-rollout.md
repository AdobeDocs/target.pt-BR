---
title: Definir um recurso para implantação gradual
description: Saiba como configurar uma implantação gradual com base em porcentagem para um sinalizador de recurso em Sinalizadores.
hide: true
exl-id: 1e03c533-398d-4a83-9f4a-c0419828b460
source-git-commit: 35fa45d2a5374dcc47a02bb737f28f24847d7fc6
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 2%

---

# Definir um recurso para implantação gradual {#gradual-rollout-feature}

A porcentagem de implantação de um sinalizador de recurso está configurada na guia **Detalhes Básicos**. Você pode ajustar esse valor para cima ou para baixo a qualquer momento, conforme o progresso da implantação.

## Como funciona {#how-it-works}

Ao definir uma porcentagem de implantação — por exemplo, 25% — essa porcentagem do público-alvo definido é exposta ao recurso. A porcentagem de implantação é **necessária** e o padrão é **100%** (o recurso é distribuído a todo o público correspondente). Você pode ajustá-la em **1% incrementos**. A porcentagem restante é colocada no **grupo de controle**, que recebe a experiência padrão.

Você pode aumentar ou diminuir a porcentagem ao longo do tempo para expandir ou contrair a implantação. Reduzir a porcentagem para 0% desativa efetivamente o recurso para todos no público-alvo sem excluir o sinalizador.

## Consulte também {#see-also}

* [Implantação gradual](../../concepts/gradual-rollout.md)
* [Definir um grupo de recursos para implantação gradual](set-feature-group-gradual-rollout.md)
* [Criar o primeiro sinalizador de recurso](create-your-first-feature-flag.md)

<!-- -->
