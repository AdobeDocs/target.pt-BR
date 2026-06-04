---
keywords: experience;aem;adobe experience manager;exportar para adobe target;fragmentos de experiência;fragmentos;XF
description: Saiba como usar [!DNL Adobe Experience Manager] [!UICONTROL Fragmentos de experiência] em [!DNL Adobe Target] atividades.
title: Como Usar  [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Fragmentos De Experiência]?
feature: Integrations
exl-id: 400d0cde-e435-4cac-9bf0-64a6cad98995
TQID: https://experienceleague.adobe.com/-W1ELJx0ajes6BPEVIiS8q6ebmRLTTgIrxvGMUEWEaM
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
topic_v2:
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1446
ht-degree: 32%

---

# [!UICONTROL Fragmentos de experiência] do AEM

Use os [!UICONTROL Fragmentos de experiência] (XFs) criados em [!DNL Adobe Experience Manager] (AEM) em [!DNL Target] atividades para auxiliar na otimização e na personalização.

## Considerações

Considere o seguinte ao trabalhar com os [!UICONTROL Fragmentos de experiência] do AEM em [!DNL Target]:

* Esse recurso exige que você seja um cliente do [!DNL Adobe Experience Manager] (AEM). Para obter mais informações, consulte os [Requisitos](#section_AE6F0971E1574B3AA324003599B96E5A) abaixo.
* Os [!UICONTROL Fragmentos de experiência] e os [!UICONTROL Fragmentos de conteúdo] estão disponíveis para os seguintes tipos de atividades:

   * [[!UICONTROL Teste A/B]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Alocação automática]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Direcionamento automático]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Direcionamento de experiência] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* Os [!UICONTROL Fragmentos de experiência] e os [!UICONTROL Fragmentos de conteúdo] não estão disponíveis para os seguintes tipos de atividades:

   * [[!UICONTROL Teste multivariado] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recomendações]](/help/main/c-recommendations/recommendations.md)

* Você pode consumir [!UICONTROL Fragmentos de experiência] em [!DNL Target] atividades usando o [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) e o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md).

Para saber mais sobre o AEM [!UICONTROL Fragmentos de experiência] e [!UICONTROL Fragmentos de conteúdo], consulte a [Visão geral dos [!UICONTROL Fragmentos de experiência] e dos Fragmentos de conteúdo](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Requisitos {#requirements}

Você deve estar provido da funcionalidade [!UICONTROL Fragmentos de experiência] em [!DNL Target]. Além disso, você deve usar o [!DNL AEM] as a Cloud Service ou o [!DNL AEM] 6.4 (ou posterior). Seu representante de conta pode ajudar a assegurar que você atenda aos requisitos para usar este recurso:

* [!DNL Adobe Experience Manager] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5
* [!DNL Adobe Experience Manager] 6.4
* Conta do [!DNL Adobe Target Standard] ou [!DNL Adobe Target Premium].

As versões 6.3 e 6.4 do [!DNL Adobe Experience Manager] atingiram o fim da vida útil e não são mais compatíveis (exceto para clientes que compraram o suporte estendido).

Entre em contato com o [Atendimento ao cliente do Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para habilitar a integração e obter os detalhes de autenticação.

## Criando e configurando [!UICONTROL Fragmentos de experiência] em [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Para usar [!DNL AEM] [!UICONTROL Fragmentos de experiência] em [!DNL Target], execute as seguintes etapas:

### Etapa 1: integrar o [!DNL AEM] com o [!DNL Target]

Para obter mais informações, consulte:

* **AEM as a Cloud Service**: [Integração com o Adobe Target](https://experienceleague.adobe.com/pt-br/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target){target=_blank} no guia do *Experience Manager as a Cloud Service*.
* **Adobe Developer**: [Integração com o Adobe Target usando o Adobe I/O](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-target-ims-adobe-io.html?lang=pt-BR){target=_blank} na documentação do *Guia de Administração do Usuário*.
* **[!DNL AEM]6.5**: [Ativação do Adobe Analytics e do Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=pt_BR){target=_blank} na documentação do *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4**: [Ativação do Adobe Analytics e do Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=pt_BR){target=_blank} na documentação do *Adobe Experience Manager 6.4*.

### Etapa 2: criar o fragmento de experiência

[!UICONTROL Fragmentos de experiência] criados em [!DNL AEM]. Para obter mais informações, consulte:

* **AEM as a Cloud Service**: [[!UICONTROL Fragmentos de experiência]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=pt-BR){target=_blank} no guia do *Experience Manager as a Cloud Service*.
* **[!DNL AEM]6.5**: [[!UICONTROL Fragmentos de experiência]](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=pt_BR){target=_blank} na documentação do *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4**: [[!UICONTROL Fragmentos de experiência]](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=pt_BR){target=_blank} na documentação do *Adobe Experience Manager 6.4*.

### Etapa 3: configurar [!DNL AEM] para compartilhar o [!UICONTROL Fragmento de experiência] com [!DNL Target]

1. Dentro de [!DNL AEM], selecione o [!UICONTROL Fragmento de Experiência] desejado ou sua pasta recipiente, depois clique em **[!UICONTROL Propriedades]**.
2. Clique na guia **[!UICONTROL Cloud Services]** e, na lista suspensa **[!UICONTROL Configuração do Cloud Service]**, selecione **[!UICONTROL Adobe Target]**.

   A etapa anterior pressupõe que alguém em sua empresa tenha criado a configuração do [!DNL Adobe Target].

3. Clique em **[!UICONTROL Salvar e fechar]**.

### Etapa 4: publique o [!UICONTROL Fragmento de experiência] e exporte-o para o [!DNL Target]

Dependendo da versão do [!DNL AEM], consulte os seguintes links para obter instruções passo a passo:

* **AEM as a Cloud Service**: [Exportação de [!UICONTROL Fragmentos de experiência] para o Adobe Target](https://experienceleague.adobe.com/pt-br/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target?lang=en){target=_blank} no guia do *Experience Manager as a Cloud Service*.
* **[!DNL AEM]6.5**: [Exportação de um fragmento de experiência para o Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=pt-BR){target=_blank} na documentação do *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4**: [Exportação de um fragmento de experiência para o Target](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html?lang=pt_BR){target=_blank} na documentação do *Adobe Experience Manager 6.4*.

## Usando [!UICONTROL Fragmentos de experiência] em [!DNL Target] atividades {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Depois de executar as tarefas anteriores, o [!UICONTROL Fragmento de experiência] é exibido na página [!UICONTROL Ofertas] em [!DNL Target].

[!DNL Target] atualmente procura por [!UICONTROL Fragmentos de experiência] para importar a cada dez minutos. O [!UICONTROL Fragmento de Experiência] importado deve estar disponível em [!DNL Target] dentro de dez minutos, mas esse intervalo de tempo deve ficar mais curto no futuro.

O [!UICONTROL Fragmento de experiência] é importado para [!DNL Target] como uma oferta HTML ou JSON. A versão &quot;principal&quot; do [!UICONTROL Fragmento de experiência] permanece em [!DNL AEM]. Você não pode editar o [!UICONTROL Fragmento de experiência] em [!DNL Target].

Você pode filtrar e pesquisar por [!UICONTROL HTML XFs] e [!UICONTROL JSON XFs] para ajudá-lo a distinguir entre os tipos de [!UICONTROL Fragmento de experiência] exportados para [!DNL Target].

![Filtrar por tipos de fragmentos de experiência (HTML ou JSON) na interface do Target](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Você pode passar o mouse sobre um [!UICONTROL Fragmento de experiência] na lista e clicar no ícone [!UICONTROL Exibir] ![Ícone de informações](/help/main/assets/icons/InfoOutline.svg) para ver informações adicionais sobre o [!UICONTROL Fragmento de experiência], incluindo seu [!UICONTROL Nome], [!UICONTROL Tipo], [!UICONTROL ID da oferta], [!UICONTROL Caminho da oferta] e informações sobre as últimas modificações. Clique em [!UICONTROL [!UICONTROL Exibir Detalhes Completos]] para ver as atividades que fazem referência a esta oferta.

![Pop-up de informações do fragmento de experiência](/help/main/c-integrating-target-with-mac/aem/assets/xf-info-popup.png)

Você pode consumir [!UICONTROL Fragmentos de experiência] em [!DNL Target] atividades usando o [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) e o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md).

>[!TIP]
>
>Use a Inteligência artificial, o Aprendizado de máquina e as recomendações com [!UICONTROL Fragmentos de experiência]:
>
>* Para utilizar toda a funcionalidade de IA e aprendizado de máquina do [!DNL Target], você pode selecionar o recurso de [alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) ou [direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) ao criar uma atividade.
>
>* Não há suporte para [!UICONTROL Fragmentos de experiência] em [!DNL Recommendations] atividades. No entanto, para usar os [!UICONTROL Fragmentos de experiência] para recomendações, você pode criar uma atividade de [!UICONTROL Teste A/B] (incluindo a [!UICONTROL Alocação automática] e a [!UICONTROL Direcionamento automático]) ou uma atividade de [!UICONTROL Direcionamento de experiência] (XT) e [incluir recomendações como uma oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).

**Para consumir [!UICONTROL Fragmentos de experiência] usando o VEC:**

1. No [!DNL Target], ao criar ou editar uma experiência no [Visual Experience Composer](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), clique no local da página onde você deseja inserir o conteúdo do [!DNL AEM] e, em seguida, clique em **[!UICONTROL Substituir conteúdo]** > **[!UICONTROL Fragmento de experiência]** para exibir a caixa de diálogo [!UICONTROL Fragmento de experiência].

   A caixa de diálogo [!UICONTROL Fragmento de Experiência] exibe o conteúdo criado em [!DNL AEM] que está agora nativamente disponível dentro de [!DNL Target].

   >[!NOTE]
   >
   >A opção [!UICONTROL Substituir Conteúdo] não está disponível para imagens. Se você quiser usar essa opção com uma imagem, clique no elemento de contêiner que contém a imagem desejada.

   ![imagem experience_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

1. Selecione o [!UICONTROL Fragmento de experiência] desejado e clique em **[!UICONTROL Adicionar]**.
1. Termine configurando a atividade.

   Para obter mais informações sobre a configuração de vários tipos de atividades, consulte os tópicos a seguir:

   * **Teste A/B:** [criar um teste A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **Autoalocação:** [autoalocação](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **Direcionamento automático:** [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **Para obter mais informações, consulte** [Criação de uma atividade de Personalização automatizada](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **Direcionamento de experiência (XT):** [criar uma atividade de direcionamento de experiência](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Recommendations em uma atividade de Teste A/B ou de XT:** [Recommendations como uma oferta](/help/main/c-recommendations/recommendations-as-an-offer.md)

   [!UICONTROL Fragmentos de experiência] exportados como JSON em [!DNL Target] não podem ser usados em atividades criadas usando o VEC; somente [!UICONTROL Fragmentos de experiência] do HTML têm suporte em atividades baseadas em VEC. Se você quiser usar JSON [!UICONTROL Fragmentos de experiência], use-os em atividades criadas com o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md).

**Para consumir [!UICONTROL Fragmentos de experiência] usando o [!UICONTROL Experience Composer baseado em formulário]:**

1. No [!DNL Target], ao criar ou editar uma experiência no [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), selecione o local da página onde deseja inserir o conteúdo do [!DNL AEM], clique no ícone **[!UICONTROL Mais Detalhes]** ( ![ícone Mais Detalhes](/help/main/assets/icons/MoreSmall.svg) ) e selecione **[!UICONTROL Alterar Fragmento de Experiência]** para exibir a caixa de diálogo [!UICONTROL Alterar Fragmento de Experiência].

   ![imagem experience_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

   A caixa de diálogo [!UICONTROL Fragmento de Experiência] exibe o conteúdo criado em [!DNL AEM] que está agora nativamente disponível dentro de [!DNL Target].

1. Selecione o [!UICONTROL Fragmento de experiência] desejado e clique em **[!UICONTROL Adicionar]**.
1. Termine configurando a atividade.

## Informações adicionais

* [!DNL Target] atualmente procura por [!UICONTROL Fragmentos de experiência] para importar a cada dez minutos. O [!UICONTROL Fragmento de Experiência] importado deve estar disponível em [!DNL Target] dentro de dez minutos, mas esse intervalo de tempo deve ficar mais curto no futuro.
* O [!UICONTROL Fragmento de experiência] é importado para [!DNL Target] como uma oferta HTML ou JSON. A versão &quot;principal&quot; do [!UICONTROL Fragmento de experiência] permanece em [!DNL AEM]. Você não pode editar o [!UICONTROL Fragmento de experiência] em [!DNL Target].
* Você não pode criar [!UICONTROL Fragmentos de experiência] usando [!DNL Adobe Developer]. Crie [!UICONTROL Fragmentos de experiência] usando o AEM, conforme explicado acima.
* Se você atualizar seu [!UICONTROL Fragmento de experiência] no AEM, o [!UICONTROL Fragmento de experiência] deverá ser publicado e exportado novamente para [!DNL Target] para que o [!DNL Target] possa usar as alterações mais recentes.

## Removendo clientlibs e HTML extras de [!UICONTROL Fragmentos de experiência] exportados para [!UICONTROL Destino]

Ao usar as ofertas do [!UICONTROL Fragmento de experiência] com [!DNL Target] em uma página entregue pelo AEM, a página direcionada já contém as Bibliotecas de Clientes necessárias. Observe que os elementos de HTML externos da oferta também não são necessários.

Às vezes, páginas inteiras do HTML envolvem o [!UICONTROL Fragmento de experiência] e causam problemas. Certifique-se de que o [!UICONTROL Fragmento de experiência] seja uma pequena parte do HTML e não uma página HTML completa com HTML, HEAD, BODY e assim por diante.

Para obter mais informações, consulte a seguinte publicação do blog: [AEM 6.5: Removendo clientlibs de [!UICONTROL Fragmentos de experiência] exportados para o Target](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser/){target=_blank}.

## Vídeo de treinamento: Usando o AEM [!UICONTROL Fragmentos de experiência] com [!DNL Adobe Target]

O vídeo a seguir mostra como configurar e usar [!UICONTROL Fragmentos de experiência]:

>[!VIDEO](https://video.tv.adobe.com/v/34848?captions=por_br)

>[!NOTE]
>
>O recurso de deeplink [!DNL AEM] discutido em 4:54 foi removido.

Para obter informações mais detalhadas, consulte [Usando [!UICONTROL Fragmentos de experiência] com o Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html?lang=pt_BR) na página *Vídeos e Tutoriais do AEM Sites*.
