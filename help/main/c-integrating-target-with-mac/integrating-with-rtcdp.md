---
keywords: Real-time Customer Data Platform;rtcdp;personalização;públicos aep;públicos adobe experience platform
description: Saiba como usar a integração  [!DNL Target]/[!DNL Real-time Customer Data Platform]  (RTCDP) para fornecer dados mais avançados do cliente e personalização mais impactante.
title: Como integrar o  [!DNL Target]  com a  [!DNL Real-time Customer Data Platform]?
feature: Integrations
exl-id: 1c066b62-91a2-4b8c-807a-3cc56fca7778
source-git-commit: e776f4f3871350c00ac5e00ae7a915a0396d979e
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 20%

---

# Integração com a Real-time Customer Data Platform

Criada na [!DNL Adobe Experience Platform], a [!DNL Real-time Customer Data Platform] (RTCDP) ajuda empresas a reunir dados conhecidos e anônimos de várias fontes corporativas para criar perfis de clientes que podem ser usados para fornecer experiências personalizadas em todos os canais e dispositivos em tempo real.

Para obter mais informações sobre RTCDP, consulte [Visão geral do Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=pt-BR){target=_blank}.

## Usar públicos-alvo de [!DNL Adobe Experience Platform] {#aep}

Usando [públicos](/help/main/c-target/c-audiences/audiences.md) criado em [!DNL Adobe Experience Platform] forneça dados mais avançados do cliente, o que resulta em personalização mais impactante. O [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=pt-BR){target=_blank} (RTCDP), criado em [!DNL Adobe Experience Platform], ajuda as empresas a unir dados conhecidos e anônimos de várias fontes corporativas. Esse processo permite criar perfis de clientes que podem ser usados para fornecer experiências personalizadas de clientes em todos os canais e dispositivos em tempo real.

Conectando o [!DNL Target] à [!DNL Real-time Customer Data Platform], os clientes podem enriquecer a personalização da web desbloqueando novos segmentos que antes podiam estar indisponíveis no [!DNL Target] e permitir a personalização em tempo real e em milissegundos na primeira página visitada pelo cliente na web. Uso de públicos-alvo e atributos de perfil criados no [!DNL Adobe Experience Platform] permite expandir os pontos de dados disponíveis para personalização mais avançada.

Essa integração desbloqueia casos de uso principais com a CDP em tempo real:

* Personalização de mesma página/próxima ocorrência
* Personalização pela primeira vez / usuários desconhecidos

Os principais recursos incluem:

* Direta [!DNL Target] integração com a CDP/ em tempo real[!DNL Adobe Experience Platform] no Edge (removendo dependência em [!DNL Audience Core services] - AAM)
* [!UICONTROL Cartão de Destinos da borda do Target] com a governação e a aplicação das políticas
* Segmentos da CDP em tempo real e atributos de perfil compartilhados

Limitações de recursos e considerações dos atributos de perfil da CDP em tempo real:

* Os atributos em uma determinada oferta devem ser da mesma sandbox da AEP. (Em outras palavras, uma oferta não pode conter atributos de sandboxes da AEP diferentes.)
* Os atributos em uma determinada oferta podem vir de fontes diferentes; a saber, o [!DNL Target] e o perfil do AEP. (Em outras palavras, é possível combinar atributos de origem [!DNL Target] ou do perfil do AEP.)
* Ao definir uma oferta, você pode atribuir valores padrão para Atributos de perfil da CDP em tempo real, caso o atributo não tenha um valor explícito. Por exemplo, se uma política de consentimento ou de governança bloquear o atributo que está sendo usado no serviço de personalização, o valor padrão poderá ser usado.
* Quando compartilhados, os Atributos de perfil da CDP em tempo real são usados nos modelos de personalização de Inteligência artificial/Aprendizagem de máquina para [!UICONTROL Direcionamento automático] e [!UICONTROL Automated Personalization] atividades.

>[!NOTE]
>
>O recurso Atributos de perfil da CDP em tempo real está disponível em Beta para ofertas do HTML e [Ofertas JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md).

Para obter mais informações, consulte os seguintes tópicos:

* [Notas de versão de destinos](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=en#destinations){target=_blank} no *Notas de versão do Adobe Experience Platform*
* [Configurar destinos de personalização para a personalização da mesma página e da próxima página](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html){target=_blank} no *Visão geral dos destinos* guia.
* [Conexão de personalização personalizada](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/custom-personalization.html){target=_blank} no *Visão geral dos destinos* guia
* [Conexão Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html){target=_blank} no *Visão geral dos destinos* guia
* [Configurar destinos de personalização para a mesma página e casos de uso de personalização da próxima página](https://www.adobe.com/go/destinations-edge-personalization-en){target=_blank} no *Visão geral dos destinos* guia

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
| Eventos de [!UICONTROL at.js] | Não | Sim | N/A |
| Eventos de [!DNL Target Mobile] SDKs | Não | Sim | N/A |
| Eventos do upload em lote | Não | Não | Sim |
| Eventos de dados offline (fluxo) | Não | Sim | Sim |

### Vídeo: Personalização de próxima ocorrência com a CDP em tempo real e [!DNL Adobe Target]{#RTCDP}

Saiba como personalizar na próxima ocorrência com [!DNL Real-time Customer Data Platform] e [!DNL Adobe Target]. O [!DNL Adobe Target] destino em [!DNL Real-time CDP] permite usar [!DNL Experience Platform] segmentos em [!DNL Adobe Target] para a mesma personalização de página e personalização de próxima página com suporte de governança e privacidade.

Para obter mais informações, consulte [Personalização de próxima ocorrência com a CDP em tempo real e a Adobe Target](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html){target=_blank} no *Tutorials da plataforma* guia.

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

### Blog e vídeo do Adobe Target:

[[!DNL Adobe] announces Same Page Enhanced Personalization with [!DNL Adobe Target] e [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}

## Compartilhar atributos de perfil da CDP em tempo real com [!DNL Target] {#rtcdp-profile-attributes}

Os atributos de perfil da CDP em tempo real podem ser compartilhados com [!DNL Target] para uso em ofertas HTML e [Ofertas JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md). (Observe que esse recurso está atualmente na versão beta.)

Caso de uso de exemplo: Como comerciante online, você deseja que o Perfil AEP/Unified compartilhe valores de atributo com a [!DNL Target] para fornecer personalização em tempo real. Ao usar Atributos de perfil da CDP em tempo real, é possível exibir o valor do atributo da AEP em um [!DNL Target] oferta usando substituição de token. Por exemplo, você pode personalizar de acordo com a cor favorita de um cliente usando `${aep.profile.favoriteColor}`ou seu nível de fidelidade e valor do ponto de fidelidade usando os tokens `${aep.loyalty.tier}` e `${aep.loyalty.points}`.

![offer-json-aep-shared-attribute image](/help/main/c-experiences/c-manage-content/assets/offer-json-aep-shared-attribute.png)

Observe que a atribuição de valores padrão é opcional.
