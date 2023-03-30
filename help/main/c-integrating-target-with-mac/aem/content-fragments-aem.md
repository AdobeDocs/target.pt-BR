---
keywords: experiência; json; aem; adobe experience manager; exportar para adobe target; fragmentos de conteúdo; fragmentos; CF; cf; sem cabeçalho; personalização; experimentação
description: Saiba como usar [!DNL Adobe Experience Manager] [!UICONTROL Fragmentos de conteúdo] em [!DNL Adobe Target] atividades.
title: Como usar [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Fragmentos de conteúdo]?
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip="What are Target Beta release features?"
feature: Integrations
source-git-commit: c5629159f55bf3daa09a8ddbe739dfcd6272d285
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 4%

---

# AEM [!UICONTROL Fragmentos de conteúdo]

Use [!UICONTROL Fragmentos de conteúdo] (CFs) criadas em [!DNL Adobe Experience Manager] (AEM) em [!DNL Target] atividades para auxiliar na personalização e na experimentação sem periféricos.

AEM fragmentos de conteúdo para personalização e experimentação sem periféricos

>[!NOTE]
>
>Esse recurso deve ser lançado em 6 de abril de 2023.


>[!NOTE]
>
>Considere o seguinte ao trabalhar com o AEM [!UICONTROL Fragmentos de conteúdo] em [!DNL Target]:
> 
>* Esse recurso exige que você seja uma [!DNL Adobe Experience Manager] (AEM) cliente. Para obter mais informações, consulte [Requisitos](#section_AE6F0971E1574B3AA324003599B96E5A) abaixo.
>
>* Esse recurso está disponível para os seguintes tipos de atividades: [!UICONTROL Teste A/B], [!UICONTROL Alocação automática], [!UICONTROL Direcionamento automático], [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Direcionamento de experiência] (XT). Este recurso não está disponível em [!UICONTROL Teste multivariado] (MVT) e [!UICONTROL Recommendations] atividades.
>
>* Você pode consumir [!UICONTROL Fragmentos de conteúdo] em [!DNL Target] atividades que utilizam [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md) somente. Você não pode consumir [!UICONTROL Fragmentos de conteúdo] usando o [!UICONTROL Visual Experience Composer] (VEC).


Para saber mais sobre AEM [!UICONTROL Fragmentos de conteúdo] e [!UICONTROL Fragmentos de experiência], consulte [AEM [!UICONTROL Fragmentos de experiência] e [!UICONTROL Fragmentos de conteúdo] visão geral](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Exigências {#requirements}

Você deve ser provisionado com a variável [!UICONTROL Fragmentos de conteúdo] funcionalidade no [!DNL Target]. Além disso, você deve usar [!DNL AEM] as a Cloud Service. Seu representante de conta pode ajudar a assegurar que você atenda aos requisitos para usar este recurso:

Entre em contato com o [Atendimento ao cliente do Adobe Target](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para ativar a integração e obter os detalhes de autenticação.

## Como configurar e trabalhar com [!UICONTROL Fragmentos de conteúdo] em [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Para exportar [!UICONTROL Fragmentos de conteúdo] para usar no [!DNL Target] , você deve executar algumas etapas preliminares em AEM. Para obter mais informações, consulte [Exportar fragmentos de conteúdo para o Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html){target=_blank} no *Documentação do Experience Manager as a Cloud Service*. Observe que este link estará disponível no dia do lançamento (6 de abril de 2023)

Para obter informações sobre design, criação, preparação e publicação [!UICONTROL Fragmentos de conteúdo], consulte [[!UICONTROL Fragmentos de conteúdo]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=en){target=_blank} and [Working with Content Fragments](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html){target=_blank} in the [Experience Manager as a Cloud Service documentation](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html){target=_blank}.

## Usando [!UICONTROL Fragmentos de conteúdo] em [!DNL Target] atividades {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Depois de executar as tarefas anteriores, a [!UICONTROL Fragmento de conteúdo] é exibido na [!UICONTROL Ofertas] em [!DNL Target].

[!DNL Target] atualmente procura por [!UICONTROL Fragmentos de conteúdo] para importar a cada dez minutos. O importado [!UICONTROL Fragmento de conteúdo] deve estar disponível em [!DNL Target] em dez minutos, mas esse período deve ser reduzido no futuro.

O [!UICONTROL Fragmento de conteúdo] é importado para [!DNL Target] como uma oferta JSON. Essa [!UICONTROL Fragmento de conteúdo] A versão &quot;primária&quot; permanece em [!DNL AEM]. Não é possível editar o [!UICONTROL Fragmento de conteúdo] em [!DNL Target].

Você pode filtrar e pesquisar por [!UICONTROL HTML XFs], [!UICONTROL JSON XFs]e [!UICONTROL Fragmentos de conteúdo] para ajudar a distinguir entre tipos de ofertas diferentes que são exportadas para o [!DNL Target].

![Filtrar por tipos de Fragmento de conteúdo: HTML ou JSON na interface do usuário do Target](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

Você pode passar o mouse sobre um [!UICONTROL Fragmento de conteúdo] na lista, em seguida, clique no botão [!UICONTROL Exibir] ícone ![Ícone Info](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) para ver informações adicionais sobre o [!UICONTROL Fragmento de conteúdo], incluindo o seu [!UICONTROL Caminho AEM] e [!UICONTROL AEM deep link]. Clique no botão [!UICONTROL Uso da oferta] para ver as atividades que fazem referência a essa oferta.

![pop-up Informações do fragmento de conteúdo](/help/main/c-integrating-target-with-mac/aem/assets/cf-info-popup.png)

Você pode consumir [!UICONTROL Fragmentos de conteúdo] em [!DNL Target] atividades que utilizam [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md) somente. Você *cannot* consume [!UICONTROL Fragmentos de conteúdo] em [!DNL Target] atividades que utilizam [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC). [!UICONTROL Fragmentos de conteúdo] são exportados como JSON em [!DNL Target] e não podem ser usadas em atividades criadas usando o VEC.

>[!TIP]
>
>Use inteligência artificial, aprendizado de máquina e recomendações com [!UICONTROL Fragmentos de conteúdo]:
>
>* Para usar totalmente a variável [!DNL Target] Funcionalidade AI e ML, você pode selecionar [Alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) ou [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) ao criar um teste A/B.
>
>* [!UICONTROL Fragmentos de conteúdo] não são compatíveis com o [!DNL Recommendations] atividades. No entanto, para usar [!UICONTROL Fragmentos de conteúdo] para recomendações, você pode criar um [!UICONTROL Teste A/B] atividade (incluindo [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático]) ou [!UICONTROL Direcionamento de experiência] (XT) e [incluir recomendações como uma oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).


**Para consumir [!UICONTROL Fragmentos de conteúdo] usando o [!UICONTROL Experience Composer baseado em formulário]:**

1. Em [!DNL Target]ao criar ou editar uma experiência no [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), selecione o local na página que deseja inserir [!DNL AEM] conteúdo e selecione **[!UICONTROL Alterar fragmento do conteúdo]** para exibir o [!UICONTROL Escolher um fragmento de conteúdo] lista.

   ![imagem da lista_fragmento_de_conteúdo](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   O [!UICONTROL Fragmento de conteúdo] exibe o conteúdo criado em [!DNL AEM] agora está nativamente disponível dentro de [!DNL Target].

1. Selecione o [!UICONTROL Fragmento de conteúdo], depois clique em **[!UICONTROL Salvar]**.
1. Termine configurando a atividade.

## Considerações {#considerations}

* [!DNL Target] atualmente procura por [!UICONTROL Fragmentos de conteúdo] para importar a cada dez minutos. O importado [!UICONTROL Fragmento de conteúdo] deve estar disponível em [!DNL Target] em dez minutos, mas esse período deve ser reduzido no futuro.
* O [!UICONTROL Fragmento de conteúdo] é importado para [!DNL Target] como uma oferta JSON. O [!UICONTROL Fragmento de conteúdo] A versão &quot;primária&quot; permanece em [!DNL AEM]. Não é possível editar o [!UICONTROL Fragmento de conteúdo] em [!DNL Target].
* Não é possível criar [!UICONTROL Fragmentos de conteúdo] usar [!DNL Adobe I/O]. Criar [!UICONTROL Fragmentos de conteúdo] usando AEM, conforme explicado acima.
* Se você atualizar seu [!UICONTROL Fragmento de conteúdo] em AEM, o [!UICONTROL Fragmento de conteúdo] deve ser publicada e exportada para [!DNL Target] novamente [!DNL Target] O pode usar as alterações mais recentes.