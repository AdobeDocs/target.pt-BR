---
keywords: experiência; controle; personalização automatizada; direcionamento automático
description: Saiba como selecionar uma experiência para ser usada como controle ao criar uma atividade do [!UICONTROL Automated Personalization] (AP) ou do [!UICONTROL Direcionamento automático] no [!DNL Adobe Target].
title: Como posso usar uma experiência específica como controle em uma atividade do [!UICONTROL Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Automated Personalization, Auto-Target
solution: Target,Analytics
exl-id: a0a36ace-3cba-4d8d-9bbd-e35204ff6453
TQID: 'https://experienceleague.adobe.com/a-lIVDWxeAi-VCp7-lLD-zaClCDCKJGfa25XMKF0vZA'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
  - id: db15a02f-03cd-46fe-a53e-02064cdeadfa
    internal-label: Auto target
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 3%
---
# Selecionar a experiência de controle {#experience-as-control}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba como escolher o controle de uma atividade do **[!UICONTROL Automated Personalization]** ou do **[!UICONTROL Direcionamento automático]** e o que considerar ao usar uma experiência específica como controle.

>[!ENDSHADEBOX]

Você pode selecionar uma experiência disponibilizada aleatoriamente ou uma experiência específica para usar como controle ao criar uma atividade do [**[!UICONTROL Automated Personalization]**](/help/main/c-activities/t-automated-personalization/automated-personalization.md#automated-personalization-overview) (AP) ou do [**[!UICONTROL Direcionamento automático]**](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT). O tráfego de controle é roteado para as experiências relevantes com base na porcentagem de alocação de tráfego configurada na atividade, para que você possa avaliar os relatórios de desempenho do tráfego personalizado em relação ao tráfego de controle.

Em um **[!UICONTROL Teste A/B]** manual, você pode alterar o que os relatórios mostram como controle, e o aumento é calculado a partir dessa experiência, pois o tráfego é disponibilizado aleatoriamente para todas as experiências, independentemente do controle. Nas atividades do **[!UICONTROL Automated Personalization]** e do **[!UICONTROL Direcionamento automático]**, o controle afeta o modo como o tráfego de visitantes é disponibilizado. Portanto, escolha-o com cuidado.

Duas opções estão disponíveis para o controle:

* **Disponibilizada aleatoriamente:** a porcentagem de controle do tráfego disponibiliza aleatoriamente todas as experiências na atividade, sem considerar o perfil do visitante. Ele funciona como um **[!UICONTROL Teste A/B]** dentro da sua atividade e mostra o índice de conversão não personalizado de cada experiência ou oferta, o que ajuda a analisar os resultados.

* **Experiência específica:** a porcentagem de controle do tráfego disponibiliza aleatoriamente apenas essa experiência. Essa opção permite comparar o tráfego disponibilizado pelos modelos de personalização do [!DNL Target] com uma experiência específica definida por você, por exemplo, a página inicial padrão.

## Considerações {#considerations}

Lembre-se dos seguintes pontos ao usar uma experiência específica como controle:

* Não é recomendável a alteração da experiência de controle em uma atividade já ativa. A experiência de controle mais recente selecionada é nomeada nos relatórios, mesmo se os relatórios mais antigos estiverem baseados em outra experiência.

* Não é recomendável excluir a experiência de controle.

* Não é recomendável adicionar muitas novas ofertas ou experiências a uma atividade ativa com uma experiência específica como controle.

* Em atividades de **[!UICONTROL Automated Personalization]**, não é recomendável incluir direcionamento na experiência de controle que possa restringir ainda mais quem pode vê-la.

* Em atividades do **[!UICONTROL Automated Personalization]**, as informações de incentivo e confiança *não* estarão disponíveis no relatório de nível de oferta se uma experiência específica estiver selecionada. Isso ocorre porque não é lógico comparar o índice de conversão de uma experiência específica ao de uma oferta devido à diferença em unidades. As informações de lift e confiança estão disponíveis no nível geral de tráfego de &quot;controle&quot; versus &quot;direcionado&quot; para a atividade e em todos os níveis, se &quot;aleatório&quot; estiver selecionado como controle. As informações disponíveis em uma atividade de **[!UICONTROL Direcionamento automático]** são as mesmas, independentemente do tipo de controle selecionado.

* Quando você seleciona uma experiência específica como controle, todo o tráfego de controle vai para uma única experiência ou conjunto de ofertas. Com um controle aleatório, o tráfego de controle é dividido pelo número de experiências ou ofertas na atividade. Como resultado, você geralmente não precisa de muito tráfego para fluir para o controle com uma experiência específica. 10% é um bom ponto para iniciar.

* Se você executar um dos seguintes procedimentos em uma atividade ativa com uma experiência específica como controle, o controle será redefinido automaticamente para as experiências disponibilizadas aleatoriamente (em vez da experiência específica selecionada anteriormente):

  * Excluir uma experiência.
  * Remover um local ou oferta (**[!UICONTROL Automated Personalization]** somente).
  * Exclua uma experiência manualmente, removendo ofertas duplicadas ou por meio de um grupo de exclusão (somente **[!UICONTROL Automated Personalization]**).


## Definir uma experiência específica como controle {#specify-control}

Especificar uma experiência específica como controle fornece ao tráfego personalizado uma experiência conhecida para ser comparada, como sua experiência padrão atual, nos relatórios da atividade.

1. Ao criar ou editar uma atividade de [**[!UICONTROL Automated Personalization &#x200B;]**](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity) ou uma atividade de [**[!UICONTROL Direcionamento automático]**](/help/main/c-activities/auto-target/create-auto-target.md#create-auto-target-activity), configure as experiências conforme desejado.

1. Na página **[!UICONTROL Direcionamento]** (etapa 2 do fluxo de trabalho guiado de três etapas), clique na experiência de controle para exibir as opções de **[!UICONTROL Controle]** no painel direito.

   ![Painel de controle](/help/main/c-activities/t-automated-personalization/assets/control.png)

1. Na lista suspensa **[!UICONTROL Controle]**, selecione **[!UICONTROL Experiência Aleatória]** ou selecione a experiência que deseja usar como controle.

1. Clique no controle **[!UICONTROL Alocação de tráfego]** e especifique a alocação de tráfego para a experiência de controle e as outras experiências.

   ![Painel de alocação de tráfego](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation.png)

   Para um controle de experiência específico, recomenda-se de 10% a 30%.

1. Continue na página **[!UICONTROL Metas e configurações]**.

Quando a atividade estiver ativa, os relatórios compararão o tráfego personalizado com a experiência de controle selecionada. Revise as [considerações](#considerations) antes de alterar uma atividade online, pois algumas alterações redefinem automaticamente o controle para as experiências aleatoriamente enviadas.
