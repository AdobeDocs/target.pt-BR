---
keywords: mvt; teste multivariado; criação de teste multivariado; criação de teste multivariado; criar mvt; criação de mvt; como mvt; como fazer teste multivariado
description: Saiba como usar o [!UICONTROL Visual Experience Composer] (VEC) no [!DNL Adobe Target] para criar um [!UICONTROL Teste multivariado] (MVT).
title: Como criar um [!UICONTROL teste multivariado]?
feature: Multivariate Tests
exl-id: 7712b747-543a-4e19-b689-bea36c44805c
TQID: https://experienceleague.adobe.com/gxrnY43A7OWsiW48Rlq1Orp7ZxBswdAPZEAbRQrCDZA
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 809
ht-degree: 23%

---

# Criar um teste multivariado

O [!UICONTROL Visual Experience Composer] (VEC) no [!DNL Adobe Target] facilita a criação de um [!UICONTROL Teste multivariado] e a modificação de partes da página no [!DNL Target].

O editor de apontar e clicar do [!DNL Target] permite que você escolha qualquer local e adicione várias ofertas.

O [!UICONTROL Teste multivariado] (MVT) ocupa um relatório de primeira página. Em outras palavras, o teste é executado em um URL específico, com as experiências projetadas para essa página.

1. Clique em **[!UICONTROL Criar Atividade]** > **[!UICONTROL Teste Multivariado]**.

   >[!NOTE]
   >
   >Para obter mais informações sobre os diversos tipos de atividades disponíveis no [!DNL Target] e suas diferenças, consulte [Atividades](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Consulte [Tipos de atividade do Target](/help/main/c-activities/target-activities-guide.md) para ajudá-lo a decidir qual tipo de atividade se adapta melhor as suas necessidades.

1. (Condicional) Escolha o tipo de entrega: [!UICONTROL Web], [!UICONTROL Celular], [!UICONTROL Email] ou [!UICONTROL Outro/API].

1. (Condicional) Se você for um cliente do [Target Premium](/help/main/c-intro/intro.md#premium), [escolha um espaço de trabalho](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. [Especifique a URL](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/url.md#concept_C12E4A85FF3B4E518E3110F6CF1AF9C0) da página que deseja testar e clique em **[!UICONTROL Criar]**.

   >[!NOTE]
   >
   >Use um URL completo, incluindo HTTP ou HTTPS no início.

   Se uma mensagem aparecer, solicitando que você ative o navegador para conteúdo misto, siga as instruções na mensagem. Depois de ativar seu navegador para conteúdo misto, comece de novo na Etapa 1.

   O [!UICONTROL Visual Experience Composer] se abre.

1. Para nomear a atividade, clique no ícone **[!UICONTROL Editar]** ( ![Ícone Editar](/help/main/assets/icons/Edit.svg) ) ao lado de &quot;[!UICONTROL Atividade sem título]&quot;, especifique um nome descritivo para a atividade e clique em **[!UICONTROL Salvar]**.

   O nome da atividade não pode começar com nenhum dos seguintes caracteres:

   | Caractere | Descrição |
   |--- |--- |
   | `=` | Igual a |
   | `+` | Plus |
   | `-` | menos |
   | `@` | Sinal de arroba |

   O nome da atividade não pode conter nenhuma das sequências de caracteres a seguir:

   | Sequência de caracteres | Descrição |
   |--- |--- |
   | ;= | Ponto e vírgula, Igual a |
   | ;+ | Ponto-e-vírgula, Mais |
   | ;- | Ponto e vírgula, sinal de subtração |
   | ;@ | Ponto e vírgula, no sinal |
   | ,= | Vírgula, Igual a |
   | ,+ | Vírgula, Mais |
   | ,- | Vírgula, menos |
   | ,@ | Vírgula, No sinal |
   | `[`&quot; | Colchete de abertura, aspas duplas |
   | &quot;`]` | Aspas duplas, colchete de fechamento |

1. [Crie as ofertas em cada local](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md#concept_DCE6B45C30F7419B8EC17AFDEE8D8AA6).

   Você pode adicionar os seguintes tipos de ofertas:

   * HTML
   * Imagem
   * Texto

1. Clique em **[!UICONTROL Visualizar]** para [visualizar suas experiências](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md).

1. Clique no ícone **[!UICONTROL Mostrar experiências]** ( ![ícone Mostrar experiências](/help/main/assets/icons/WebPages.svg) ) para exibir a lista de todas as experiências no quadro esquerdo.

1. Clique em uma experiência específica na lista para exibi-la.

1. (Condicional) Para excluir uma ou mais experiências da atividade, clique no ícone **[!UICONTROL Gerenciar conteúdo]** ( ![Ícone Gerenciar experiências](/help/main/assets/icons/Experience.svg) ) para exibir a caixa de diálogo [!UICONTROL Gerenciar experiências].

1. (Condicional) Na caixa de diálogo [!UICONTROL Gerenciar Experiências], clique no ícone **[!UICONTROL Mais Ações]** ( ![ícone Mais Ações](/help/main/assets/icons/MoreSmallList.svg) ) ao lado da experiência que você deseja excluir e clique em **[!UICONTROL Excluir]**.

   É possível excluir uma experiência que mostra variações conflitantes ou que não esteja esteticamente equilibrada.

1. (Condicional) Para excluir várias experiências, marque as caixas de seleção das experiências desejadas e clique em **[!UICONTROL Excluir]**.

1. [Use o Avaliador de tráfego](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) para testar a viabilidade do seu plano de teste.

1. Clique em **[!UICONTROL Avançar]** para avançar para a página [!UICONTROL Direcionamento].

   A etapa **Direcionamento** lhe parece familiar se você já tiver usado outros tipos de atividades [!DNL Target]. Aqui, é possível selecionar um público-alvo e especificar a porcentagem de visitantes que visualizarão cada experiência.

   O diagrama do fluxo guia você pelas etapas da atribuição de um público-alvo e sua porcentagem de tráfego, selecionando o método de alocação de tráfego e especificando a alocação de tráfego para cada experiência na atividade.

1. (Condicional) Clique no controle **[!UICONTROL Todos os visitantes]** para selecionar outro público-alvo para a atividade.

   O público-alvo [!UICONTROL Todos os visitantes] está definido como padrão. Se você selecionar outro público-alvo, o nome dele será exibido no controle mais à esquerda.

   O quadro direito é exibido, permitindo adicionar ou excluir um público-alvo e atribuir a porcentagem de visitante à atividade.

   1. Para alterar o público-alvo, clique no ícone **[!UICONTROL Substituir]** ( ![Ícone Substituir](/help/main/assets/icons/Retweet.svg) ) no quadro direito.
   1. Na caixa de diálogo [!UICONTROL Adicionar público-alvo], [selecione o público-alvo desejado](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) e clique em **[!UICONTROL Atribuir público-alvo]**.

      Você pode clicar em **Combinar Públicos-alvo** para [criar um público-alvo que combine vários públicos-alvo](/help/main/c-target/combining-multiple-audiences.md).

      Se precisar criar um novo público-alvo que ainda não esteja na [!UICONTROL Biblioteca de Público-Alvo], clique em **Criar Público**. Durante o [fluxo de trabalho de criação de público-alvo](/help/main/c-target/c-audiences/audiences.md), você pode escolher entre as seguintes opções:

      * **[!UICONTROL Biblioteca de público-alvo]**: crie um público-alvo sob demanda que seja salvo na [!UICONTROL Biblioteca de público-alvo] e que possa ser reutilizado em outras atividades.
      * **[!UICONTROL Somente esta atividade]**: crie um [público-alvo específico da atividade](/help/main/c-target/creating-activity-only-audience.md) que não esteja salvo na [!UICONTROL Biblioteca de Público-alvo] e possa ser usado somente na atividade atual.

   1. Clique em **[!UICONTROL Porcentagem de visitantes]** no quadro direito e escolha a porcentagem de visitantes qualificados que você deseja inserir na atividade.

   Por exemplo, você pode limitar as entradas a 50% de todos os visitantes ou 45% do público-alvo na Califórnia.

1. [Revise o resumo do teste](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7), faça as alterações desejadas e clique em **[!UICONTROL Avançar]**.

1. [Especifique as metas e as configurações](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) do teste.

1. Clique em **[!UICONTROL Salvar e fechar]** para criar a atividade.

## Vídeo de treinamento: Criando Testes Multivariados (9:25) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo demonstra como planejar e criar um teste multivariado usando o fluxo de trabalho guiado de três etapas do [!DNL Target].

* Definir e projetar um teste multivariado
* Criar um teste multivariado

>[!VIDEO](https://video.tv.adobe.com/v/17395)
