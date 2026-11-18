---
keywords: personalização automatizada;ap;públicos;conjunto;random forest;multi-armed bandit;thompson sampling;ml;aprendizado de máquina
description: Saiba como usar as atividades de [!UICONTROL Automated Personalization] (AP) em [!DNL Adobe Target] que usam aprendizagem de máquina avançada para corresponder diferentes variações de oferta para cada visitante.
title: O que é uma Atividade de [!UICONTROL Automated Personalization] (AP)?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Automated Personalization
exl-id: 3654dce4-0d6c-42a3-8be7-e081ec478075
TQID: 'https://experienceleague.adobe.com/BBtKgNRTlqNFFoAjr1LQkhHyZeAlXG2h8D7bsndh4kQ'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: fff07a91-d479-45f4-ae95-9762e79b1b7c
    internal-label: Shared audiences
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
source-git-commit: de439134b0ee5aa795ae255bba852b9b6f10da12
workflow-type: tm+mt
source-wordcount: '908'
ht-degree: 15%
---
# Introdução ao [!UICONTROL Automated Personalization] {#automated-personalization-overview}

>[!BEGINSHADEBOX]

**Nesta página:** saiba como uma atividade do **[!UICONTROL Automated Personalization]** corresponde a variações de oferta para cada visitante e o que considerar ao usá-la.

>[!ENDSHADEBOX]

>[!NOTE]
>
>O **[!UICONTROL Automated Personalization]** está disponível como parte da solução [!DNL Target Premium]. Este recurso não está disponível no [!DNL Target Standard] sem uma licença do [!DNL Target Premium]. Para obter mais informações sobre os recursos avançados fornecidos por esta licença, consulte [Target Premium](/help/main/c-intro/intro.md#premium).

As atividades de **[!UICONTROL Automated Personalization]** (AP) no [!DNL Adobe Target] combinam ofertas ou mensagens e usam aprendizagem de máquina avançada para corresponder diferentes variações de oferta a cada visitante com base em seu perfil de cliente individual, a fim de personalizar o conteúdo e impulsionar o incentivo.

Os profissionais de marketing implementam um arquivo em seu site, o que permite apontar e clicar em qualquer conteúdo e, em seguida, criar visualmente opções de conteúdo adicionais para essa área usando o **[!UICONTROL Visual Experience Composer]** (VEC). O algoritmo determina automaticamente qual parte do conteúdo será entregue a cada visitante, com base em todos os dados comportamentais que o sistema tem sobre esse visitante.

O **[!UICONTROL Automated Personalization]** adapta-se às mudanças no comportamento do visitante, para que possa ser executado sem uma data final definida para fornecer aumento e personalização contínuos. Às vezes, esse modo é chamado de &quot;sempre ativo&quot;. O profissional de marketing não precisa executar um teste, analisar os resultados e encontrar um vencedor antes de realizar o aumento. O **[!UICONTROL Automated Personalization]** também é valioso na fase de descoberta do teste e quando você direciona visitantes diversos. Para obter mais informações sobre como ele difere do **[!UICONTROL Direcionamento automático]**, consulte [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB).

Os termos a seguir são úteis quando falamos de **[!UICONTROL Automated Personalization]**:

| Termo | Definição |
|---|---|
| Multi-armed bandit | Uma abordagem multi-armed bandit à otimização equilibra o aprendizado exploratório e o aproveitamento desse aprendizado. |
| Floresta Aleatória | Uma abordagem líder em aprendizado de máquina. Em termos de ciência de dados, é um método de classificação ou regressão de conjunto que funciona construindo muitas árvores de decisão com base nos atributos do visitante e da visita. |
| Amostragem de Thompson | O objetivo do Thompson Sampling é determinar qual experiência é a melhor em geral (não personalizada), minimizando o &quot;custo&quot; de encontrar essa experiência. O Thompson Sampling sempre escolhe um vencedor, mesmo se não houver diferença estatística entre duas experiências. Para obter mais informações, consulte [Amostragem de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling). |

## Como o modelo de personalização funciona {#how-ap-works}

**[!UICONTROL O Automated Personalization]** usa um algoritmo Random Forest para personalizar. Random Forest é uma abordagem líder de aprendizado de máquina. Em termos de ciência de dados, é um método de classificação ou regressão de conjunto que funciona construindo muitas árvores de decisão com base nos atributos do visitante e da visita. Dentro de [!DNL Target], o Random Forest é usado para determinar qual experiência deve ter a maior probabilidade de conversão (ou a maior receita por visita) para cada visitante específico.

Por exemplo, os visitantes que usam o Chrome, são membros de fidelidade Ouro e acessam o site às terças-feiras podem ter maior probabilidade de conversão com a Experiência A. Os visitantes de Nova York podem ter maior probabilidade de conversão com a Experiência B.

Para obter mais informações sobre Floresta Aleatória em [!DNL Target], consulte [Algoritmo Floresta Aleatória](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

| Aspecto | Como funciona |
|---|---|
| **Otimização para cada visita** | O algoritmo prevê a probabilidade de um visitante converter (ou a receita estimada da conversão) para fornecer a melhor experiência. Um visitante está qualificado para uma nova experiência no final de uma sessão existente, a menos que o visitante esteja no grupo de controle. Um visitante do grupo de controle vê a mesma experiência da primeira visita. A experiência não é alterada em uma sessão para manter a consistência visual. |
| **Adaptação a alterações no comportamento do visitante** | O bandido multi-armado sempre gasta uma pequena fração do tráfego para continuar aprendendo durante a vida da atividade e para evitar a exploração excessiva de tendências previamente aprendidas. Os modelos subjacentes são recriados a cada 24 horas usando os dados de comportamento do visitante mais recentes. Se o algoritmo não puder determinar experiências vencedoras para visitantes individuais, ele mostrará a experiência geral com melhor desempenho, encontrada usando o [Thompson Sampling](https://en.wikipedia.org/wiki/Thompson_sampling), enquanto continua a procurar vencedores personalizados. |
| **Métrica de meta** | O modelo otimiza continuamente uma única métrica de meta, que pode ser baseada em conversão ou em receita (mais especificamente, **[!UICONTROL Receita por visita]**). |
| **Dados e públicos-alvo** | O [!DNL Target] coleta automaticamente informações sobre os visitantes para criar os modelos de personalização. Para obter mais informações sobre os atributos usados em **[!UICONTROL Direcionamento automático]** e **[!UICONTROL Automated Personalization]**, consulte [Coleção de dados da Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-data.md). O [!DNL Target] também usa automaticamente todos os [!DNL Adobe Experience Cloud] públicos-alvo compartilhados, portanto, você não precisa fazer nada específico para adicionar públicos-alvo ao modelo. Para obter mais informações, consulte [Experience Cloud Audiences](/help/main/c-integrating-target-with-mac/mmp.md). |
| **Dados personalizados** | Os profissionais de marketing podem fazer upload de dados offline, como informações de CRM, pontuações de propensão de churn de clientes ou outros dados personalizados para criar modelos de personalização. Os dados podem ser inseridos com [parâmetros de mbox](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=pt-BR){target=_blank}, [parâmetros de perfil](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=pt-BR){target=_blank} ou [APIs do servidor para atualização de perfil](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=pt-BR){target=_blank}. |

## Vídeo de treinamento: tipos de atividade {#training-video}

Este vídeo explica os tipos de atividade disponíveis no [!DNL Target]. **[!UICONTROL Automated Personalization]** é discutido a partir de 5:55.

* Descreva os tipos de atividade incluídos no [!DNL Adobe Target]
* Selecione o tipo de atividade apropriado para atingir suas metas
* Descreva o fluxo de trabalho guiado em três etapas que se aplica a todos os tipos de atividade

>[!VIDEO](https://video.tv.adobe.com/v/17386)
