---
keywords: Direcionamento, filtro de público-alvo, públicos-alvo, filtro
description: Saiba como usar filtros de público-alvo no [!DNL Adobe Target] para exibir dados de visitantes que compartilham características.
title: Posso usar os filtros de público-alvo para os relatórios?
feature: Públicos-alvo
exl-id: af8dae97-4b10-4edb-a0e6-0d8daf2f0d22
source-git-commit: 20a5201b5c05b1f083252ac73b3b4bbc91e97aaa
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 74%

---

# Filtros de público-alvo para relatórios

Os filtros de público-alvo (ou públicos-alvo) em [!DNL Adobe Target] são grupos de visitantes que compartilham uma característica específica ou um conjunto de características.

Use filtros de público-alvo para especificar os públicos-alvo usados nos relatórios. É possível selecionar um público-alvo e comparar seu desempenho com o tráfego geral. Pode ser interessante saber se os seus vencedores foram várias outras fontes de tráfego em comparação com o tráfego em geral. Os filtros de público-alvo ajudam você a descobrir públicos que devem ser potencialmente direcionados para conteúdo diferente. Em muitos casos, um vencedor não é adequado para todo o tráfego.

Por exemplo, visitantes que chegam à sua página a partir de um certo mecanismo de busca podem ser um público-alvo. Outros públicos-alvo podem ter como base sexo, idade, local, status de registro, histórico de compras ou qualquer outro detalhe que você coletar sobre os seus visitantes. Utilize os filtros de público-alvo para dividir o tráfego de visitantes e para comparar o desempenho da experiência de cada segmento de tráfego.

Ao planejar o uso de filtros de público-alvo para uma atividade, considere as seguintes diretrizes:

* **Os visitantes podem estar em diversos públicos-alvo.** Se houver dois públicos-alvo configurados (por exemplo, &quot;novos visitantes&quot; e &quot;visitantes do Google&quot;) e uma pessoa atender ambos os critérios, esse visitante será contado e rastreado em ambos os públicos-alvo. Como resultado, a soma dos visitantes nos públicos-alvo não corresponde ao número de visitantes em uma campanha.
* **Configure os públicos-alvo antes de iniciar a atividade.** Os dados de público-alvo não podem ser recuperados de forma retroativa. Se você não configurar os filtros de público-alvo antes de começar a atividade e decidir usá-los depois que a atividade já estiver em execução por algum tempo, você não coletará os dados do tempo que já passou.
* **Comece com dois a quatro públicos-alvo.** Concentre-se nas informações básicas como fonte de tráfego.
* **Renomeie os públicos-alvo, conforme necessário.** É possível renomear um público-alvo sem afetar os dados para fazer com que o nome do público-alvo seja mais significativo para os resultados coletados, mesmo que a atividade esteja ativa.
* **Insira valores precisos.** Os valores de filtros de público-alvo distinguem maiúsculas de minúsculas. Por exemplo, se você estiver utilizando um público-alvo que filtre por cidades, você deve utilizar uma condição &quot;OU&quot; para incluir possíveis variações de digitação e maiúsculas de minúsculas como &quot;Vienna,&quot; &quot;vienna,&quot; &quot;viena&quot; e &quot;Viena&quot;.
* **[!UICONTROL Os públicos-alvo criados na lista de segmentos são reutilizáveis.]** Os públicos-alvo criados como parte de uma atividade não podem ser reutilizados.

As seções a seguir fornecem mais informações sobre a configuração e o relatório sobre públicos-alvo:

| Tarefa | Tópico |
|--- |--- |
| Crie uma atividade ou teste apropriado. | [Atividades e testes](/help/c-intro/target-key-concepts.md) |
| Crie públicos-alvo, se necessário. | [Criar um público-alvo](/help/c-target/c-audiences/create-audience.md) |
| Combine vários públicos-alvo, se necessário. | [Combinar vários públicos](/help/c-target/combining-multiple-audiences.md) |
| Aplique os públicos-alvo na página Metas e configurações da atividade. | Teste A/B: [Metas e configurações](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)<br>Automated Personalization:  [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md)<br>Direcionamento de experiência: [Metas e configurações](/help/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md)<br>Teste multivariado:  [Metas e configurações](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md)<br>Recommendations: [Configurações de atividade do Recommendations](/help/c-recommendations/t-create-recs-activity/recs-activity-settings.md)<br>Configurações de atividade: [Configurações da atividade](/help/c-activities/activity-settings.md) |
| Visualize relatórios com informações sobre seus filtros de segmento. | [Configurações do relatório](/help/c-reports/c-report-settings/report-settings.md) |
