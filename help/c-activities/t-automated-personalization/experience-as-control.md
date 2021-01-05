---
keywords: experience;control;automated personalization;auto-target
description: Selecione uma experiência para ser usada como controle ao criar uma atividade de Personalização automatizada (AP) ou de Direcionamento automático (AT) no Adobe Target.
title: Usar uma experiência específica como controle no Adobe Target
feature: Automated Personalization
solution: Target,Analytics
translation-type: tm+mt
source-git-commit: 4adade56529fb95e4400e06d04d3c6c69e120edc
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 100%

---


# ![PREMIUM](/help/assets/premium.png) Selecione o controle da atividade de Personalização automatizada ou do Direcionamento automático

É possível selecionar uma experiência disponibilizada aleatoriamente ou uma experiência específica para ser usada como controle ao criar uma atividade de [Personalização automatizada](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) ou de [Direcionamento automático](/help/c-activities/auto-target/auto-target-to-optimize.md) (AT).

Esse recurso permite rotear o tráfego de controle para as experiências relevantes, com base na porcentagem de alocação de tráfego configurada na atividade. Em seguida, você pode avaliar os relatórios de desempenho do tráfego personalizado em relação ao tráfego desse controle.

As opções para configurar um controle em atividades AP e AT são um pouco diferentes dos outros tipos de atividades. Em um Teste A/B manual, é possível alterar o que os relatórios exibem como controle, e o lift é calculado com base no índice de conversão dessa experiência de controle. É possível fazer essa alteração facilmente, pois o tráfego é disponibilizado aleatoriamente para cada uma das experiências incluídas na atividade, independentemente do controle definido inicialmente. Ou seja, a seleção do controle não afeta o modo como o tráfego é disponibilizado. Nas atividades de AP e AT, a escolha do controle afeta o modo como o tráfego do visitante é disponibilizado. Como resultado, você precisa considerar com mais cautela a sua decisão.

Há duas opções disponíveis para controle nas atividades de AP e AT: experiências disponibilizadas aleatoriamente ou uma experiência específica.

* **Disponibilizada aleatoriamente**: para um controle aleatório, a porcentagem de controle do tráfego disponibiliza aleatoriamente todas as experiências na atividade, sem considerar o perfil do visitante. Pense no controle como uma ajuda para responder a pergunta: &quot;Se uma experiência (ou oferta) for disponibilizada aleatoriamente para os visitantes e não considerar seus perfis, qual é o índice de conversão dessa experiência (ou oferta)?&quot; O controle é como um Teste A/B na atividade de IA. Essas informações sobre o índice de conversão não personalizado para cada experiência ou oferta podem ser úteis para entender a análise dos resultados da atividade.

* **Experiência específica**: um controle de experiência específica permite comparar seu tráfego disponibilizado pelos modelos de personalização do Target a uma experiência específica definida pelo profissional de marketing (por exemplo, a página inicial padrão). Com essa opção, a porcentagem de controle disponibiliza aleatoriamente o tráfego apenas para aquela experiência.

## Definir uma experiência específica como controle

1. Ao criar uma atividade de [AP](/help/c-activities/t-automated-personalization/create-ap-activity.md) ou [AT](/help/c-activities/t-test-ab/t-test-create-ab/ab-audience.md), configure as experiências conforme desejado.
1. Na página [!UICONTROL Direcionamento] (etapa 2 do fluxo de trabalho guiado de três etapas), selecione a experiência desejada como controle.
1. Especifique a alocação de tráfego desejada para a experiência de controle e outras experiências.

   Para um controle de experiência específico, recomenda-se de 10% a 30%.

1. Continue na página [!UICONTROL Metas e configurações] .

## Limitações e considerações conhecidas

Lembre-se dos pontos a seguir ao usar uma experiência específica como controle:

* Não é recomendável a alteração da experiência de controle em uma atividade já ativa. A experiência de controle mais recente selecionada é nomeada nos relatórios (mesmo se os relatórios mais antigos estiverem baseados em outra experiência).
* Não é recomendável excluir a experiência de controle.
* Não é recomendável adicionar um grande número de novas ofertas/experiências a uma atividade ativa com uma experiência específica como controle.
* Em atividades de AP, não é recomendável incluir direcionamento na experiência de controle que possa restringir ainda mais quem consegue vê-la.
* Em atividades de AP, se uma experiência específica estiver selecionada, as informações de lift e confiança *NÃO* estarão disponíveis no relatório de nível de oferta. As informações de lift e confiança estão disponíveis no nível geral de tráfego de &quot;controle&quot; vs. &quot;direcionado&quot; para a atividade de AP. As informações de lift e confiança estão disponíveis se a opção &quot;aleatória&quot; estiver selecionada como controle. Essa distinção ocorre porque não é lógico comparar o índice de conversão de uma experiência específica ao de uma oferta devido à diferença em unidades. As informações disponíveis em uma atividade de AT são as mesmas, independentemente do tipo de controle selecionado.
* Como todo o tráfego de controle é encaminhado para uma única experiência ou para um conjunto de ofertas, ao selecionar a experiência como controle (comparada à aleatória, em que o valor do tráfego de controle é dividido pelo número de experiências ou ofertas na atividade), geralmente não é necessário direcionar muito tráfego para o controle. 10% é um bom ponto para iniciar.
* Se você executar um dos seguintes procedimentos em uma atividade ativa com uma experiência específica como controle, o controle será redefinido automaticamente para as experiências disponibilizadas aleatoriamente (em vez da experiência específica selecionada anteriormente):

   * Excluir uma experiência
   * Remover um local ou oferta (somente para AP)
   * Excluir uma experiência manualmente por meio da remoção de ofertas duplicadas ou por um grupo de exclusão (somente para AP)

