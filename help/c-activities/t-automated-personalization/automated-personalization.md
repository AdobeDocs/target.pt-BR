---
keywords: automated personalization;Audiences;ensemble;random forest
description: A Personalização automatizada (AP) combina ofertas ou mensagens e usa aprendizagem de máquina avançada para corresponder diferentes variações de oferta a cada visitante com base em seu perfil de cliente individual, a fim de personalizar o conteúdo e impulsionar o incentivo.
title: Personalização automatizada
feature: ap
topic: Advanced
uuid: cf9489f2-45b2-4028-8956-36d0afe0ee0a
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '1023'
ht-degree: 98%

---


# ![PREMIUM](/help/assets/premium.png) Personalização automatizada{#automated-personalization}

A [!UICONTROL Personalização automatizada] (AP) combina ofertas ou mensagens e usa aprendizagem de máquina avançada para corresponder diferentes variações de oferta a cada visitante com base em seu perfil de cliente individual, a fim de personalizar o conteúdo e impulsionar o incentivo.

>[!NOTE]
>
>A [!UICONTROL Personalização automatizada] está disponível como parte da solução [!DNL Target Premium]. Não está incluído com o [!DNL Target Standard] sem uma licença do [!DNL Target Premium]. Se você tiver uma licença do [!DNL Target Premium], o cartão [!DNL Target Premium] substituirá o [!DNL Target Standard] no [!DNL Adobe Experience Cloud].

De maneira semelhante ao [!UICONTROL Direcionamento automático], a [!UICONTROL Personalização automatizada] usa um algoritmo Random Forest, um dos principais métodos de conjunto de ciência de dados, como seu principal algoritmo de personalização para determinar a melhor experiência para mostrar a um visitante. [!UICONTROL A Personalização automatizada] pode ser valiosa na fase de descoberta do teste. Também é útil permitir que a aprendizagem de máquina determine o conteúdo mais eficiente ao direcionar vários visitantes. Ao longo do tempo, o algoritmo aprende a prever o conteúdo mais eficaz e exibe o conteúdo com maior probabilidade de atingir suas metas.

Para encontrar mais informações sobre como a [!UICONTROL Personalização automatizada] difere do [!UICONTROL Direcionamento automático], consulte [Direcionamento automático para experiências personalizadas](../../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3).

Os profissionais de marketing implementam um arquivo em seu site, o que os permite apontar e clicar em qualquer conteúdo, bem como criar visualmente e selecionar opções de conteúdo adicionais para essa área usando o VEC ([!UICONTROL Visual Experience Composer]). Em seguida, o algoritmo determina automaticamente qual parte do conteúdo será entregue a cada visitante com base em todos os dados comportamentais que o sistema tem sobre esse visitante, proporcionando uma experiência personalizada. Como a [!UICONTROL Personalização automatizada] pode adaptar-se a mudanças no comportamento do visitante, é possível executá-la sem uma data final definida para fornecer aumento e personalização contínuos. Por vezes, também é conhecido como modo &quot;sempre ligado&quot;. O profissional de marketing não precisa executar um teste, analisar os resultados e encontrar um vencedor antes de perceber a comparação encontrada na otimização, ou seja, uma ordem padrão de operações para implementar o resultado de uma atividade A/B padrão.

Os termos a seguir são úteis ao discutir a [!UICONTROL Personalização automatizada]:

| Termo | Definição |
|---|---|
| Multi-armed bandit | Uma abordagem multi-armed bandit à otimização equilibra o aprendizado exploratório e o aproveitamento desse aprendizado. |
| Floresta Aleatória | Random Forest é uma abordagem de aprendizado de máquina líder. No contexto da ciência de dados, é um método de classificação ou regressão de conjuntos que funciona por meio da construção de um grande número de árvores de decisão com base nos atributos do visitante e da visita. No Target, o Random Forest é usado para determinar qual experiência deve ter a maior probabilidade de conversão (ou maior receita por visita) para cada visitante específico. Para obter mais informações sobre o Random Forest no Target, consulte  [Algoritmo Random Forest](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA). |
| Amostragem de Thompson | O objetivo da Amostragem de Thompson é determinar qual experiência é a melhor em geral (não personalizada), enquanto minimiza o &quot;custo&quot; da procura dessa experiência. A amostragem de Thompson sempre escolhe um vencedor, mesmo que não haja diferença estatística entre duas experiências. Para obter mais informações, consulte [Amostragem de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling). |

Considere os detalhes a seguir ao usar a [!UICONTROL Personalização automatizada]:

**[!UICONTROL A Personalização automatizada]usa o algoritmo Random Forest para personalizar.**

Random Forest é uma abordagem de aprendizado de máquina líder. No contexto da ciência de dados, é um método de classificação ou regressão de conjuntos que funciona por meio da construção de um grande número de árvores de decisão com base nos atributos do visitante e da visita. No Target, o Random Forest é usado para determinar qual experiência deve ter a maior probabilidade de conversão (ou maior receita por visita) para cada visitante específico. Por exemplo, os visitantes que usam o Chrome, são membros de fidelidade Ouro e acessam o site às terças-feiras podem ter maior probabilidade de conversão com a Experiência A, enquanto que os visitantes de Nova York podem ter maior probabilidade de conversão com a Experiência B. Para obter mais informações sobre o Random Forest no Target, consulte  [Algoritmo Random Forest](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA).

**O modelo de personalização é otimizado para cada visita.**

* O algoritmo prevê a probabilidade de conversão de um visitante (ou a receita estimada da conversão) para oferecer a melhor experiência.
* Um visitante é qualificado para uma nova experiência ao final de uma sessão existente (a menos que ele esteja no grupo de controle e, nesse caso, a experiência que o visitante vê na primeira visita é a mesma que ele verá nas visitas subsequentes).
* Em uma sessão, a experiência apresentada não muda para manter a consistência visual.

**O modelo de personalização se adapta às mudanças de comportamento do visitante.**

* O multi-armed bandit garante que o modelo esteja sempre &quot;gastando&quot; uma pequena fração do tráfego para continuar aprendendo durante toda a vida da atividade e para evitar a exploração excessiva de tendências aprendidas anteriormente.
* Os modelos subjacentes são reconstruídos a cada 24 horas usando os dados mais recentes sobre o comportamento do visitante para garantir que o Target esteja sempre aproveitando as preferências atuais do visitante.
* Se o algoritmo não puder determinar as experiências vencedoras para visitantes individuais, ele alternará automaticamente para mostrar a experiência com melhor desempenho geral e continuará a procurar vencedores personalizados. A experiência com melhor desempenho é encontrada usando a [Amostragem de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling).

**O modelo otimiza continuamente uma única meta de métrica.**

* Essa métrica pode ser baseada em conversão ou em receita (mais especificamente, [!UICONTROL Receita por visitante]).

**O Target coleta automaticamente informações sobre os visitantes para criar os modelos de personalização.**

* Para obter mais informações sobre os atributos usados no [!UICONTROL Direcionamento automático] e na [!UICONTROL Personalização automatizada], consulte [Coleta de dados de personalização automatizada](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058).

**O Target usa automaticamente todos os[!DNL Adobe Experience Cloud]públicos-alvo compartilhados para criar os modelos de personalização.**

* Você não precisa fazer nada específico para adicionar públicos-alvo ao modelo. Para obter informações sobre como usar o [!DNL Experience Cloud Audiences] com [!DNL Target], consulte [Públicos-alvo da Experience Cloud](../../c-integrating-target-with-mac/mmp.md#concept_F4863DE4C92D4805AB690B4B3D487969).

**Os profissionais de marketing podem fazer upload offline de dados, pontuações de propensão ou outros dados personalizados para criar os modelos de personalização.**

Dados offline, como informações de CRM ou pontuações de tendência de perda de clientes, podem ser extremamente valiosos ao criar modelos de personalização. Há várias maneiras de inserir dados em algoritmos de [!UICONTROL Personalização automatizada] (AP) e [!UICONTROL Direcionamento automático].

* [parâmetros de mbox](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17)
* [Parâmetros do perfil](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17)
* [APIs do lado do servidor para atualização de perfil](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17)

Para obter informações sobre os dados coletados e usados automaticamente pelos [!UICONTROL algoritmos de Personalização automatizada] e [!UICONTROL Direcionamento automático], consulte [Coleta de dados de personalização automatizada](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058).

## ![Vídeo de treinamento do emblema](/help/assets/overview.png) Visão geral: Tipos de atividade

Este vídeo explica os tipos de atividades disponíveis no [!DNL Target Standard/Premium]. [!UICONTROL A personalização automatizada é discutida a partir de 5:55.]

* Descreva os tipos de atividades incluídas em [!DNL Adobe Target]
* Selecione o tipo de atividade apropriado para atingir suas metas
* Descreva o fluxo de trabalho guiado em três etapas que se aplica a todos os tipos de atividade

>[!VIDEO](https://video.tv.adobe.com/v/17386)