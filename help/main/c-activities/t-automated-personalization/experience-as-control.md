---
keywords: experiência; controle; personalização automatizada; direcionamento automático
description: Saiba como selecionar uma experiência para ser usada como controle ao criar uma atividade do [!UICONTROL Automated Personalization] (AP) ou do [!UICONTROL Direcionamento automático] no [!DNL Adobe Target].
title: Como posso usar uma experiência específica como controle em uma atividade do [!UICONTROL Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Automated Personalization, Auto-Target
solution: Target,Analytics
exl-id: a0a36ace-3cba-4d8d-9bbd-e35204ff6453
TQID: https://experienceleague.adobe.com/a-lIVDWxeAi-VCp7-lLD-zaClCDCKJGfa25XMKF0vZA
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 840
ht-degree: 36%

---

# Selecione o controle da atividade [!UICONTROL Automated Personalization] ou [!UICONTROL Direcionamento automático]

É possível selecionar uma experiência disponibilizada aleatoriamente ou uma experiência específica para ser usada como controle ao criar uma atividade do [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) ou do [[!UICONTROL Direcionamento automático]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT).

Esse recurso permite rotear o tráfego de controle para as experiências relevantes, com base na porcentagem de alocação de tráfego configurada na atividade. Em seguida, você pode avaliar os relatórios de desempenho do tráfego personalizado em relação ao tráfego desse controle.

As opções para definir um controle nas atividades do [!UICONTROL Automated Personalization] e do [!UICONTROL Direcionamento automático] são um pouco diferentes dos outros tipos de atividades. Em um [!UICONTROL Teste A/B] manual, você pode alterar o que os relatórios exibem como controle, e o aumento é calculado com base no índice de conversão dessa experiência de controle. É possível fazer essa alteração facilmente, pois o tráfego é disponibilizado aleatoriamente para cada uma das experiências incluídas na atividade, independentemente do controle definido inicialmente. Em outras palavras, a seleção do controle não afeta o modo como o tráfego é disponibilizado. Nas atividades do [!UICONTROL Automated Personalization] e do [!UICONTROL Direcionamento automático], sua decisão sobre o que escolher como controle afeta o modo como o tráfego de visitantes é disponibilizado. Como resultado, você deve pensar com mais cuidado sobre sua decisão.

Há duas opções disponíveis para controle nas atividades do [!UICONTROL Automated Personalization] e do [!UICONTROL Direcionamento automático]:

* **Disponibilizada aleatoriamente**: para um controle aleatório, a porcentagem de controle do tráfego disponibiliza aleatoriamente todas as experiências na atividade, sem considerar o perfil do visitante. Pense no controle como uma ajuda para responder a pergunta: &quot;Se uma experiência (ou oferta) for disponibilizada aleatoriamente para os visitantes e não considerar seus perfis, qual é o índice de conversão dessa experiência (ou oferta)?&quot; O controle é como um [!UICONTROL Teste A/B] dentro da atividade de IA. Essas informações sobre o índice de conversão não personalizado para cada experiência ou oferta podem ser úteis para entender a análise dos resultados da atividade.

* **Experiência específica**: um controle de experiência específica permite comparar seu tráfego disponibilizado pelos modelos de personalização [!DNL Target] a uma experiência específica definida pelo profissional de marketing (por exemplo, a página inicial padrão). Com essa opção, a porcentagem de controle disponibiliza aleatoriamente o tráfego apenas para aquela experiência.

## Definir uma experiência específica como controle

1. Ao criar ou editar uma atividade de [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) ou [[!UICONTROL Direcionamento automático]](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md), configure as experiências conforme desejado.
1. Na página [!UICONTROL Direcionamento] (etapa 2 do fluxo de trabalho guiado de três etapas), clique na experiência de controle para exibir as opções de [!UICONTROL Controle] no painel direito.

   ![Painel de controle](/help/main/c-activities/t-automated-personalization/assets/control.png)

1. Na lista suspensa [!UICONTROL Controle], selecione [!UICONTROL Experiência Aleatória] ou selecione a experiência desejada que deseja usar para o controle.

1. Clique no controle [!UICONTROL Alocação de tráfego] e especifique a alocação de tráfego desejada para a experiência de controle e as outras experiências.

   ![Painel de alocação de tráfego](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation.png)

   Para um controle de experiência específico, recomenda-se de 10% a 30%.

1. Continue na página [!UICONTROL Metas e configurações].

## Limitações e considerações conhecidas

Lembre-se dos seguintes pontos ao usar uma experiência específica como controle:

* Não é recomendável a alteração da experiência de controle em uma atividade já ativa. A experiência de controle mais recente selecionada é nomeada nos relatórios (mesmo se os relatórios mais antigos estiverem baseados em outra experiência).
* Não é recomendável excluir a experiência de controle.
* Não é recomendável adicionar muitas novas ofertas ou experiências a uma atividade ativa com uma experiência específica como controle.
* Em atividades de [!UICONTROL Automated Personalization], não é recomendável incluir direcionamento na experiência de controle que possa restringir ainda mais quem pode vê-la.
* Em atividades do [!UICONTROL Automated Personalization], as informações de incentivo e confiança *NÃO* estarão disponíveis no relatório de nível de oferta se uma experiência específica estiver selecionada. As informações de lift e confiança estão disponíveis no nível geral de tráfego de &quot;controle&quot; versus &quot;direcionado&quot; para a atividade [!UICONTROL Automated Personalization]. As informações de lift e confiança estão disponíveis se a opção &quot;aleatória&quot; estiver selecionada como controle. Essa distinção ocorre porque não é lógico comparar o índice de conversão de uma experiência específica ao de uma oferta devido à diferença em unidades. As informações disponíveis em uma atividade de [!UICONTROL Direcionamento automático] são as mesmas, independentemente do tipo de controle selecionado.
* Como todo o tráfego de controle é encaminhado para uma única experiência ou para um conjunto de ofertas, ao selecionar a experiência como controle (comparada à aleatória, em que o valor do tráfego de controle é dividido pelo número de experiências ou ofertas na atividade), geralmente não é necessário direcionar muito tráfego para o controle. 10% é um bom ponto para iniciar.
* Se você executar um dos seguintes procedimentos em uma atividade ativa com uma experiência específica como controle, o controle será redefinido automaticamente para as experiências disponibilizadas aleatoriamente (em vez da experiência específica selecionada anteriormente):

   * Excluir uma experiência
   * Remover um local ou oferta ([!UICONTROL Automated Personalization] somente)
   * Excluir uma experiência manualmente, por meio da remoção de ofertas duplicadas ou por um grupo de exclusão ([!UICONTROL Automated Personalization] somente)
