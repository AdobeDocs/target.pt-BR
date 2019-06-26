---
description: Selecione uma experiência a ser usada como controle ao criar uma atividade de Personalização automatizada (AP) ou de Auto-alvo.
keywords: experiência; control; personalização automatizada; segmentação automática
seo-description: Selecione uma experiência a ser usada como controle ao criar uma atividade de Personalização automatizada (AP) ou de Auto-alvo no Adobe Target.
seo-title: Usar uma experiência específica como controle no Adobe Target
solution: Target,Analytics
title: Usar uma experiência específica como controle
uuid: c67901d2-19cd-47d3-b8c4-abdcb046f404
translation-type: tm+mt
source-git-commit: add895d353e7483dfcbe82f1bca55b277bc65f20

---


# ![PREMIUM](/help/assets/premium.png) Selecione o controle da atividade de Personalização automatizada ou do Target automático

You can select a randomly served experience or a specific experience to be used as control while creating an [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) or [Auto-Target](/help/c-activities/auto-target-to-optimize.md) (AT) activity.

Esse recurso permite direcionar o tráfego de controle para as experiências relevantes, com base na porcentagem de alocação de tráfego configurada na atividade. Em seguida, você pode avaliar os relatórios de desempenho do tráfego personalizado contra o controle do tráfego para esse controle.

As opções para definir um controle em atividades AP e AT são um pouco diferentes dos outros tipos de atividades. Em um teste A/B manual, é possível alterar quais relatórios são exibidos como seu controle e o incentivo é calculado com base na taxa de conversão dessa experiência de controle. É possível fazer essa alteração facilmente, pois o tráfego é servido aleatoriamente para cada uma das experiências incluídas na atividade, independentemente do controle definido inicialmente. Em outras palavras, a seleção do controle não afeta a forma como o tráfego é servido. Nas atividades AP e AT, sua decisão sobre o que escolher como o controle afeta a forma como o tráfego do visitante é disponibilizado. Como resultado, você precisa considerar mais cuidadosamente sobre sua decisão.

Há duas opções disponíveis para seu controle nas atividades AP e AT: experiências aleatoriamente fornecidas ou uma experiência específica.

* **Servido aleatoriamente**: Para um controle aleatório, a porcentagem de controle do tráfego atende aleatoriamente todas as experiências na atividade, sem considerar o perfil do visitante. Você pode pensar no controle como ajudar a responder a pergunta: &quot;Se eu distribuir aleatoriamente uma experiência (ou oferta) para os visitantes e não considerar seus perfis, qual é a taxa de conversão dessa experiência (ou oferta)? » O controle é como um teste A/B na atividade do AI. Essa informação da taxa de conversão não personalizada para cada experiência ou oferta pode ser útil para entender ao analisar os resultados da atividade.

* **Experiência específica**: Um controle de experiência específico permite comparar seu tráfego servido pelos modelos de personalização do Target a uma experiência específica definida pelo comerciante (por exemplo, a página inicial padrão). Com essa opção, a porcentagem de controle do tráfego proporciona tráfego aleatoriamente apenas para aquela experiência.

## Especificar uma experiência específica como controle

1. While creating an [AP activity](/help/c-activities/t-automated-personalization/create-ap-activity.md) or [AT activity](/help/c-activities/t-test-ab/t-test-create-ab/ab-audience.md), configure the experiences as desired.
1. On the [!UICONTROL Targeting] page (step 2 of the three-part guided workflow), select the desired experience as the control.
1. Especifique a alocação de tráfego desejada para a experiência de controle e outras experiências.

   Para um controle de experiência específico, é recomendado 10% a 30%.

1. Continue with the [!UICONTROL Goals &amp; Settings] page.

## Limitações e considerações conhecidas

Lembre-se dos pontos a seguir ao usar uma experiência específica como controle:

* A alteração da experiência de controle em uma atividade já ativa não é recomendada. A experiência de controle mais recente selecionada é nomeada nos relatórios (mesmo se os relatórios mais antigos tiverem por base outra experiência).
* Não é recomendável excluir a experiência de controle.
* Adicionando um grande número de novas ofertas/experiências a uma atividade ao vivo com uma experiência específica, pois o controle não é recomendado.
* Em atividades AP, incluindo a definição de metas na experiência de controle que pode restringir ainda mais quem pode ver essa experiência não é recomendada.
* In AP activities, lift and confidence information is *NOT* available in the offer-level report if a specific experience is selected. As informações de elevação e confiança estão disponíveis no nível de tráfego &quot;direcionado&quot; geral vs. &quot;controle&quot; para a atividade AP. As informações de elevação e confiança estão disponíveis se &quot;aleatório&quot; estiver selecionado como controle. Essa diferença ocorre porque comparar a taxa de conversão de uma experiência específica à taxa de conversão de uma oferta não é lógica devido à diferença em unidades. As informações disponíveis em uma atividade AT são as mesmas, independentemente do tipo de controle selecionado.
* Como todo o tráfego de controle vai para uma única experiência ou um conjunto de ofertas quando você seleciona a experiência como controle (comparada a aleatório, onde o valor do tráfego de controle é dividido sobre o número de experiências ou ofertas na atividade), geralmente não é necessário haver tráfego para fluir para o controle. 10% é um bom local para iniciar.
* Se você executar um dos seguintes procedimentos para uma atividade ao vivo com uma experiência específica, o controle será redefinido automaticamente para experiências aleatoriamente enviadas (em vez da experiência específica selecionada anteriormente):

   * Excluir uma experiência
   * Remover um local ou oferta (AP apenas)
   * Excluir uma experiência manualmente, por meio da remoção de ofertas duplicadas ou por um grupo de exclusão (AP apenas)

