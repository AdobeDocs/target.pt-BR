---
keywords: personalização automatizada;ap;públicos;conjunto;random forest;multi-armed bandit;thompson sampling;ml;aprendizado de máquina
description: Saiba como usar as atividades de [!UICONTROL Automated Personalization] (AP) no  [!DNL Adobe Target] que usam aprendizagem de máquina avançada para corresponder diferentes variações de oferta a cada visitante.
title: O que é uma atividade de [!UICONTROL Automated Personalization] (AP)?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Automated Personalization
exl-id: 3654dce4-0d6c-42a3-8be7-e081ec478075
source-git-commit: d5b24f298ae405d57c2ba639082cbe99c4e358fd
workflow-type: tm+mt
source-wordcount: '931'
ht-degree: 28%

---

# [!UICONTROL Automated Personalization] (AP)

As atividades de [!UICONTROL Automated Personalization] (AP) no [!DNL Adobe Target] combinam ofertas ou mensagens e usam aprendizagem de máquina avançada para corresponder diferentes variações de oferta a cada visitante com base em seu perfil de cliente individual, a fim de personalizar o conteúdo e impulsionar o incentivo.

>[!NOTE]
>
>[!UICONTROL Automated Personalization] está disponível como parte da solução [!DNL Target Premium]. Este recurso não está disponível no [!DNL Target Standard] sem uma licença do [!DNL Target Premium]. Para obter mais informações sobre os recursos avançados fornecidos por esta licença, consulte [Target Premium](/help/main/c-intro/intro.md#premium).

De modo semelhante a [!UICONTROL Auto-Target], [!UICONTROL Automated Personalization] usa um [algoritmo Random Forest](/help/main/c-activities/t-automated-personalization/algo-random-forest.md), um dos principais métodos de conjunto de ciência de dados, como seu principal algoritmo de personalização para determinar a melhor experiência para mostrar a um visitante. [!UICONTROL Automated Personalization] pode ser valioso na fase de descoberta do teste. Também é útil permitir que a aprendizagem de máquina determine o conteúdo mais eficiente ao direcionar vários visitantes. Ao longo do tempo, o algoritmo aprende a prever o conteúdo mais eficaz e exibe o conteúdo com maior probabilidade de atingir suas metas.

Para obter mais informações sobre como [!UICONTROL Automated Personalization] difere de [!UICONTROL Auto-Target], consulte [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB).

Os profissionais de marketing implementam um arquivo em seu site, o que permite apontar e clicar em qualquer conteúdo, bem como criar visualmente e selecionar opções de conteúdo adicionais para essa área usando o [!UICONTROL Visual Experience Composer] (VEC). Em seguida, o algoritmo determina automaticamente qual parte do conteúdo será entregue a cada visitante com base em todos os dados comportamentais que o sistema tem sobre esse visitante, proporcionando uma experiência personalizada. Como o [!UICONTROL Automated Personalization] pode adaptar-se a mudanças no comportamento do visitante, ele pode ser executado sem uma data final definida para fornecer aumento e personalização contínuos. Às vezes, esse modo é chamado de &quot;sempre ativo&quot;. O profissional de marketing não precisa executar um teste, analisar os resultados e encontrar um vencedor antes de perceber a comparação encontrada na otimização, ou seja, uma ordem padrão de operações para implementar o resultado de uma atividade A/B padrão.

Os termos a seguir são úteis quando falamos de [!UICONTROL Automated Personalization]:

| Termo | Definição |
|---|---|
| Multi-armed bandit | Uma abordagem multi-armed bandit à otimização equilibra o aprendizado exploratório e o aproveitamento desse aprendizado. |
| Floresta Aleatória | Uma abordagem líder em aprendizado de máquina. Em termos de ciência de dados, é um método de classificação ou regressão de conjunto que funciona construindo muitas árvores de decisão com base nos atributos do visitante e da visita. |
| Amostragem de Thompson | O objetivo do Thompson Sampling é determinar qual experiência é a melhor em geral (não personalizada), minimizando o &quot;custo&quot; de encontrar essa experiência. A amostragem de Thompson sempre escolhe um vencedor, mesmo que não haja diferença estatística entre duas experiências. Para obter mais informações, consulte [Amostragem de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling). |

Considere os detalhes a seguir ao usar [!UICONTROL Automated Personalization]:

## [!UICONTROL Automated Personalization] usa o algoritmo Random Forest para personalizar

Random Forest é uma abordagem líder de aprendizado de máquina. Em termos de ciência de dados, é um método de classificação ou regressão de conjunto que funciona construindo muitas árvores de decisão com base nos atributos do visitante e da visita. Dentro de [!DNL Target], o Random Forest é usado para determinar qual experiência deve ter a maior probabilidade de conversão (ou a maior receita por visita) para cada visitante específico. Por exemplo, os visitantes que usam o Chrome, são membros de fidelidade Ouro e acessam o site às terças-feiras podem ter maior probabilidade de conversão com a Experiência A. Os visitantes de Nova York podem ter maior probabilidade de conversão com a Experiência B. Para obter mais informações sobre Floresta Aleatória em [!DNL Target], consulte [Algoritmo Floresta Aleatória](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

## O modelo de personalização otimiza para cada visita

* O algoritmo prevê a probabilidade de conversão de um visitante (ou a receita estimada da conversão) para fornecer a melhor experiência.
* Um visitante está qualificado para uma nova experiência no final de uma sessão existente, a menos que o visitante esteja no grupo de controle. Se o visitante estiver no grupo de controle, a experiência que o visitante vê na primeira visita é a mesma experiência vista em visitas subsequentes.
* A experiência apresentada não é alterada em uma sessão para manter a consistência visual.

## O modelo de personalização se adapta a alterações no comportamento do visitante

* O multi-arm bandit garante que o modelo está sempre &quot;gastando&quot; uma pequena fração do tráfego para continuar aprendendo ao longo da vida da atividade e evitar a exploração excessiva de tendências previamente aprendidas.
* Os modelos subjacentes são recriados a cada 24 horas usando os dados de comportamento do visitante mais recentes para garantir que [!DNL Target] esteja sempre usando a alteração das preferências do visitante.
* Se o algoritmo não puder determinar as experiências vencedoras para visitantes individuais, ele alternará automaticamente para mostrar a experiência com melhor desempenho geral e continuará a procurar vencedores personalizados. A experiência com melhor desempenho é encontrada usando a [Amostragem de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling).

## O modelo otimiza continuamente uma única meta de métrica

* Essa métrica pode ser baseada em conversão ou em receita (mais especificamente, [!UICONTROL Revenue per Visitor]).

## [!DNL Target] coleta automaticamente informações sobre visitantes para criar modelos de personalização

* Para obter mais informações sobre os atributos usados em [!UICONTROL Auto-Target] e [!UICONTROL Automated Personalization], consulte [Coleção de dados da Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-data.md).

## [!DNL Target] usa automaticamente todos os [!DNL Adobe Experience Cloud] públicos-alvo compartilhados para criar os modelos de personalização

* Não é necessário fazer nada específico para adicionar públicos-alvo ao modelo. Para obter informações sobre como usar o [!DNL Experience Cloud Audiences] com [!DNL Target], consulte [Públicos-alvo da Experience Cloud](/help/main/c-integrating-target-with-mac/mmp.md).

## Os profissionais de marketing podem fazer upload de dados offline, pontuações de propensão ou outros dados personalizados para criar modelos de personalização

Dados offline, como informações de CRM ou pontuações de propensão de churn do cliente, podem ser incrivelmente valiosos ao criar modelos de personalização. Há várias maneiras de inserir dados em algoritmos de personalização do [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Auto-Target].

* [parâmetros de mbox](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=pt-BR){target=_blank}
* [Parâmetros de perfil](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=pt-BR){target=_blank}
* [APIs do servidor para atualização de perfil](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=pt-BR){target=_blank}

Para obter informações sobre os dados coletados e usados automaticamente pelos algoritmos de personalização [!UICONTROL Automated Personalization] e [!UICONTROL Auto-Target], consulte [Coleção de dados do Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-data.md).

## Vídeo de treinamento: tipos de atividade

Este vídeo explica os tipos de atividade disponíveis no [!DNL Target]. O [!UICONTROL Automated Personalization] é discutido a partir de 5:55.

* Descreva os tipos de atividade incluídos no [!DNL Adobe Target]
* Selecione o tipo de atividade apropriado para atingir suas metas
* Descreva o fluxo de trabalho guiado em três etapas que se aplica a todos os tipos de atividade

>[!VIDEO](https://video.tv.adobe.com/v/17386)
