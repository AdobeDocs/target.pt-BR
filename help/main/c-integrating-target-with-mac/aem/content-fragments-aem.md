---
keywords: experiência;json;aem;gerenciador de experiência da adobe;exportar para o adobe target;fragmentos de conteúdo;fragmentos;CF;cf;headless;personalização;experimentação
description: Saiba como usar [!DNL Adobe Experience Manager] [!UICONTROL Fragmentos de conteúdo] em [!DNL Adobe Target] atividades.
title: Como Usar  [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Fragmentos De Conteúdo]?
feature: Integrations
exl-id: 2057d9fe-c0f9-41d5-82e1-529db9ef7ca5
TQID: https://experienceleague.adobe.com/tb500kFSZoR3czs10Gs3EIOWEX2ybnd7tSWwDmWSMWQ
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
topic_v2:
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 775
ht-degree: 20%

---

# [!UICONTROL Fragmentos de conteúdo] do AEM

Use os [!UICONTROL Fragmentos de conteúdo] (CFs) criados em [!DNL Adobe Experience Manager] (AEM) em [!DNL Target] atividades para auxiliar na personalização e experimentação headless.

## Considerações

Considere o seguinte ao trabalhar com o AEM [!UICONTROL Fragmentos de conteúdo] em [!DNL Target]:

* Esse recurso exige que você seja um cliente do [!DNL Adobe Experience Manager as a Cloud Service]. Para obter mais informações, consulte os [Requisitos](#section_AE6F0971E1574B3AA324003599B96E5A) abaixo.
* Os [!UICONTROL Fragmentos de experiência] e os [!UICONTROL Fragmentos de conteúdo] estão disponíveis para os seguintes tipos de atividades:

   * [[!UICONTROL Teste A/B]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Alocação automática]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Direcionamento automático]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Direcionamento de experiência] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* Os [!UICONTROL Fragmentos de experiência] e os [!UICONTROL Fragmentos de conteúdo] não estão disponíveis para os seguintes tipos de atividades:

   * [[!UICONTROL Teste multivariado] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recomendações]](/help/main/c-recommendations/recommendations.md)

* Você pode consumir [!UICONTROL Fragmentos de conteúdo] em [!DNL Target] atividades usando somente o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md). Você *não pode* consumir [!UICONTROL Fragmentos de conteúdo] em [!DNL Target] atividades usando o [!UICONTROL Visual Experience Composer] (VEC).

Para saber mais sobre os [!UICONTROL Fragmentos de conteúdo] e os [!UICONTROL Fragmentos de experiência] do AEM, consulte a [Visão geral dos [!UICONTROL Fragmentos de experiência] e [!UICONTROL Fragmentos de conteúdo] do AEM](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Requisitos {#requirements}

Você deve usar o [[!DNL AEM] as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=pt-BR){target=_blank}. Seu representante de conta pode ajudar a assegurar que você atenda aos requisitos para usar este recurso:

Entre em contato com o [Atendimento ao cliente do Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para habilitar a integração e obter os detalhes de autenticação.

## Configurando e trabalhando com [!UICONTROL Fragmentos de conteúdo] em [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Para exportar [!UICONTROL Fragmentos de conteúdo] para usar em atividades [!DNL Target], execute algumas etapas preliminares no AEM. Para obter mais informações, consulte [Exportar fragmentos de conteúdo para o Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html?lang=pt-BR){target=_blank} na *documentação do Experience Manager as a Cloud Service*.

Para obter informações sobre como projetar, criar, preparar e publicar [!UICONTROL Fragmentos de conteúdo], consulte [[!UICONTROL Fragmentos de conteúdo]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=pt-BR){target=_blank} e [Trabalhar com fragmentos de conteúdo](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html?lang=pt-BR){target=_blank} na [documentação do Experience Manager as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html?lang=pt-BR){target=_blank}.

## Usando [!UICONTROL Fragmentos de conteúdo] em [!DNL Target] atividades {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Depois de executar as tarefas anteriores, o [!UICONTROL Fragmento do conteúdo] é exibido na página [!UICONTROL Ofertas] em [!DNL Target].

Atualmente, [!DNL Target] procura por [!UICONTROL Fragmentos de conteúdo] para importar a cada dez minutos. O [!UICONTROL Fragmento do Conteúdo] importado deve estar disponível em [!DNL Target] dentro de dez minutos, mas esse intervalo de tempo deve ficar mais curto no futuro.

O [!UICONTROL Fragmento do Conteúdo] é importado para [!DNL Target] como uma oferta JSON. A versão &quot;primária&quot; do [!UICONTROL Fragmento do conteúdo] permanece em [!DNL AEM]. Não é possível editar o [!UICONTROL Fragmento do conteúdo] em [!DNL Target].

Você pode filtrar e pesquisar por [!UICONTROL XFs do HTML], [!UICONTROL XFs do JSON] e [!UICONTROL Fragmentos de Conteúdo] para ajudá-lo a distinguir entre os diferentes tipos de ofertas que são exportados para [!DNL Target].

![Filtrar por tipos de fragmento de conteúdo (HTML ou JSON) na interface do Target](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Você pode passar o mouse sobre um [!UICONTROL Fragmento de experiência] da lista e clicar no ícone [!UICONTROL Exibir] ![Ícone de informações](/help/main/assets/icons/InfoOutline.svg) para ver informações adicionais sobre o [!UICONTROL Fragmento de conteúdo], incluindo seu [!UICONTROL Nome], [!UICONTROL Tipo], [!UICONTROL ID da oferta], [!UICONTROL Caminho da oferta] e as informações sobre as últimas modificações. Clique em [!UICONTROL [!UICONTROL Exibir Detalhes Completos]] para ver as atividades que fazem referência a esta oferta.

Você pode consumir [!UICONTROL Fragmentos de conteúdo] em [!DNL Target] atividades usando somente o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md). Você *não pode* consumir [!UICONTROL Fragmentos de conteúdo] em [!DNL Target] atividades usando o [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC). [!UICONTROL Fragmentos de Conteúdo] são exportados como JSON em [!DNL Target] e não podem ser usados em atividades criadas com o VEC.

>[!TIP]
>
>Use a Inteligência artificial, o Aprendizado de máquina e as recomendações com [!UICONTROL Fragmentos de conteúdo]:
>
>* Para usar toda a funcionalidade de inteligência automatizada e aprendizado de máquina do [!DNL Target], você pode selecionar [Alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) ou [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) ao criar uma atividade de [!UICONTROL Teste A/B].
>
>* Não há suporte para [!UICONTROL Fragmentos de conteúdo] em [!DNL Recommendations] atividades. No entanto, para usar [!UICONTROL Fragmentos de conteúdo] para recomendações, você pode criar uma atividade de [!UICONTROL Teste A/B] (incluindo [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático]) ou uma atividade de [!UICONTROL Direcionamento de experiência] (XT) e [incluir recomendações como uma oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).

**Para consumir [!UICONTROL Fragmentos de conteúdo] usando o [!UICONTROL Experience Composer baseado em formulário]:**

1. No [!DNL Target], ao criar ou editar uma experiência no [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), selecione o local da página onde deseja inserir o conteúdo do [!DNL AEM] e, em seguida, selecione **[!UICONTROL Alterar fragmento de conteúdo]** para exibir a lista [!UICONTROL Escolher um fragmento de conteúdo].

   ![imagem content_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   A lista [!UICONTROL Fragmento do Conteúdo] exibe o conteúdo criado em [!DNL AEM] que está agora nativamente disponível dentro de [!DNL Target].

1. Selecione o [!UICONTROL Fragmento do conteúdo] desejado e clique em **[!UICONTROL Salvar]**.
1. Termine configurando a atividade.

## Informações adicionais

* Atualmente, [!DNL Target] procura por [!UICONTROL Fragmentos de conteúdo] para importar a cada dez minutos. O [!UICONTROL Fragmento do Conteúdo] importado deve estar disponível em [!DNL Target] dentro de dez minutos, mas esse intervalo de tempo deve ficar mais curto no futuro.
* O [!UICONTROL Fragmento do Conteúdo] é importado para [!DNL Target] como uma oferta JSON. A versão &quot;primária&quot; do [!UICONTROL Fragmento do conteúdo] permanece em [!DNL AEM]. Não é possível editar o [!UICONTROL Fragmento do conteúdo] em [!DNL Target].
* Você não pode criar [!UICONTROL Fragmentos de conteúdo] usando [!DNL Adobe I/O]. Crie [!UICONTROL Fragmentos de conteúdo] usando o AEM, conforme explicado acima.
* Se você atualizar o [!UICONTROL Fragmento do Conteúdo] no AEM, o [!UICONTROL Fragmento do Conteúdo] deverá ser publicado e exportado novamente para [!DNL Target] para que o [!DNL Target] possa usar as alterações mais recentes.
