---
keywords: experience;aem;adobe experience manager;exportar para adobe target;fragmentos de experiência;fragmentos;XF
description: Saiba como usar  [!DNL Adobe Experience Manager] [!UICONTROL Experience Fragments] em  [!DNL Adobe Target] atividades.
title: Como Usar O  [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Experience Fragments]?
feature: Integrations
exl-id: 400d0cde-e435-4cac-9bf0-64a6cad98995
source-git-commit: 51e484d54f4d318ea59fdfdb16d1ed7014abdfdb
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 31%

---

# AEM [!UICONTROL Experience Fragments]

Use os [!UICONTROL Experience Fragments] (XFs) criados no [!DNL Adobe Experience Manager] (AEM) em [!DNL Target] atividades para auxiliar na otimização e na personalização.

## Considerações

Considere o seguinte ao trabalhar com o AEM [!UICONTROL Experience Fragments] em [!DNL Target]:

* Esse recurso exige que você seja um cliente do [!DNL Adobe Experience Manager] (AEM). Para obter mais informações, consulte os [Requisitos](#section_AE6F0971E1574B3AA324003599B96E5A) abaixo.
* [!UICONTROL Experience Fragments] e [!UICONTROL Content Fragments] estão disponíveis para os seguintes tipos de atividades:

   * [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Experience Targeting] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL Experience Fragments] e [!UICONTROL Content Fragments] não estão disponíveis para os seguintes tipos de atividades:

   * [[!UICONTROL Multivariate Test] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* Você pode consumir [!UICONTROL Experience Fragments] em [!DNL Target] atividades usando o [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) e o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md).

Para saber mais sobre o AEM [!UICONTROL Experience Fragments] e [!UICONTROL Content Fragments], consulte [Visão geral do AEM [!UICONTROL Experience Fragments] e dos Fragmentos de conteúdo](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Requisitos {#requirements}

Você deve ser provisionado com a funcionalidade [!UICONTROL Experience Fragments] dentro de [!DNL Target]. Além disso, você deve usar o [!DNL AEM] as a Cloud Service ou o [!DNL AEM] 6.4 (ou posterior). Seu representante de conta pode ajudar a assegurar que você atenda aos requisitos para usar este recurso:

* [!DNL Adobe Experience Manager] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5
* [!DNL Adobe Experience Manager] 6.4
* Conta do [!DNL Adobe Target Standard] ou [!DNL Adobe Target Premium].

As versões 6.3 e 6.4 do [!DNL Adobe Experience Manager] atingiram o fim da vida útil e não são mais compatíveis (exceto para clientes que compraram o suporte estendido).

Entre em contato com o [Atendimento ao cliente do Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para ativar a integração e obter os detalhes de autenticação.

## Criando e configurando [!UICONTROL Experience Fragments] em [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Para usar [!DNL AEM] [!UICONTROL Experience Fragments] em [!DNL Target], você deve executar as seguintes etapas:

### Etapa 1: integrar o [!DNL AEM] com o [!DNL Target]

Para obter mais informações, consulte:

* **AEM as a Cloud Service**: [Integração com o Adobe Target](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target){target=_blank} no guia do *Experience Manager as a Cloud Service*.
* **Adobe Developer**: [Integração com o Adobe Target usando o Adobe I/O](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-target-ims-adobe-io.html){target=_blank} na documentação do *Guia de Administração do Usuário*.
* **[!DNL AEM]6.5**: [Ativação do Adobe Analytics e do Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=pt_BR){target=_blank} na documentação do *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4**: [Ativação do Adobe Analytics e do Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=pt_BR){target=_blank} na documentação do *Adobe Experience Manager 6.4*.

### Etapa 2: criar o fragmento de experiência

[!UICONTROL Experience Fragments] foram criados em [!DNL AEM]. Para obter mais informações, consulte:

* **AEM as a Cloud Service**: [[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=pt-BR){target=_blank} no guia do *Experience Manager as a Cloud Service*.
* **[!DNL AEM]6.5**: [[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=pt_BR){target=_blank} na documentação do *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4**: [[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=pt_BR){target=_blank} na documentação do *Adobe Experience Manager 6.4*.

### Etapa 3: configurar [!DNL AEM] para compartilhar o [!UICONTROL Experience Fragment] com [!DNL Target]

1. Dentro de [!DNL AEM], selecione o [!UICONTROL Experience Fragment] desejado ou sua pasta recipiente, em seguida, clique em **[!UICONTROL Properties]**.
2. Clique na guia **[!UICONTROL Cloud Services]** e, na lista suspensa **[!UICONTROL Cloud Service Configuration]**, selecione **[!UICONTROL Adobe Target]**.

   A etapa anterior pressupõe que alguém em sua empresa tenha criado a configuração do [!DNL Adobe Target].

3. Clique em **[!UICONTROL Save & Close]**.

### Etapa 4: publique o [!UICONTROL Experience Fragment] e exporte-o para [!DNL Target]

Dependendo da versão do [!DNL AEM], consulte os seguintes links para obter instruções passo a passo:

* **AEM as a Cloud Service**: [Exportar [!UICONTROL Experience Fragments] para Adobe Target](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target?lang=en){target=_blank} no guia do *Experience Manager as a Cloud Service*.
* **[!DNL AEM]6.5**: [Exportação de um fragmento de experiência para o Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=pt-BR){target=_blank} na documentação do *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4**: [Exportação de um fragmento de experiência para o Target](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html?lang=pt_BR){target=_blank} na documentação do *Adobe Experience Manager 6.4*.

## Usando [!UICONTROL Experience Fragments] em [!DNL Target] atividades {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Depois de executar as tarefas anteriores, o [!UICONTROL Experience Fragment] é exibido na página [!UICONTROL Offers] em [!DNL Target].

[!DNL Target] atualmente procura [!UICONTROL Experience Fragments] para importar a cada dez minutos. O [!UICONTROL Experience Fragment] importado deve estar disponível em [!DNL Target] dentro de dez minutos, mas esse intervalo de tempo deve ficar mais curto no futuro.

O [!UICONTROL Experience Fragment] é importado para [!DNL Target] como uma oferta HTML ou JSON. A versão &quot;principal&quot; do [!UICONTROL Experience Fragment] permanece em [!DNL AEM]. Você não pode editar o [!UICONTROL Experience Fragment] em [!DNL Target].

Você pode filtrar e pesquisar por [!UICONTROL HTML XFs] e [!UICONTROL JSON XFs] para ajudá-lo a distinguir entre [!UICONTROL Experience Fragment] tipos que são exportados para [!DNL Target].

![Filtrar por tipos de fragmentos de experiência (HTML ou JSON) na interface do Target](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Você pode passar o mouse sobre um [!UICONTROL Experience Fragment] na lista e clicar no ícone [!UICONTROL View] ![Ícone de informações](/help/main/assets/icons/InfoOutline.svg) para ver informações adicionais sobre o [!UICONTROL Experience Fragment], incluindo suas informações sobre [!UICONTROL Name], [!UICONTROL Type], [!UICONTROL Offer ID], [!UICONTROL Offer path] e sobre as últimas modificações. Clique em [!UICONTROL [!UICONTROL View Full Details]] para ver as atividades que fazem referência a esta oferta.

![Pop-up de informações do fragmento de experiência](/help/main/c-integrating-target-with-mac/aem/assets/xf-info-popup.png)

Você pode consumir [!UICONTROL Experience Fragments] em [!DNL Target] atividades usando o [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) e o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md).

>[!TIP]
>
>Use a Inteligência Artificial, o Aprendizado de Máquina e as recomendações com [!UICONTROL Experience Fragments]:
>
>* Para utilizar toda a funcionalidade de IA e aprendizado de máquina do [!DNL Target], você pode selecionar o recurso de [alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) ou [direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) ao criar uma atividade.
>
>* Não há suporte para [!UICONTROL Experience Fragments] em atividades [!DNL Recommendations]. No entanto, para usar [!UICONTROL Experience Fragments] para recomendações, você pode criar uma atividade [!UICONTROL A/B Test] (incluindo [!UICONTROL Auto-Allocate] e [!UICONTROL Auto-Target]) ou uma atividade [!UICONTROL Experience Targeting] (XT) e [incluir recomendações como uma oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).

**Para consumir [!UICONTROL Experience Fragments] usando o VEC:**

1. No [!DNL Target], ao criar ou editar uma experiência no [Visual Experience Composer](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), clique no local da página onde você deseja inserir o conteúdo do [!DNL AEM] e, em seguida, clique em **[!UICONTROL Replace Content]** > **[!UICONTROL Experience Fragment]** para exibir a caixa de diálogo [!UICONTROL Experience Fragment].

   A caixa de diálogo [!UICONTROL Experience Fragment] exibe o conteúdo criado em [!DNL AEM] que está agora nativamente disponível dentro de [!DNL Target].

   >[!NOTE]
   >
   >A opção [!UICONTROL Replace Content] não está disponível para imagens. Se você quiser usar essa opção com uma imagem, clique no elemento de contêiner que contém a imagem desejada.

   ![imagem experience_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

1. Selecione o [!UICONTROL Experience Fragment] desejado e clique em **[!UICONTROL Add]**.
1. Termine configurando a atividade.

   Para obter mais informações sobre a configuração de vários tipos de atividades, consulte os tópicos a seguir:

   * **Teste A/B:** [criar um teste A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **Autoalocação:** [autoalocação](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **Direcionamento automático:** [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **Para obter mais informações, consulte** [Criação de uma atividade de Personalização automatizada](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **Direcionamento de experiência (XT):** [criar uma atividade de direcionamento de experiência](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Recommendations em uma atividade de Teste A/B ou de XT:** [Recommendations como uma oferta](/help/main/c-recommendations/recommendations-as-an-offer.md)

   [!UICONTROL Experience Fragments] exportado como JSON em [!DNL Target] não pode ser usado em atividades criadas usando o VEC; somente o HTML [!UICONTROL Experience Fragments] tem suporte em atividades baseadas em VEC. Se você quiser usar o JSON [!UICONTROL Experience Fragments], use-o em atividades criadas com o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md).

**Para consumir [!UICONTROL Experience Fragments] usando [!UICONTROL Form-based Experience Composer]:**

1. No [!DNL Target], ao criar ou editar uma experiência no [Experience Composer Baseado em Formulário](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), selecione o local da página onde você deseja inserir o conteúdo do [!DNL AEM], clique no ícone do **[!UICONTROL More Details]** ( ![ícone de Mais Detalhes](/help/main/assets/icons/MoreSmall.svg) ) e selecione **[!UICONTROL Change Experience Fragment]** para exibir a caixa de diálogo [!UICONTROL Change Experience Fragment].

   ![imagem experience_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

   A caixa de diálogo [!UICONTROL Experience Fragment] exibe o conteúdo criado em [!DNL AEM] que está agora nativamente disponível dentro de [!DNL Target].

1. Selecione o [!UICONTROL Experience Fragment] desejado e clique em **[!UICONTROL Add]**.
1. Termine configurando a atividade.

## Informações adicionais

* [!DNL Target] atualmente procura [!UICONTROL Experience Fragments] para importar a cada dez minutos. O [!UICONTROL Experience Fragment] importado deve estar disponível em [!DNL Target] dentro de dez minutos, mas esse intervalo de tempo deve ficar mais curto no futuro.
* O [!UICONTROL Experience Fragment] é importado para [!DNL Target] como uma oferta HTML ou JSON. A versão &quot;principal&quot; do [!UICONTROL Experience Fragment] permanece em [!DNL AEM]. Você não pode editar o [!UICONTROL Experience Fragment] em [!DNL Target].
* Você não pode criar [!UICONTROL Experience Fragments] usando [!DNL Adobe Developer]. Crie [!UICONTROL Experience Fragments] usando o AEM, conforme explicado acima.
* Se você atualizar o [!UICONTROL Experience Fragment] no AEM, o [!UICONTROL Experience Fragment] deverá ser publicado e exportado novamente para [!DNL Target] para que o [!DNL Target] possa usar as alterações mais recentes.

## Removendo clientlibs e HTML extras de [!UICONTROL Experience Fragments] exportadas para [!UICONTROL Target]

Ao usar as ofertas do [!UICONTROL Experience Fragment] com [!DNL Target] em uma página entregue pela AEM, a página de destino já contém as Bibliotecas de Clientes necessárias. Observe que os elementos de HTML externos da oferta também não são necessários.

Às vezes, páginas inteiras do HTML envolvem [!UICONTROL Experience Fragment] e causam problemas. Certifique-se de que [!UICONTROL Experience Fragment] seja uma pequena parte do HTML e não uma página completa do HTML com HTML, HEAD, BODY e assim por diante.

Para obter mais informações, consulte a seguinte publicação do blog: [AEM 6.5: Removendo clientlibs de [!UICONTROL Experience Fragments] exportadas para o Target](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser/){target=_blank}.

## Vídeo de treinamento: usando o AEM [!UICONTROL Experience Fragments] com [!DNL Adobe Target]

O vídeo a seguir mostra como configurar e usar o [!UICONTROL Experience Fragments]:

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>O recurso de deeplink [!DNL AEM] discutido em 4:54 foi removido.

Para obter informações mais detalhadas, consulte [Usando [!UICONTROL Experience Fragments] com Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html?lang=pt_BR) na página *Vídeos e Tutoriais do AEM Sites*.
