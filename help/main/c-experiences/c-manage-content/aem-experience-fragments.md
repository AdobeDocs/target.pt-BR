---
keywords: experience;aem;adobe experience manager;exportar para adobe target;fragmentos de experiência;fragmentos;XF
description: Saiba como usar [!DNL Adobe Experience Manager] fragmentos de experiência em [!DNL Adobe Target] atividades.
title: Como usar [!DNL Adobe Experience Manager] (AEM) Fragmentos de experiência?
feature: Experiences and Offers
exl-id: 3dd811a4-c7be-443d-a5ad-5b9adcaf1a2c
source-git-commit: 358b1d97ba6b9e6ffa276f096596d09d7197b82b
workflow-type: tm+mt
source-wordcount: '1380'
ht-degree: 57%

---

# Fragmentos de experiência do AEM

Usar fragmentos de experiência criados em [!DNL Adobe Experience Manager] (AEM) em [!DNL Target] atividades para auxiliar na otimização ou na personalização.

>[!NOTE]
>
>Esse recurso exige que você seja uma [!DNL Adobe Experience Manager] (AEM) cliente. Para obter mais informações, consulte [Requisitos](#section_AE6F0971E1574B3AA324003599B96E5A) abaixo.

Uso de fragmentos de experiência criados em [!DNL AEM] em [!DNL Target] permite combinar a facilidade de uso e o poder da [!DNL AEM] com poderosos recursos de Inteligência Artificial (AI) e Aprendizagem de Máquina (ML) em [!DNL Target] para testar e personalizar experiências em escala.

O [!DNL AEM] reúne todo o seu conteúdo e ativos em um local central para alimentar sua estratégia de personalização. O [!DNL AEM] permite que você crie conteúdo facilmente para desktops, tablets e dispositivos móveis em um único local sem escrever código. Não há necessidade de criar páginas para cada dispositivo. O [!DNL AEM] ajusta automaticamente cada experiência usando o seu conteúdo.

O [!DNL Target] permite entregar experiências personalizadas em escala com base em uma combinação de abordagens de aprendizagem de máquina baseadas em regras e AI que incorporam variáveis comportamentais, contextuais e offline. Com [!DNL Target], você pode configurar e executar facilmente [Teste A/B](/help/main/c-activities/t-test-ab/test-ab.md) e [Multivariado](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) para determinar as melhores ofertas, conteúdo e experiências.

Os fragmentos de experiência representam um enorme passo à frente para vincular os criadores e gerentes de conteúdo/experiência aos profissionais de otimização e personalização que impulsionam os resultados de negócios usando o [!DNL Target].

## Exigências {#section_AE6F0971E1574B3AA324003599B96E5A}

Você deve estar provido da funcionalidade dos fragmentos de experiência dentro do [!DNL Target]. Além disso, você deve usar [!DNL AEM] as a Cloud Service ou [!DNL AEM] 6.4 (ou posterior). Seu representante de conta pode ajudar a assegurar que você atenda aos requisitos para usar este recurso:

* [!DNL Adobe Experience Manager ] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5.
* [!DNL Adobe Experience Manager] 6.4.
* Conta do [!DNL Adobe Target Standard] ou do [!DNL Adobe Target Premium].

>[!NOTE]
>
>[!DNL Adobe Experience Manager] As versões 6.3 e 6.4 atingiram o fim da vida útil e não são mais compatíveis (exceto para clientes que compraram suporte estendido).

Entre em contato com o [Atendimento ao cliente do Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para ativar a integração e obter os detalhes de autenticação.

## Criação e configuração dos fragmentos de experiência no [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Para usar fragmentos de experiência do [!DNL AEM] no [!DNL Target], você deve executar as seguintes etapas:

### Etapa 1: integrar o [!DNL AEM] com o [!DNL Target]

Para obter mais informações, consulte:

* **AEM as a Cloud Service**: [Integração com o Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target.html){target=_blank} no *Experience Manager as a Cloud Service* guia.
* **Adobe I/O**: [Integração com o Adobe Target usando o Adobe I/O](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html?lang=pt_BR){target=_blank} na documentação do *Guia de administração do usuário*.
* **[!DNL AEM]6.5**: [Ativação do Adobe Analytics e do Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=pt_BR){target=_blank} na documentação do *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4**: [Ativação do Adobe Analytics e do Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=pt_BR){target=_blank} na documentação do *Adobe Experience Manager 6.4*.

### Etapa 2: criar o fragmento de experiência

Fragmentos de experiência são criados no [!DNL AEM]. Para obter mais informações, consulte:

* **AEM as a Cloud Service**: [Fragmentos de experiência](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=en){target=_blank} no *Experience Manager as a Cloud Service* guia.
* **[!DNL AEM]6.5**: [Fragmentos de experiência](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=pt_BR){target=_blank} na documentação do *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4**: [Fragmentos de experiência](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=pt_BR){target=_blank} na documentação do *Adobe Experience Manager 6.4*.

### Etapa 3: configurar o [!DNL AEM] para compartilhar o fragmento de experiência com o [!DNL Target]

1. Dentro do [!DNL AEM], selecione o fragmento de experiência desejado ou a pasta que o contém, depois clique em **[!UICONTROL Propriedades]**.
2. Clique na guia **[!UICONTROL Serviços em nuvem]**, em seguida, na lista suspensa **[!UICONTROL Configuração do serviço em nuvem]**, selecione **[!UICONTROL Adobe Target]**.

   >[!NOTE]
   >
   >A etapa anterior pressupõe que alguém em sua empresa tenha criado a configuração do [!DNL Adobe Target].

3. Clique em **[!UICONTROL Salvar e fechar]**.

### Etapa 4: publique o fragmento de experiência e exporte-o para o [!DNL Target]

Dependendo da versão do [!DNL AEM], consulte os seguintes links para obter instruções passo a passo:

* **AEM as a Cloud Service**: [Exportar fragmentos de experiência para o Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target.html?lang=en){target=_blank} no *Experience Manager as a Cloud Service* guia.
* **[!DNL AEM]6.5**: [Exportação de um fragmento de experiência para o Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=en){target=_blank} na documentação do *Adobe Experience Manager 6.5*.
* **[!DNL AEM]6.4**: [Exportação de um fragmento de experiência para o Target](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html?lang=pt_BR){target=_blank} na documentação do *Adobe Experience Manager 6.4*.

## Uso de fragmentos de experiência nas atividades do [!DNL Target] {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Depois de executar as tarefas anteriores, o fragmento de experiência é exibido na página [!UICONTROL Ofertas] no [!DNL Target].

>[!NOTE]
>
>* No [!DNL Target] momento, o procura fragmentos de experiência a cada dez minutos. O fragmento de experiência importado deve estar disponível no [!DNL Target] dentro de dez minutos, mas esse intervalo de tempo deve ficar mais curto no futuro.
>
>* O fragmento de experiência é importado para [!DNL Target] como HTML ou oferta JSON. Essa versão &quot;primária&quot; do fragmento de experiência permanece em [!DNL AEM]. Você não pode editar o fragmento de experiência no [!DNL Target].


Você pode filtrar e pesquisar por [!UICONTROL HTML XF] e [!UICONTROL JSON XF] para ajudar você a distinguir entre tipos de fragmento de experiência exportados para o [!DNL Target].

Você pode passar o mouse sobre um fragmento de experiência na lista e, depois, clicar no ícone [!UICONTROL Exibir] ![ícone Exibir](assets/icon_info.png) para ver informações adicionais sobre o fragmento de experiência, incluindo o URL de entrega de oferta pública e o caminho do [!DNL AEM].

Você pode consumir fragmentos de experiência em atividades do [!DNL Target] usando o [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) ou o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>Para usar totalmente a variável [!DNL Target] Funcionalidade AI e ML, você pode selecionar [Alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) ou [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) ao criar um teste A/B.
>
>Fragmentos de experiência não são suportados em [!DNL Recommendations] atividades. No entanto, para usar fragmentos de experiência para recomendações, você pode criar um [!UICONTROL Teste A/B] atividade (incluindo [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático]) ou [!UICONTROL Direcionamento de experiência] (XT) e [incluir recomendações como uma oferta](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

**Para consumir fragmentos de experiência usando o VEC:**

1. No [!DNL Target], ao criar ou editar uma experiência no [Visual Experience Composer](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), clique no local da página onde deseja inserir o conteúdo do [!DNL AEM], em seguida, selecione a opção desejada para exibir a lista [!UICONTROL Escolher um fragmento de experiência].

   * [!UICONTROL Inserir antes]
   * [!UICONTROL Inserir depois de]
   * [!UICONTROL Trocar com fragmento de experiência]

   O [!UICONTROL Fragmento de experiência] exibe o conteúdo criado em [!DNL AEM] agora está nativamente disponível dentro de [!DNL Target].

   >[!NOTE]
   >
   >A opção [!UICONTROL Trocar com fragmento de experiência] não está disponível para imagens. Se você quiser usar essa opção com uma imagem, clique no elemento de contêiner que contém a imagem desejada.

   ![imagem experience_fragment_list](assets/experience_fragment_list.png)

1. Selecione o fragmento de experiência desejado e clique em **[!UICONTROL Concluído]**.
1. Termine configurando a atividade.

   Para obter mais informações sobre a configuração de vários tipos de atividades, consulte os tópicos a seguir:

   * **Teste A/B:** [criar um teste A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **Autoalocação:** [autoalocação](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **Direcionamento automático:** [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **Para obter mais informações, consulte** [Criação de uma atividade de Personalização automatizada](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **Direcionamento de experiência (XT):** [criar uma atividade de direcionamento de experiência](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Teste multivariado (MVT):** [criar um teste multivariado](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710)
   * **Recommendations:** [criar uma atividade do Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

>[!NOTE]
>
>Fragmentos de experiência exportados como JSON em [!DNL Target] não pode ser usado em atividades criadas usando o VEC; somente os fragmentos de experiência do HTML são suportados em atividades baseadas no VEC. Se quiser usar fragmentos de experiência JSON, use-os em atividades criadas usando o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md).

**Para consumir fragmentos de experiência usando o Experience Composer baseado em formulário:**

1. No [!DNL Target], ao criar ou editar uma experiência no [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), selecione o local da página onde deseja inserir o conteúdo do [!DNL AEM] e, em seguida, selecione **[!UICONTROL Alterar fragmento de experiência]** para exibir a lista [!UICONTROL Escolher um fragmento de experiência].

   ![imagem experience_fragment_list](assets/experience_fragment_list.png)

   O [!UICONTROL Fragmento de experiência] exibe o conteúdo criado em [!DNL AEM] agora está nativamente disponível dentro de [!DNL Target].

1. Selecione o fragmento de experiência desejado e clique em **[!UICONTROL Salvar]**.
1. Termine configurando a atividade.

## Considerações {#considerations}

* No [!DNL Target] momento, o procura fragmentos de experiência a cada dez minutos. O fragmento de experiência importado deve estar disponível no [!DNL Target] dentro de dez minutos, mas esse intervalo de tempo deve ficar mais curto no futuro.
* O fragmento de experiência é importado para [!DNL Target] como HTML ou oferta JSON. A versão &quot;primária&quot; do fragmento de experiência permanece em [!DNL AEM]. Você não pode editar o fragmento de experiência no [!DNL Target].
* Não é possível criar fragmentos de experiência usando [!DNL Adobe I/O]. Crie fragmentos de experiência usando AEM, conforme explicado acima.
* Se você atualizar o fragmento de experiência no AEM, o fragmento de experiência deverá ser publicado e exportado para [!DNL Target] novamente [!DNL Target] O pode usar as alterações mais recentes.

## Remoção de ClientLibs e HTML extras dos Fragmentos de experiência exportados para o Target

Ao usar ofertas de fragmento de experiência com [!DNL Target] em uma página entregue pelo AEM, a página de destino já contém todas as bibliotecas de clientes necessárias. Observe também que elementos HTML irrelevantes na oferta também não são necessários.

Às vezes, as páginas de HTML inteiras envolvem o fragmento de experiência e causam problemas. Certifique-se de que o fragmento de experiência seja um pequeno HTML e não uma página HTML completa com HTML, HEAD, BODY e assim por diante.

Para obter mais informações, consulte a seguinte publicação do blog: [AEM 6.5: Remoção de bibliotecas de clientes dos fragmentos de experiência exportados para o Target](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser){target=_blank}.

## Vídeo de treinamento: Uso AEM fragmentos de experiência com [!DNL Adobe Target]

O vídeo a seguir mostra como configurar e usar fragmentos de experiência:

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>O recurso de deeplink do [!DNL AEM] discutido aos 4:54 foi removido.

Para obter informações mais detalhadas, consulte [Uso de fragmentos de experiência com o Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html?lang=pt_BR) no *Vídeos e Tutorials do AEM Sites* página.
