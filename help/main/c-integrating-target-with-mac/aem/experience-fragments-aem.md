---
keywords: experience;aem;adobe experience manager;exportar para adobe target;fragmentos de experiência;fragmentos;XF
description: Saiba como usar fragmentos de experiência do  [!DNL Adobe Experience Manager] [!UICONTROL ] em atividades do  [!DNL Adobe Target] .
title: Como usar [!UICONTROL fragmentos de experiência] do  [!DNL Adobe Experience Manager]  (AEM)?
feature: Integrations
exl-id: 400d0cde-e435-4cac-9bf0-64a6cad98995
source-git-commit: 7c81362a82ca6692bb8c183b8e8fc50c6329e2e8
workflow-type: ht
source-wordcount: '1352'
ht-degree: 100%

---

# [!UICONTROL Fragmentos de experiência] do AEM

Use os [!UICONTROL fragmentos de experiência] (XFs) criados no [!DNL Adobe Experience Manager] (AEM) em atividades do [!DNL Target] para auxiliar na otimização e personalização.

## Considerações

Considere o seguinte ao trabalhar com [!UICONTROL fragmentos de experiência] do AEM no [!DNL Target]:

* Esse recurso exige que você seja um cliente do [!DNL Adobe Experience Manager] (AEM). Para obter mais informações, consulte os [Requisitos](#section_AE6F0971E1574B3AA324003599B96E5A) abaixo.
* Os [!UICONTROL fragmentos de experiência] e [!UICONTROL fragmentos de conteúdo] estão disponíveis para os seguintes tipos de atividade:

   * [[!UICONTROL Teste A/B]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Alocação automática]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Direcionamento automático]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Personalização automatizada] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Direcionamento de experiência] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* Os [!UICONTROL fragmentos de experiência] e [!UICONTROL fragmentos de conteúdo] não estão disponíveis para os seguintes tipos de atividade:

   * [[!UICONTROL Teste multivariado] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* Você pode consumir [!UICONTROL fragmentos de experiência] em atividades do [!DNL Target] usando o [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) e o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md).

Para saber mais sobre os [!UICONTROL fragmentos de experiência] e [!UICONTROL fragmentos de conteúdo] do AEM, consulte a [Visão geral dos [!UICONTROL fragmentos de experiência] e fragmentos de conteúdo do AEM](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Requisitos {#requirements}

Você deve ter a funcionalidade dos [!UICONTROL fragmentos de experiência] provisionada no [!DNL Target]. Além disso, você deve usar o [!DNL AEM] as a Cloud Service ou o [!DNL AEM] 6.4 (ou posterior). Seu representante de conta pode ajudar a assegurar que você atenda aos requisitos para usar este recurso:

* [!DNL Adobe Experience Manager ] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5
* [!DNL Adobe Experience Manager] 6.4
* Conta do [!DNL Adobe Target Standard] ou [!DNL Adobe Target Premium].

As versões 6.3 e 6.4 do [!DNL Adobe Experience Manager] atingiram o fim da vida útil e não são mais compatíveis (exceto para clientes que compraram o suporte estendido).

Entre em contato com o [Atendimento ao cliente do Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para ativar a integração e obter os detalhes de autenticação.

## Criação e configuração de [!UICONTROL fragmentos de experiência] no [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Para usar [!UICONTROL fragmentos de experiência] do [!DNL AEM] no [!DNL Target], você deve executar as seguintes etapas:

### Etapa 1: integrar o [!DNL AEM] com o [!DNL Target]

Para obter mais informações, consulte:

* **AEM as a Cloud Service**: [Integração com o Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target.html?lang=pt-BR){target=_blank} no guia do *Experience Manager as a Cloud Service*.
* **Adobe I/O**: [Integração com o Adobe Target usando o Adobe I/O](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html?lang=pt_BR){target=_blank} na documentação do *Guia de administração do usuário*.
* **[!DNL AEM]6.5**: [Ativação do Adobe Analytics e do Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=pt_BR){target=_blank} na documentação do *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4**: [Ativação do Adobe Analytics e do Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=pt_BR){target=_blank} na documentação do *Adobe Experience Manager 6.4*.

### Etapa 2: criar o fragmento de experiência

Os [!UICONTROL fragmentos de experiência] são criados no [!DNL AEM]. Para obter mais informações, consulte:

* **AEM as a Cloud Service**: [[!UICONTROL Fragmentos de experiência]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=pt-BR){target=_blank} no guia do *Experience Manager as a Cloud Service*.
* **[!DNL AEM]6.5**: [[!UICONTROL Fragmentos de experiência]](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=pt_BR){target=_blank} na documentação do *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4**: [[!UICONTROL Fragmentos de experiência]](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=pt_BR){target=_blank} na documentação do *Adobe Experience Manager 6.4*.

### Etapa 3: configurar o [!DNL AEM] para compartilhar o [!UICONTROL fragmento de experiência] com o [!DNL Target]

1. Dentro do [!DNL AEM], selecione o [!UICONTROL fragmento de experiência] desejado ou a pasta que o contém e clique em **[!UICONTROL Propriedades]**.
2. Clique na guia **[!UICONTROL Serviços em nuvem]**, em seguida, na lista suspensa **[!UICONTROL Configuração do serviço em nuvem]**, selecione **[!UICONTROL Adobe Target]**.

   A etapa anterior pressupõe que alguém em sua empresa tenha criado a configuração do [!DNL Adobe Target].

3. Clique em **[!UICONTROL Salvar e fechar]**.

### Etapa 4: publique o [!UICONTROL fragmento de experiência] e exporte-o para o [!DNL Target]

Dependendo da versão do [!DNL AEM], consulte os seguintes links para obter instruções passo a passo:

* **AEM as a Cloud Service**: [Exportar [!UICONTROL fragmentos de experiência] para o Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target.html?lang=pt-BR){target=_blank} no guia do *Experience Manager as a Cloud Service*.
* **[!DNL AEM]6.5**: [Exportação de um fragmento de experiência para o Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=pt-BR){target=_blank} na documentação do *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4**: [Exportação de um fragmento de experiência para o Target](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html?lang=pt_BR){target=_blank} na documentação do *Adobe Experience Manager 6.4*.

## Usar [!UICONTROL fragmentos de experiência] em atividades do [!DNL Target] {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Depois de executar as tarefas anteriores, o [!UICONTROL fragmento de experiência] será exibido na página [!UICONTROL Ofertas] do [!DNL Target].

No momento, o [!DNL Target] procura [!UICONTROL fragmentos de experiência] para importar a cada dez minutos. O [!UICONTROL fragmento de experiência] importado deverá estar disponível no [!DNL Target] em até dez minutos, mas esse intervalo de tempo deve diminuir no futuro.

O [!UICONTROL fragmento de experiência] será importado para o [!DNL Target] como uma oferta HTML ou JSON. A versão “principal” do [!UICONTROL fragmento de experiência] permanece no [!DNL AEM]. Não é possível editar o [!UICONTROL fragmento de experiência] no [!DNL Target].

É possível filtrar e pesquisar por [!UICONTROL fragmentos de experiência de HTML] e [!UICONTROL fragmentos de experiência de JSON] para ajudar a distinguir entre os tipos de [!UICONTROL fragmentos de experiência] que são exportados para o [!DNL Target].

![Filtrar por tipos de fragmentos de experiência (HTML ou JSON) na interface do Target](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Você pode passar o mouse sobre um [!UICONTROL fragmento de experiência] na lista e clicar no ícone [!UICONTROL Exibir] ![Ícone de informação](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) para ver informações adicionais sobre o [!UICONTROL fragmento de experiência], incluindo seu [!UICONTROL Nome], [!UICONTROL Tipo], [!UICONTROL ID da oferta], [!UICONTROL Caminho da oferta] e informações das últimas modificações. Clique na guia [!UICONTROL Uso da oferta] para ver as atividades que fazem referência a essa oferta.

![Pop-up de informações do fragmento de experiência](/help/main/c-integrating-target-with-mac/aem/assets/xf-info-popup.png)

Você pode consumir [!UICONTROL fragmentos de experiência] em atividades do [!DNL Target] usando o [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) e o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md).


>[!TIP]
>
>Use inteligência artificial, aprendizado de máquina e recomendações com [!UICONTROL fragmentos de experiência]:
>
>* Para utilizar toda a funcionalidade de IA e aprendizado de máquina do [!DNL Target], você pode selecionar o recurso de [alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) ou [direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) ao criar uma atividade.
>
>* [!UICONTROL Fragmentos de experiência] não são compatíveis com as atividades do [!DNL Recommendations]. No entanto, para usar [!UICONTROL fragmentos de experiência] em recomendações, você pode criar uma atividade de [!UICONTROL Teste A/B] (incluindo [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático]) ou uma atividade de [!UICONTROL Direcionamento de experiência] (XT) e [incluir o Recommendations como uma oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).


**Para consumir [!UICONTROL fragmentos de experiência] usando o VEC:**

1. No [!DNL Target], ao criar ou editar uma experiência no [Visual Experience Composer](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), clique no local da página onde deseja inserir o conteúdo do [!DNL AEM], em seguida, selecione a opção desejada para exibir a lista [!UICONTROL Escolher um fragmento de experiência].

   * [!UICONTROL Inserir antes]
   * [!UICONTROL Inserir depois de]
   * [!UICONTROL Trocar com fragmento de experiência]

   A lista de [!UICONTROL fragmentos de experiência] exibe o conteúdo criado no [!DNL AEM] que está agora disponível de forma nativa no [!DNL Target].

   >[!NOTE]
   >
   >A opção [!UICONTROL Trocar com fragmento de experiência] não está disponível para imagens. Se você quiser usar essa opção com uma imagem, clique no elemento de contêiner que contém a imagem desejada.

   ![imagem experience_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

1. Selecione o [!UICONTROL fragmento de experiência] desejado e clique em **[!UICONTROL Concluído]**.
1. Termine configurando a atividade.

   Para obter mais informações sobre a configuração de vários tipos de atividades, consulte os tópicos a seguir:

   * **Teste A/B:** [criar um teste A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **Autoalocação:** [autoalocação](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **Direcionamento automático:** [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **Para obter mais informações, consulte** [Criação de uma atividade de Personalização automatizada](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **Direcionamento de experiência (XT):** [criar uma atividade de direcionamento de experiência](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Recommendations em uma atividade de Teste A/B ou de XT:** [Recommendations como uma oferta](/help/main/c-recommendations/recommendations-as-an-offer.md)

   [!UICONTROL Fragmentos de experiência] exportados como JSON no [!DNL Target] não podem ser usados em atividades criadas usando o VEC. Somente [!UICONTROL fragmentos de experiência] de HTML são compatíveis com as atividades baseadas no VEC. Se desejar usar [!UICONTROL fragmentos de experiência] de JSON, use-os em atividades criadas com o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md).

**Para consumir [!UICONTROL fragmentos de experiência] usando o [!UICONTROL Experience Composer baseado em formulário]:**

1. No [!DNL Target], ao criar ou editar uma experiência no [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), selecione o local da página onde deseja inserir o conteúdo do [!DNL AEM] e, em seguida, selecione **[!UICONTROL Alterar fragmento de experiência]** para exibir a lista [!UICONTROL Escolher um fragmento de experiência].

   ![imagem experience_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

   A lista de [!UICONTROL fragmentos de experiência] exibe o conteúdo criado no [!DNL AEM] que está agora disponível de forma nativa no [!DNL Target].

1. Selecione o [!UICONTROL fragmento de experiência] desejado e clique em **[!UICONTROL Salvar]**.
1. Termine configurando a atividade.

## Informações adicionais

* No momento, o [!DNL Target] procura [!UICONTROL fragmentos de experiência] para importar a cada dez minutos. O [!UICONTROL fragmento de experiência] importado deverá estar disponível no [!DNL Target] em até dez minutos, mas esse intervalo de tempo deve diminuir no futuro.
* O [!UICONTROL fragmento de experiência] será importado para o [!DNL Target] como uma oferta HTML ou JSON. A versão “principal” do [!UICONTROL fragmento de experiência] permanece no [!DNL AEM]. Não é possível editar o [!UICONTROL fragmento de experiência] no [!DNL Target].
* Não é possível criar [!UICONTROL fragmentos de experiência] usando o [!DNL Adobe I/O]. Crie [!UICONTROL fragmentos de experiência] usando o AEM, conforme explicado acima.
* Se você atualizar o [!UICONTROL fragmento de experiência] no AEM, o [!UICONTROL fragmento de experiência] deverá ser publicado e exportado para o [!DNL Target] novamente para que o [!DNL Target] possa usar as alterações mais recentes.

## Remover bibliotecas de cliente e elementos de HTML externos dos [!UICONTROL fragmentos de experiência] exportados para o [!UICONTROL Target]

Ao usar ofertas de [!UICONTROL fragmento de experiência] com o [!DNL Target] em uma página entregue pelo AEM, a página de destino já conterá todas as bibliotecas de cliente necessárias. Observe que os elementos de HTML externos da oferta também não são necessários.

Às vezes, páginas HTML inteiras envolvem o [!UICONTROL fragmento de experiência] e causam problemas. Certifique-se de que o [!UICONTROL fragmento de experiência] seja um pequeno trecho de HTML, e não uma página HTML completa com elementos HTML, HEAD, BODY e assim por diante.

Para obter mais informações, consulte a seguinte publicação do blog: [AEM 6.5: remover bibliotecas de cliente de [!UICONTROL fragmentos de experiência] exportados para o Target](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser){target=_blank}.

## Vídeo de treinamento: uso de [!UICONTROL fragmentos de experiência] do AEM com o [!DNL Adobe Target]

O vídeo a seguir mostra como configurar e usar os [!UICONTROL fragmentos de experiência]:

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>O recurso de deeplink do [!DNL AEM] discutido aos 4:54 foi removido.

Para obter informações mais detalhadas, consulte [Uso de [!UICONTROL fragmentos de experiência] com o Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html?lang=pt_BR) na página *Vídeos e tutoriais do AEM Sites*.
