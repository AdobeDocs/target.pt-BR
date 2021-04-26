---
keywords: implementação; biblioteca javascript; js; atjs; decisão no dispositivo; no device decisioning; at.js; no dispositivo; no dispositivo
description: Saiba como executar a decisão no dispositivo com a biblioteca at.js
title: Como o On-device Decisioning funciona com a biblioteca JavaScript da at.js?
feature: 'at.js '
role: Developer
exl-id: 5ad6032b-9865-4c80-8800-705673657286
translation-type: tm+mt
source-git-commit: 7b9870fc79a41e387f557dd36edf5a7af4b443c7
workflow-type: tm+mt
source-wordcount: '3747'
ht-degree: 6%

---

# Decisão no dispositivo para at.js

>[!NOTE]
>
>A decisão no dispositivo estará disponível com a próxima [versão da at.js 2.5.0](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md). Data a anunciar em breve.

A partir da versão 2.5.0, a at.js oferece decisão no dispositivo. A decisão no dispositivo permite armazenar em cache as atividades [A/B Test](/help/c-activities/t-test-ab/test-ab.md) e [Direcionamento de experiência](/help/c-activities/t-experience-target/experience-target.md) (XT) no navegador para executar a decisão na memória sem uma solicitação de rede de bloqueio para a [!DNL Adobe Target] Edge Network.

[!DNL Target] O também oferece a flexibilidade de fornecer a experiência mais relevante e atualizada de suas atividades de personalização orientadas por ML (experimentação e aprendizado de máquina) por meio de uma chamada de servidor ao vivo. Em outras palavras, quando o desempenho é mais importante, você pode optar por usar a decisão no dispositivo. No entanto, quando a experiência mais relevante, atualizada e orientada por ML for necessária, uma chamada de servidor poderá ser feita.

## Quais são os benefícios da tomada de decisões no dispositivo?

Os benefícios da decisão no dispositivo incluem:

* **Forneça decisões e experiências extremamente rápidas.** A compartimentalização e a decisão são executadas na memória e no navegador para evitar o bloqueio de solicitações de rede.
* **Melhore o desempenho do aplicativo.** Execute experimentos e forneça personalização para seus clientes e usuários sem comprometer as experiências dos usuários finais.
* **Melhore a Pontuação de Qualidade do Site do Google.** Com a decisão acontecendo na memória, melhore a pontuação de qualidade do site do Google em seus negócios online para torná-la mais detectável para os consumidores.
* **Saiba mais sobre análises em tempo real.** Obtenha insights do desempenho de sua atividade em tempo real por meio dos relatórios do  [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md)  (A4T). O A4T permite girar sua estratégia em momentos críticos.

## Recursos compatíveis 

O SDK JS da Adobe Target oferece aos clientes a flexibilidade para escolher entre desempenho e atualização de dados para decisões. Em outras palavras, se o fornecimento do conteúdo personalizado mais relevante e envolvente por meio do aprendizado de máquina for mais importante para você, uma chamada de servidor ao vivo deverá ser feita. Mas quando o desempenho é mais importante, uma decisão no dispositivo e na memória deve ser tomada. Para que a decisão no dispositivo funcione, consulte a lista de recursos compatíveis:

* Tipos de atividades 
* Direcionamento de público-alvo
* Método de alocação

Para obter mais informações, consulte [Recursos suportados para decisões no dispositivo](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/supported-features.md).

## Como a decisão no dispositivo funciona?

Ao implantar e inicializar a at.js com a decisão no dispositivo ativada, um [artefato de regra](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/rule-artifact.md) que inclui a decisão no dispositivo para atividades A/B e XT, públicos e ativos, é baixado do Akamai CDN mais próximo ao visitante e armazenado em cache localmente no navegador do visitante. Quando uma solicitação é feita da at.js para recuperar uma experiência, a decisão sobre qual experiência retornar é tomada na memória, com base nos metadados codificados no artefato de regra em cache.

## Método de decisão

Com a decisão no dispositivo, [!DNL Target] introduz uma nova configuração chamada [!UICONTROL Método de decisão]. A configuração [!UICONTROL Método de decisão] determina como a at.js fornece suas experiências. [!UICONTROL O ] Método de Decisão tem três valores:

* [!UICONTROL Somente no lado do servidor]
* [!UICONTROL Somente no dispositivo]
* [!UICONTROL Híbrido]

### Somente no lado do servidor

[!UICONTROL O lado do servidor ] somente é o método de decisão padrão definido imediatamente quando o at.js 2.5.0+ é implementado e implantado em suas propriedades da Web.

Usar [!UICONTROL somente do lado do servidor] como configuração padrão significa que todas as decisões são tomadas na rede de borda [!DNL Target], que envolve uma chamada de servidor de bloqueio. Essa abordagem pode introduzir latência incremental, mas também oferece benefícios significativos, como fornecer a você a capacidade de aplicar os recursos de aprendizado de máquina do Target que incluem as atividades de [Recommendations](/help/c-recommendations/recommendations.md), [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) e [Direcionamento automático](/help/c-activities/auto-target/auto-target-to-optimize.md).

Além disso, aprimorar suas experiências personalizadas usando o perfil de usuário do Target, que é persistente em sessões e canais, pode fornecer resultados avançados para sua empresa.

Por fim, [!UICONTROL somente no lado do servidor] permite usar a Adobe Experience Cloud e refinar públicos-alvo que podem ser direcionados por meio de segmentos do Audience Manager e Adobe Analytics.

O diagrama a seguir ilustra a interação entre o visitante, o navegador, a at.js 2.5.0+ e a rede Adobe Target Edge. Esse diagrama de fluxo captura novos visitantes e visitantes recorrentes.

![Diagrama de fluxo somente do lado do servidor](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/server-side-only.png)

A lista a seguir corresponde aos números no diagrama:

| Etapa | Descrição |
| --- | --- |
| 1 | O [!DNL Experience Cloud Visitor ID] é recuperado do [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en). |
| 2 | A biblioteca at.js é carregada de modo síncrono e oculta o corpo do documento.<br>   A biblioteca at.js também pode ser carregada de forma assíncrona com um trecho opcional de pré-ocultação implementado na página. |
| 3 | A biblioteca at.js oculta o corpo para evitar oscilações. |
| 4 | É feita uma solicitação de carregamento de página que inclui todos os parâmetros configurados, como (ECID, ID do cliente, Parâmetros personalizados, Perfil de usuário e assim por diante). |
| 5 | Os scripts de perfil executam e, em seguida, fazem o feed na Loja do perfil.<br>A Loja de perfis solicita públicos qualificados da Biblioteca de público-alvo (por exemplo, públicos-alvo compartilhados de  [!DNL Adobe Analytics],  [!DNL Adobe Audience Manager] e assim por diante).<br>Os atributos do cliente são enviados à Loja de perfis em um processo em lote. |
| 6 | A Loja de perfis é usada para qualificação de público-alvo e segmentação para filtrar atividades. |
| 7 | O conteúdo resultante é selecionado depois que a experiência é determinada a partir de atividades [!DNL Target] ativas. |
| 8 | A biblioteca at.js oculta os elementos correspondentes na página que estão associados à experiência que deve ser renderizada. |
| 9 | A biblioteca at.js exibe o corpo para que o restante da página possa ser carregado para que o visitante visualize. |
| 10 | A biblioteca at.js manipula o DOM para renderizar a experiência da Rede de borda do Target. |
| 11 | A experiência é renderizada para o visitante. |
| 12 | A página da Web inteira é carregada. |
| 13 | Os dados do [!DNL Analytics] são enviados ao servidores de Coleção de dados. |
| 14 | Os dados direcionados correspondem aos dados [!DNL Analytics] por meio da SDID e são processados no armazenamento de relatório [!DNL Analytics]. Em seguida, os dados do [!DNL Analytics] podem ser visualizados no [!DNL Analytics] e no [!DNL Target] pelos relatórios do [!UICONTROL Analytics for Target] (A4T). |

### Somente no dispositivo

[!UICONTROL O On-Device ] é apenas o método de decisão que deve ser definido no at.js 2.5.0+, quando a tomada de decisão no dispositivo deve ser usada somente em suas páginas da Web.

O On-device decisioning pode fornecer suas experiências e atividades de personalização a uma velocidade extremamente rápida, pois as decisões são tomadas a partir de um artefato de regras em cache que contém todas as suas atividades qualificadas para decisões no dispositivo.

Para saber mais sobre quais atividades se qualificam para a tomada de decisão no dispositivo, consulte [Recursos compatíveis na tomada de decisão no dispositivo](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/supported-features.md).

Esse método de decisão deve ser usado somente se o desempenho for altamente crítico em todas as páginas que exigem decisões de [!DNL Target]. Além disso, lembre-se de que, quando esse método de decisão for selecionado, suas atividades [!DNL Target] que não se qualificam para a tomada de decisão no dispositivo não serão entregues ou executadas. A biblioteca at.js 2.5.0+ está configurada para procurar somente o artefato de regras em cache para tomar decisões.

O diagrama a seguir ilustra a interação entre o visitante, o navegador, a at.js 2.5.0+ e a Akamai CDN. O Akamai CDN armazena em cache o artefato de regras para a primeira visita do visitante. Para a primeira visita à página de um novo visitante, o artefato de regras JSON deve ser baixado do Akamai CDN para ser armazenado em cache localmente no navegador do visitante. Após o download do artefato de regras JSON, a decisão é tomada imediatamente sem uma chamada de rede de bloqueio. O diagrama de fluxo a seguir captura novos visitantes.

![Diagrama de fluxo somente no dispositivo](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-only.png)

A lista a seguir corresponde aos números no diagrama:

>[!NOTE]
>
>[!DNL Adobe Target] Os servidores de administração qualificam todas as suas atividades qualificadas para decisões no dispositivo, geram o artefato de regras JSON e o propagam para o Akamai CDN. Suas atividades são continuamente monitoradas para que atualizações produzam um novo artefato de regras JSON que será propagado para o Akamai CDN.

| Etapa | Descrição |
| --- | --- |
| 1 | O [!DNL Experience Cloud Visitor ID] é recuperado do [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | A biblioteca at.js é carregada de modo síncrono e oculta o corpo do documento.<br>A biblioteca at.js também pode ser carregada de forma assíncrona com um trecho opcional de pré-ocultação implementado na página. |
| 1 | A biblioteca at.js oculta o corpo para evitar oscilações. |
| 4 | A biblioteca at.js faz uma solicitação para recuperar o artefato da regra JSON do Akamai CDN mais próximo ao visitante. |
| 5 | O Akamai CDN responde com o artefato da regra JSON. |
| 6 | O artefato da regra JSON é armazenado em cache localmente no navegador do visitante. |
| 7 | A biblioteca at.js interpreta o artefato da regra JSON e executa a decisão de recuperar a experiência e oculta os elementos testados. |
| 8 | A biblioteca at.js exibe o corpo para que o restante da página possa ser carregado para que o visitante visualize. |
| 9 | A biblioteca at.js manipula o DOM para renderizar a experiência do artefato de regra JSON em cache. |
| 10º | A experiência é renderizada para o visitante. |
| 11º | A página da Web inteira é carregada. |
| 12º | Os dados do [!DNL Analytics] são enviados ao servidores de Coleção de dados. Os dados direcionados correspondem aos dados [!DNL Analytics] por meio da SDID e são processados no armazenamento de relatório [!DNL Analytics]. [!DNL Analytics][!DNL Analytics]Em seguida, os dados do podem ser visualizados no e no pelos relatórios do Analytics for Target (A4T).[!DNL Target] |

O diagrama a seguir ilustra a interação entre o visitante, o navegador, a at.js 2.5.0+ e o artefato de regra JSON armazenado em cache para a ocorrência de página subsequente do visitante ou a visita recorrente. Como o artefato de regras JSON já está em cache e disponível no navegador, a decisão é tomada imediatamente sem uma chamada de rede de bloqueio. Esse diagrama de fluxo captura a navegação de página subsequente ou os visitantes recorrentes.

![Diagrama de fluxo somente no dispositivo para a navegação de página subsequente e visitas repetidas](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-only-subsequent.png)

A lista a seguir corresponde aos números no diagrama:

>[!NOTE]
>
>[!DNL Adobe Target] Os servidores de administração qualificam todas as suas atividades qualificadas para decisões no dispositivo, geram o artefato de regras JSON e o propagam para o Akamai CDN. Suas atividades são continuamente monitoradas para que atualizações produzam um novo artefato de regras JSON que será propagado para o Akamai CDN.

| Etapa | Descrição |
| --- | --- |
| 1 | O [!DNL Experience Cloud Visitor ID] é recuperado do [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | A biblioteca at.js é carregada de modo síncrono e oculta o corpo do documento.<br>A biblioteca at.js também pode ser carregada de forma assíncrona com um trecho opcional de pré-ocultação implementado na página. |
| 1 | A biblioteca at.js oculta o corpo para evitar oscilações. |
| 4 | A biblioteca at.js interpreta o artefato da regra JSON e executa a decisão na memória para recuperar a experiência. |
| 5 | Os elementos testados estão ocultos. |
| 6 | A biblioteca at.js exibe o corpo para que o restante da página possa ser carregado para que o visitante visualize. |
| 7 | A biblioteca at.js manipula o DOM para renderizar a experiência do artefato de regra JSON em cache. |
| 8 | A experiência é renderizada para o visitante. |
| 9 | A página da Web inteira é carregada. |
| 10º | Os dados do [!DNL Analytics] são enviados ao servidores de Coleção de dados. Os dados direcionados correspondem aos dados [!DNL Analytics] por meio da SDID e são processados no armazenamento de relatório [!DNL Analytics]. Em seguida, os dados do [!DNL Analytics] podem ser visualizados no [!DNL Analytics] e no [!DNL Target] pelos relatórios do [!UICONTROL Analytics for Target] (A4T). |

### Híbrido

 O Hybridis é o método de decisão que deve ser definido no at.js 2.5.0+, quando decisões no dispositivo e atividades que exigem uma chamada de rede para a rede do Adobe Target Edge devem ser executadas.

Ao gerenciar atividades de decisão no dispositivo e atividades no lado do servidor, pode ser um pouco complicado e entediante ao pensar em como implantar e provisionar [!DNL Target] em suas páginas. Com híbrido como o método de decisão, [!DNL Target] sabe quando deve fazer uma chamada de servidor para a rede do Adobe Target Edge para atividades que exigem execução no lado do servidor e também quando executar apenas decisões no dispositivo.

O artefato de regras JSON inclui metadados para informar à at.js se uma mbox tem uma atividade do lado do servidor em execução ou uma atividade de decisão no dispositivo. Esse método de decisão garante que as atividades que você pretende entregar rapidamente sejam realizadas por meio de decisões no dispositivo e para atividades que exigem personalização mais poderosa orientada por ML, essas atividades são realizadas por meio da rede Adobe Target Edge.

O diagrama a seguir ilustra a interação entre o visitante, o navegador, a at.js 2.5.0+, a Akamai CDN e a Rede de borda da Adobe Target para um novo visitante visitar sua página pela primeira vez. A solução desse diagrama é que o artefato de regras JSON é baixado de forma assíncrona enquanto as decisões são tomadas por meio da rede Adobe Target Edge.

Essa abordagem garante que o tamanho do artefato, que pode incluir muitas atividades, não influencie negativamente a latência da decisão. Baixar o artefato de regras JSON de forma síncrona e tomar a decisão posteriormente também pode ter efeitos adversos na latência e pode ser inconsistente. Portanto, o método de decisão híbrido é uma recomendação de prática recomendada para sempre fazer uma chamada do lado do servidor para a decisão de um novo visitante, e como o artefato de regras JSON é armazenado em cache em paralelo. Para quaisquer visitas de página subsequentes e visitas de retorno, as decisões são feitas do cache e na memória por meio do artefato de regras JSON.

![Diagrama de fluxo híbrido para um visitante pela primeira vez](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/hybrid-first-time-visitor.png)

A lista a seguir corresponde aos números no diagrama:

>[!NOTE]
>
>[!DNL Adobe Target] Os servidores de administração qualificam todas as suas atividades qualificadas para decisões no dispositivo, geram o artefato de regras JSON e o propagam para o Akamai CDN. Suas atividades são continuamente monitoradas para que atualizações produzam um novo artefato de regras JSON que será propagado para o Akamai CDN.

| Etapa | Descrição |
| --- | --- |
| 1 | O [!DNL Experience Cloud Visitor ID] é recuperado do [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | A biblioteca at.js é carregada de modo síncrono e oculta o corpo do documento.<br>A biblioteca at.js também pode ser carregada de forma assíncrona com um trecho opcional de pré-ocultação implementado na página. |
| 1 | A biblioteca at.js oculta o corpo para evitar oscilações. |
| 4 | Uma solicitação de carregamento de página é feita à Rede de borda da Adobe Target, incluindo todos os parâmetros configurados, como (ECID, ID do cliente, Parâmetros personalizados, Perfil de usuário, e assim por diante). |
| 5 | Paralelamente, a at.js faz uma solicitação para recuperar o artefato da regra JSON do Akamai CDN mais próximo ao visitante. |
| 6 | (Adobe Target Edge Network) Os scripts de perfil são executados e, em seguida, fazem o feed na Loja de perfis. A Loja de perfil solicita públicos qualificados da Biblioteca de público-alvo (por exemplo, públicos-alvo compartilhados de [!DNL Adobe Analytics], [!DNL Adobe Audience Manager] e assim por diante). |
| 7 | O Akamai CDN responde com o artefato da regra JSON. |
| 8 | A Loja de perfis é usada para qualificação de público-alvo e segmentação para filtrar atividades. |
| 9 | O conteúdo resultante é selecionado depois que a experiência é determinada a partir de atividades [!DNL Target] ativas. |
| 10º | A biblioteca at.js oculta os elementos correspondentes na página que estão associados à experiência que deve ser renderizada. |
| 11º | A biblioteca at.js exibe o corpo para que o restante da página possa ser carregado para que o visitante visualize. |
| 12º | A biblioteca at.js manipula o DOM para renderizar a experiência da Rede de borda do Target. |
| 13º | A experiência é renderizada para o visitante. |
| 14. | A página da Web inteira é carregada. |
| 15 | Os dados do [!DNL Analytics] são enviados ao servidores de Coleção de dados. Os dados direcionados correspondem aos dados [!DNL Analytics] por meio da SDID e são processados no armazenamento de relatório [!DNL Analytics]. Em seguida, os dados do [!DNL Analytics] podem ser visualizados no [!DNL Analytics] e no [!DNL Target] pelos relatórios do [!UICONTROL Analytics for Target] (A4T). |

O diagrama a seguir ilustra a interação entre o visitante, o navegador, a at.js 2.5.0+ e o artefato de regras JSON armazenado em cache para uma navegação de página subsequente ou uma visita de retorno. Nesse diagrama, concentre-se apenas no caso de uso em que uma decisão no dispositivo é tomada para a navegação da página subsequente ou a visita de retorno. Lembre-se de que, dependendo de quais atividades estão ativas para determinadas páginas, uma chamada do lado do servidor pode ser feita para executar decisões do lado do servidor.

![Diagrama de fluxo híbrido para a navegação de página subsequente e visitas repetidas](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/hybrid-subsequent.png)

A lista a seguir corresponde aos números no diagrama:

>[!NOTE]
>
>[!DNL Adobe Target] Os servidores de administração qualificam todas as suas atividades qualificadas para decisões no dispositivo, geram o artefato de regras JSON e o propagam para o Akamai CDN. Suas atividades são continuamente monitoradas para que atualizações produzam um novo artefato de regras JSON que será propagado para o Akamai CDN.

| Etapa | Descrição |
| --- | --- |
| 1 | O [!DNL Experience Cloud Visitor ID] é recuperado do [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | A biblioteca at.js é carregada de modo síncrono e oculta o corpo do documento.<br>A biblioteca at.js também pode ser carregada de forma assíncrona com um trecho opcional de pré-ocultação implementado na página. |
| 1 | A biblioteca at.js oculta o corpo para evitar oscilações. |
| 4 | Uma solicitação é feita para recuperar uma experiência. |
| 5 | A biblioteca at.js confirma que o artefato da regra JSON já foi armazenado em cache e executa a decisão na memória para recuperar a experiência. |
| 6 | Os elementos testados estão ocultos. |
| 7 | A biblioteca at.js exibe o corpo para que o restante da página possa ser carregado para que o visitante visualize. |
| 8 | A biblioteca at.js manipula o DOM para renderizar a experiência do artefato de regra JSON em cache. |
| 9 | A experiência é renderizada para o visitante. |
| 10º | A página da Web inteira é carregada. |
| 11º | Os dados do [!DNL Analytics] são enviados ao servidores de Coleção de dados. Os dados direcionados correspondem aos dados [!DNL Analytics] por meio da SDID e são processados no armazenamento de relatório [!DNL Analytics]. Em seguida, os dados do [!DNL Analytics] podem ser visualizados no [!DNL Analytics] e no [!DNL Target] pelos relatórios do [!UICONTROL Analytics for Target] (A4T). |

## Como ativar a tomada de decisão no dispositivo?

A decisão no dispositivo está disponível para todos os clientes [!DNL Target] que usam o At.js 2.5.0+.

Para ativar a decisão no dispositivo:

>[!NOTE]
>
>Você deve ter o [!UICONTROL Admin] ou [!UICONTROL Aprovador] [função de usuário](/help/administrating-target/c-user-management/user-management.md) para habilitar ou desabilitar a alternância de decisão no dispositivo.

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Implementação]** > **[!UICONTROL Detalhes da conta]**.
1. Em **[!UICONTROL Detalhes da conta]**, deslize o botão **[!UICONTROL On-Device Decisioning]** para a posição &quot;on&quot;.

   ![Alternância de decisão no dispositivo](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-toggle.png)

   A opção &quot;[!UICONTROL Incluir todas as atividades qualificadas de decisão no dispositivo existentes no artefato]&quot; é exibida se você ativar a tomada de decisão no dispositivo.
1. (Condicional) Deslize o botão para a posição &quot;ativada&quot; se desejar que todas as atividades ativas do Target qualificadas para a tomada de decisão no dispositivo sejam incluídas automaticamente no artefato.

   Deixar essa opção desativada significa que você deve recriar e ativar todas as atividades de decisão no dispositivo para que sejam incluídas no artefato de regras gerado. Em outras palavras, qualquer atividade no estado ativo antes de ativar a alternância [!UICONTROL No dispositivo Decisioning] não é incluída no artefato de regras.

Depois de ativar o botão [!UICONTROL On-Device Decisioning], [!DNL Target] começa a gerar e propagar [artefatos de regra](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/rule-artifact.md) para o seu cliente.

>[!IMPORTANT]
>
>Certifique-se de ativar o botão de alternância antes de inicializar o SDK do Adobe Target para usar a tomada de decisão no dispositivo. Os artefatos da regra primeiro precisam gerar e se propagar para as CDNs do Akamai para que a decisão no dispositivo funcione. A propagação pode levar de cinco a dez minutos para que o primeiro artefato de regra seja gerado e propagado para o Akamai CDN.

## Como configuro o at.js 2.5.0+ para usar a tomada de decisão no dispositivo?

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Implementação]** > **[!UICONTROL Detalhes da conta]**.
1. Em **[!UICONTROL Métodos de implementação]** > **[!UICONTROL Método de implementação principal]**, clique em **[!UICONTROL Editar]** ao lado da versão at.js (deve ser at.js 2.5.0 ou posterior).

   ![Editar configurações do Método de implementação principal](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/main-implementation-method.png)

   >[!IMPORTANT]
   >
   >Antes de alterar essas configurações padrão, consulte o Atendimento ao cliente para não afetar sua implementação atual.

1. Selecione o método de decisão desejado:

   * [!UICONTROL Somente no lado do servidor]
   * [!UICONTROL Somente no dispositivo]
   * [!UICONTROL Híbrido]

   ![Editar o painel de configurações da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/global-settings.png)

### Configurações globais

Você pode configurar um [!UICONTROL Método de Decisão] padrão para todas as decisões [!DNL Target]. Os vários métodos de decisão são [!UICONTROL Somente no lado do servidor], [!UICONTROL Somente no dispositivo] e [!UICONTROL Híbrido]. O método de decisão selecionado na interface do usuário do Target é configurado em `window.targetGlobalSettings` no campo `decisioningMethod` . Saiba mais sobre o `decisioningMethod` em [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).

```javascript
<head> 
    <script type="text/javascript">

        window.targetGlobalSettings = { 
            clientCode: "yourClientCodeHere", 
            imsOrgId: "imsOrgId@AdobeOrg", 
            decisioningMethod: "on-device"

        }; 
    </script>

    <script type="text/javascript" src="at.js"></script> 
</head>
```

### Configuração personalizada

Se você definir o `decisioningMethod` em `window.targetGlobalSettings`, mas quiser substituir o `decisioningMethod` para cada decisão do Adobe Target de acordo com seu caso de uso, poderá fazer esse procedimento especificando `decisioningMethod` na chamada [getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) de At.js2.5.0+.

```javascript
adobe.target.getOffers({ 

  decisioningMethod:"on-device", 
  request: { 
    execute: { 
      mboxes: [ 
        { 
          index: 0, 
          name: "homepage" 
        } 
      ] 
    } 
 } 
});
```

>[!NOTE]
>
>Para usar &quot;no dispositivo&quot; ou &quot;híbrido&quot; como método de decisão na chamada getOffers() , verifique se a configuração global tem `decisioningMethod` como &quot;no dispositivo&quot; ou &quot;híbrido&quot;. A biblioteca at.js 2.5.0+ deve saber se o artefato de regras JSON deve ser baixado e armazenado em cache imediatamente após ser carregado na página. Se o método de decisão da configuração global estiver definido como &quot;no lado do servidor&quot; e o método de decisão &quot;no dispositivo&quot; ou &quot;híbrido&quot; for passado para a chamada getOffers(), o at.js 2.5.0+ não terá o artefato da regra JSON armazenado em cache para executar suas decisões no dispositivo.

### TTL do Cache de Artefatos

[!DNL Target] representa suas atividades qualificadas para decisão no dispositivo como um artefato que consiste em metadados, regras e condições. Esse artefato é armazenado em cache no Akamai CDN. Durante a primeira visita do usuário, o navegador do usuário baixa e armazena em cache o artefato que representa as atividades de decisão no dispositivo.

Em visitas subsequentes ao site, o navegador verifica automaticamente se ele deve baixar uma versão mais recente do artefato. Essa verificação adiciona latência. O TTL do Cache de Artefatos define o número de minutos em que você não deseja que o navegador verifique se há um artefato atualizado desde o último download bem-sucedido. Quanto maior o período, melhor o desempenho. Quanto menor o intervalo de tempo, melhor a atualização dos dados, mas ao custo de latência adicionada.

## Como sei se uma atividade está qualificada para a tomada de decisão no dispositivo?

Depois de criar uma atividade elegível para decisão no dispositivo, um rótulo que lê [!UICONTROL On-Device Decisioning Eligable] é visível na página [!UICONTROL Visão geral] da atividade.

![No dispositivo Decisioning Elegível na página Visão geral da atividade.](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-eligible-label.png)

Esse rótulo não significa que a atividade sempre será entregue por meio de decisões no dispositivo. Somente quando a at.js 2.5.0+ estiver configurada para usar a tomada de decisão no dispositivo essa atividade será executada no dispositivo. Se o at.js 2.5.0+ não estiver configurado para usar no dispositivo, essa atividade ainda será entregue por meio de uma chamada de servidor feita do at.js.

Você pode filtrar por todas as atividades que são elegíveis para decisão no dispositivo na página [!UICONTROL Activities] por meio do filtro [!UICONTROL On-Device Decisioning Eliged] .

![On-Device Decisioning Filtro elegível na página Atividades .](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-filter.png)

>[!NOTE]
>
>Depois de criar e ativar uma atividade que é elegível para decisão no dispositivo, ela pode levar de cinco a dez minutos antes de ser incluída no artefato de regras gerado e propagado para o ponto de presenças do Akamai CDN.

## Resumo das etapas para garantir que minhas atividades de decisão no dispositivo sejam entregues por meio da At.js 2.5.0+?

1. Acesse a interface do usuário do Adobe Target e navegue até **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** > **[!DNL Account Details]** para habilitar o botão **[!UICONTROL On-Device Decisioning]**.
1. Ative a opção **&quot;[!UICONTROL Inclua todas as atividades qualificadas de decisão no dispositivo existentes na alternância artefato]&quot;**.

   A primeira geração de artefatos de regras JSON pode levar até 10 minutos.

1. Crie e ative um tipo de atividade [compatível com o on-device decisioning](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/supported-features.md) e verifique se ele é elegível para decisão no dispositivo.
1. Defina o **[!UICONTROL Método de decisão]** como **[!UICONTROL &quot;Híbrido&quot;]** ou **[!UICONTROL &quot;Somente no dispositivo&quot;]** por meio da interface do usuário de configurações da at.js.
1. Baixe e implante o At.js 2.5.0+ em suas páginas.

## Solução de problemas

Complete as etapas a seguir para solucionar problemas no dispositivo de decisão:

1. Ativar o log do console para at.js
1. Verifique o download do artefato da regra na guia Rede do navegador
1. Verificar o download do artefato da regra usando eventos personalizados da at.js

As seções a seguir descrevem cada etapa com mais detalhes:

### Etapa 1: Ativar o log do console para at.js

Anexar o parâmetro de URL `mboxDebug=1` permite que o at.js imprima mensagens no console do navegador.

Todas as mensagens contêm um prefixo &quot;AT:&quot; para obter uma visão geral conveniente. Para garantir que um artefato tenha sido carregado com êxito, o log do console deve conter mensagens semelhantes ao seguinte:

```
AT: LD.ArtifactProvider fetching artifact - https://assets.adobetarget.com/your-client-cide/production/v1/rules.json
AT: LD.ArtifactProvider artifact received - status=200
```

A ilustração a seguir mostra essas mensagens no log do console:

![Logon do console com mensagens de artefato](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/browser-console.png)

### Etapa 2: Verifique o download do artefato da regra na guia Rede do navegador

Abra a guia Rede do navegador.

Por exemplo, para abrir o DevTools no Google Chrome:

1. Pressione Control+Shift+J (Windows) ou Command+Option+J (Mac).
1. Navegue até a guia Rede.
1. Filtre suas chamadas por palavra-chave &quot;rules.json&quot; para garantir que somente o arquivo de regras de artefato seja exibido.

   Além disso, você pode filtrar por &quot;/delivery|rules.json/&quot; para exibir todas as chamadas [!DNL Target] e o artefato rules.json.

   ![Guia Rede no Google Chrome](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/rule-json.png)

### Verificar o download do artefato da regra usando eventos personalizados da at.js

A biblioteca at.js despacha dois novos eventos personalizados para suportar decisões no dispositivo.

* `adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED`
* `adobe.target.event.ARTIFACT_DOWNLOAD_FAILED`

Você pode assinar para ouvir esses eventos personalizados em seu aplicativo para ação após o sucesso ou falha do download do arquivo de regras de artefato.

O exemplo a seguir mostra uma amostra de código ouvindo os eventos de sucesso e falha do download de artefatos:

```javascript
document.addEventListener(adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED, function(e) { 
  console.log("Artifact successfully downloaded", e.detail);
}, false);

document.addEventListener(adobe.target.event.ARTIFACT_DOWNLOAD_FAILED, function(e) { 
  console.log("Artifact failed to download", e.detail);
}, false);
```
