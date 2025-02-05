---
keywords: Direcionamento de experiência;criar;Experience Targeting;xt;create
description: Saiba como usar o [!UICONTROL Visual Experience Composer] (VEC) no  [!DNL Adobe Target] para criar uma atividade do [!UICONTROL Experience Targeting] (XT).
title: Como criar uma atividade [!UICONTROL Experience Targeting]?
feature: Experience Targeting
exl-id: fc7fc37f-40bf-4947-a4d0-e51fa09b6c56
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 38%

---

# Criar uma atividade [!UICONTROL Experience Targeting] (XT)

Use o [!UICONTROL Visual Experience Composer] (VEC) para criar uma atividade do [!UICONTROL Experience Targeting] (XT) em uma página habilitada para [!DNL Target] e modificar partes da página no [!DNL Adobe Target].

O [!UICONTROL Experience Targeting] (XT) fornece conteúdo a um público-alvo específico com base em um conjunto de regras e critérios definidos pelo profissional de marketing.

[!UICONTROL Experience Targeting], incluindo o [geolocalização](/help/main/c-target/c-audiences/c-target-rules/geo.md), é algo valioso para definir regras que direcionem uma experiência ou conteúdo específico para um público em particular. Várias regras podem ser definidas em uma atividade para levar diferentes variações de conteúdo para públicos-alvo diferentes.

Para obter mais informações sobre [!UICONTROL Experience Targeting], um cenário de casos de uso e vídeos de treinamento, consulte [Direcionamento de experiência](/help/main/c-activities/t-experience-target/experience-target.md).

**Para criar uma atividade [!UICONTROL Experience Targeting]:**

1. Na lista [!UICONTROL Activities], clique em **[!UICONTROL Create Activity]** > **[!UICONTROL Experience Targeting]**.

   ![Criar atividade > Direcionamento de experiência](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >Os tipos de atividades disponíveis dependem da sua conta do [!DNL Target]. Alguns tipos de atividades podem não aparecer na lista. Por exemplo, [!UICONTROL Automated Personalization] é um [recurso do Target Premium](/help/main/c-intro/intro.md#premium).
   >
   >Para obter mais informações sobre os diversos tipos de atividades disponíveis no [!DNL Target] e suas diferenças, consulte [Atividades](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Consulte [Tipos de atividade do Target](/help/main/c-activities/target-activities-guide.md) para ajudá-lo a decidir qual tipo de atividade se adapta melhor as suas necessidades.

1. Selecione **[!UICONTROL Visual (Default)]**, se necessário.

   Se preferir usar o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md), selecione [!UICONTROL Form].

   >[!NOTE]
   >
   >Além do VEC e do [!UICONTROL Form-Based Experience Composer], o [!DNL Target] oferece o VEC para Aplicativos de Página Única. Para obter mais informações sobre os vários composers, consulte [Experiências e ofertas](/help/main/c-experiences/experiences.md).
   >
   >Para obter informações sobre a solução de problemas do VEC, consulte [Solução de problemas do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Condicional) Se você for um cliente do [!DNL Target Premium], [escolha um espaço de trabalho](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

   A opção [!UICONTROL Choose Workplace] é um recurso [Target Premium](/help/main/c-intro/intro.md). Se sua organização tiver uma licença do [!DNL Target Standard], caso você não veja essa opção.

1. Especifique o [URL da atividade](/help/main/c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90) e clique em **[!UICONTROL Create]**.

   Se sua conta foi [configurada com um URL padrão](/help/main/administrating-target/visual-experience-composer-set-up.md), esse URL aparece por padrão. Você pode alterar o URL padrão por outro, se necessário.

   O VEC é aberto, mostrando a página especificada no URL.

   ![Atividade de Direcionamento de experiência no VEC](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt-in-vec.png)

1. Digite um nome para a atividade no espaço fornecido.

   ![Campo nome](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_name-new.png)

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

1. Crie novas experiências direcionadas a públicos diferentes.

   Para obter instruções passo a passo, consulte [Adicionar experiência](/help/main/c-activities/t-experience-target/t-xt-create/xt-add-experience.md).

1. Especifique as [metas e configurações](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) da atividade.
