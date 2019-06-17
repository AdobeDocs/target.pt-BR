---
description: O Visual Experience Composer no Target facilita a criação do teste diretamente em uma página habilitada pelo Target e a modificação de partes da página no Target.
keywords: mvt; teste multivariado; criação de teste multivariado; criação de teste multivariado; criar mvt; criação de mvt; como mvt; como fazer teste multivariado
seo-description: O Visual Experience Composer no Target facilita a criação do teste diretamente em uma página habilitada pelo Target e a modificação de partes da página no Target.
seo-title: Criar um teste multivariado
solution: Target
title: Criar um teste multivariado
uuid: 876441bd-d841-4974-b1ec-3ad7cb6ef3ee
translation-type: tm+mt
source-git-commit: f689812658d45342f958629d02b74c252c7f0369

---


# Criar um teste multivariado{#create-a-multivariate-test}

O [!UICONTROL Visual Experience Composer] (VEC) facilita [!DNL Target] a criação de seu teste diretamente em uma página ativada pelo Target e para modificar partes da página dentro [!DNL Target].

O editor de apontar e clicar do Target permite que você escolha qualquer local e adicione várias ofertas.

O Teste [!UICONTROL multivariado] (MVT) ocupa um relatório de página. Em outras palavras, o teste é executado em um URL específico, com as experiências projetadas para essa página.

1. Clique em **[!UICONTROL Criar atividade]** &gt; **[!UICONTROL Teste multivariado]**.

   ![Criar teste multivariado](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/create-multivariate.png)

   >[!NOTE]
   >
   >Os tipos de atividades disponíveis dependem da sua conta do Target. Alguns tipos de atividades podem não aparecer na lista. Por exemplo, [!UICONTROL a Personalização automatizada] é um [recurso Target Premium](/help/c-intro/intro.md#premium).
   >
   >Para obter mais informações sobre os diversos tipos de atividades disponíveis [!DNL Target] e suas diferenças, consulte [Atividades](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Consulte [Tipos de atividade do Target](/help/c-activities/target-activities-guide.md) para ajudá-lo a decidir qual tipo de atividade melhor suite suas necessidades.

1. Selecione **[!UICONTROL Visual (Padrão)]**, se necessário.

   ![Caixa de diálogo Criar atividade de direcionamento de experiência](/help/c-activities/t-experience-target/t-xt-create/assets/form_url-new.png)

   Se preferir usar o Experience Composer baseado em formulário, selecione [!UICONTROL Formulário]. Consulte [Criador de experiências baseado em forma](/help/c-experiences/form-experience-composer.md) para obter mais informações.

   >[!NOTE]
   >
   >Além do VEC e do Criador de experiências baseado em forma, o Target oferece o VEC do aplicativo de página única e o VEC para aplicativos móveis. Para obter mais informações sobre os vários compositores, consulte [Experiências e ofertas](/help/c-experiences/experiences.md).
   >
   >Em caso de problemas, para obter informações sobre a solução de problemas do VEC, consulte [Solução de problemas do Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >A opção [!UICONTROL Escolher local de trabalho] na ilustração anterior é um [recurso do Target Premium](/help/c-intro/intro.md) . Sua organização tem uma licença do Target Standard caso não veja essa opção.]

1. (Condicional) Se você for um cliente do Target Premium, [escolha uma área de trabalho](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. [Especifique o URL](../../../c-activities/c-multivariate-testing/t-create-multivariate-test/url.md#concept_C12E4A85FF3B4E518E3110F6CF1AF9C0) da página que deseja testar e clique **[!UICONTROL em Avançar]**.

   >[!NOTE]
   >
   >Use um URL completo, incluindo HTTP ou HTTPS no início.

   Se uma mensagem aparecer, solicitando que você ative o navegador para conteúdo misto, siga as instruções na mensagem. Depois de ativar seu navegador para conteúdo misto, comece de novo na Etapa 1.

   O Visual Experience Composer é aberto.

1. Digite um nome para a atividade.

   ![Campo Nome da atividade](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/activityname.png)

   Os seguintes caracteres não são permitidos em um nome de atividade:

   | Caractere | Descrição |
   |--- |--- |
   | / | Barra |
   | ? | Ponto de interrogação |
   | # | Sinal numérico |
   | : | Dois-pontos |
   | = | Igual a |
   | + | Plus |
   | - | Menos |
   | @ | Sinal de arroba |

1. [Crie as ofertas em cada local](../../../c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md#concept_DCE6B45C30F7419B8EC17AFDEE8D8AA6).

   ![Caixa de diálogo Editar texto/HTML](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/editoffers.png)

   Você pode adicionar os seguintes tipos de ofertas:

   * HTML
   * Imagem
   * Texto

1. Clique **[!UICONTROL em Visualizar]** para [visualizar suas experiências](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md).

   ![Visualizar experiências](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt.png)

   Você pode exibir cada experiência e excluir aquelas que não quiser incluir no seu teste. Para excluir uma ou mais experiências, selecione as caixas de seleção desejadas e clique **[!UICONTROL em Excluir]** .

   ![Excluir experiências](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt-exclude.png)

1. [Use o Avaliador de tráfego](../../../c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) para testar a viabilidade do seu plano de teste.

   ![Indicador de tráfego](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-traffic-indicator.png)

   A ilustração a seguir indica que a atividade tem tráfego insuficiente.

   ![](assets/estimator.png)

   A ilustração a seguir indica que a atividade tem tráfego insuficiente.

   ![](assets/estimator2.png)

1. Clique **[!UICONTROL em Avançar]** para avançar para a página [!UICONTROL de Definição de metas] .]

1. Escolha o público-alvo e porcentagem de visitantes qualificados que você quer inserir na atividade.

   ![Página de definição de metas na atividade MVT](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_audperc.png)

   Por exemplo, você pode limitar as entradas a 50% de todos os visitantes ou 45% do público-alvo na Califórnia.

   >[!NOTE]
   >
   >Além de selecionar um público-alvo existente, você pode combinar vários deles para criar públicos-alvo combinados ad hoc em vez de criar um novo. Para obter mais informações, consulte [Combinar vários públicos-alvo](../../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. [Revise o resumo do teste](../../../c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7) e faça as alterações desejadas e clique **[!UICONTROL em Avançar]**.

1. [Especifique as metas e as configurações](../../../c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) do teste.

1. Clique em **[!UICONTROL Salvar e fechar]** para criar a atividade.

## Vídeo de treinamento: Criação de testes multivariados (9:25)

Este vídeo monstra como planejar e criar um teste multivariado usando o fluxo de trabalho orientado de três etapas do Target.

* Definir e projetar um teste multivariado
* Criar um teste multivariado

>[!VIDEO](https://video.tv.adobe.com/v/17395?captions=por_br)
