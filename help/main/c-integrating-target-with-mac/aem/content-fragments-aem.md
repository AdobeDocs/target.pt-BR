---
keywords: experience;json;aem;adobe experience manager;exportar para o adobe target;fragmentos de conteúdo;fragmentos;CF;cf;headless;personalização;experimentação
description: Saiba como usar  [!DNL Adobe Experience Manager] [!UICONTROL fragmentos de conteúdo] em atividades do  [!DNL Adobe Target] .
title: Como usar [!UICONTROL fragmentos de conteúdo] do  [!DNL Adobe Experience Manager]  (AEM)?
badgePrerelease: label="Prerelease"
feature: Integrations
exl-id: 2057d9fe-c0f9-41d5-82e1-529db9ef7ca5
source-git-commit: e30c87476496f6103790dbb2fa0c3d60e4c26572
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 87%

---

# [!UICONTROL Fragmentos de conteúdo] do AEM

Use os [!UICONTROL fragmentos de conteúdo] (CFs) criados no [!DNL Adobe Experience Manager] (AEM) em atividades do [!DNL Target] para auxiliar na experimentação e personalização headless.

>[!NOTE]
>
>Esse recurso está disponível como um recurso de pré-lançamento em 12 de abril de 2023. Como um recurso de pré-lançamento, você pode experimentar com [!UICONTROL Fragmentos de conteúdo] uso de ambientes de desenvolvimento e de preparo, mas não em ambientes de produção.
>
>Esse recurso estará disponível para lançamento do GA (Disponibilidade Geral) em 26 de abril de 2023.

## Considerações

Considere o seguinte ao trabalhar com [!UICONTROL fragmentos de conteúdo] do AEM no [!DNL Target]:

* Esse recurso exige que você seja uma [!DNL Adobe Experience Manager as a Cloud Service] cliente. Para obter mais informações, consulte os [Requisitos](#section_AE6F0971E1574B3AA324003599B96E5A) abaixo.
* [!UICONTROL Fragmentos de experiência] e [!UICONTROL Fragmentos de conteúdo] estão disponíveis para os seguintes tipos de atividade:

   * [[!UICONTROL Teste A/B]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Alocação automática]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Direcionamento automático]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Personalização automatizada] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Direcionamento de experiência] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL Fragmentos de experiência] e [!UICONTROL Fragmentos de conteúdo] não estão disponíveis para os seguintes tipos de atividade:

   * [[!UICONTROL Teste multivariado] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* Você pode consumir [!UICONTROL fragmentos de conteúdo] em atividades do [!DNL Target] usando apenas o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md). Você *não pode* consumir [!UICONTROL fragmentos de conteúdo] em atividades do [!DNL Target] usando o [!UICONTROL Visual Experience Composer] (VEC).

Para saber mais sobre os [!UICONTROL fragmentos de conteúdo] e [!UICONTROL fragmentos de experiência] do AEM, consulte a [visão geral dos [!UICONTROL fragmentos de experiência] e [!UICONTROL fragmentos de conteúdo] do AEM](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Requisitos {#requirements}

Você deve ter a funcionalidade de [!UICONTROL fragmentos de conteúdo] provisionada no [!DNL Target]. Além disso, você deve usar o [[!DNL AEM]  as a Cloud Service](https://experienceleague.corp.adobe.com/docs/experience-manager-cloud-service.html){target=_blank}. Seu representante de conta pode ajudar a assegurar que você atenda aos requisitos para usar este recurso:

Entre em contato com o [Atendimento ao cliente do Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para ativar a integração e obter os detalhes de autenticação.

## Como configurar e trabalhar com [!UICONTROL fragmentos de conteúdo] no [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Para exportar [!UICONTROL fragmentos de conteúdo] para uso em atividades do [!DNL Target], você deve executar algumas etapas preliminares no AEM. Para obter mais informações, consulte [Exportar fragmentos de conteúdo para o Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html){target=_blank} na *documentação do Experience Manager as a Cloud Service*.

Para obter informações sobre design, criação, preparação e publicação de [!UICONTROL fragmentos de conteúdo], consulte [[!UICONTROL Fragmentos de conteúdo]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=pt-BR){target=_blank} and [Working with Content Fragments](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html?lang=pt-BR){target=_blank} in the [Experience Manager as a Cloud Service documentation](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html?lang=pt-BR){target=_blank}.

## Usar [!UICONTROL fragmentos de conteúdo] em atividades do [!DNL Target] {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Depois de executar as tarefas anteriores, o [!UICONTROL fragmento de conteúdo] é exibido na página [!UICONTROL Ofertas] do [!DNL Target].

No momento, o [!DNL Target] procura [!UICONTROL fragmentos de conteúdo] para importar a cada dez minutos. O [!UICONTROL fragmento de conteúdo] importado deve estar disponível no [!DNL Target] dentro de dez minutos, mas esse intervalo de tempo deve diminuir no futuro.

O [!UICONTROL fragmento de conteúdo] é importado para o [!DNL Target] como uma oferta JSON. A versão “primária” do [!UICONTROL fragmento de conteúdo] permanece no [!DNL AEM]. Não é possível editar o [!UICONTROL fragmento de conteúdo] no [!DNL Target].

É possível filtrar e pesquisar por [!UICONTROL XFs de HTML], [!UICONTROL XFs de JSON] e [!UICONTROL fragmentos de conteúdo] para ajudar a distinguir entre os diferentes tipos de ofertas que são exportados para o [!DNL Target].

![Filtrar por tipos de fragmento de conteúdo (HTML ou JSON) na interface do Target](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Você pode passar o mouse sobre um [!UICONTROL fragmento de conteúdo] na lista e, em seguida, clicar no ícone [!UICONTROL Exibir] ![Ícone de informação](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) para ver informações adicionais sobre o [!UICONTROL fragmento de conteúdo], incluindo o seu [!UICONTROL caminho do AEM] e [!UICONTROL deep link do AEM]. Clique na guia [!UICONTROL Uso da oferta] para ver as atividades que fazem referência a essa oferta.

![Pop-up de informações do fragmento de conteúdo](/help/main/c-integrating-target-with-mac/aem/assets/cf-info-popup.png)

Você pode consumir [!UICONTROL fragmentos de conteúdo] em atividades do [!DNL Target] usando apenas o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md). Você *não pode* consumir [!UICONTROL fragmentos de conteúdo] em atividades do [!DNL Target] usando o [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC). Os [!UICONTROL fragmentos de conteúdo] são exportados como JSON no [!DNL Target] e não podem ser usados em atividades criadas usando o VEC.

>[!TIP]
>
>Use inteligência artificial, aprendizado de máquina e recomendações com [!UICONTROL fragmentos de conteúdo]:
>
>* Para usar totalmente a variável [!DNL Target] Funcionalidade AI e ML, você pode selecionar [Alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) ou [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) ao criar uma [!UICONTROL Teste A/B] atividade .
>
>* [!UICONTROL Fragmentos de conteúdo] não são compatíveis com atividades do [!DNL Recommendations]. No entanto, para usar [!UICONTROL fragmentos de conteúdo] em recomendações, você pode criar uma atividade de [!UICONTROL Teste A/B] (incluindo [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático]) ou uma atividade de [!UICONTROL Direcionamento de experiência] (XT) e [incluir o Recommendations como uma oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).


**Para consumir [!UICONTROL fragmentos de conteúdo] usando o [!UICONTROL Experience Composer baseado em formulário]:**

1. No [!DNL Target], ao criar ou editar uma experiência no [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), selecione o local da página onde deseja inserir o conteúdo do [!DNL AEM] e, em seguida, selecione **[!UICONTROL Alterar fragmento de conteúdo]** para exibir a lista [!UICONTROL Escolher um fragmento de conteúdo].

   ![imagem content_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   A lista de [!UICONTROL fragmentos de conteúdo] exibe o conteúdo criado no [!DNL AEM] que está agora disponível de forma nativa no [!DNL Target].

1. Selecione o [!UICONTROL fragmento de conteúdo] desejado e clique em **[!UICONTROL Salvar]**.
1. Termine configurando a atividade.

## Informações adicionais

* No momento, o [!DNL Target] procura [!UICONTROL fragmentos de conteúdo] para importar a cada dez minutos. O [!UICONTROL fragmento de conteúdo] importado deve estar disponível no [!DNL Target] dentro de dez minutos, mas esse intervalo de tempo deve diminuir no futuro.
* O [!UICONTROL fragmento de conteúdo] é importado para o [!DNL Target] como uma oferta JSON. A versão “primária” do [!UICONTROL fragmento de conteúdo] permanece no [!DNL AEM]. Não é possível editar o [!UICONTROL fragmento de conteúdo] no [!DNL Target].
* Não é possível criar [!UICONTROL fragmentos de conteúdo] usando o [!DNL Adobe I/O]. Crie [!UICONTROL fragmentos de conteúdo] usando o AEM, conforme explicado acima.
* Se você atualizar seu [!UICONTROL fragmento de conteúdo] no AEM, o [!UICONTROL fragmento de conteúdo] deverá ser publicado e exportado para o [!DNL Target] novamente para que o [!DNL Target] possa usar as alterações mais recentes.
