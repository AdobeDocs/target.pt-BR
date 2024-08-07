---
keywords: Direcionamento;filtro de público-alvo;públicos-alvo;filtro
description: Saiba como usar os filtros de público-alvo no [!DNL Adobe Target]  para exibir dados de visitantes que compartilham características.
title: Posso usar filtros de público-alvo para relatórios?
feature: Audiences
exl-id: af8dae97-4b10-4edb-a0e6-0d8daf2f0d22
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 72%

---

# Filtros de público-alvo para relatórios

Os filtros de público-alvo (ou públicos-alvo) em [!DNL Adobe Target] são grupos de visitantes que compartilham uma característica ou um conjunto de características específicas.

Use filtros de público-alvo para especificar os públicos-alvo usados nos relatórios. É possível selecionar um público-alvo e comparar seu desempenho com o tráfego geral. Pode ser interessante saber se os seus vencedores foram várias outras fontes de tráfego em comparação com o tráfego em geral. Os filtros de público-alvo ajudam você a descobrir públicos-alvo que devem ser potencialmente direcionados a conteúdo diferente. Em muitos casos, um vencedor não é adequado para todo o tráfego.

Por exemplo, visitantes que chegam à sua página a partir de um certo mecanismo de busca podem ser um público-alvo. Outros públicos-alvo podem ter como base sexo, idade, local, status de registro, histórico de compras ou qualquer outro detalhe que você coletar sobre os seus visitantes. Utilize os filtros de público-alvo para dividir o tráfego de visitantes e para comparar o desempenho da experiência de cada segmento de tráfego.

Ao planejar o uso de filtros de público-alvo para uma atividade, considere as seguintes diretrizes:

* **Os visitantes podem estar em diversos públicos-alvo.** Se houver dois públicos-alvo configurados (por exemplo, &quot;novos visitantes&quot; e &quot;visitantes do Google&quot;) e uma pessoa atender a ambos os critérios, esse visitante será contado e rastreado em ambos os públicos-alvo. Como resultado, a soma dos visitantes nos públicos-alvo não corresponde ao número de visitantes em uma campanha.
* **Configure os públicos-alvo antes de iniciar a atividade.** Os dados de público-alvo não podem ser recuperados de forma retroativa. Se você não configurar os filtros de público-alvo antes de começar a atividade e decidir usá-los depois que a atividade já estiver em execução por algum tempo, você não coletará os dados do tempo que já passou.
* **Comece com dois a quatro públicos-alvo.** Concentre-se nas informações básicas como fonte de tráfego.
* **Renomeie os públicos-alvo, conforme necessário.** É possível renomear um público-alvo sem afetar os dados para fazer com que o nome do público-alvo seja mais significativo para os resultados coletados, mesmo que a atividade esteja ativa.
* **Insira valores precisos.** Os valores de filtros de público-alvo distinguem maiúsculas de minúsculas. Por exemplo, se você estiver utilizando um público-alvo que filtre por cidades, você deve utilizar uma condição &quot;OU&quot; para incluir possíveis variações de digitação e maiúsculas de minúsculas como &quot;Vienna,&quot; &quot;vienna,&quot; &quot;viena&quot; e &quot;Viena&quot;.
* **Os públicos-alvo criados na lista [!UICONTROL Audiences] são reutilizáveis.** Os públicos-alvo criados como parte de uma atividade não podem ser reutilizados.

As seções a seguir fornecem mais informações sobre a configuração e o relatório sobre públicos-alvo:

| Tarefa | Tópico |
|--- |--- |
| Crie uma atividade ou teste apropriado. | [Atividades e testes](/help/main/c-intro/target-key-concepts.md) |
| Crie públicos-alvo, se necessário. | [Criar um público-alvo](/help/main/c-target/c-audiences/create-audience.md) |
| Combine vários públicos-alvo, se necessário. | [Combinar vários públicos](/help/main/c-target/combining-multiple-audiences.md) |
| Aplique os públicos-alvo na página Metas e configurações da atividade. | Teste A/B: [Metas e Configurações](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)<br>Automated Personalization: [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<br>Direcionamento de Experiência: [Metas e Configurações](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md)<br>Teste Multivariado: [Metas e Configurações](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md)<br>Recommendations: [Configurações de atividade do Recommendations](/help/main/c-recommendations/t-create-recs-activity/recs-activity-settings.md)<br>Configurações da atividade: [Configurações da Atividade](/help/main/c-activities/activity-settings.md) |
| Visualize relatórios com informações sobre seus filtros de segmento. | [Configurações do relatório](/help/main/c-reports/c-report-settings/report-settings.md) |
