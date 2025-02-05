---
keywords: relatórios, baixar relatórios, csv, métrica de sucesso, detalhes do pedido
description: Saiba como baixar dados de atividades Adobe [!DNL Target] em um formato CVS para permitir uma importação rápida para Excel, Access ou outros programas de análise de dados.
title: Como baixar dados de relatório em um arquivo CSV?
feature: Reports
exl-id: b4387184-8730-4367-8bc3-52d8fbe2583e
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 34%

---

# Download de dados em um arquivo CSV

Baixe dados em um formato .csv para permitir uma importação rápida para [!DNL Excel], [!DNL Access] ou outros programas de análise de dados.

Download de dados em um arquivo CSV:

1. Clique em **[!UICONTROL Activities]** e depois clique na atividade desejada na lista.

   Se você tiver muitas atividades, clique no ícone Filtro ( ![Ícone Filtro](/help/main/assets/icons/Filter.svg) ) para filtrar a lista selecionando opções nas listas suspensas [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type] e [!UICONTROL Activity Source].

1. Clique na guia **[!UICONTROL Reports]**.
1. Clique no ícone **[!UICONTROL Download]** ( ![Ícone de download](/help/main/assets/icons/Download.svg) ) e selecione um tipo de relatório para baixar para análise em Excel e outras ferramentas.

   * [!UICONTROL Export Reports to CSV]
   * [!UICONTROL Export Order Details to CSV]

## [!UICONTROL Export Report to CSV] {#section_38BD9743EB254453B5F4A0A6F2720CD3}

O relatório [!UICONTROL Success Metrics] mostra informações sobre suas métricas de sucesso e as seguintes métricas que não estão disponíveis na interface do usuário do [!DNL Target]:

* O tempo médio para a conversão em horas, assim você pode visualizar quanto tempo o visitante médio leva para atingir o ponto de conversão
* Soma das receitas, elevado ao quadrado, para cálculos de confiança estatística offline

Os dados são salvos até o final da atividade.

>[!NOTE]
>
>O relatório de CSV inclui apenas dados brutos e não inclui métricas calculadas, como receita por visitante, aumento ou confiança usada para testes A/B. Para calcular essas métricas, baixe o arquivo do Excel [!DNL Target] [Calculadora de Confiança Completa](/help/main/assets/complete_confidence_calculator.xlsx) para inserir o valor da atividade ou revise [Cálculos estatísticos em testes A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## [!UICONTROL Export Order Details to CSV] {#section_96B3F578F91F4CA3AFE38BACA2A0F11E}

O relatório [!UICONTROL Order Details] mostra as informações sobre seus pedidos, incluindo:

* Data e hora do pedido
* Quantidade de pedido (se foi inserida uma mbox de colocação de pedido)

  O relatório [!UICONTROL Order Details] funciona somente se você tiver pedidos.

* Indicador de pedido (pedidos duplicados ou extremos)

  Um pedido é sinalizado como extremo se for maior que +/- 3 desvios padrão do valor médio de pedido. Esse cálculo usa o último mês dos dados (até o momento em que o cálculo foi feito). Uma atividade terá seus pedidos extremos excluídos após a atividade ter sido executada por uma hora ou 15 pedidos, o que ocorrer primeiro. Para obter mais informações, consulte [Exceto pedidos extremos](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA).

* Identificação do produto

  O comprimento total das IDs do produto, concatenadas com vírgulas, não deve exceder 255 caracteres ou as IDs não são exibidas corretamente no relatório. Por exemplo: se seu pedido tem produtos com os IDs &quot;aa, bb&quot;, o tamanho total é &quot;aa,bb&quot; = 5.

* Experiência

  No relatório [!UICONTROL Order Details] para atividades de [!UICONTROL A/B Test], [!UICONTROL Experience Targeting] (XT) e [!UICONTROL Multivariate Test] (MVT), a coluna [!UICONTROL Experience] contém a experiência `localId`. Este é o valor emitido de `$campaign.recipe.id` em tokens de oferta.

  Não há uma coluna [!UICONTROL Experience] para atividades de [!UICONTROL Automated Personalization] (AP). A coluna [!UICONTROL Algorithm Name] atual foi substituída pela terminologia &quot;Controle&quot; versus &quot;Segmentação&quot;, conforme mostrado no [!DNL Target].

  Não houve impacto para [!UICONTROL Recommendations] atividades.

>[!NOTE]
>
>* Os dados do relatório do pedido incluem quatro semanas de dados para o ambiente padrão (grupo de hosts) e duas semanas para todos os ambientes não padrão.
>* Métricas de receita definidas como &quot;[!UICONTROL Increment count and keep the user in the activity]&quot; registram detalhes da ordem somente para a primeira ordem feita pelo mesmo visitante. Todos os pedidos subsequentes aumentam a contagem de conversão, mas não adicionam receita a RPV/AOV/Vendas e não estão incluídos no relatório [!UICONTROL Order Details].

## Práticas recomendadas

* Para registrar um registro de pedido, o parâmetro `orderTotal` deve ser transmitido.
* Valores transmitidos por meio do parâmetro mbox `ProductPurchasedId` estão listados no relatório [!UICONTROL Order Details].
* A prática recomendada é incluir um `orderID` e um `orderTotal`. Isso permite duplicar pedidos para serem omitidos automaticamente.

## Avisos {#section_49B9590904A645B18E694B4EFFFC1DEF}

As seguintes informações se aplicam à opção [!UICONTROL Download]:

* Você pode baixar ambos os relatórios para atividades de [!UICONTROL A/B Test], [!UICONTROL Automated Personalization], [!UICONTROL Experience Targeting] e [!UICONTROL Multivariate]. Você não pode baixar o relatório [!UICONTROL Success Metrics] para [!UICONTROL Recommendations] atividades.
* A opção [!UICONTROL Download] não está disponível para atividades [!UICONTROL A/B Test] e [!UICONTROL Experience Targeting] criadas antes da versão [!DNL Target] 15.7.1 (julho de 2015).
* Experiências sem dados associados não são registradas no relatório baixado.
* Os públicos aplicados na interface do usuário de relatórios [!DNL Target] não são transferidos para o relatório de download.
* Os relatórios gerados para download como arquivos .csv são inconsistentes se a atividade usar mais de uma métrica. O relatório que pode ser baixado é gerado somente com base nas configurações do relatório e considera o mesmo valor para qualquer outra métrica usada. A fonte da verdade é sempre o relatório exibido na interface do usuário do [!DNL Target].
