---
keywords: mvt; teste multivariado; criação de teste multivariado; criação de teste multivariado; criar mvt; criação de mvt; como mvt; como fazer teste multivariado
description: Saiba como usar o [!UICONTROL Visual Experience Composer] (VEC) no [!DNL Adobe Target] para criar um [!UICONTROL Teste multivariado] (MVT).
title: Como criar um [!UICONTROL teste multivariado]?
feature: Multivariate Tests
exl-id: 7712b747-543a-4e19-b689-bea36c44805c
TQID: 'https://experienceleague.adobe.com/gxrnY43A7OWsiW48Rlq1Orp7ZxBswdAPZEAbRQrCDZA'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: aad553690f1f399177214c94a2276d038f46d9cb
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 16%
---
# Criar um teste multivariado {#create-mvt}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba como criar um **[!UICONTROL Teste Multivariado]** (MVT) no **[!UICONTROL Visual Experience Composer]** (VEC). Você cria a atividade, cria e revisa as experiências, define o direcionamento e define metas e configurações.

>[!ENDSHADEBOX]

O **[!UICONTROL Visual Experience Composer]** (VEC) no [!DNL Adobe Target] facilita a criação de um **[!UICONTROL Teste multivariado]** e a modificação de partes da página no [!DNL Target].

O editor de apontar e clicar do [!DNL Target] permite que você escolha qualquer local e adicione várias ofertas.

O **[!UICONTROL Teste multivariado]** (MVT) ocupa um relatório de primeira página. Em outras palavras, o teste é executado em um URL específico, com as experiências projetadas para essa página.

Siga as etapas abaixo para criar um **[!UICONTROL Teste multivariado]** (MVT):

1. [Criar a atividade](#create-activity)
1. [Criar e revisar as experiências](#build-experiences)
1. [Definir direcionamento](#set-targeting)
1. [Definir metas e configurações](#configure-goals-and-settings)

## Criar a atividade {#create-activity}

Escolha o tipo de atividade e o tipo de delivery, especifique a página que será testada e nomeie a atividade.

1. Clique em **[!UICONTROL Criar Atividade]** > **[!UICONTROL Teste Multivariado]**.

   Para obter mais informações sobre os diversos tipos de atividades disponíveis no [!DNL Target] e suas diferenças, consulte [Atividades](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Consulte [Tipos de atividade do Target](/help/main/c-activities/target-activities-guide.md) para ajudá-lo a decidir qual tipo de atividade se adapta melhor as suas necessidades.

   ![](../../assets/create-mvt-1.png)

1. Escolha o tipo de entrega: **[!UICONTROL Web]**, **[!UICONTROL Celular]**, **[!UICONTROL Email]** ou **[!UICONTROL Outro/API]**.

1. (Condicional) Se você for um cliente do [Target Premium](/help/main/c-intro/intro.md#premium), [escolha um espaço de trabalho](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. [Especifique a URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md#ab-activity-url) da página que deseja testar. Use um URL completo, incluindo HTTP ou HTTPS no início.

1. Em seguida, clique em **[!UICONTROL Criar]**. O **[!UICONTROL Visual Experience Composer]** se abre.

1. Para nomear a atividade, clique no ícone **[!UICONTROL Editar]** ( ![Ícone Editar](/help/main/assets/icons/Edit.svg) ) e especifique um nome descritivo para a atividade e clique em **[!UICONTROL Salvar]**.

   {{activity-name-rules}}

   ![](../../assets/create-mvt-2.png)

## Criar e revisar as experiências {#build-experiences}

Adicione ofertas a cada local, visualize as experiências resultantes e verifique se o plano de teste é viável.

1. [Crie as ofertas em cada local](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md#concept_DCE6B45C30F7419B8EC17AFDEE8D8AA6).

   Você pode adicionar os seguintes tipos de ofertas:

   * HTML
   * Imagem
   * Texto

1. Clique em **[!UICONTROL Visualizar]** para [visualizar suas experiências](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md).

1. Clique no ícone **[!UICONTROL Mostrar experiências]** ( ![ícone Mostrar experiências](/help/main/assets/icons/WebPages.svg) ) para exibir a lista de todas as experiências no quadro esquerdo e clique em uma experiência específica na lista para exibi-la.

1. [Use o Avaliador de tráfego](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) para testar a viabilidade do seu plano de teste.

### Excluir experiências (opcional) {#exclude-experiences}

É possível excluir uma experiência que mostra variações conflitantes ou que não esteja esteticamente equilibrada.

1. Clique no ícone **[!UICONTROL Gerenciar Conteúdo]** ( ![Ícone Gerenciar Experiências](/help/main/assets/icons/Experience.svg) ) para exibir a caixa de diálogo **[!UICONTROL Gerenciar Experiências]**.

1. Para excluir uma experiência, clique no ícone **[!UICONTROL Mais Ações]** ( ![Ícone Mais Ações](/help/main/assets/icons/MoreSmallList.svg) ) ao lado dessa experiência e clique em **[!UICONTROL Excluir]**.

1. Para excluir várias experiências, marque as caixas de seleção das experiências desejadas e clique em **[!UICONTROL Excluir]**.

## Definir direcionamento {#set-targeting}

Escolha quais visitantes entram no teste e revise o resumo do teste.

1. Clique em **[!UICONTROL Avançar]** para acessar a página **[!UICONTROL Direcionamento]**.

   O diagrama do fluxo guia você pelas etapas da atribuição de um público-alvo e sua porcentagem de tráfego, selecionando o método de alocação de tráfego e especificando a alocação de tráfego para cada experiência na atividade.

1. (Condicional) Clique no controle **[!UICONTROL Todos os visitantes]** para selecionar outro público-alvo para a atividade.

   O público-alvo **[!UICONTROL Todos os visitantes]** está definido como padrão. Se você selecionar outro público-alvo, o nome dele será exibido no controle mais à esquerda. Por exemplo, você pode limitar as entradas a 50% de todos os visitantes ou 45% do público-alvo na Califórnia.

   +++ Etapas para selecionar um público diferente

   O quadro direito é exibido, permitindo adicionar ou excluir um público-alvo e atribuir a porcentagem de visitante à atividade.

   1. Para alterar o público-alvo, clique no ícone **[!UICONTROL Substituir]** ( ![Ícone Substituir](/help/main/assets/icons/Retweet.svg) ) no quadro direito.
   1. Na caixa de diálogo **[!UICONTROL Adicionar público-alvo]**, [selecione o público-alvo desejado](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) e clique em **[!UICONTROL Atribuir público-alvo]**.

      Para criar um público-alvo que combine vários públicos-alvo, clique em **[!UICONTROL Combinar públicos-alvo]**. Para obter detalhes, consulte [Combinar vários públicos-alvo](/help/main/c-target/combining-multiple-audiences.md).

      Para criar um novo público-alvo que ainda não esteja na **[!UICONTROL Biblioteca de Público-alvo]**, clique em **[!UICONTROL Criar Público-alvo]**. No [fluxo de trabalho create-audience](/help/main/c-target/c-audiences/audiences.md), escolha uma das seguintes opções:

      * **[!UICONTROL Biblioteca de público-alvo]**: crie um público-alvo sob demanda que seja salvo na **[!UICONTROL Biblioteca de público-alvo]** e possa ser reutilizado em outras atividades.
      * **[!UICONTROL Somente esta atividade]**: crie um [público-alvo específico da atividade](/help/main/c-target/creating-activity-only-audience.md) que não esteja salvo na **[!UICONTROL Biblioteca de Público-alvo]** e possa ser usado somente na atividade atual.

   1. Clique em **[!UICONTROL Porcentagem de visitantes]** no quadro direito e escolha a porcentagem de visitantes qualificados que você deseja inserir na atividade.

   +++

1. [Revise o resumo do teste](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7), faça as alterações desejadas e clique em **[!UICONTROL Avançar]**.

## Definir metas e configurações {#configure-goals-and-settings}

Na página **[!UICONTROL Metas e configurações]**, você informa a [!DNL Target] como medir o teste. As configurações disponíveis dependem se você usa [!DNL Target] ou [!DNL Analytics] como a fonte de relatórios.

1. Revise as seções da página e defina o que for necessário. Consulte [O que você definiu na página Metas e Configurações](#goals-settings-overview).


   | Seção | O que você definiu |
   |---|---|
   | **[!UICONTROL Configurações da atividade]** | Um objetivo opcional, a **[!UICONTROL Prioridade]** (usada quando várias atividades compartilham um local e um público) e a **[!UICONTROL Duração]** (datas de início e término). |
   | **[!UICONTROL Configurações da geração de relatórios]** | A fonte de relatórios, a métrica de meta (por exemplo, uma métrica **[!UICONTROL Conversão]**), métricas adicionais e públicos-alvo para relatórios. As configurações avançadas para a métrica de meta também estão disponíveis aqui. |
   | **[!UICONTROL Outros metadados]** | Observações sobre a atividade que são úteis para você ou para outros membros da equipe. |

1. Clique em **[!UICONTROL Salvar e fechar]** para criar a atividade.

Para obter detalhes sobre cada opção, consulte [Metas e configurações](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#ab-goals-and-settings).

## Vídeo de treinamento: Criação de testes multivariados (9:25) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo demonstra como planejar e criar um teste multivariado usando o fluxo de trabalho guiado de três etapas do [!DNL Target].

* Definir e projetar um teste multivariado
* Criar um teste multivariado

>[!VIDEO](https://video.tv.adobe.com/v/30985?captions=por_br)
