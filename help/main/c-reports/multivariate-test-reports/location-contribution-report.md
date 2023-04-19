---
keywords: mvt, teste multivariado, relatório de contribuição da localização
description: Saiba como usar o relatório de Contribuição de localização para o Adobe [!DNL Target] [!UICONTROL Direcionamento de experiência] atividades que mostram o desempenho de cada elemento e cada oferta.
title: Como usar o [!UICONTROL Contribuição de localização] Relatório para [!UICONTROL Teste multivariado] atividades?
feature: Reports
exl-id: 2fb7d2b3-d981-44fd-9bb2-021903605a09
source-git-commit: 6f70ff18cfbee5c02e6bb2bd345acbd2e1b2006f
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 37%

---

# [!UICONTROL Relatório de contribuição de localização (MVT)]

O [!UICONTROL Contribuição de localização] mostra o desempenho de cada elemento e cada oferta.

A parte superior do relatório mostra a métrica, as datas de início e término e o público-alvo usado no relatório. Você pode alterar qualquer um desses fatores.

>[!NOTE]
>
>Lembre-se das seguintes informações ao trabalhar com o [!UICONTROL Contribuição de localização] relatório:
>
>* O público-alvo e o seletor de métrica estão disponíveis somente se [!DNL Analytics] é usada como a fonte de relatórios (A4T).
>
>* Dados para a [!UICONTROL Contribuição de localização] é obtido do [!DNL Target] backend mesmo se a atividade estiver configurada para usar [!UICONTROL Analytics como fonte de relatórios] (A4T).
>
>* Dados para a [!UICONTROL Contribuição de localização] O relatório é buscado no ambiente &quot;Produção&quot; mesmo se um ambiente padrão diferente for definido na variável [!DNL Target] nível da conta.


O [!UICONTROL Contribuição de localização] inclui duas tabelas.

A primeira tabela mostra a influência relativa de cada elemento. Essa tabela mostra quais dos elementos em que você adicionou ofertas estão resultando em mais conversões.

![Relatório de contribuição de localização no Adobe Target](/help/main/c-reports/assets/locationcontributiontop.png)

A segunda tabela fornece um relatório de nível de oferta. Ela mostra o índice de conversão, levantamento e confiança para cada oferta em cada elemento. Esta tabela ajuda a determinar quais ofertas são as mais bem-sucedidas. A segunda coluna mostra os valores para a métrica selecionada (índice de conversão, RPV, AOV, pedidos ou métricas de envolvimento) da oferta e uma padronização.

![Relatório de contribuição de localização no Adobe Target](/help/main/c-reports/assets/locationcontributionbottom.png)

## Vídeo de treinamento: Criar um teste MVT ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo mostra como criar um teste multivariado usando o fluxo de trabalho orientado de três etapas do Target. O relatório de Contribuição da localização é descrito no começo às 08:45.

>[!VIDEO](https://video.tv.adobe.com/v/17395)
