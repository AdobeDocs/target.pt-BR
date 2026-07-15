---
title: Relatório
description: Saiba como exibir relatórios de sinalizadores de recursos em Sinalizadores usando o Customer Journey Analytics.
hide: true
exl-id: edddca99-f263-461b-a16f-b46ee7c15f6c
source-git-commit: 35fa45d2a5374dcc47a02bb737f28f24847d7fc6
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 1%

---

# Relatório {#reporting}

Os sinalizadores fornecem relatórios por meio do **Customer Journey Analytics (CJA)**. Não há guia Resultados ou Relatórios no console — em vez disso, um botão **Relatório** em cada sinalizador de recurso ou grupo de recursos abre um painel do CJA com escopo para esse item.

## Pré-requisitos {#prerequisites}

Antes de visualizar os relatórios, verifique se:

1. Os relatórios estão configurados para seu aplicativo — consulte [Configurar relatórios com o Customer Journey Analytics](#setup).
1. Seu sinalizador de recurso ou grupo de recursos está ativo e tem dados acumulados.

## Exibir um relatório {#view-report}

Para abrir um relatório de um sinalizador de recurso ou grupo de recursos:

1. Navegue até o sinalizador de recurso ou grupo de recursos no console.
1. Selecione **Relatório**.

Um painel de controle do Customer Journey Analytics com escopo é aberto, mostrando os dados desse sinalizador ou grupo de recursos. O painel inclui:

* **Participantes** — Número total de usuários qualificados para o recurso (variante + grupo de controle combinado)
* **Grupo de controle** — Número de usuários atribuídos ao grupo de controle (usuários que receberam a experiência padrão)
* **Detalhamento de variante** — Contagem cumulativa de usuários inscritos em cada variante e no grupo de controle
* **Inscrição diária** — Gráficos de nível diário que mostram a inscrição em cada variante e no grupo de controle ao longo do tempo

## Configurar relatórios com o Customer Journey Analytics {#setup}

Os relatórios exigem um conjunto de dados do Customer Journey Analytics conectado ao aplicativo Sinalizadores. Entre em contato com o suporte a Sinalizadores ou com o representante da Adobe para habilitar os relatórios do seu aplicativo.

>[!NOTE]
>
>A identidade transmitida na solicitação de recurso não precisa ser vinculada a um perfil. A avaliação acontece no tempo de execução e o evento é enviado para a Customer Journey Analytics.

## Consulte também {#see-also}

* [Criar o primeiro sinalizador de recurso](create-your-first-feature-flag.md)
* [Teste A/B com sinalizadores de recursos](a-b-testing.md)
* [Criar um grupo de recursos](create-a-feature-group.md)

<!-- -->
