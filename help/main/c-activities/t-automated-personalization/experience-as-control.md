---
keywords: experiência; controle; personalização automatizada; direcionamento automático
description: Saiba como selecionar uma experiência para ser usada como controle ao criar uma atividade [!UICONTROL Automated Personalization] (AP) ou [!UICONTROL Auto-Target] no  [!DNL Adobe Target].
title: Como posso usar uma experiência específica como controle em uma atividade [!UICONTROL Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Automated Personalization, Auto-Target
solution: Target,Analytics
exl-id: a0a36ace-3cba-4d8d-9bbd-e35204ff6453
source-git-commit: 29f8c19e24443e84b8d900f630495d163530f80e
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 42%

---

# Selecione o controle para sua atividade [!UICONTROL Automated Personalization] ou [!UICONTROL Auto-Target]

É possível selecionar uma experiência disponibilizada aleatoriamente ou uma experiência específica para ser usada como controle ao criar uma atividade do [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) ou do [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT).

Esse recurso permite rotear o tráfego de controle para as experiências relevantes, com base na porcentagem de alocação de tráfego configurada na atividade. Em seguida, você pode avaliar os relatórios de desempenho do tráfego personalizado em relação ao tráfego desse controle.

As opções para configurar um controle em atividades [!UICONTROL Automated Personalization] e [!UICONTROL Auto-Target] são um pouco diferentes de outros tipos de atividades. Em um [!UICONTROL A/B Test] manual, você pode alterar o que os relatórios exibem como controle, e o aumento é calculado com base no índice de conversão dessa experiência de controle. É possível fazer essa alteração facilmente, pois o tráfego é disponibilizado aleatoriamente para cada uma das experiências incluídas na atividade, independentemente do controle definido inicialmente. Em outras palavras, a seleção do controle não afeta o modo como o tráfego é disponibilizado. Em atividades de [!UICONTROL Automated Personalization] e [!UICONTROL Auto-Target], sua decisão sobre o que escolher como controle afeta o modo como o tráfego de visitantes é disponibilizado. Como resultado, você deve pensar com mais cuidado sobre sua decisão.

Há duas opções disponíveis para controle nas atividades [!UICONTROL Automated Personalization] e [!UICONTROL Auto-Target]:

* **Disponibilizada aleatoriamente**: para um controle aleatório, a porcentagem de controle do tráfego disponibiliza aleatoriamente todas as experiências na atividade, sem considerar o perfil do visitante. Pense no controle como uma ajuda para responder a pergunta: &quot;Se uma experiência (ou oferta) for disponibilizada aleatoriamente para os visitantes e não considerar seus perfis, qual é o índice de conversão dessa experiência (ou oferta)?&quot; O controle é como um [!UICONTROL A/B Test] na atividade de IA. Essas informações sobre o índice de conversão não personalizado para cada experiência ou oferta podem ser úteis para entender a análise dos resultados da atividade.

* **Experiência específica**: um controle de experiência específica permite comparar seu tráfego disponibilizado pelos modelos de personalização [!DNL Target] a uma experiência específica definida pelo profissional de marketing (por exemplo, a página inicial padrão). Com essa opção, a porcentagem de controle disponibiliza aleatoriamente o tráfego apenas para aquela experiência.

## Definir uma experiência específica como controle

1. Ao criar ou editar uma atividade [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) ou [[!UICONTROL Auto-Target]](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md), configure as experiências conforme desejado.
1. Na página [!UICONTROL Targeting] (etapa 2 do fluxo de trabalho guiado de três etapas), selecione a experiência desejada como controle.
1. Especifique a alocação de tráfego desejada para a experiência de controle e outras experiências.

   Para um controle de experiência específico, recomenda-se de 10% a 30%.

1. Continue com a página [!UICONTROL Goals & Settings].

## Limitações e considerações conhecidas

Lembre-se dos seguintes pontos ao usar uma experiência específica como controle:

* Não é recomendável a alteração da experiência de controle em uma atividade já ativa. A experiência de controle mais recente selecionada é nomeada nos relatórios (mesmo se os relatórios mais antigos estiverem baseados em outra experiência).
* Não é recomendável excluir a experiência de controle.
* Não é recomendável adicionar muitas novas ofertas ou experiências a uma atividade ativa com uma experiência específica como controle.
* Em atividades de [!UICONTROL Automated Personalization], não é recomendável incluir direcionamento na experiência de controle que possa restringir ainda mais quem consegue vê-la.
* Em [!UICONTROL Automated Personalization] atividades, as informações de incentivo e confiança *NÃO* estarão disponíveis no relatório de nível de oferta se uma experiência específica estiver selecionada. As informações de lift e confiança estão disponíveis no nível geral de tráfego de &quot;controle&quot; versus &quot;direcionado&quot; para a atividade [!UICONTROL Automated Personalization]. As informações de lift e confiança estão disponíveis se a opção &quot;aleatória&quot; estiver selecionada como controle. Essa distinção ocorre porque não é lógico comparar o índice de conversão de uma experiência específica ao de uma oferta devido à diferença em unidades. As informações disponíveis em uma atividade [!UICONTROL Auto-Target] são as mesmas, independentemente do tipo de controle selecionado.
* Como todo o tráfego de controle é encaminhado para uma única experiência ou para um conjunto de ofertas, ao selecionar a experiência como controle (comparada à aleatória, em que o valor do tráfego de controle é dividido pelo número de experiências ou ofertas na atividade), geralmente não é necessário direcionar muito tráfego para o controle. 10% é um bom ponto para iniciar.
* Se você executar um dos seguintes procedimentos em uma atividade ativa com uma experiência específica como controle, o controle será redefinido automaticamente para as experiências disponibilizadas aleatoriamente (em vez da experiência específica selecionada anteriormente):

   * Excluir uma experiência
   * Remover um local ou oferta ([!UICONTROL Automated Personalization] somente)
   * Excluir uma experiência manualmente, por meio da remoção de ofertas duplicadas ou por um grupo de exclusão (somente [!UICONTROL Automated Personalization])
