---
keywords: público-alvo, regras de público-alvo, criar público-alvo, criação de público-alvo, direcionamento de público-alvo, geração de relatório de público-alvo, relatar público-alvo, segmento, parâmetros de perfil personalizado, definição de público-alvo, lista de público-alvo
description: Saiba como usar públicos-alvo no [!DNL Adobe Target].
title: Como uso a lista de públicos-alvo?
feature: Audiences
exl-id: 7af7f101-f550-4fdc-bcd9-90e4107b0415
source-git-commit: 24f445128aa76eb7e0af7d0f2c5de96f11b8d110
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 33%

---

# Criar públicos-alvo

Públicos-alvo em [!DNL Adobe Target] determine quem vê o conteúdo e as experiências em uma atividade direcionada.

Os público-alvo são usados sempre que o direcionamento estiver disponível. Ao direcionar uma atividade, você tem as seguintes opções:

* Selecione um público-alvo reutilizável no [!UICONTROL Públicos-alvo] lista
* [Criar um público-alvo para uma atividade específica](/help/main/c-target/creating-activity-only-audience.md) e direcionar
* [Combinar vários públicos](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) para criar um público-alvo ad hoc

Você também pode usar os dados do público-alvo coletados por [!DNL Adobe Analytics] para direcionamento e personalização em tempo real no [!DNL Target] e outros [!DNL Adobe Experience Cloud] aplicativos. Consulte [Públicos-alvo do Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=pt-BR) no *Componentes da interface central do Experience Cloud* guia.

Há dois tipos de públicos-alvo no [!DNL Target]:

* **Direcionamento de públicos-alvo:** Usado para oferecer conteúdo diferente para diferentes tipos de visitantes.
* **Públicos-alvo do relatório:** Usado para determinar como diferentes tipos de visitantes respondem ao mesmo conteúdo para que você possa analisar os resultados de seus testes.

   No [!DNL Target], é possível configurar relatórios de públicos-alvo apenas se você usar o [!DNL Target] como fonte de geração de relatórios. Se você usa o [ Adobe Analytics como fonte de relatórios](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), precisa configurar os públicos dos relatórios no [!DNL Analytics].

## Use o [!UICONTROL Públicos-alvo] lista {#use-list}

Para acessar a lista [!UICONTROL Públicos-alvo], clique em **[!UICONTROL Públicos-alvo]** na barra do menu superior:

![Lista de públicos](assets/audiences_list.png)

O [!UICONTROL Públicos-alvo] contém os públicos que você pode usar em suas atividades. Use o [!UICONTROL Públicos-alvo] lista para criar, editar, duplicar, copiar ou combinar públicos. A lista também mostra a fonte onde o público-alvo foi criado:

* [!DNL Adobe Target]
* [!DNL Adobe Target Classic]
* [!DNL Experience Cloud]
* [!DNL Adobe Experience Platform]

   >[!NOTE]
   >
   >O [!DNL Adobe Experience Platform] A fonte está disponível para todos [!DNL Target] clientes que usam o [Adobe Experience Platform Web SDK](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/){target=_blank}. Públicos-alvo disponíveis na [!DNL Adobe Experience Platform] pode ser usada como está ou [combinado com públicos-alvo existentes](/help/main/c-target/combining-multiple-audiences.md).
   >
   >Os usuários devem ter [!UICONTROL Aprovador] ou acima do status em [!DNL Target] para configurar [!DNL Target] [!UICONTROL Destinos] cartões em AEP/RTCDP ([!DNL Real-time Customer Data Platform]).
   >
   >Para obter mais informações, consulte [Usar públicos-alvo do Adobe Experience Platform](#aep).

Públicos-alvo predefinidos, como &quot;[!UICONTROL Novos visitantes]&quot; e &quot;[!UICONTROL Visitantes recorrentes],&quot; não pode ser renomeado.

Ao trabalhar com públicos-alvo que foram originalmente criados em [!DNL Experience Cloud] ou [!DNL Adobe Experience Platform], [!DNL Target] O alerta se você fizer referência a um público-alvo em [!DNL Target] atividades que foram excluídas posteriormente em [!DNL Experience Cloud] ou [!DNL Adobe Experience Platform].

* Se um público-alvo foi excluído em [!DNL Experience Cloud] ou [!DNL Adobe Experience Platform], um ícone de aviso em ambas as [!UICONTROL Público] lista e o seletor de público-alvo é exibido. Uma dica de ferramenta na [!DNL Target] A interface do usuário também indica que o público-alvo foi excluído em [!DNL Experience Cloud] ou [!DNL Adobe Experience Platform].
* Se você tentar combinar vários públicos com um público-alvo excluído, ou se tentar salvar uma atividade que faça referência a um público-alvo excluído, será exibida uma mensagem de aviso.

Você também pode direcionar parâmetros de perfis personalizados e parâmetros de `user.`. Ao criar um público-alvo, arraste os atributos que deseja usar para direcionar sua atividade para a janela do construtor de público-alvo. Se o atributo desejado não for exibido, ele não foi acionado por uma mbox. Outros parâmetros de mbox personalizados estão disponíveis na lista suspensa [!UICONTROL Parâmetros personalizados].

Use o [!UICONTROL Filtros] para filtrar o [!UICONTROL Públicos-alvo] listar por origem: [!DNL Adobe Target], [!DNL Adobe Target Classic], [!DNL Experience Cloud]e [!DNL Adobe Experience Platform].

![Opção de Filtros na [!UICONTROL Públicos-alvo] lista](assets/filters.png)

Use o [!UICONTROL Pesquisar públicos-alvo] para pesquisar sua [!UICONTROL Públicos-alvo] lista. Você pode procurar qualquer parte de um nome de público-alvo ou pode colocar uma determinada sequência de caracteres entre aspas.

Você pode classificar a lista de [!UICONTROL Públicos-alvo] por nome de público-alvo ou pela data da última modificação. Para classificar por nome ou data, clique no cabeçalho da coluna e selecione para exibir os públicos-alvo em ordem crescente ou decrescente.

## Exibir definições de público-alvo {#section_11B9C4A777E14D36BA1E925021945780}

Você pode exibir os detalhes da definição de público-alvo em um cartão pop-up em vários locais na [!DNL Target] Interface do usuário sem abrir o público-alvo. Essa funcionalidade se aplica a públicos-alvo criados no [!DNL Target Standard/Premium] e públicos-alvo importados de [!DNL Target Classic] ou criado por meio da API.

Por exemplo, o seguinte cartão de definição de público-alvo é acessado clicando-se no link [!UICONTROL Exibir detalhes] ícone para o público-alvo desejado:

![Atividades > Definição de público](assets/audience_definition_list.png)

O seguinte cartão de definição de público-alvo é acessado clicando-se em [!UICONTROL Exibir detalhes] em uma atividade [!UICONTROL Visão geral] página:

![Atividades > Definição de público](assets/view-details-activity-overview.png)

O cartão de definição de público-alvo mostra o tipo, a fonte e os atributos do público-alvo. Clique em **[!UICONTROL Exibir detalhes completos]** para ver outras atividades que fazem referência a esse público-alvo, se aplicável. Se você estiver visualizando um cartão de definição de público-alvo de uma atividade [!UICONTROL Visão geral] página, clique em **[!UICONTROL Uso de público-alvo]**.

As informações de uso do público-alvo podem ajudá-lo a evitar um impacto acidental em outras atividades ao editar os públicos-alvo. As informações incluem [!UICONTROL Atividades ao vivo], [!UICONTROL Atividades inativas], [!UICONTROL Atividades arquivadas]e [!UICONTROL Atividades de sincronização]. Esse recurso está disponível para todos os públicos-alvo (público-alvo de biblioteca e  [públicos-alvo somente de atividades](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)).

Se um público-alvo for [combinado com outro público](/help/main/c-target/combining-multiple-audiences.md) e o público-alvo combinado é usado para criar uma atividade, as informações de uso para ambos os públicos-alvo listam essa atividade recém-criada.

![imagem audience_definition_list_usage](assets/audience_definition_list_usage.png)

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

## Usar públicos-alvo de [!DNL Adobe Experience Platform] {#aep}

O uso de públicos-alvo criados na [!DNL Adobe Experience Platform] fornece dados do cliente mais avançados, o que resulta em uma personalização mais impactante.

Para obter mais informações, consulte [Usar públicos-alvo de [!DNL Adobe Experience Platform]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#aep).

## Vídeo de treinamento: Uso de públicos-alvo ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo inclui informações sobre o uso de públicos-alvo.

* Explique o termo &quot;público-alvo&quot;
* Explicar as duas maneiras como o público-alvo é usado para otimização
* Encontre públicos-alvo na lista de públicos-alvo
* Segmente uma atividade para um público-alvo
* Use públicos-alvo para relatórios passivos em uma atividade

>[!VIDEO](https://video.tv.adobe.com/v/17398)
