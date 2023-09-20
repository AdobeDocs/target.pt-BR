---
keywords: Direcionamento de experiência;criar;Experience Targeting;xt;create
description: Saiba como usar o [!UICONTROL Visual Experience Composer] (VEC) no [!DNL Adobe Target] para criar um [!UICONTROL Direcionamento de experiência] (XT).
title: Como criar um [!UICONTROL Direcionamento de experiência] Atividade?
feature: Experience Targeting
exl-id: fc7fc37f-40bf-4947-a4d0-e51fa09b6c56
source-git-commit: 4faafcef38d02674072d8b20ae03d3e2ef2115d6
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 51%

---

# Criar um [!UICONTROL Direcionamento de experiência] Atividade de (XT)

Use o [!UICONTROL Visual Experience Composer] (VEC) para criar uma [!UICONTROL Direcionamento de experiência] (XT) atividade em um [!DNL Target]página habilitada para e modificar partes da página no [!DNL Adobe Target].

O [!UICONTROL Direcionamento de experiência] (XT) fornece conteúdo a um público-alvo específico com base em um conjunto de regras e critérios definidos pelo profissional de marketing.

O Direcionamento de experiência, incluindo o [Direcionamento geográfico](/help/main/c-target/c-audiences/c-target-rules/geo.md), é importante para definir regras que direcionem uma experiência ou conteúdo específico para um determinado público-alvo. Várias regras podem ser definidas em uma atividade para levar diferentes variações de conteúdo para públicos-alvo diferentes.

Para obter mais informações sobre [!UICONTROL Direcionamento de experiência], um cenário de caso de uso e vídeos de treinamento, consulte [Direcionamento de experiência](/help/main/c-activities/t-experience-target/experience-target.md).

**Para criar uma [!UICONTROL Direcionamento de experiência] atividade:**

1. Na lista [!UICONTROL Atividades], clique em **[!UICONTROL Criar atividade]** > **[!UICONTROL Direcionamento de experiência]**.

   ![Criar atividade > Direcionamento de experiência](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >Os tipos de atividades disponíveis dependem da sua conta do [!DNL Target]. Alguns tipos de atividades podem não aparecer na lista. Por exemplo, a [!UICONTROL Personalização automatizada] é um [recurso do Target Premium](/help/main/c-intro/intro.md#premium).
   >
   >Para obter mais informações sobre os diversos tipos de atividades disponíveis no [!DNL Target] e suas diferenças, consulte [Atividades](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Consulte [Tipos de atividade do Target](/help/main/c-activities/target-activities-guide.md) para ajudá-lo a decidir qual tipo de atividade se adapta melhor as suas necessidades.

1. Selecione **[!UICONTROL Visual (Padrão)]**, se necessário.

   Se preferir usar a variável [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md), selecione [!UICONTROL Formulário].

   >[!NOTE]
   >
   >Além do VEC e do [!UICONTROL Experience Composer baseado em formulário], [!DNL Target] O oferece o VEC para aplicativos de página única. Para obter mais informações sobre os vários composers, consulte [Experiências e ofertas](/help/main/c-experiences/experiences.md).
   >
   >Para obter informações sobre solução de problemas do VEC, consulte [Solução de problemas do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Condicional) Se você for um [!DNL Target Premium] cliente, [escolher um espaço de trabalho](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

   A variável [!UICONTROL Escolher local de trabalho] a opção é uma [Target Premium](/help/main/c-intro/intro.md) recurso. Se sua organização tiver uma [!DNL Target Standard] caso não veja essa opção.

1. Especifique o [URL da atividade](/help/main/c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90) e clique em **[!UICONTROL Criar]**.

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
   | ,- | Vírgula, menos |
   | ,@ | Vírgula, No sinal |
   | `[`&quot; | Colchete de abertura, aspas duplas |
   | &quot;`]` | Aspas duplas, colchete de fechamento |

1. Crie novas experiências direcionadas a públicos diferentes.

   Para obter instruções passo a passo, consulte [Adicionar experiência](/help/main/c-activities/t-experience-target/t-xt-create/xt-add-experience.md).

1. Especifique as [metas e configurações](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) da atividade.
