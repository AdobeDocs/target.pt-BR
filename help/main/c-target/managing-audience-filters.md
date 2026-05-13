---
keywords: Direcionamento;filtro de público-alvo;públicos-alvo;filtro
description: Saiba como usar os filtros de público-alvo no [!DNL Adobe Target]  para exibir dados de visitantes que compartilham características.
title: Posso usar filtros de público-alvo para relatórios?
feature: Audiences
exl-id: af8dae97-4b10-4edb-a0e6-0d8daf2f0d22
TQID: https://experienceleague.adobe.com/7h16ay64Y1IVu2CbkEJny-rnGms80q8X7G6gOM1P900
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
subfeature_v2:
  - id: b6f5758b-84f7-4943-8b05-1297a046943c
  - id: e73b329c-f712-4a22-abe7-bfbf3be6d0f9
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 477
ht-degree: 59%

---

# Filtros de público-alvo para relatórios

Os filtros de público-alvo (ou públicos-alvo) em [!DNL Adobe Target] são grupos de visitantes que compartilham uma característica ou um conjunto de características específicas.

Use filtros de público-alvo para especificar os públicos-alvo usados nos relatórios. É possível selecionar um público-alvo e comparar seu desempenho com o tráfego geral. Pode ser interessante saber se os seus vencedores foram várias outras fontes de tráfego em comparação com o tráfego em geral. Os filtros de público-alvo ajudam você a descobrir públicos-alvo que devem ser potencialmente direcionados a conteúdo diferente. Em muitos casos, um vencedor não é adequado para todo o tráfego.

Por exemplo, visitantes que chegam à sua página a partir de um certo mecanismo de busca podem ser um público-alvo. Outros públicos-alvo podem ter como base sexo, idade, local, status de registro, histórico de compras ou qualquer outro detalhe que você coletar sobre os seus visitantes. Utilize os filtros de público-alvo para dividir o tráfego de visitantes e para comparar o desempenho da experiência de cada segmento de tráfego.

Ao planejar o uso de filtros de público-alvo para uma atividade, considere as seguintes diretrizes:

* **Os visitantes podem estar em vários públicos.** Se houver dois públicos-alvo configurados (por exemplo, &quot;novos visitantes&quot; e &quot;visitantes do Google&quot;) e uma pessoa atender a ambos os critérios, esse visitante será contado e rastreado em ambos os públicos-alvo. Como resultado, a soma dos visitantes nos públicos-alvo não corresponde ao número de visitantes em uma campanha.
* **Configure os públicos-alvo antes de iniciar a atividade.** Os dados de público-alvo não podem ser recuperados retroativamente. Se você não configurar os filtros de público-alvo antes de começar a atividade e decidir usá-los depois que a atividade já estiver em execução por algum tempo, você não coletará os dados do tempo que já passou.
* **Comece com dois a quatro públicos-alvo.** Concentre-se nas informações básicas como fonte de tráfego.
* **Renomeie os públicos-alvo conforme necessário.** É possível renomear um público-alvo sem afetar os dados para fazer com que o nome do público-alvo seja mais significativo para os resultados coletados, mesmo que a atividade esteja ativa.
* **Insira valores precisos.** Os valores de filtro de público-alvo diferenciam maiúsculas de minúsculas. Por exemplo, se você estiver utilizando um público-alvo que filtre por cidades, você deve utilizar uma condição &quot;OU&quot; para incluir possíveis variações de digitação e maiúsculas de minúsculas como &quot;Vienna,&quot; &quot;vienna,&quot; &quot;viena&quot; e &quot;Viena&quot;.
* **Os públicos-alvo criados na lista [!UICONTROL Audiences] são reutilizáveis.** Os públicos-alvo criados como parte de uma atividade não podem ser reutilizados.

As seções a seguir fornecem mais informações sobre a configuração e o relatório sobre públicos-alvo:

| Tarefa | Tópico |
|--- |--- |
| Crie uma atividade ou teste apropriado. | [Atividades e testes](/help/main/c-intro/target-key-concepts.md) |
| Crie públicos-alvo, se necessário. | [Criar um público-alvo](/help/main/c-target/c-audiences/create-audience.md) |
| Combine vários públicos-alvo, se necessário. | [Combinar vários públicos-alvos](/help/main/c-target/combining-multiple-audiences.md) |
| Aplique os públicos-alvo na página Metas e configurações da atividade. | Teste A/B: [Metas e Configurações](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)<br>Automated Personalization: [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<br>Direcionamento de Experiência: [Metas e Configurações](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md)<br>Teste Multivariado: [Metas e Configurações](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md)<br>Recomendações: [Configurações de atividade do Recommendations](/help/main/c-recommendations/t-create-recs-activity/recs-activity-settings.md)<br>Configurações de atividade: [Configurações de Atividade](/help/main/c-activities/activity-settings.md) |
| Visualize relatórios com informações sobre seus filtros de público-alvo. | [Configurações do relatório](/help/main/c-reports/c-report-settings/report-settings.md) |
