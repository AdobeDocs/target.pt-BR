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


# ![PREMIUM](/help/assets/premium.png) Use uma experiência específica como controle

You can select an experience to be used as control while creating an [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) or [Auto-Target](/help/c-activities/auto-target-to-optimize.md) (AT) activity.

Esse recurso permite direcionar todo o tráfego de controle para uma experiência específica, com base na porcentagem de alocação de tráfego configurada na atividade. Em seguida, você pode avaliar os relatórios de desempenho do tráfego personalizado contra o controle do tráfego para aquela experiência.

A opção de controle para disponibilizar aleatoriamente experiências também está disponível.

Usando uma experiência específica como o controle, seus relatórios podem ajudar a responder a pergunta, &quot;Está executando uma atividade AP/AT melhor do que faria em vez disso?&quot; Uma vantagem das atividades AP/AT é que você pode criar mais opções que talvez não façam sentido entregar a todos os usuários, mas pode ser poderoso para o usuário correto. Mas isso significa que a comparação do algoritmo a aleatório não é razoável; você nunca executaria todas as opções para todos os visitantes do site.

## Especificar uma experiência específica como controle

1. While creating an [AP activity](/help/c-activities/t-automated-personalization/create-ap-activity.md) or [AT activity](/help/c-activities/t-test-ab/t-test-create-ab/ab-audience.md), configure the experiences as desired.
1. On the [!UICONTROL Targeting] page (step 2 of the three-part guided workflow), select the desired experience as the control.
1. Especifique a alocação de tráfego desejada para a experiência de controle e outras experiências.
1. Continue with the [!UICONTROL Goals &amp; Settings] page.

## Limitações conhecidas

As limitações a seguir são conhecidas ao usar uma experiência específica como controle:

* A alteração da experiência de controle em uma atividade já ativa não é recomendada. A experiência de controle mais recente selecionada é nomeada nos relatórios (mesmo se os relatórios mais antigos tiverem por base outra experiência).
* Não é recomendável excluir a experiência de controle.
* Em atividades AP, incluindo a definição de metas na experiência de controle não é recomendável restringir ainda mais quem pode ver essa experiência.
* In AP activities, lift and confidence information is *NOT* available in the offer-level report if a specific experience is selected. As informações de elevação e confiança estão disponíveis se &quot;aleatório&quot; estiver selecionado como controle.

   Lift and confidence information *is* available at the overall &quot;targeted&quot; vs. &quot;control&quot; traffic level for the activity. Essa diferença ocorre porque comparar a taxa de conversão de uma experiência específica à taxa de conversão de uma oferta não é lógica devido à diferença em unidades.

## Solução de problemas

Se houver problemas, considere as seguintes dicas de solução de problemas:

* Como todo o tráfego de controle vai para uma única experiência ou um conjunto de ofertas quando você seleciona a experiência como controle (em comparação a aleatório, onde o valor do tráfego de controle é dividido sobre o número de experiências/ofertas na atividade), geralmente não é necessário haver tráfego para fluir para o controle. 10% é um bom local para iniciar.
* Se você executar um dos seguintes procedimentos para uma atividade ao vivo, o controle será redefinido automaticamente para experiências aleatoriamente enviadas (em vez da experiência específica selecionada anteriormente):

   * Excluir uma experiência
   * Remover um local ou oferta (AP apenas)
   * Excluir uma experiência manualmente, por meio da remoção de ofertas duplicadas ou por um grupo de exclusão (AP apenas)
