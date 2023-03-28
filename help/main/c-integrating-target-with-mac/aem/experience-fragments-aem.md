---
keywords: experience;aem;adobe experience manager;exportar para adobe target;fragmentos de experiência;fragmentos;XF
description: Saiba como usar [!DNL Adobe Experience Manager] [!UICONTROL Fragmentos de experiência] em [!DNL Adobe Target] atividades.
title: Como usar [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Fragmentos de experiência]?
feature: Integrations
source-git-commit: 0135831b56c48b0adca49e843c5ddd6574358aa4
workflow-type: tm+mt
source-wordcount: '1346'
ht-degree: 32%

---

# AEM [!UICONTROL Fragmentos de experiência]

Use [!UICONTROL Fragmentos de experiência] (XFs) criado em [!DNL Adobe Experience Manager] (AEM) em [!DNL Target] atividades para auxiliar na otimização ou na personalização.

>[!NOTE]
>
>Considere o seguinte ao trabalhar com o AEM [!UICONTROL Fragmentos de experiência] em [!DNL Target]:
> 
>* Esse recurso exige que você seja uma [!DNL Adobe Experience Manager] (AEM) cliente. Para obter mais informações, consulte [Requisitos](#section_AE6F0971E1574B3AA324003599B96E5A) abaixo.
>* Esse recurso está disponível para os seguintes tipos de atividades: [!UICONTROL Teste A/B], [!UICONTROL Alocação automática], [!UICONTROL Direcionamento automático], [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Direcionamento de experiência] (XT). Este recurso não está disponível em [!UICONTROL Teste multivariado] (MVT) e [!UICONTROL Recommendations] atividades.
>
>* Você pode consumir [!UICONTROL Fragmentos de experiência] em [!DNL Target] atividades que utilizam [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) ou [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md).


Para saber mais sobre AEM [!UICONTROL Fragmentos de experiência] e Fragmentos de conteúdo, consulte [AEM [!UICONTROL Fragmentos de experiência] Visão geral dos Fragmentos de conteúdo e do](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Exigências {#requirements}

Você deve ser provisionado com a variável [!UICONTROL Fragmentos de experiência] funcionalidade no [!DNL Target]. Além disso, você deve usar [!DNL AEM] as a Cloud Service ou [!DNL AEM] 6.4 (ou posterior). Seu representante de conta pode ajudar a assegurar que você atenda aos requisitos para usar este recurso:

* [!DNL Adobe Experience Manager ] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5.
* [!DNL Adobe Experience Manager] 6.4.
* Conta do [!DNL Adobe Target Standard] ou do [!DNL Adobe Target Premium].

[!DNL Adobe Experience Manager] As versões 6.3 e 6.4 atingiram o fim da vida útil e não são mais compatíveis (exceto para clientes que compraram suporte estendido).

Entre em contato com o [Atendimento ao cliente do Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para ativar a integração e obter os detalhes de autenticação.

## Criação e configuração [!UICONTROL Fragmentos de experiência] em [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Para usar [!DNL AEM] [!UICONTROL Fragmentos de experiência] em [!DNL Target], você deve executar as seguintes etapas:

### Etapa 1: integrar o [!DNL AEM] com o [!DNL Target]

Para obter mais informações, consulte:

* **AEM as a Cloud Service**: [Integração com o Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target.html){target=_blank} no *Experience Manager as a Cloud Service* guia.
* **Adobe I/O**: [Integração com o Adobe Target usando o Adobe I/O](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html?lang=pt_BR){target=_blank} na documentação do *Guia de administração do usuário*.
* **[!DNL AEM]6.5**: [Ativação do Adobe Analytics e do Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=pt_BR){target=_blank} na documentação do *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4**: [Ativação do Adobe Analytics e do Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=pt_BR){target=_blank} na documentação do *Adobe Experience Manager 6.4*.

### Etapa 2: Criar o fragmento de experiência

[!UICONTROL Fragmentos de experiência] são criados em [!DNL AEM]. Para obter mais informações, consulte:

* **AEM as a Cloud Service**: [[!UICONTROL Fragmentos de experiência]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=en){target=_blank} no *Experience Manager as a Cloud Service* guia.
* **[!DNL AEM]6.5**: [[!UICONTROL Fragmentos de experiência]](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=pt_BR){target=_blank} na documentação do *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4**: [[!UICONTROL Fragmentos de experiência]](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=pt_BR){target=_blank} na documentação do *Adobe Experience Manager 6.4*.

### Etapa 3: Configurar [!DNL AEM] para compartilhar o Fragmento de experiência com [!DNL Target]

1. De dentro [!DNL AEM], selecione o Fragmento de experiência desejado ou a pasta que o contém, em seguida, clique em **[!UICONTROL Propriedades]**.
2. Clique na guia **[!UICONTROL Serviços em nuvem]**, em seguida, na lista suspensa **[!UICONTROL Configuração do serviço em nuvem]**, selecione **[!UICONTROL Adobe Target]**.

   A etapa anterior pressupõe que alguém em sua empresa tenha criado a configuração do [!DNL Adobe Target].

3. Clique em **[!UICONTROL Salvar e fechar]**.

### Etapa 4: Publique o fragmento de experiência e exporte-o para [!DNL Target]

Dependendo da versão do [!DNL AEM], consulte os seguintes links para obter instruções passo a passo:

* **AEM as a Cloud Service**: [Exportar [!UICONTROL Fragmentos de experiência] para o Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target.html?lang=en){target=_blank} no *Experience Manager as a Cloud Service* guia.
* **[!DNL AEM]6.5**: [Exportação de um fragmento de experiência para o Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=en){target=_blank} na documentação do *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4**: [Exportação de um fragmento de experiência para o Target](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html?lang=pt_BR){target=_blank} na documentação do *Adobe Experience Manager 6.4*.

## Usando [!UICONTROL Fragmentos de experiência] em [!DNL Target] atividades {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Depois de executar as tarefas anteriores, o Fragmento de experiência é exibido no [!UICONTROL Ofertas] em [!DNL Target].

[!DNL Target] atualmente procura por [!UICONTROL Fragmentos de experiência] para importar a cada dez minutos. O Fragmento de experiência importado deve estar disponível em [!DNL Target] em dez minutos, mas esse período deve ser reduzido no futuro.

O Fragmento de experiência é importado para [!DNL Target] como HTML ou oferta JSON. Essa versão &quot;primária&quot; do fragmento de experiência permanece em [!DNL AEM]. Você não pode editar o fragmento de experiência no [!DNL Target].

Você pode filtrar e pesquisar por [!UICONTROL HTML XFs] e [!UICONTROL JSON XFs] para ajudar você a distinguir entre os tipos de Fragmento de experiência que são exportados para o [!DNL Target].

![Filtrar por tipos de Fragmento de experiência: HTML ou JSON na interface do usuário do Target](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Você pode passar o mouse sobre um Fragmento de experiência na lista e clicar no botão [!UICONTROL Exibir] ícone ![Ícone Info](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) para ver informações adicionais sobre o Fragmento de experiência, incluindo seu [!UICONTROL Nome], [!UICONTROL Tipo], [!UICONTROL ID da oferta], [!UICONTROL Caminho da oferta]e as últimas modificações. Clique no botão [!UICONTROL Uso da oferta] para ver as atividades que fazem referência a essa oferta.

![pop-up Informações do fragmento de experiência](/help/main/c-integrating-target-with-mac/aem/assets/xf-info-popup.png)

Você pode consumir [!UICONTROL Fragmentos de experiência] em [!DNL Target] atividades que utilizam [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) ou [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md).


>[!TIP]
>
>Use inteligência artificial, aprendizado de máquina e recomendações com [!UICONTROL Fragmentos de experiência]:
>
>* Para usar totalmente a variável [!DNL Target] Funcionalidade AI e ML, você pode selecionar [Alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) ou [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) ao criar um teste A/B.
>
>* [!UICONTROL Fragmentos de experiência] não são compatíveis com o [!DNL Recommendations] atividades. No entanto, para usar [!UICONTROL Fragmentos de experiência] para recomendações, você pode criar um [!UICONTROL Teste A/B] atividade (incluindo [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático]) ou [!UICONTROL Direcionamento de experiência] (XT) e [incluir recomendações como uma oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).


**Para consumir Fragmentos de experiência usando o VEC:**

1. No [!DNL Target], ao criar ou editar uma experiência no [Visual Experience Composer](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), clique no local da página onde deseja inserir o conteúdo do [!DNL AEM], em seguida, selecione a opção desejada para exibir a lista [!UICONTROL Escolher um fragmento de experiência].

   * [!UICONTROL Inserir antes]
   * [!UICONTROL Inserir depois de]
   * [!UICONTROL Trocar com fragmento de experiência]

   O [!UICONTROL Fragmento de experiência] exibe o conteúdo criado em [!DNL AEM] agora está nativamente disponível dentro de [!DNL Target].

   >[!NOTE]
   >
   >A opção [!UICONTROL Trocar com fragmento de experiência] não está disponível para imagens. Se você quiser usar essa opção com uma imagem, clique no elemento de contêiner que contém a imagem desejada.

   ![imagem experience_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

1. Selecione o Fragmento de experiência desejado e clique em **[!UICONTROL Concluído]**.
1. Termine configurando a atividade.

   Para obter mais informações sobre a configuração de vários tipos de atividades, consulte os tópicos a seguir:

   * **Teste A/B:** [criar um teste A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **Autoalocação:** [autoalocação](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **Direcionamento automático:** [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **Para obter mais informações, consulte** [Criação de uma atividade de Personalização automatizada](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **Direcionamento de experiência (XT):** [criar uma atividade de direcionamento de experiência](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Recommendations em uma atividade de Teste A/B ou XT:** [Recommendations como uma oferta](/help/main/c-recommendations/recommendations-as-an-offer.md)

   [!UICONTROL Fragmentos de experiência] exportado como JSON em [!DNL Target] não pode ser usado em atividades criadas usando o VEC; only HTML [!UICONTROL Fragmentos de experiência] são compatíveis com atividades baseadas em VEC. Se quiser usar JSON [!UICONTROL Fragmentos de experiência], use-os em atividades criadas usando o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md).

**Para consumir Fragmentos de experiência usando o Experience Composer baseado em formulário:**

1. No [!DNL Target], ao criar ou editar uma experiência no [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), selecione o local da página onde deseja inserir o conteúdo do [!DNL AEM] e, em seguida, selecione **[!UICONTROL Alterar fragmento de experiência]** para exibir a lista [!UICONTROL Escolher um fragmento de experiência].

   ![imagem experience_fragment_list](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

   O [!UICONTROL Fragmento de experiência] exibe o conteúdo criado em [!DNL AEM] agora está nativamente disponível dentro de [!DNL Target].

1. Selecione o Fragmento de experiência desejado e clique em **[!UICONTROL Salvar]**.
1. Termine configurando a atividade.

## Considerações {#considerations}

* [!DNL Target] atualmente procura por [!UICONTROL Fragmentos de experiência] para importar a cada dez minutos. O Fragmento de experiência importado deve estar disponível em [!DNL Target] em dez minutos, mas esse período deve ser reduzido no futuro.
* O Fragmento de experiência é importado para [!DNL Target] como HTML ou oferta JSON. A versão &quot;primária&quot; do Fragmento de experiência permanece em [!DNL AEM]. Não é possível editar o Fragmento de experiência em [!DNL Target].
* Não é possível criar [!UICONTROL Fragmentos de experiência] usar [!DNL Adobe I/O]. Criar [!UICONTROL Fragmentos de experiência] usando AEM, conforme explicado acima.
* Se você atualizar o Fragmento de experiência no AEM, o Fragmento de experiência deverá ser publicado e exportado para [!DNL Target] novamente [!DNL Target] O pode usar as alterações mais recentes.

## Remoção de ClientLibs e HTML irrelevantes do [!UICONTROL Fragmentos de experiência] exportados para [!UICONTROL Target]

Ao usar ofertas de Fragmento de experiência com [!DNL Target] em uma página entregue pelo AEM, a página de destino já contém todas as bibliotecas de clientes necessárias. Observe também que elementos HTML irrelevantes na oferta também não são necessários.

Às vezes, as páginas de HTML inteiras envolvem o Fragmento de experiência e causam problemas. Certifique-se de que o Fragmento de experiência seja um pequeno HTML e não uma página HTML completa com HTML, HEAD, BODY e assim por diante.

Para obter mais informações, consulte a seguinte publicação do blog: [AEM 6.5: Removendo ClientLibs de [!UICONTROL Fragmentos de experiência] exportado para o Target](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser){target=_blank}.

## Vídeo de treinamento: Uso de AEM [!UICONTROL Fragmentos de experiência] com [!DNL Adobe Target]

O vídeo a seguir mostra como configurar e usar [!UICONTROL Fragmentos de experiência]:

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>O recurso de deeplink do [!DNL AEM] discutido aos 4:54 foi removido.

Para obter informações mais detalhadas, consulte [Usando [!UICONTROL Fragmentos de experiência] com o Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html?lang=pt_BR) no *Vídeos e Tutorials do AEM Sites* página.