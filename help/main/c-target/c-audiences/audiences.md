---
keywords: público-alvo, regras de público-alvo, criar público-alvo, criação de público-alvo, direcionamento de público-alvo, geração de relatório de público-alvo, relatar público-alvo, segmento, parâmetros de perfil personalizado, definição de público-alvo, lista de público-alvo
description: Saiba como usar públicos-alvo no [!DNL Adobe Target].
title: Como uso a lista de públicos-alvo?
feature: Audiences
exl-id: 7af7f101-f550-4fdc-bcd9-90e4107b0415
source-git-commit: 342d26bdda5740d23682768b15a788921a0a3001
workflow-type: tm+mt
source-wordcount: '1500'
ht-degree: 24%

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

![](assets/audience_definition_list_usage.png)

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

O uso de públicos-alvo criados na [!DNL Adobe Experience Platform] fornece dados do cliente mais avançados, o que resulta em uma personalização mais impactante. O [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=pt-BR){target=_blank} (RTCDP), criado em [!DNL Adobe Experience Platform], ajuda as empresas a unir dados conhecidos e anônimos de várias fontes corporativas. Esse processo permite criar perfis de clientes que podem ser usados para fornecer experiências personalizadas de clientes em todos os canais e dispositivos em tempo real.
+
Conectando o [!DNL Target] à [!DNL Real-time Customer Data Platform], os clientes podem enriquecer a personalização da web desbloqueando novos segmentos que antes podiam estar indisponíveis no [!DNL Target] e permitir a personalização em tempo real e em milissegundos na primeira página visitada pelo cliente na web. Uso de públicos-alvo e atributos de perfil criados no [!DNL Adobe Experience Platform] permite expandir os pontos de dados disponíveis para personalização mais avançada.

Essa integração desbloqueia casos de uso principais com a CDP em tempo real:

* Personalização de mesma página/próxima ocorrência
* Personalização pela primeira vez / usuários desconhecidos

Os principais recursos incluem:

* Integração direta do Target com a CDP/ em tempo real[!DNL Adobe Experience Platform] no Edge (removendo dependência em [!DNL Audience Core services] - AAM)
* [!UICONTROL Cartão de Destinos da borda do Target] com a governação e a aplicação das políticas
* Segmentos da CDP em tempo real e atributos de perfil compartilhados

Limitações de recursos e considerações dos atributos de perfil da CDP em tempo real:

* Os atributos em uma determinada oferta devem ser da mesma sandbox da AEP. (Em outras palavras, uma oferta não pode conter atributos de sandboxes da AEP diferentes.)
* Os atributos de uma determinada oferta podem vir de fontes diferentes; ou seja, o perfil do Target e o perfil do AEP.(Em outras palavras, é possível combinar atributos provenientes do Target ou do perfil da AEP.)
* Ao definir uma oferta, você pode atribuir valores padrão para Atributos de perfil da CDP em tempo real, caso o atributo não tenha um valor explícito. Por exemplo, se uma política de consentimento ou de governança bloquear o atributo que está sendo usado no serviço de personalização, o valor padrão poderá ser usado.
* Quando compartilhados, os Atributos de perfil da CDP em tempo real são usados nos modelos de personalização de Inteligência artificial/Aprendizagem de máquina para Direcionamento automático e Automated Personalization.

>[!NOTE]
>
>O recurso Atributos de perfil da CDP em tempo real está disponível em Beta para ofertas do HTML e [Ofertas JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md).


Para obter mais informações, consulte os seguintes tópicos:

* [Notas de versão de destinos](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=en#destinations){target=_blank} na *Notas de versão do Adobe Experience Platform*
* [Configurar destinos de personalização para a personalização da mesma página e da próxima página](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html){target=_blank} na *Visão geral dos destinos* guia.
* [Conexão de personalização personalizada](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/custom-personalization.html){target=_blank} na *Visão geral dos destinos* guia
* [Conexão Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html){target=_blank} na *Visão geral dos destinos* guia
* [Configurar destinos de personalização para a mesma página e casos de uso de personalização da próxima página](https://www.adobe.com/go/destinations-edge-personalization-en){target=_blank} na *Visão geral dos destinos* guia

### Informações adicionais

Considere as seguintes informações ao usar públicos-alvo de [!DNL Adobe Experience Platform]:

#### Casos de uso de personalização

A tabela a seguir mostra qual tipo de caso de uso de personalização (próxima sessão ou mesma página) está disponível ao usar o [!DNL Adobe Experience Platform Web SDK] versus usar at.js:

| Implementação | Soluções/Caso de uso habilitado |
| --- | --- |
| at.js | **As soluções**:<ul><li>[!DNL Adobe Audience Manager] (AAM) e [!DNL Target]</li><li>[!DNL RTCDP] (Premium ou Ultimate) e [!DNL Target]</li><li>[!DNL RTCDP] (qualquer SKU), [!DNL AAM]e [!DNL Target]</li></ul>**Caso de uso**:<ul><li>Personalização da próxima sessão</li></ul> |
| [!DNL Platform Web SDK] ou [!DNL AEP Server-Side API] | **As soluções**:<ul><li>[!DNL RTCDP] (qualquer SKU) e [!DNL Target]</li></ul>**Caso de uso**:<ul><li>Personalização da próxima sessão</li><li>Personalização de mesma página via Edge</li><li>Governança aplicada ao compartilhar segmentos</li></ul>**As soluções**:<ul><li>[!DNL RTCDP] (qualquer SKU), [!DNL AAM]e [!DNL Target]</li></ul>**Caso de uso**:<ul><li>Personalização da próxima sessão</li><ul><li>[!DNL AAM] segmentos</li><li>Segmentos de terceiros via [!DNL AAM]</li></ul><li>Personalização de mesma página via Edge</li><ul><li>[!DNL RTCDP] segmentos</li><li>Governança aplicada ao compartilhar segmentos</li></ul> |
| Mistura de [!UICONTROL at.js] e [!DNL Platform Web SDK] | **As soluções**:<ul><li>[!DNL RTCDP] (qualquer SKU) e [!DNL Target]</li></ul>**Caso de uso**:<ul><li>Personalização da próxima sessão</li><ul><li>Para todas as páginas com [!UICONTROL at.js]</li></ul><li>Personalização de mesma página</li><ul><li>Para todas as páginas com [!DNL Platform Web SDK]</li></ul></ul>**As soluções**:<ul><li>[!DNL RTCDP] (qualquer SKU), [!DNL AAM]e [!DNL Target]</li></ul>**Caso de uso**:<ul><li>Personalização da próxima sessão</li><ul><li>Para todas as páginas com [!UICONTROL at.js]</li><li>[!DNL AAM] segmentos</li><li>Segmentos de terceiros via [!DNL AAM]</li></ul> |

#### Tempo de avaliação do segmento

A tabela a seguir mostra o tempo de avaliação de segmento para eventos provenientes de diferentes cenários de implementação:

| Cenário | Segmento de borda (avaliação de milissegundos) | Segmento de transmissão (avaliação por minuto) | Avaliação de segmento em lote |
| --- | --- | --- | --- |
| Eventos/dados de [!DNL Adobe Experience Platform] SDKs | Sim | Sim | N/A |
| Eventos de [!UICONTROL at.js] | Não | Sim | N/D |
| Eventos de [!DNL Target Mobile] SDKs | Não | Sim | N/D |
| Eventos do upload em lote | Não | Não | Sim |
| Eventos de dados offline (fluxo) | Não | Sim | Sim |

### Vídeo: Personalização de próxima ocorrência com a CDP em tempo real e [!DNL Adobe Target]{#RTCDP}

Saiba como personalizar na próxima ocorrência com [!DNL Real-time Customer Data Platform] e [!DNL Adobe Target]. O [!DNL Adobe Target] destino em [!DNL Real-time CDP] permite usar [!DNL Experience Platform] segmentos em [!DNL Adobe Target] para a mesma página e a personalização da próxima página com suporte a governança e privacidade.

Para obter mais informações, consulte [Personalização de próxima ocorrência com a CDP em tempo real e a Adobe Target](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html){target=_blank} na *Tutorials da plataforma* guia.

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

### Blog e vídeo do Adobe Target:

[[!DNL Adobe] announces Same Page Enhanced Personalization with [!DNL Adobe Target] e [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}

## Vídeo de treinamento: Uso de públicos-alvo ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo inclui informações sobre o uso de públicos-alvo.

* Explique o termo &quot;público-alvo&quot;
* Explicar as duas maneiras como o público-alvo é usado para otimização
* Encontre públicos-alvo na lista de públicos-alvo
* Segmente uma atividade para um público-alvo
* Use públicos-alvo para relatórios passivos em uma atividade

>[!VIDEO](https://video.tv.adobe.com/v/17398)
