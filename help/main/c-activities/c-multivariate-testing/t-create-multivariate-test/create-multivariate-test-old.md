---
keywords: mvt; teste multivariado; criação de teste multivariado; criação de teste multivariado; criar mvt; criação de mvt; como mvt; como fazer teste multivariado
description: Saiba como usar o [!UICONTROL Visual Experience Composer] (VEC) no  [!DNL Adobe Target] para criar um [!UICONTROL Multivariate Test] (MVT).
title: Como criar um [!UICONTROL Multivariate Test]?
feature: Multivariate Tests
exl-id: 7712b747-543a-4e19-b689-bea36c44805c
source-git-commit: 8f9c0ea65197fd639d463628e54db79db993c2da
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 56%

---

# Criar um teste multivariado

O [!UICONTROL Visual Experience Composer] (VEC) no [!DNL Adobe Target] facilita a criação de um [!UICONTROL Multivariate Test] e a modificação de partes da página no [!DNL Target].

O editor de apontar e clicar do [!DNL Target] permite que você escolha qualquer local e adicione várias ofertas.

O [!UICONTROL Multivariate Test] (MVT) ocupa um relatório de primeira página. Em outras palavras, o teste é executado em um URL específico, com as experiências projetadas para essa página.

1. Clique em **[!UICONTROL Create Activity]** > **[!UICONTROL Multivariate Test]**.

   ![Criar um teste multivariado](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/create-multivariate.png)

   >[!NOTE]
   >
   >Para obter mais informações sobre os diversos tipos de atividades disponíveis no [!DNL Target] e suas diferenças, consulte [Atividades](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Consulte [Tipos de atividade do Target](/help/main/c-activities/target-activities-guide.md) para ajudá-lo a decidir qual tipo de atividade se adapta melhor as suas necessidades.

1. (Condicional) Escolha o tipo de entrega: [!UICONTROL Web], [!UICONTROL Mobile], [!UICONTROL Email] ou [!UICONTROL Other/API].

1. (Condicional) Se você for um cliente do [Target Premium](/help/main/c-intro/intro.md#premium), [escolha um espaço de trabalho](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. [Especifique a URL](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/url.md#concept_C12E4A85FF3B4E518E3110F6CF1AF9C0) da página que deseja testar e clique em **[!UICONTROL Next]**.

   >[!NOTE]
   >
   >Use um URL completo, incluindo HTTP ou HTTPS no início.

   Se uma mensagem aparecer, solicitando que você ative o navegador para conteúdo misto, siga as instruções na mensagem. Depois de ativar seu navegador para conteúdo misto, comece de novo na Etapa 1.

   O [!UICONTROL Visual Experience Composer] se abre.

1. Digite um nome para a atividade.

   ![Campo Nome da atividade](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/activityname.png)

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
   | - | Vírgula, menos |
   | ,@ | Vírgula, No sinal |
   | `[`&quot; | Colchete de abertura, aspas duplas |
   | &quot;`]` | Aspas duplas, colchete de fechamento |

1. [Crie as ofertas em cada local](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md#concept_DCE6B45C30F7419B8EC17AFDEE8D8AA6).

   ![Caixa de diálogo Editar texto/HTML](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/editoffers.png)

   Você pode adicionar os seguintes tipos de ofertas:

   * HTML
   * Imagem
   * Texto

1. Clique em **[!UICONTROL Preview]** para [visualizar suas experiências](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md).

   ![Visualizar experiências](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt.png)

   Você pode exibir cada experiência e excluir aquelas que não quiser incluir no seu teste. Para excluir uma ou mais experiências, marque as caixas de seleção desejadas e clique em **[!UICONTROL Exclude]**.

   ![Excluir experiências](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt-exclude.png)

1. [Use o Avaliador de tráfego](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) para testar a viabilidade do seu plano de teste.

   ![Indicador de tráfego](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-traffic-indicator.png)

   A ilustração a seguir indica que a atividade tem tráfego insuficiente.

   ![imagem do avaliador](assets/estimator.png)

   A ilustração a seguir indica que a atividade tem tráfego insuficiente.

   ![imagem do estimador2](assets/estimator2.png)

1. Clique em **[!UICONTROL Next]** para avançar para a página [!UICONTROL Targeting].

1. Escolha o público-alvo e porcentagem de visitantes qualificados que você quer inserir na atividade.

   ![Página Direcionamento na atividade MVT](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_audperc.png)

   Por exemplo, você pode limitar as entradas a 50% de todos os visitantes ou 45% do público-alvo na Califórnia.

   >[!NOTE]
   >
   >Além de selecionar um público-alvo existente, você pode combinar vários deles para criar públicos-alvo combinados ad hoc em vez de criar um novo. Para obter mais informações, consulte [Combinar vários públicos-alvo](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. [Revise o resumo do teste](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7), faça as alterações desejadas e clique em **[!UICONTROL Next]**.

1. [Especifique as metas e as configurações](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) do teste.

1. Clique em **[!UICONTROL Save and Close]** para criar a atividade.

## Vídeo de treinamento: Criação de testes multivariados (9:25) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo demonstra como planejar e criar um teste multivariado usando o fluxo de trabalho guiado de três etapas do [!DNL Target].

* Definir e projetar um teste multivariado
* Criar um teste multivariado

>[!VIDEO](https://video.tv.adobe.com/v/30985?captions=por_br)
