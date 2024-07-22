---
keywords: experiência;json;aem;gerenciador de experiência da adobe;exportar para o adobe target;fragmentos de conteúdo;fragmentos;CF;cf;headless;personalização;experimentação
description: Saiba como usar  [!DNL Adobe Experience Manager] [!UICONTROL Content Fragments] em  [!DNL Adobe Target] atividades.
title: Como usar  [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Content Fragments]?
feature: Integrations
exl-id: 2057d9fe-c0f9-41d5-82e1-529db9ef7ca5
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 21%

---

# AEM [!UICONTROL Content Fragments]

Use os [!UICONTROL Content Fragments] (CFs) criados em [!DNL Adobe Experience Manager] (AEM) em atividades de [!DNL Target] para auxiliar na personalização e experimentação headless.

## Considerações

Considere o seguinte ao trabalhar com o AEM [!UICONTROL Content Fragments] em [!DNL Target]:

* Esse recurso exige que você seja um cliente do [!DNL Adobe Experience Manager as a Cloud Service]. Para obter mais informações, consulte os [Requisitos](#section_AE6F0971E1574B3AA324003599B96E5A) abaixo.
* [!UICONTROL Experience Fragments] e [!UICONTROL Content Fragments] estão disponíveis para os seguintes tipos de atividades:

   * [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Experience Targeting] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL Experience Fragments] e [!UICONTROL Content Fragments] não estão disponíveis para os seguintes tipos de atividades:

   * [[!UICONTROL Multivariate Test] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* Você pode consumir [!UICONTROL Content Fragments] em [!DNL Target] atividades usando somente o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md). Você *não pode* consumir [!UICONTROL Content Fragments] em [!DNL Target] atividades usando o [!UICONTROL Visual Experience Composer] (VEC).

Para saber mais sobre o AEM [!UICONTROL Content Fragments] e [!UICONTROL Experience Fragments], consulte [AEM [!UICONTROL Experience Fragments] e [!UICONTROL Content Fragments] visão geral](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Requisitos {#requirements}

É necessário usar o [[!DNL AEM]  as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=pt-BR){target=_blank}.  Seu representante de conta pode ajudar a assegurar que você atenda aos requisitos para usar este recurso:

Entre em contato com o [Atendimento ao cliente do Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para ativar a integração e obter os detalhes de autenticação.

## Configurando e trabalhando com [!UICONTROL Content Fragments] em [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Para exportar [!UICONTROL Content Fragments] para uso em atividades [!DNL Target], é necessário executar algumas etapas preliminares no AEM. Para obter mais informações, consulte [Exportar fragmentos de conteúdo para o Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html){target=_blank} na *documentação do Experience Manager as a Cloud Service*.

Para obter informações sobre como projetar, criar, preparar e publicar [!UICONTROL Content Fragments], consulte [[!UICONTROL Content Fragments]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=pt-BR){target=_blank} e [Trabalhando com Fragmentos de Conteúdo](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html?lang=pt-BR){target=_blank} na [documentação as a Cloud Service do Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html?lang=pt-BR){target=_blank}.

## Usando [!UICONTROL Content Fragments] em [!DNL Target] atividades {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Depois de executar as tarefas anteriores, o [!UICONTROL Content Fragment] é exibido na página [!UICONTROL Offers] em [!DNL Target].

[!DNL Target] atualmente procura [!UICONTROL Content Fragments] para importar a cada dez minutos. O [!UICONTROL Content Fragment] importado deve estar disponível em [!DNL Target] dentro de dez minutos, mas esse intervalo de tempo deve ficar mais curto no futuro.

O [!UICONTROL Content Fragment] é importado para [!DNL Target] como uma oferta JSON. A versão &quot;principal&quot; do [!UICONTROL Content Fragment] permanece em [!DNL AEM]. Você não pode editar o [!UICONTROL Content Fragment] em [!DNL Target].

Você pode filtrar e pesquisar por [!UICONTROL HTML XFs], [!UICONTROL JSON XFs] e [!UICONTROL Content Fragments] para ajudá-lo a distinguir entre os diferentes tipos de ofertas que são exportados para [!DNL Target].

![Filtrar por tipos de fragmento de conteúdo (HTML ou JSON) na interface do Target](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Você pode passar o mouse sobre um [!UICONTROL Content Fragment] na lista e clicar no ícone [!UICONTROL View] ![Ícone de informações](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) para ver informações adicionais sobre o [!UICONTROL Content Fragment], incluindo seus [!UICONTROL AEM path] e [!UICONTROL AEM deep link]. Clique na guia [!UICONTROL Offer Usage] para ver as atividades que fazem referência a esta oferta.

![Pop-up de informações do fragmento de conteúdo](/help/main/c-integrating-target-with-mac/aem/assets/cf-info-popup.png)

Você pode consumir [!UICONTROL Content Fragments] em [!DNL Target] atividades usando somente o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md). Você *não pode* consumir [!UICONTROL Content Fragments] em [!DNL Target] atividades usando o [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC). [!UICONTROL Content Fragments] são exportados como JSON em [!DNL Target] e não podem ser usados em atividades criadas usando o VEC.

>[!TIP]
>
>Use a Inteligência Artificial, o Aprendizado de Máquina e as recomendações com [!UICONTROL Content Fragments]:
>
>* Para usar toda a funcionalidade de inteligência automatizada e aprendizado de máquina do [!DNL Target], você pode selecionar [Alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) ou [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) ao criar uma atividade [!UICONTROL A/B Test].
>
>* Não há suporte para [!UICONTROL Content Fragments] em atividades [!DNL Recommendations]. No entanto, para usar [!UICONTROL Content Fragments] para recomendações, você pode criar uma atividade [!UICONTROL A/B Test] (incluindo [!UICONTROL Auto-Allocate] e [!UICONTROL Auto-Target]) ou uma atividade [!UICONTROL Experience Targeting] (XT) e [incluir recomendações como uma oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).

**Para consumir [!UICONTROL Content Fragments] usando [!UICONTROL Form-based Experience Composer]:**

1. No [!DNL Target], ao criar ou editar uma experiência no [Experience Composer Baseado em Formulário](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), selecione o local da página onde você deseja inserir o conteúdo do [!DNL AEM] e, em seguida, selecione **[!UICONTROL Change Content Fragment]** para exibir a lista do [!UICONTROL Choose a Content Fragment].

   ![imagem content_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   A lista [!UICONTROL Content Fragment] exibe o conteúdo criado em [!DNL AEM] que está agora nativamente disponível dentro de [!DNL Target].

1. Selecione o [!UICONTROL Content Fragment] desejado e clique em **[!UICONTROL Save]**.
1. Termine configurando a atividade.

## Informações adicionais

* [!DNL Target] atualmente procura [!UICONTROL Content Fragments] para importar a cada dez minutos. O [!UICONTROL Content Fragment] importado deve estar disponível em [!DNL Target] dentro de dez minutos, mas esse intervalo de tempo deve ficar mais curto no futuro.
* O [!UICONTROL Content Fragment] é importado para [!DNL Target] como uma oferta JSON. A versão &quot;principal&quot; do [!UICONTROL Content Fragment] permanece em [!DNL AEM]. Você não pode editar o [!UICONTROL Content Fragment] em [!DNL Target].
* Você não pode criar [!UICONTROL Content Fragments] usando [!DNL Adobe I/O]. Crie [!UICONTROL Content Fragments] usando AEM, conforme explicado acima.
* Se você atualizar o [!UICONTROL Content Fragment] no AEM, o [!UICONTROL Content Fragment] deverá ser publicado e exportado novamente para [!DNL Target] para que o [!DNL Target] possa usar as alterações mais recentes.
