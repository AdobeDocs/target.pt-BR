---
keywords: Real-time Customer Data Platform;rtcdp;personalização;públicos da aep;públicos da adobe experience platform;atributos de perfil
description: Saiba como usar a integração  [!DNL Target]/[!DNL Real-Time Customer Data Platform]  (RTCDP) para fornecer dados mais avançados do cliente e personalização mais impactante.
title: Como integrar o  [!DNL Target]  com a  [!DNL Real-Time Customer Data Platform]?
feature: Integrations
exl-id: 1c066b62-91a2-4b8c-807a-3cc56fca7778
source-git-commit: 08422323607f7238a7cf9bac5b863032ce734662
workflow-type: ht
source-wordcount: '936'
ht-degree: 100%

---

# Integrar com a [!DNL Real-Time Customer Data Platform]

Integrada na [!DNL Adobe Experience Platform], a [!DNL Real-Time Customer Data Platform] (RTCDP) ajuda as empresas a unir dados conhecidos e anônimos de várias fontes corporativas. A RTCDP permite criar perfis de clientes que podem ser usados para fornecer experiências personalizadas em todos os canais e dispositivos em tempo real.

Para obter mais informações sobre a RTCDP, consulte a [Visão geral da Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=pt-BR){target=_blank}.

## Principais recursos

Os principais recursos incluem:

* Integração direta do [!DNL Target] com a Real-Time CDP/[!DNL Adobe Experience Platform] na borda (removendo a dependência do [!DNL Audience Core services] - AAM)
* [!UICONTROL Cartão de destinos da borda do Target] com governança e aplicação de políticas
* Segmentos da Real-time CDP e atributos de perfil compartilhados

## Cenários de implementação

As seções a seguir mostram que tipo de caso de uso de personalização (próxima sessão ou mesma página) está disponível ao usar métodos de implementação diferentes:

### Implementação da at.js

| Soluções | Caso de uso habilitado |
| --- | --- |
| <ul><li>[!DNL Adobe Audience Manager] (AAM) e [!DNL Target]</li><li>[!DNL RTCDP] (Premium ou Ultimate) e [!DNL Target]</li><li>[!DNL RTCDP] (qualquer SKU), [!DNL AAM] e [!DNL Target]</li></ul> | Personalização da próxima sessão |

### Implementação do [!DNL Adobe Experience Platform Web SDK] ou da [!DNL Experience Platform Server-Side API]

| Soluções | Caso de uso habilitado |
| --- | --- |
| <ul><li>[!DNL RTCDP] (qualquer SKU) e [!DNL Target]</li></ul> | <ul><li>Personalização da próxima sessão</li><li>Personalização da mesma página pela borda</li><li>Governança aplicada ao compartilhar segmentos</li></ul> |
| <ul><li>[!DNL RTCDP] (qualquer SKU), [!DNL AAM] e [!DNL Target]</li></ul> | <ul><li>Personalização da próxima sessão</li><ul><li>Segmentos do [!DNL AAM]</li><li>Segmentos de terceiros por meio do [!DNL AAM]</li></ul><li>Personalização da mesma página pela borda</li><ul><li>Segmentos da [!DNL RTCDP]</li><li>Governança aplicada ao compartilhar segmentos</li></ul> |

### Combinação de implementação da [!UICONTROL at.js] e do [!DNL Platform Web SDK]

| Soluções | Caso de uso habilitado |
| --- | --- |
| <ul><li>[!DNL RTCDP] (qualquer SKU) e [!DNL Target]</li></ul> | <ul><li>Personalização da próxima sessão</li><ul><li>Para todas as páginas com [!UICONTROL at.js]</li></ul><li>Personalização da mesma página</li><ul><li>Para todas as páginas com o [!DNL Platform Web SDK]</li></ul> |
| <ul><li>[!DNL RTCDP] (qualquer SKU), [!DNL AAM] e [!DNL Target]</li></ul> | <ul><li>Personalização da próxima sessão</li><ul><li>Para todas as páginas com [!UICONTROL at.js]</li><li>Segmentos do [!DNL AAM]</li><li>Segmentos de terceiros por meio do [!DNL AAM]</li></ul> |

## Tempo de avaliação do segmento

A tabela a seguir mostra o tempo de avaliação do segmento para eventos provenientes de diferentes cenários de implementação:

| Cenário | Segmento de borda (avaliação por milissegundos) | Segmento de transmissão (avaliação por minuto) | Avaliação de segmento em lote |
| --- | --- | --- | --- |
| Eventos/dados de SDKs da [!DNL Adobe Experience Platform] | Sim | Sim | N/A |
| Eventos da [!UICONTROL at.js] | Não | Sim | N/A |
| Eventos de SDKs do [!DNL Target Mobile] | Não | Sim | N/A |
| Eventos de upload em lote | Não | Não | Sim |
| Eventos de dados offline (fluxo) | Não | Sim | Sim |

## Usar públicos da [!DNL Adobe Experience Platform] {#aep}

O uso de [públicos](/help/main/c-target/c-audiences/audiences.md) criados na [!DNL Adobe Experience Platform] fornece dados mais avançados do cliente, o que resulta em personalizações mais impactantes. A [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=pt-BR){target=_blank} (RTCDP), integrada na [!DNL Adobe Experience Platform], ajuda as empresas a unir dados conhecidos e anônimos de várias fontes corporativas. Esse processo permite criar perfis de clientes que podem ser usados para fornecer experiências personalizadas aos clientes em todos os canais e dispositivos em tempo real.

Ao conectar o [!DNL Target] à [!DNL Real-Time Customer Data Platform], os clientes podem enriquecer sua personalização da Web. Essa integração permite que você desbloqueie novos segmentos que antes eram inacessíveis ao [!DNL Target], a fim de permitir a personalização em tempo real em milissegundos na primeira página de uma visita à Web de um cliente. Usar públicos e atributos de perfil criados na [!DNL Adobe Experience Platform] permite expandir os pontos de dados disponíveis para uma personalização mais avançada.

Essa integração desbloqueia os principais casos de uso da Real-Time CDP:

* Personalização de mesma página/próxima ocorrência
* Personalização de usuários novos/desconhecidos

## Compartilhar atributos de perfil da Real-Time CDP com o [!DNL Target] {#rtcdp-profile-attributes}

Os atributos de perfil da Real-Time CDP podem ser compartilhados com o [!DNL Target] para uso em ofertas HTML e [JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md).

### Limitações de recursos e considerações dos atributos de perfil da Real-Time CDP

>[!NOTE]
>
>O recurso de Atributos de perfil da Real-Time CDP está disponível em beta para ofertas HTML e [JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md).

Considere o seguinte:

* Os atributos em uma determinada oferta devem ser da mesma sandbox da [!UICONTROL Experience Platform]. (Em outras palavras, uma oferta não pode conter atributos de diferentes sandboxes da [!UICONTROL Experience Platform].)
* Os atributos de uma determinada oferta podem vir de diferentes fontes; por exemplo, do perfil do [!DNL Target] e do perfil da [!UICONTROL Experience Platform]. (Em outras palavras, é possível combinar atributos, sejam eles do [!DNL Target] ou do perfil da [!UICONTROL Experience Platform].)
* Ao definir uma oferta, é possível atribuir valores padrão para os [!UICONTROL atributos de perfil da Real-Time CDP], caso o atributo não tenha um valor explícito. Por exemplo, se uma política de consentimento ou de governança bloquear o atributo que está sendo usado no serviço de personalização, o valor padrão poderá ser usado.

### Exemplo de caso de uso em JSON

Como profissional de marketing online, você deseja que o perfil unificado/AEP compartilhe valores de atributo com o [!DNL Target] para fornecer personalização em tempo real. Ao usar os [!UICONTROL atributos de perfil da Real-Time CDP], é possível exibir o valor do atributo da [!UICONTROL Experience Platform] em uma oferta do [!DNL Target] usando a substituição de token. Por exemplo, você pode personalizar de acordo com a cor favorita de um cliente usando `${aep.profile.favoriteColor}` ou de acordo com seu nível de fidelidade e valor do ponto de fidelidade usando os tokens `${aep.loyalty.tier}` e `${aep.loyalty.points}`.

Para criar uma oferta JSON para compartilhar atributos do perfil unificado/AEP com o [!DNL Target]:

1. Ao [criar uma oferta JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md), na lista **[!UICONTROL Selecionar uma origem]**, selecione **[!UICONTROL Adobe Experience Platform]**.
1. Na lista **[!UICONTROL Selecionar um nome de sandbox de perfil]**, selecione a sandbox desejada.
1. Na lista **[!UICONTROL Selecionar um atributo de perfil]**, selecione os atributos desejados.
1. (Opcional) Na lista **[!UICONTROL Inserir um valor padrão]**, selecione os valores desejados.
1. Clique em **[!UICONTROL Adicionar]**.

A ilustração a seguir mostra que dois atributos de perfil, `loyalty.tier` e `loyalty.points`, foram adicionados à oferta JSON.

![imagem offer-json-aep-shared-attribute](/help/main/c-experiences/c-manage-content/assets/offer-json-aep-shared-attribute.png)

## Links para mais informações

Para obter mais informações, consulte os seguintes tópicos:

* [Notas de versão de destinos](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=pt-BR#destinations){target=_blank} nas *notas de versão da Adobe Experience Platform*
* [Configurar destinos de personalização para a personalização da mesma página e da próxima página](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=pt-BR){target=_blank} no guia *Visão geral dos destinos*.
* [Conexão do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection.html?lang=pt-BR){target=_blank} no guia *Visão geral dos destinos*
* [Mapear atributos](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/activate-profile-request-destinations.html?lang=pt-BR#map-attributes){target=_blank} no guia *Visão geral dos destinos*.

## Vídeos e publicações do blog

Os vídeos e publicações do blog a seguir fornecem mais informações sobre a personalização aprimorada com o Target e a RTCDP:

### Vídeo: personalização de próxima ocorrência com a Real-Time CDP e o [!DNL Adobe Target]{#RTCDP}

Saiba como personalizar na próxima ocorrência com a [!DNL Real-Time Customer Data Platform] e o [!DNL Adobe Target]. O destino do [!DNL Adobe Target] na [!DNL Real-Time CDP] permite usar segmentos da [!DNL Experience Platform] no [!DNL Adobe Target] para a personalização de mesma página e personalização de próxima página com suporte de governança e privacidade.

Para obter mais informações, consulte [Personalização de próxima ocorrência com a Real-Time CDP e o Adobe Target](https://experienceleague.adobe.com/docs/platform-learn/tutorials/experience-cloud/next-hit-personalization.html?lang=pt-BR){target=_blank} no guia *Tutoriais da Platform*.

>[!VIDEO](https://video.tv.adobe.com/v/340091?quality=12&learn=on)

### Blog e vídeo do [!DNL Adobe Target]: personalização aprimorada de mesma página

[[!DNL Adobe] announces Same-Page Enhanced Personalization with [!DNL Adobe Target]  e  [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}
