---
keywords: público-alvo, regras de público-alvo, criar público-alvo, criação de público-alvo, direcionamento de público-alvo, geração de relatório de público-alvo, relatar público-alvo, segmento, parâmetros de perfil personalizado, definição de público-alvo, lista de público-alvo
description: Saiba como usar a lista [!UICONTROL Audiences] em [!DNL Adobe Target].
title: Como uso a lista de públicos-alvo?
feature: Públicos-alvo
exl-id: 7af7f101-f550-4fdc-bcd9-90e4107b0415
source-git-commit: f7d73de376c2345b628e3ebadb1d4ab4dc598693
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 32%

---

# Criar públicos-alvo

Os públicos-alvo em [!DNL Adobe Target] determinam quem vê o conteúdo e as experiências em uma atividade direcionada.

Os público-alvo são usados sempre que o direcionamento estiver disponível. Ao direcionar uma atividade, você tem as seguintes opções:

* Selecione um público-alvo reutilizável na lista [!UICONTROL Públicos-alvo]
* [Criar um ](/help/c-target/creating-activity-only-audience.md) público-alvo específico da atividade e direcioná-lo
* [Combinar vários ](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) públicos para criar um público-alvo ad hoc

Você também pode usar os dados do público-alvo coletados por [!DNL Adobe Analytics] para o direcionamento e personalização em tempo real em [!DNL Target] e outros aplicativos [!DNL Adobe Experience Cloud]. Consulte [Experience Cloud Audiences](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=pt-BR) no guia *Experience Cloud Central Interface Components*.

Há dois tipos de públicos-alvo em [!DNL Target]:

* **Direcionamento de públicos-alvo:** usado para oferecer conteúdo diferente para diferentes tipos de visitantes.
* **Relatório de públicos-alvo:** usado para determinar como diferentes tipos de visitantes respondem ao mesmo conteúdo para que você possa analisar os resultados de seus testes.

   No [!DNL Target], é possível configurar relatórios de públicos-alvo apenas se você usar o [!DNL Target] como fonte de geração de relatórios. Se você usa o [ Adobe Analytics como fonte de relatórios](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T), precisa configurar os públicos dos relatórios no [!DNL Analytics].

## Use a lista [!UICONTROL Públicos-alvo]

Para acessar a lista [!UICONTROL Públicos-alvo], clique em **[!UICONTROL Públicos-alvo]** na barra do menu superior:

![Lista de públicos](assets/audiences_list.png)

A lista [!UICONTROL Audiences] contém os públicos que você pode usar em suas atividades. Use a lista [!UICONTROL Audiences] para criar, editar, duplicar, copiar ou combinar públicos. A lista também mostra a fonte onde o público-alvo foi criado:

* [!DNL Adobe Target]
* [!DNL Adobe Target Classic]
* [!DNL Experience Cloud]
* [!DNL Adobe Experience Platform]

   >[!NOTE]
   >
   >A fonte [!DNL Adobe Experience Platform] está em um programa de teste Beta, mas está disponível para todos os [!DNL Target] clientes que usam o [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md). Os públicos-alvo disponíveis no [!DNL Adobe Experience Platform] podem ser usados como estão ou [combinados com públicos-alvo existentes](/help/c-target/combining-multiple-audiences.md).

Públicos predefinidos, como &quot;[!UICONTROL Novos visitantes]&quot; e &quot;[!UICONTROL Visitantes que retornam]&quot;, não podem ser renomeados.

Ao trabalhar com públicos-alvo que foram originalmente criados em [!DNL Experience Cloud] ou [!DNL Adobe Experience Platform], [!DNL Target] o alerta se você fizer referência a um público-alvo em [!DNL Target] atividades que foram posteriormente excluídas em [!DNL Experience Cloud] ou [!DNL Adobe Experience Platform].

* Se um público-alvo foi excluído em [!DNL Experience Cloud] ou [!DNL Adobe Experience Platform], um ícone de aviso é exibido na lista [!UICONTROL Público-alvo] e o seletor de público-alvo. Uma dica de ferramenta na interface [!DNL Target] também indica que o público-alvo foi excluído em [!DNL Experience Cloud] ou [!DNL Adobe Experience Platform].
* Se você tentar combinar vários públicos com um público-alvo excluído, ou se tentar salvar uma atividade que faça referência a um público-alvo excluído, será exibida uma mensagem de aviso.

Você também pode direcionar parâmetros de perfis personalizados e parâmetros de `user.`. Ao criar um público-alvo, arraste os atributos que deseja usar para direcionar sua atividade para a janela do construtor de público-alvo. Se o atributo desejado não for exibido, ele não foi acionado por uma mbox. Outros parâmetros de mbox personalizados estão disponíveis na lista suspensa [!UICONTROL Parâmetros personalizados].

Use o botão [!UICONTROL Filters] para filtrar a lista [!UICONTROL Audiences] por origem: [!DNL Adobe Target], [!DNL Adobe Target Classic], [!DNL Experience Cloud] e [!DNL Adobe Experience Platform].

![Opção Filtros na   lista de públicos-alvo](assets/filters.png)

Use a caixa [!UICONTROL Pesquisar públicos] para pesquisar sua lista de [!UICONTROL Públicos-alvo]. Você pode procurar qualquer parte de um nome de público-alvo ou pode colocar uma determinada sequência de caracteres entre aspas.

Você pode classificar a lista de [!UICONTROL Públicos-alvo] por nome de público-alvo ou pela data da última modificação. Para classificar por nome ou data, clique no cabeçalho da coluna e selecione para exibir os públicos-alvo em ordem crescente ou decrescente.

## Exibir definições de público-alvo {#section_11B9C4A777E14D36BA1E925021945780}

Você pode visualizar os detalhes da definição do público-alvo em um cartão pop-up na interface do usuário [!DNL Target] sem precisar abrir o público-alvo. Essa funcionalidade se aplica a públicos-alvo criados em [!DNL Target Standard/Premium] e a públicos-alvo importados de [!DNL Target Classic] ou criados por meio da API.

Por exemplo, o seguinte cartão de definição de público-alvo é acessado clicando-se no ícone [!UICONTROL Exibir detalhes] para o público-alvo desejado:

![Atividades > Definição de público](assets/audience_definition_list.png)

O seguinte cartão de definição de público-alvo é acessado clicando-se no ícone [!UICONTROL Exibir detalhes] na página [!UICONTROL Visão geral] de uma atividade:

![Atividades > Definição de público](assets/view-details-activity-overview.png)

O cartão de definição de público-alvo mostra o tipo, a fonte e os atributos do público-alvo. Clique em **[!UICONTROL Exibir detalhes completos]** para ver outras atividades que fazem referência a esse público-alvo, se aplicável. Se você estiver visualizando um cartão de definição de público-alvo a partir de uma página [!UICONTROL Visão geral] de uma atividade, clique em **[!UICONTROL Uso de público-alvo]**.

As informações de uso do público-alvo podem ajudá-lo a evitar um impacto acidental em outras atividades ao editar os públicos-alvo. As informações incluem [!UICONTROL Atividades ao vivo], [!UICONTROL Atividades inativas], [!UICONTROL Atividades arquivadas] e [!UICONTROL Atividades de sincronização]. Esse recurso está disponível para todos os públicos-alvo (público-alvo de biblioteca e  [públicos-alvo somente de atividades](/help/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)).

Se um público-alvo for [combinado com outro público-alvo](/help/c-target/combining-multiple-audiences.md) e o público-alvo combinado for usado para criar uma atividade, as informações de uso para ambos os públicos-alvo listarão essa atividade recém-criada.

![](assets/audience_definition_list_usage.png)

<!--The following audience definition card is for an audience imported from the Adobe Experience Cloud. In this instance, the audience was imported from Adobe Audience Manager (AAM).

![Usage tab on Audience Definition card](assets/audience_definition_mc.png)

The following details are available for these imported audience types:

| Audience Type | Details |
|--- |--- |
|Mobile audience|Marketing Name, Vendor, and Model.<br>The `matches | does not match` operator displays instead of `equals | does not equal`<br>![Imported Mobile Audience](/help/c-target/c-audiences/assets/imported_mobile_audience.png).|
|Visitor-behavior audience|**user.categoryAffinity:** `categoryAffinity` with `FAVORITE` parameter.<br>![Imported Category Affinity](/help/c-target/c-audiences/assets/imported_category_affinity.png)<br>**Monitoring:** Monitoring service equals true.<br>**No Monitoring Service:** Monitoring service equals false.<br>![Imported Monitoring](/help/c-target/c-audiences/assets/imported_monitoring.png)|
|Audiences using the NOT operator|**Single Rule:** Target displays the audience in the format `[All Visitor AND [NOT [rule]`. Single NOT rule displays with AND with `AllVisitor` audience.<br>![Imported Not Audience](/help/c-target/c-audiences/assets/imported_not_audience.png)|

Keep the following points in mind as you work with imported audiences:

* Expression target audiences are no longer supported in Target Standard/Premium. 
* Target Standard/Premium does not support some deprecated audiences or has improved operators for ease of use. Because of this, the definition of an imported audience, although working as per definition, does not mean that same is now available for creation in the Standard/Premium interface. For example, Social Audiences are visible with their rules but Target Standard/Premium does not allow social audiences to be created.-->

## Vídeo de treinamento: Uso de públicos-alvo ![Selo tutorial](/help/assets/tutorial.png)

Este vídeo inclui informações sobre o uso de públicos-alvo.

* Explique o termo &quot;público-alvo&quot;
* Explicar as duas maneiras como o público-alvo é usado para otimização
* Encontre públicos-alvo na lista de públicos-alvo
* Segmente uma atividade para um público-alvo
* Use públicos-alvo para relatórios passivos em uma atividade

>[!VIDEO](https://video.tv.adobe.com/v/17398)
