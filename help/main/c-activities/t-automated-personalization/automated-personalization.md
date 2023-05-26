---
keywords: personalização automatizada;ap;públicos;conjunto;random forest;multi-armed bandit;thompson sampling;ml;aprendizado de máquina
description: Saiba como usar as atividades de Automated Personalization (AP) no Adobe [!DNL Target] que usam aprendizagem de máquina avançada para corresponder diferentes variações de oferta para cada visitante.
title: O que é uma atividade de Automated Personalization (AP)?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Automated Personalization
exl-id: 3654dce4-0d6c-42a3-8be7-e081ec478075
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '1054'
ht-degree: 82%

---

# Automated Personalization (AP)

[!UICONTROL Automated Personalization] (AP) atividades no [!DNL Adobe Target] combine ofertas ou mensagens e use o aprendizado de máquina avançado para corresponder diferentes variações de oferta a cada visitante com base em seu perfil de cliente individual, a fim de personalizar o conteúdo e impulsionar o incentivo.

>[!NOTE]
>
>A [!UICONTROL Personalização automatizada] está disponível como parte da solução [!DNL Target Premium]. Não está incluído com o [!DNL Target Standard] sem uma licença do [!DNL Target Premium]. Se você tiver uma licença do [!DNL Target Premium], o cartão [!DNL Target Premium] substituirá o [!DNL Target Standard] no [!DNL Adobe Experience Cloud].

De maneira semelhante ao [!UICONTROL Direcionamento automático], a [!UICONTROL Personalização automatizada] usa um algoritmo Random Forest, um dos principais métodos de conjunto de ciência de dados, como seu principal algoritmo de personalização para determinar a melhor experiência para mostrar a um visitante. [!UICONTROL A Personalização automatizada] pode ser valiosa na fase de descoberta do teste. Também é útil permitir que a aprendizagem de máquina determine o conteúdo mais eficiente ao direcionar vários visitantes. Ao longo do tempo, o algoritmo aprende a prever o conteúdo mais eficaz e exibe o conteúdo com maior probabilidade de atingir suas metas.

Para obter mais informações sobre como [!UICONTROL Automated Personalization] difere de [!UICONTROL Direcionamento automático], consulte [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

Os profissionais de marketing implementam um arquivo em seu site, o que os permite apontar e clicar em qualquer conteúdo, bem como criar visualmente e selecionar opções de conteúdo adicionais para essa área usando o VEC ([!UICONTROL Visual Experience Composer]). Em seguida, o algoritmo determina automaticamente qual parte do conteúdo será entregue a cada visitante com base em todos os dados comportamentais que o sistema tem sobre esse visitante, proporcionando uma experiência personalizada. Como a [!UICONTROL Personalização automatizada] pode adaptar-se a mudanças no comportamento do visitante, é possível executá-la sem uma data final definida para fornecer aumento e personalização contínuos. Às vezes, isso é chamado de modo &quot;sempre ativo&quot;. O profissional de marketing não precisa executar um teste, analisar os resultados e encontrar um vencedor antes de perceber a comparação encontrada na otimização, ou seja, uma ordem padrão de operações para implementar o resultado de uma atividade A/B padrão.

Os termos a seguir são úteis ao discutir a [!UICONTROL Personalização automatizada]:

| Termo | Definição |
|---|---|
| Multi-armed bandit | Uma abordagem multi-armed bandit à otimização equilibra o aprendizado exploratório e o aproveitamento desse aprendizado. |
| Floresta Aleatória | Random Forest é uma abordagem de aprendizado de máquina líder. No contexto da ciência de dados, é um método de classificação ou regressão de conjuntos que funciona por meio da construção de um grande número de árvores de decisão com base nos atributos do visitante e da visita. No Target, o Random Forest é usado para determinar qual experiência deve ter a maior probabilidade de conversão (ou maior receita por visita) para cada visitante específico. Para obter mais informações sobre o Random Forest no Target, consulte  [Algoritmo Random Forest](/help/main/c-activities/t-automated-personalization/algo-random-forest.md). |
| Amostragem de Thompson | O objetivo do Thompson Sampling é determinar qual experiência é a melhor em geral (não personalizada), minimizando o &quot;custo&quot; de encontrar essa experiência. A amostragem de Thompson sempre escolhe um vencedor, mesmo que não haja diferença estatística entre duas experiências. Para obter mais informações, consulte [Amostragem de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling). |

Considere os detalhes a seguir ao usar a [!UICONTROL Personalização automatizada]:

**[!UICONTROL A Personalização automatizada] usa o algoritmo Random Forest para personalizar.**

Random Forest é uma abordagem de aprendizado de máquina líder. No contexto da ciência de dados, é um método de classificação ou regressão de conjuntos que funciona por meio da construção de um grande número de árvores de decisão com base nos atributos do visitante e da visita. No Target, o Random Forest é usado para determinar qual experiência deve ter a maior probabilidade de conversão (ou maior receita por visita) para cada visitante específico. Por exemplo, os visitantes que usam o Chrome, são membros de fidelidade Ouro e acessam o site às terças-feiras podem ter maior probabilidade de conversão com a Experiência A, enquanto que os visitantes de Nova York podem ter maior probabilidade de conversão com a Experiência B. Para obter mais informações sobre o Random Forest no Target, consulte  [Algoritmo Random Forest](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

**O modelo de personalização é otimizado para cada visita.**

* O algoritmo prevê a probabilidade de conversão de um visitante (ou a receita estimada da conversão) para oferecer a melhor experiência.
* Um visitante é qualificado para uma nova experiência ao final de uma sessão existente (a menos que ele esteja no grupo de controle e, nesse caso, a experiência que o visitante vê na primeira visita é a mesma que ele verá nas visitas subsequentes).
* Em uma sessão, a experiência apresentada não muda para manter a consistência visual.

**O modelo de personalização se adapta às mudanças de comportamento do visitante.**

* O multi-arm bandit garante que o modelo está sempre &quot;gastando&quot; uma pequena fração do tráfego para continuar aprendendo durante a vida da atividade, e para evitar a exploração excessiva de tendências aprendidas anteriormente.
* Os modelos subjacentes são reconstruídos a cada 24 horas usando os dados mais recentes sobre o comportamento do visitante para garantir que o Target esteja sempre aproveitando as preferências atuais do visitante.
* Se o algoritmo não puder determinar as experiências vencedoras para visitantes individuais, ele alternará automaticamente para mostrar a experiência com melhor desempenho geral e continuará a procurar vencedores personalizados. A experiência com melhor desempenho é encontrada usando a [Amostragem de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling).

**O modelo otimiza continuamente uma única meta de métrica.**

* Essa métrica pode ser baseada em conversão ou em receita (mais especificamente, [!UICONTROL Receita por visitante]).

**O Target coleta automaticamente informações sobre os visitantes para criar os modelos de personalização.**

* Para obter mais informações sobre os atributos usados no [!UICONTROL Direcionamento automático] e na [!UICONTROL Personalização automatizada], consulte [Coleta de dados de personalização automatizada](/help/main/c-activities/t-automated-personalization/ap-data.md).

**O Target usa automaticamente todos os [!DNL Adobe Experience Cloud] públicos-alvo compartilhados para criar os modelos de personalização.**

* Você não precisa fazer nada específico para adicionar públicos-alvo ao modelo. Para obter informações sobre como usar o [!DNL Experience Cloud Audiences] com [!DNL Target], consulte [Públicos-alvo da Experience Cloud](/help/main/c-integrating-target-with-mac/mmp.md).

**Os profissionais de marketing podem fazer upload offline de dados, pontuações de propensão ou outros dados personalizados para criar os modelos de personalização.**

Dados offline, como informações de CRM ou pontuações de tendência de perda de clientes, podem ser extremamente valiosos ao criar modelos de personalização. Há várias maneiras de inserir dados em algoritmos de [!UICONTROL Personalização automatizada] (AP) e [!UICONTROL Direcionamento automático].

* [parâmetros de mbox](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}
* [Parâmetros do perfil](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}
* [APIs do lado do servidor para atualização de perfil](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}

Para obter informações sobre os dados coletados e usados automaticamente pelos [!UICONTROL algoritmos de Personalização automatizada] e [!UICONTROL Direcionamento automático], consulte [Coleta de dados de personalização automatizada](/help/main/c-activities/t-automated-personalization/ap-data.md).

## ![Selo de visão geral](/help/main/assets/overview.png) Vídeo de treinamento: tipos de atividade

Este vídeo explica os tipos de atividades disponíveis no [!DNL Target Standard/Premium]. [!UICONTROL A personalização automatizada é discutida a partir de 5:55.]

* Descreva os tipos de atividades incluídas em [!DNL Adobe Target]
* Selecione o tipo de atividade apropriado para atingir suas metas
* Descreva o fluxo de trabalho guiado em três etapas que se aplica a todos os tipos de atividade

>[!VIDEO](https://video.tv.adobe.com/v/17386)
