---
keywords: público-alvo, regras de público-alvo, criar público-alvo, criação de público-alvo, direcionamento de público-alvo, geração de relatório de público-alvo, relatar público-alvo, segmento, parâmetros de perfil personalizado, definição de público-alvo, lista de público-alvo
description: Saiba como usar a lista [!UICONTROL Audiences] no Adobe [!DNL Target] e como visualizar cartões de Definição de público-alvo que contêm detalhes de público-alvo e informações de uso.
title: Como uso a lista de públicos-alvo?
feature: Públicos-alvo
exl-id: 7af7f101-f550-4fdc-bcd9-90e4107b0415
source-git-commit: 06a5fda72a649c4037cb78d3e670747cd297a64d
workflow-type: tm+mt
source-wordcount: '940'
ht-degree: 60%

---

# Criar públicos-alvo

Os públicos-alvo em [!DNL Adobe Target] determinam quem vê o conteúdo e as experiências em uma atividade direcionada.

Os público-alvo são usados sempre que o direcionamento estiver disponível. Ao direcionar uma atividade, você pode ter as seguintes opções:

* Selecione um público-alvo reutilizável na lista [!UICONTROL Públicos-alvo]
* [Criar um ](/help/c-target/creating-activity-only-audience.md) público-alvo específico da atividade e direcioná-lo
* [Combinar vários ](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) públicos para criar um público-alvo ad hoc

Você também pode usar os dados do público-alvo coletados por [!DNL Adobe Analytics] para o direcionamento e personalização em tempo real em [!DNL Target] e outros aplicativos [!DNL Adobe Experience Cloud]. Consulte [Experience Cloud Audiences](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=pt-BR) no guia *Experience Cloud Central Interface Components*.

O [!DNL Target] define dois tipos de público-alvo:

* **Direcionamento de públicos-alvo:** usado para oferecer conteúdo diferente para diferentes tipos de visitantes.
* **Relatório de públicos-alvo:** usado para determinar como diferentes tipos de visitantes respondem ao mesmo conteúdo para que você possa analisar os resultados de seus testes.

   No [!DNL Target], é possível configurar relatórios de públicos-alvo apenas se você usar o [!DNL Target] como fonte de geração de relatórios. Se você usa o [ Adobe Analytics como fonte de relatórios](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T), precisa configurar os públicos dos relatórios no [!DNL Analytics].

## Use a lista [!UICONTROL Públicos-alvo]

Para acessar a lista [!UICONTROL Públicos-alvo], clique em **[!UICONTROL Públicos-alvo]** na barra do menu superior:

![Lista de públicos](/help/c-target/c-audiences/assets/audiences_list.png)

A lista de [!UICONTROL Públicos-alvo] contém todos os públicos-alvo que você pode usar em suas atividades. Use a lista de [!UICONTROL Públicos-alvo] para criar, editar, excluir ou copiar os públicos. A lista também mostra a fonte onde o público-alvo foi criado ([!DNL Target], [!DNL Target Classic] e [!DNL Experience Cloud]. Públicos predefinidos, como &quot;[!UICONTROL Novos visitantes]&quot; e &quot;[!UICONTROL Visitantes que retornam]&quot;, não podem ser renomeados.

Ao trabalhar com públicos-alvo que foram originalmente criados em [!DNL Experience Cloud], o Target o alerta se você fizer referência a um público-alvo em [!DNL Target] atividades que foram posteriormente excluídas em [!DNL Experience Cloud].

* Se um público-alvo foi excluído em [!DNL Experience Cloud], é exibido um ícone de aviso na lista [!UICONTROL Público-alvo] e no seletor de público-alvo. Uma dica de ferramenta na interface do usuário também indica que o público-alvo foi excluído do [!DNL Experience Cloud].
* Se você tentar combinar vários públicos com um público-alvo excluído, ou se tentar salvar uma atividade que faça referência a um público-alvo excluído, será exibida uma mensagem de aviso.

Você também pode direcionar parâmetros de perfis personalizados e parâmetros de `user.`. Ao adicionar um público-alvo, clique no atributo que deseja usar para direcionar sua atividade. Se o atributo desejado não for exibido, ele não foi acionado por uma mbox. Outros parâmetros de mbox personalizados estão disponíveis na lista suspensa [!UICONTROL Parâmetros personalizados].

Use o botão [!UICONTROL Filters] para filtrar a lista [!UICONTROL Audiences] por origem: [!DNL Adobe Target], [!DNL Adobe Target Classic] e [!DNL Experience Cloud].

![Opção Filtros na   lista de públicos-alvo](/help/c-target/c-audiences/assets/filters.png)

Use a caixa [!UICONTROL Pesquisar públicos] para pesquisar sua lista de [!UICONTROL Públicos-alvo]. Você pode procurar qualquer parte de um nome de público-alvo ou pode colocar uma determinada sequência de caracteres entre aspas.

Você pode classificar a lista de [!UICONTROL Públicos-alvo] por nome de público-alvo ou pela data da última modificação. Para classificar por nome ou data, clique no cabeçalho da coluna e selecione para exibir os públicos-alvo em ordem crescente ou decrescente.

## Exibir definições de público-alvo {#section_11B9C4A777E14D36BA1E925021945780}

É possível ver os detalhes da definição de público-alvo em um cartão pop-up na interface do usuário do Target, sem precisar abrir o público-alvo. Essa funcionalidade se aplica a públicos-alvo criados em [!DNL Target Standard/Premium] e a públicos-alvo importados de [!DNL Target Classic] ou criados por meio da API.

Por exemplo, o seguinte cartão de definição de público-alvo é acessado clicando-se no ícone [!UICONTROL Exibir detalhes] para o público-alvo desejado:

![Atividades > Definição de público](assets/audience_definition_list.png)

O seguinte cartão de definição de público-alvo é acessado clicando-se no ícone [!UICONTROL Exibir detalhes] na página [!UICONTROL Visão geral] de uma atividade:

![Atividades > Definição de público](/help/c-target/c-audiences/assets/view-details-activity-overview.png)

O cartão de definição de público-alvo mostra o tipo, a fonte e os atributos do público-alvo. Clique em **[!UICONTROL Exibir detalhes completos]** para ver outras atividades que fazem referência a esse público-alvo, se aplicável. Se você estiver visualizando um cartão de definição de público-alvo a partir de uma página [!UICONTROL Visão geral] de uma atividade, clique em **[!UICONTROL Uso de público-alvo]**.

As informações de uso do público-alvo podem ajudá-lo a evitar um impacto acidental em outras atividades ao editar os públicos-alvo. As informações incluem atividades ao vivo, atividades inativas, atividades arquivadas e atividades de sincronização. Esse recurso está disponível para todos os públicos-alvo (público-alvo de biblioteca e  [públicos-alvo somente de atividades](/help/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)).

Se um público-alvo é combinado com outro público-alvo e o público-alvo combinado é usado para criar uma atividade, as informações de uso para ambos os públicos-alvo listam essa atividade recém-criada.

![](assets/audience_definition_list_usage.png)

O seguinte cartão de definição de público-alvo é para um público-alvo importado da Adobe Experience Cloud. Neste caso, o público-alvo foi importado do Adobe Audience Manager (AAM).

![Guia Uso no cartão Definição de público-alvo](assets/audience_definition_mc.png)

Os detalhes a seguir estão disponíveis para esses tipos de público-alvo importados:

| Tipo de público-alvo | Detalhes |
|--- |--- |
| Público-alvo de dispositivos móveis | Nome de comercialização, fornecedor e modelo.<br>O operador `matches | does not match` é exibido em vez do `equals | does not equal`<br>![Público de dispositivos móveis importado](/help/c-target/c-audiences/assets/imported_mobile_audience.png). |
| Público-alvo com comportamento de visitante | **user.categoryAffinity:** `categoryAffinity` com o parâmetro `FAVORITE`.<br>![Afinidade da categoria importada ](/help/c-target/c-audiences/assets/imported_category_affinity.png)<br>**Monitoramento:** serviço de monitoramento é igual a verdadeiro.<br>**Sem serviço de monitoramento:** serviço de monitoramento igual a falso.<br>![Monitoramento importado](/help/c-target/c-audiences/assets/imported_monitoring.png) |
| Públicos-alvo que usam o operador NOT | **Regra única**: o Target exibe o público-alvo no formato `[All Visitor AND [NOT [rule]`. A regra única NÃO é exibida com E com o público-alvo de `AllVisitor`.<br>![Público não importado](/help/c-target/c-audiences/assets/imported_not_audience.png) |

Tenha os seguintes pontos em mente ao trabalhar com públicos-alvo importados:

* Os públicos-alvo de direcionamento de expressão não são mais suportados no Target Standard/Premium.
* O Target Standard/Premium não suporta alguns públicos-alvo obsoletos ou melhorou os operadores para facilidade de uso. Por causa disso, a definição de um público-alvo importado, apesar de funcionar de acordo com a definição, não significa que o mesmo esteja agora disponível para criação na interface Standard/Premium. Por exemplo, os públicos-alvo sociais são visíveis com suas regras, mas o Target Standard/Premium não permite que públicos-alvo sociais sejam criados.

## Vídeo de treinamento: Uso de públicos-alvo ![Selo do tutorial](/help/assets/tutorial.png)

Este vídeo inclui informações sobre o uso de públicos-alvo.

* Explique o termo &quot;público-alvo&quot;
* Explicar as duas maneiras como o público-alvo é usado para otimização
* Encontre públicos-alvo na lista de públicos-alvo
* Segmente uma atividade para um público-alvo
* Use públicos-alvo para relatórios passivos em uma atividade

>[!VIDEO](https://video.tv.adobe.com/v/17398)
