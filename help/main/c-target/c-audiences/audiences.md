---
keywords: público-alvo, regras de público-alvo, criar público-alvo, criação de público-alvo, direcionamento de público-alvo, geração de relatório de público-alvo, relatar público-alvo, segmento, parâmetros de perfil personalizado, definição de público-alvo, lista de público-alvo
description: Saiba como usar públicos no [!DNL Adobe Target].
title: Como usar a lista de públicos-alvo?
feature: Audiences
exl-id: 7af7f101-f550-4fdc-bcd9-90e4107b0415
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 22%

---

# Criar públicos-alvo

Os públicos-alvo em [!DNL Adobe Target] determinam quem vê o conteúdo e as experiências em uma atividade direcionada.

Os público-alvo são usados sempre que o direcionamento estiver disponível. Ao direcionar uma atividade, você tem as seguintes opções:

* Selecione um público-alvo reutilizável na lista [!UICONTROL Audiences]
* [Criar um público-alvo específico para a atividade](/help/main/c-target/creating-activity-only-audience.md) e direcioná-lo
* [Combinar vários públicos-alvo](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) para criar um público-alvo ad hoc

Você também pode usar os dados de público-alvo coletados pelo [!DNL Adobe Analytics] para o direcionamento e personalização em tempo real no [!DNL Target] e em outros aplicativos do [!DNL Adobe Experience Cloud]. Consulte [Experience Cloud Audiences](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=pt-BR) no guia *Experience Cloud Componentes da interface central*.

Há dois tipos de público-alvo em [!DNL Target]:

* **Direcionamento de públicos-alvo:** usado para fornecer conteúdo diferente a diferentes tipos de visitantes.
* **Relatório de públicos-alvo:** usado para determinar como diferentes tipos de visitantes respondem ao mesmo conteúdo para que você possa analisar os resultados de seus testes.

  No [!DNL Target], é possível configurar relatórios de públicos-alvo apenas se você usar o [!DNL Target] como fonte de geração de relatórios. Se você usa o [Adobe Analytics como fonte de relatórios](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), precisa configurar os públicos dos relatórios no [!DNL Analytics].

## Usar a lista [!UICONTROL Audiences] {#use-list}

Para acessar a lista [!UICONTROL Audiences], clique em **[!UICONTROL Audiences]** na barra de menu superior:

![[!UICONTROL Audiences] lista](assets/audiences_list.png)

A lista [!UICONTROL Audiences] contém os públicos-alvo que você pode usar em suas atividades. Use a lista [!UICONTROL Audiences] para criar, editar, duplicar, copiar ou combinar públicos. A lista também mostra a fonte onde o público-alvo foi criado:

* [!DNL Adobe Target]
* [!DNL Adobe Target Classic]
* [!DNL Experience Cloud]
* [!DNL Adobe Experience Platform]

  >[!NOTE]
  >
  >A origem [!DNL Adobe Experience Platform] está disponível para todos os clientes [!DNL Target] que usam o [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=pt-BR){target=_blank}. Os públicos-alvo disponíveis em [!DNL Adobe Experience Platform] podem ser usados como estão ou [combinados com públicos-alvo existentes](/help/main/c-target/combining-multiple-audiences.md).
  >
  >Os usuários devem ter o status [!UICONTROL Approver] ou superior em [!DNL Target] para configurar cartões [!DNL Target] [!UICONTROL Destinations] em AEP/RTCDP ([!DNL Real-time Customer Data Platform]).
  >
  >Para obter mais informações, consulte [Usar públicos do Adobe Experience Platform](#aep).

Públicos predefinidos, como &quot;[!UICONTROL New Visitors]&quot; e &quot;[!UICONTROL Returning Visitors]&quot;, não podem ser renomeados.

Ao trabalhar com públicos originalmente criados em [!DNL Experience Cloud] ou [!DNL Adobe Experience Platform], o [!DNL Target] alerta você se você fizer referência a um público em [!DNL Target] atividades que foram excluídas posteriormente em [!DNL Experience Cloud] ou [!DNL Adobe Experience Platform].

* Se um público-alvo foi excluído em [!DNL Experience Cloud] ou [!DNL Adobe Experience Platform], é exibido um ícone de aviso na lista [!UICONTROL Audience] e no seletor de público. Uma dica de ferramenta na interface do usuário [!DNL Target] também indica que o público-alvo foi excluído em [!DNL Experience Cloud] ou [!DNL Adobe Experience Platform].
* Se você tentar combinar vários públicos com um público-alvo excluído, ou se tentar salvar uma atividade que faça referência a um público-alvo excluído, será exibida uma mensagem de aviso.

Você também pode direcionar parâmetros de perfis personalizados e parâmetros de `user.`. Ao criar um público-alvo, arraste os atributos que deseja usar para direcionar sua atividade na janela do audience builder. Se o atributo desejado não for exibido, o atributo não foi acionado por uma mbox. Outros parâmetros de mbox personalizados estão disponíveis na lista suspensa [!UICONTROL Custom Parameters].

Use o botão [!UICONTROL Filters] para filtrar a lista [!UICONTROL Audiences] por origem: [!DNL Adobe Target], [!DNL Adobe Target Classic], [!DNL Experience Cloud] e [!DNL Adobe Experience Platform].

![Opção Filtros na lista [!UICONTROL Audiences]](assets/filters.png)

Use a caixa [!UICONTROL Search audiences] para pesquisar sua lista [!UICONTROL Audiences]. Você pode procurar qualquer parte de um nome de público-alvo ou pode colocar uma determinada sequência de caracteres entre aspas.

Você pode classificar a lista [!UICONTROL Audiences] por nome de público-alvo ou pela data da última modificação. Para classificar por nome ou data, clique no cabeçalho da coluna e selecione para exibir os públicos-alvo em ordem crescente ou decrescente.

## Exibir definições de público-alvo {#section_11B9C4A777E14D36BA1E925021945780}

Você pode exibir os detalhes de definição de público-alvo em um cartão pop-up em vários locais na interface do usuário do [!DNL Target] sem abrir o público-alvo. Essa funcionalidade aplica-se aos públicos-alvo criados em [!DNL Target Standard/Premium] e aos públicos-alvo importados de [!DNL Target Classic] ou criados por meio da API.

Por exemplo, o cartão de definição de público-alvo a seguir é acessado clicando-se no ícone [!UICONTROL View Details] para o público-alvo desejado:

![Atividades > Definição de público](assets/audience_definition_list.png)

O seguinte cartão de definição de público-alvo é acessado clicando-se no ícone [!UICONTROL View Details] na página [!UICONTROL Overview] de uma atividade:

![Atividades > Definição de público](assets/view-details-activity-overview.png)

O cartão de definição de público-alvo mostra o tipo, a origem e os atributos do público-alvo. Clique em **[!UICONTROL View full details]** para ver outras atividades que fazem referência a esse público-alvo, se aplicável. Se você estiver visualizando um cartão de definição de público-alvo na página [!UICONTROL Overview] de uma atividade, clique em **[!UICONTROL Audience Usage]**.

As informações de uso do público podem ajudar você a evitar impacto acidental em outras atividades ao editar públicos. As informações incluem [!UICONTROL Live Activities], [!UICONTROL Inactive Activities], [!UICONTROL Archived Activities] e [!UICONTROL Syncing Activities]. Este recurso está disponível para todos os públicos-alvo (Biblioteca de públicos-alvo e [somente atividade](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)).

Se um público-alvo for [combinado com outro público-alvo](/help/main/c-target/combining-multiple-audiences.md) e o público-alvo combinado for usado para criar uma atividade, as informações de uso para ambos os públicos-alvo listarão essa atividade recém-criada.

![imagem de audience_definition_list_usage](assets/audience_definition_list_usage.png)

<!--The following audience definition card is for an audience imported from the Adobe Experience Cloud. In this instance, the audience was imported from Adobe Audience Manager (AAM).

![Usage tab on Audience Definition card](assets/audience_definition_mc.png)

The following details are available for these imported audience types:

| Audience Type | Details |
|--- |--- |
|Mobile audience|Marketing Name, Vendor, and Model.<br>The `matches | does not match` operator displays instead of `equals | does not equal`<br>![Imported Mobile Audience](/help/main/c-target/c-audiences/assets/imported_mobile_audience.png).|
|Visitor-behavior audience|**user.categoryAffinity:** `categoryAffinity` with `FAVORITE` parameter.<br>![Imported Category Affinity](/help/main/c-target/c-audiences/assets/imported_category_affinity.png)<br>**Monitoring:** Monitoring service equals true.<br>**No Monitoring Service:** Monitoring service equals false.<br>![Imported Monitoring](/help/main/c-target/c-audiences/assets/imported_monitoring.png)|
|Audiences using the NOT operator|**Single Rule:** Target displays the audience in the format `[All Visitor AND [NOT [rule]`. Single NOT rule displays with AND with `AllVisitor` audience.<br>![Imported Not Audience](/help/main/c-target/c-audiences/assets/imported_not_audience.png)|

Keep the following points in mind as you work with imported audiences:

* Expression target audiences are no longer supported in Target Standard/Premium. 
* Target Standard/Premium does not support some deprecated audiences or has improved operators for ease of use. Because of this, the definition of an imported audience, although working as per definition, does not mean that same is now available for creation in the Standard/Premium interface. For example, Social Audiences are visible with their rules but Target Standard/Premium does not allow social audiences to be created.-->

## Usar públicos da [!DNL Adobe Experience Platform] {#aep}

O uso de públicos-alvo criados no [!DNL Adobe Experience Platform] fornece dados mais avançados do cliente, o que resulta em personalizações mais impactantes.

Para obter mais informações, consulte [Usar públicos-alvo de [!DNL Adobe Experience Platform]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#aep).

## Vídeo de treinamento: usando públicos-alvo ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo inclui informações sobre o uso de públicos-alvo.

* Explique o termo &quot;público-alvo&quot;
* Explicar as duas maneiras como o público-alvo é usado para otimização
* Encontre públicos-alvo na lista de públicos-alvo
* Segmente uma atividade para um público-alvo
* Use públicos-alvo para relatórios passivos em uma atividade

>[!VIDEO](https://video.tv.adobe.com/v/17398)
