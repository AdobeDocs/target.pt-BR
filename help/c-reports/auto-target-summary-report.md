---
description: Informações sobre como interpretar o relatório de Resumo do direcionamento automático.
keywords: relatórios, direcionamento automático, direcionamento automático, AT
seo-description: Informações sobre como interpretar o relatório de Resumo do direcionamento automático.
seo-title: Relatório de Resumo do direcionamento automático
solution: Target
subtopic: Teste multivariado
title: Relatório de Resumo do direcionamento automático
topic: Padrão
uuid: a30fa886-e8df-408f-bbc9-11a917a592d8
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Relatório de Resumo do direcionamento automático{#auto-target-summary-report}

Informações sobre como interpretar o relatório de Resumo do direcionamento automático.

A ilustração a seguir mostra como é um relatório de resumo típico quando você usa o Direcionamento automático:

![](assets/autotarget.png)

Algumas dicas e considerações ao interpretar seus relatórios de Direcionamento automático:

* As várias linhas na tabela ajudam a entender o desempenho da atividade.

   * As duas primeiras linhas na tabela na página de relatórios mostram os resultados de um teste A/B entre os visitantes que foram atribuídos ao controle (ou seja, experiências apresentadas aleatoriamente) e os visitantes que foram atribuídos ao algoritmo de personalização. Essas informações podem ser usadas para medir o desempenho do algoritmo de personalização em comparação com o controle apresentado aleatoriamente.
   * As linhas restantes mostram resultados em nível de experiência. Para cada experiência, há uma comparação entre a resposta média dos visitantes que mostraram essa experiência como um controle apresentado aleatoriamente e a resposta média dos visitantes que mostraram a experiência usando o algoritmo de personalização.

* O ícone de verificação verde ao lado de cada experiência no relatório indica que um modelo personalizado de aprendizagem de máquina foi gerado para essa experiência. O ícone do relógio indica que não foi fornecido tráfego suficiente para construir o modelo.

   * Como o modelo é construído por experiência, é possível ver um modelo para algumas experiências com uma marca verde e outras com um ícone de relógio.
   * Neste caso, para aumentar a velocidade da atividade com modelos construídos para todas as experiências, o tráfego adicional é enviado para experiências com modelos não construídos.
   * Deve haver pelo menos duas experiências com modelos construídos (marca de seleção verde) para que a personalização comece.

* Comparar a taxa de conversão da experiência A com a experiência B não é a comparação correta no Direcionamento automático. A questão é se a experiência A tem um desempenho melhor quando é apresentada de maneira inteligente versus uma maneira aleatória (em outras palavras, versus o controle). Os profissionais de marketing também devem ter cautela ao interpretar os aumentos de experiências individuais, porque o algoritmo de personalização está tentando otimizar a métrica de sucesso em toda a atividade, não em cada experiência individual.
* Experiências com o aumento mais alto podem ser entendidas como tendo a maior diferenciação dentro da população. Esse é o algoritmo que encontrou um segmento que gosta mais dessa experiência em particular.

