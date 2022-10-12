---
keywords: relatórios, baixar relatórios, csv, métrica de sucesso, detalhes do pedido
description: Saiba como baixar dados do Adobe [!DNL Target] atividades em um formato CVS para permitir uma importação rápida para Excel, Access ou outros programas de análise de dados.
title: Como faço o download de dados de relatório em um arquivo CSV?
feature: Reports
exl-id: b4387184-8730-4367-8bc3-52d8fbe2583e
source-git-commit: fc1dcc2b6de1248c35191c1ecd7b36aeb891fd3f
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 54%

---

# Download de dados em um arquivo CSV

Baixe dados em um formato .csv para permitir uma importação rápida para Excel, Access ou outros programas de análise de dados.

Download de dados em um arquivo CSV:

1. Clique em **[!UICONTROL Atividades]** e depois clique na atividade desejada na lista.

   Se você tem muitas atividades, você pode filtrar a lista selecionando opções nas listas suspensas [!UICONTROL Tipo], [!UICONTROL Status], [!UICONTROL Fonte de geração de relatórios], [!UICONTROL Experience Composer], [!UICONTROL Tipo de métrica] e [!UICONTROL Fonte da atividade].

1. Clique na guia **[!UICONTROL Relatórios]**.
1. Clique no ícone **[!UICONTROL Download]** e depois selecione um tipo de relatório para baixar para análise em Excel e outras ferramentas.

   * [!UICONTROL Exportar relatórios para CSV]
   * [!UICONTROL Exportar detalhes do pedido para CSV]

   ![Baixar opções](/help/main/c-reports/assets/download-options.png)

## [!UICONTROL Exportar relatório para CSV] {#section_38BD9743EB254453B5F4A0A6F2720CD3}

O [!UICONTROL Métricas de sucesso] mostra informações sobre suas métricas de sucesso e as métricas a seguir que não estão disponíveis no [!DNL Target] IU:

* O tempo médio para a conversão em horas, assim você pode visualizar quanto tempo o visitante médio leva para atingir o ponto de conversão
* Soma das receitas, elevado ao quadrado, para cálculos de confiança estatística offline

Os dados são salvos até o final da atividade.

>[!NOTE]
>
>O relatório de CSV inclui apenas dados brutos e não inclui métricas calculadas, como receita por visitante, aumento ou confiança usada para testes A/B. Para calcular essas métricas calculadas, baixe a variável [!DNL Target] [Calculadora de confiança completa](/help/main/assets/complete_confidence_calculator.xlsx) Arquivo do Excel para inserir o valor da atividade ou revisar [Cálculos estatísticos em testes A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## [!UICONTROL Exportar detalhes do pedido para CSV] {#section_96B3F578F91F4CA3AFE38BACA2A0F11E}

O [!UICONTROL Detalhes do pedido] mostra informações sobre seus pedidos, incluindo:

* Data e hora do pedido
* Quantidade de pedido (se foi inserida uma mbox de colocação de pedido)

   O [!UICONTROL Detalhes do pedido] O relatório funciona somente se você tiver pedidos.

* Indicador de pedido (pedidos duplicados ou extremos)

   Um pedido é sinalizado como extremo se ele tiver +/- 3 desvios padrão do valor médio de pedido. Esse cálculo utiliza o último mês dos dados (até o momento em que o cálculo foi feito). Uma atividade terá seus pedidos extremos excluídos após a atividade ter sido executada por uma hora ou 15 pedidos, o que ocorrer primeiro. Para obter mais informações, consulte [Exceto pedidos extremos](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA).

* Identificação do produto

   O tamanho total das IDs de produto, concatenadas com vírgulas, não deve exceder 255 caracteres ou as IDs não serão exibidas corretamente no relatório. Por exemplo: se seu pedido tem produtos com os IDs &quot;aa, bb&quot;, o tamanho total é &quot;aa,bb&quot; = 5.

* Experiência

   No relatório [!UICONTROL Detalhes do pedido] para atividades de [!UICONTROL Teste A/B], [!UICONTROL Direcionamento de experiência] (XT) e [!UICONTROL Teste multivariado] (MVT), a coluna [!UICONTROL Experiência] contém a `localId` (identificação do local) da experiência. Este é o valor emitido de `$campaign.recipe.id` em tokens de oferta.

   Não há uma coluna [!UICONTROL Experiência] para atividades de [!UICONTROL Personalização automatizada] (AP). A coluna [!UICONTROL Nome do algoritmo] atual foi substituída pela terminologia &quot;Controle&quot; versus &quot;Segmentação&quot;, conforme mostrado no [!DNL Target].

   Não houve impacto para as atividades do [!UICONTROL Recommendations].

>[!NOTE]
>
>* Os dados do relatório do pedido incluem quatro semanas de dados para o ambiente padrão (grupo de hosts) e duas semanas para todos os ambientes não padrão.
>* Métricas de receita definidas como &quot;[!UICONTROL Incrementar a contagem e manter o usuário na atividade]&quot; registrar detalhes do pedido somente para o primeiro pedido feito pelo mesmo visitante. Todos os pedidos subsequentes aumentam a contagem de conversão, mas não adicionam receita a RPV/AOV/Vendas, e não são incluídos na [!UICONTROL Detalhes do pedido] relatório.


## Práticas recomendadas

* Para registrar um registro de pedido, a variável `orderTotal` deve ser transmitido.
* Valores transmitidos por meio do parâmetro mbox `ProductPurchasedId` estão listados no relatório Detalhes do pedido.
* A prática recomendada é incluir uma `orderID` e um `orderTotal`. Isso permite duplicar pedidos para serem omitidos automaticamente.

## Avisos {#section_49B9590904A645B18E694B4EFFFC1DEF}

As seguintes informações aplicam-se ao [!UICONTROL Baixar] opção:

* Você pode baixar ambos os relatórios para [!UICONTROL Teste A/B], [!UICONTROL Automated Personalization], [!UICONTROL Direcionamento de experiência]e [!UICONTROL Multivariado] atividades. Não é possível baixar o [!UICONTROL Métricas de sucesso] relatório de [!UICONTROL Recommendations] atividades.
* O [!UICONTROL Baixar] não está disponível para [!UICONTROL Teste A/B] e [!UICONTROL Direcionamento de experiência] atividades criadas antes de [!DNL Target] versão 15.7.1 (julho de 2015).
* Experiências sem dados associados não são registradas no relatório baixado.
* Públicos-alvo aplicados na [!DNL Target] a interface do usuário de relatórios não é transferida para o relatório de download.
* Os relatórios gerados para download como arquivos .csv são inconsistentes se a atividade usar mais de uma métrica. O relatório que pode ser baixado é gerado somente com base nas configurações do relatório e considera o mesmo valor para qualquer outra métrica usada. A fonte da verdade é sempre o relatório exibido na interface do usuário do [!DNL Target].
