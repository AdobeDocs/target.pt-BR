---
title: Definir um grupo de recursos para implantação gradual
description: Saiba como configurar uma implantação gradual com base em porcentagem para um grupo de recursos em Sinalizadores.
hide: true
exl-id: fcf187f1-2f33-4e3a-b740-985d5bc0bcdc
source-git-commit: 35fa45d2a5374dcc47a02bb737f28f24847d7fc6
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 2%

---

# Definir um grupo de recursos para implantação gradual {#gradual-rollout-feature-group}

A porcentagem de implantação de um grupo de recursos está configurada na guia **Detalhes Básicos**. Você pode ajustar esse valor para cima ou para baixo a qualquer momento, conforme o progresso da implantação.

## Como funciona {#how-it-works}

Ao definir uma porcentagem de implantação — por exemplo, 60% — essa porcentagem do público-alvo definido é exposta ao grupo de recursos. A porcentagem de implantação é **necessária** e o padrão é **100%** (o grupo de recursos é distribuído a todo o público correspondente). Você pode ajustá-la em **1% incrementos**. A porcentagem restante é colocada no **grupo de controle**, que recebe o comportamento padrão.

Se você tiver configurado várias variantes (para testes A/B), a porcentagem de exposição será distribuída igualmente entre as variantes. Por exemplo, 60% de exposição com três variantes resulta em 20% por variante, com 40% no grupo de controle.

É possível aumentar ou diminuir a porcentagem a qualquer momento para expandir, reduzir ou pausar a implantação.

## Consulte também {#see-also}

* [Criar um grupo de recursos](create-a-feature-group.md)
* [Teste A/B com sinalizadores de recursos](a-b-testing.md)
* [Implantação gradual](../../concepts/gradual-rollout.md)

<!-- -->
