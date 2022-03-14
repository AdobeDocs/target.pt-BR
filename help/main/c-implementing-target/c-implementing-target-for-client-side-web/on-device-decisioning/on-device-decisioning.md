---
keywords: implementação; biblioteca javascript; js; atjs; decisão no dispositivo; no device decisioning; at.js; no dispositivo; no dispositivo
description: Saiba como executar a decisão no dispositivo com a biblioteca at.js
title: Como o On-device Decisioning funciona com a biblioteca JavaScript da at.js?
feature: at.js
role: Developer
exl-id: 5ad6032b-9865-4c80-8800-705673657286
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '3490'
ht-degree: 19%

---

# Decisão no dispositivo para at.js

A partir da versão 2.5.0, a at.js oferece decisão no dispositivo. A decisão no dispositivo permite armazenar em cache seu [Teste A/B](/help/main/c-activities/t-test-ab/test-ab.md) e [Direcionamento de experiência](/help/main/c-activities/t-experience-target/experience-target.md) (XT) atividades no navegador para executar decisões na memória sem uma solicitação de rede de bloqueio para o [!DNL Adobe Target] Edge Network.

[!DNL Target] O também oferece a flexibilidade de fornecer a experiência mais relevante e atualizada de suas atividades de personalização orientadas por ML (experimentação e aprendizado de máquina) por meio de uma chamada de servidor ao vivo. Em outras palavras, quando o desempenho é mais importante, você pode optar por usar a decisão no dispositivo. No entanto, quando a experiência mais relevante, atualizada e orientada por ML for necessária, uma chamada de servidor poderá ser feita.

## Quais são os benefícios da tomada de decisões no dispositivo?

Os benefícios da decisão no dispositivo incluem:

* **Forneça decisões e experiências extremamente rápidas.** A compartimentalização e a decisão são executadas na memória e no navegador para evitar o bloqueio de solicitações de rede.
* **Melhore o desempenho do aplicativo.** Execute experimentos e forneça personalização para seus clientes e usuários sem comprometer as experiências dos usuários finais.
* **Melhore a pontuação de qualidade do site da Google.** Com a tomada de decisão na memória, melhore a pontuação de qualidade do site da Google em seus negócios online para torná-la mais detectável para os consumidores.
* **Saiba mais sobre análises em tempo real.** Obtenha insights do desempenho da sua atividade em tempo real por meio de [Analytics para Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) Relatórios do (A4T). O A4T permite girar sua estratégia em momentos críticos.

## Recursos compatíveis

O SDK JS da Adobe Target oferece aos clientes a flexibilidade para escolher entre desempenho e atualização de dados para decisões. Em outras palavras, se o fornecimento do conteúdo personalizado mais relevante e envolvente por meio do aprendizado de máquina for mais importante para você, uma chamada de servidor ao vivo deverá ser feita. Mas quando o desempenho é mais importante, uma decisão no dispositivo e na memória deve ser tomada. Para que a decisão no dispositivo funcione, consulte a lista de recursos compatíveis:

* Tipos de atividades 
* Direcionamento de público-alvo
* Método de alocação

Para obter mais informações, consulte [Recursos compatíveis com a tomada de decisão no dispositivo](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/supported-features.md).

## Como a decisão no dispositivo funciona?

Ao implantar e inicializar a at.js com a tomada de decisão no dispositivo ativada, uma [artefato de regra](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/rule-artifact.md) que inclui sua decisão no dispositivo para atividades A/B e XT, públicos-alvo e ativos, é baixada do Akamai CDN mais próximo ao visitante e armazenada em cache localmente no navegador do visitante. Quando uma solicitação é feita da at.js para recuperar uma experiência, a decisão sobre qual experiência retornar é tomada na memória, com base nos metadados codificados no artefato de regra em cache.

## Método de decisão

Com decisão no dispositivo, [!DNL Target] introduz uma nova configuração chamada [!UICONTROL Método de decisão]. O [!UICONTROL Método de decisão] a configuração do determina como a at.js fornece suas experiências. [!UICONTROL Método de decisão] tem três valores:

* [!UICONTROL Somente no lado do servidor]
* [!UICONTROL Somente no dispositivo]
* [!UICONTROL Híbrido]

### Somente no lado do servidor

[!UICONTROL Somente no lado do servidor] é o método de decisão padrão definido imediatamente quando a at.js 2.5.0+ é implementada e implantada em suas propriedades da Web.

Usar [!UICONTROL somente no lado do servidor] como configuração padrão significa que todas as decisões são tomadas na rede de borda do [!DNL Target], o que envolve uma chamada de servidor de bloqueio. Essa abordagem pode apresentar latência incremental, mas também oferece benefícios significativos, como a capacidade de aplicar os recursos de aprendizado de máquina do Target, que incluem as atividades de [Recomendações](/help/main/c-recommendations/recommendations.md), [Personalização automatizada](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) e [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

Além disso, aprimorar suas experiências personalizadas usando o perfil de usuário do Target, que é mantido em sessões e canais, pode trazer resultados significativos para sua empresa.

Por fim, [!UICONTROL somente no lado do servidor] permite usar a Adobe Experience Cloud e refinar públicos-alvo que podem ser direcionados por meio de segmentos do Audience Manager e do Adobe Analytics.

O diagrama a seguir ilustra a interação entre o visitante, o navegador, a at.js 2.5.0+ e a rede Adobe Target Edge. Esse diagrama de fluxo captura novos visitantes e visitantes recorrentes.

![Diagrama de fluxo somente do lado do servidor](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/server-side-only.png)

A lista a seguir corresponde aos números no diagrama:

| Etapa | Descrição |
| --- | --- |
| 1 | O [!DNL Experience Cloud Visitor ID] é recuperado do [Serviço de identidade da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en). |
| 2 | A biblioteca at.js é carregada de modo síncrono e oculta o corpo do documento.<br>   A biblioteca at.js também pode ser carregada de forma assíncrona com um trecho opcional de pré-ocultação implementado na página. |
| 3 | A biblioteca at.js oculta o corpo para evitar oscilações. |
| 4 | É feita uma solicitação de carregamento de página que inclui todos os parâmetros configurados, como (ECID, ID do cliente, Parâmetros personalizados, Perfil de usuário e assim por diante). |
| 5 | Os scripts de perfil executam e, em seguida, fazem o feed na Loja do perfil.<br>A Loja de perfis solicita públicos qualificados da Biblioteca de público-alvo (por exemplo, públicos-alvo compartilhados de [!DNL Adobe Analytics], [!DNL Adobe Audience Manager]e assim por diante.).<br>Os atributos do cliente são enviados à Loja de perfis em um processo em lote. |
| 6 | A Loja de perfis é usada para qualificação de público-alvo e segmentação para filtrar atividades. |
| 7 | O conteúdo resultante é selecionado depois que a experiência é determinada a partir do live [!DNL Target] atividades. |
| 8 | A biblioteca at.js oculta os elementos correspondentes na página que estão associados à experiência que deve ser renderizada. |
| 9 | A biblioteca at.js exibe o corpo para que o restante da página possa ser carregado para que o visitante visualize. |
| 10 | A biblioteca at.js manipula o DOM para renderizar a experiência da Rede de borda do Target. |
| 11 | A experiência é renderizada para o visitante. |
| 12 | A página da Web inteira é carregada. |
| 13 | Os dados do [!DNL Analytics] são enviados ao servidores de Coleção de dados. |
| 14 | Os dados direcionados são correspondidos a [!DNL Analytics] dados por meio da SDID e são processados na variável [!DNL Analytics] armazenamento de relatórios. Em seguida, os dados do [!DNL Analytics] podem ser visualizados no [!DNL Analytics] e no [!DNL Target] pelos relatórios do [!UICONTROL Analytics for Target] (A4T). |

### Somente no dispositivo

[!UICONTROL Somente no dispositivo] é o método de decisão que deve ser definido na at.js 2.5.0+ quando a tomada de decisão no dispositivo precisar ser usada somente em suas páginas da Web.

A decisão no dispositivo entrega experiências e atividades de personalização em uma velocidade extremamente rápida, pois as decisões são tomadas a partir de um artefato de regras em cache que contém todas as suas atividades qualificadas para decisões no dispositivo.

Para saber mais sobre quais atividades se qualificam para decisões no dispositivo, consulte [Recursos compatíveis com a tomada de decisão no dispositivo](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/supported-features.md).

Esse método de decisão deve ser usado somente se o desempenho for altamente crítico em todas as páginas que exigem decisões do [!DNL Target]. Além disso, lembre-se de que, quando esse método de decisão é selecionado, as atividades do [!DNL Target] que não se qualificam para a tomada de decisão no dispositivo não são entregues ou executadas. A biblioteca at.js 2.5.0+ está configurada para procurar somente pelo artefato de regras em cache para tomar decisões.

O diagrama a seguir ilustra a interação entre o visitante, o navegador, a at.js 2.5.0+ e a Akamai CDN. O Akamai CDN armazena em cache o artefato de regras para a primeira visita do visitante. Para a primeira visita à página de um novo visitante, o artefato de regras JSON deve ser baixado do Akamai CDN para ser armazenado em cache localmente no navegador do visitante. Após o download do artefato de regras JSON, a decisão é tomada imediatamente sem uma chamada de rede de bloqueio. O diagrama de fluxo a seguir captura novos visitantes.

![Diagrama de fluxo somente no dispositivo](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-only.png)

A lista a seguir corresponde aos números no diagrama:

>[!NOTE]
>
>[!DNL Adobe Target] Os servidores de administração qualificam todas as suas atividades qualificadas para decisões no dispositivo, geram o artefato de regras JSON e o propagam para o Akamai CDN. Suas atividades são continuamente monitoradas para que atualizações produzam um novo artefato de regras JSON que será propagado para o Akamai CDN.

| Etapa | Descrição |
| --- | --- |
| 1 | O [!DNL Experience Cloud Visitor ID] é recuperado do [Serviço de identidade da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | A biblioteca at.js é carregada de modo síncrono e oculta o corpo do documento.<br>A biblioteca at.js também pode ser carregada de forma assíncrona com um trecho opcional de pré-ocultação implementado na página. |
| 3 | A biblioteca at.js oculta o corpo para evitar oscilações. |
| 4 | A biblioteca at.js faz uma solicitação para recuperar o artefato da regra JSON do Akamai CDN mais próximo ao visitante. |
| 5 | O Akamai CDN responde com o artefato da regra JSON. |
| 6 | O artefato da regra JSON é armazenado em cache localmente no navegador do visitante. |
| 7 | A biblioteca at.js interpreta o artefato da regra JSON e executa a decisão de recuperar a experiência e oculta os elementos testados. |
| 8 | A biblioteca at.js exibe o corpo para que o restante da página possa ser carregado para que o visitante visualize. |
| 9 | A biblioteca at.js manipula o DOM para renderizar a experiência do artefato de regra JSON em cache. |
| 10º | A experiência é renderizada para o visitante. |
| 11º | A página da Web inteira é carregada. |
| 12º | Os dados do [!DNL Analytics] são enviados ao servidores de Coleção de dados. Os dados direcionados são correspondidos a [!DNL Analytics] dados por meio da SDID e são processados na variável [!DNL Analytics] armazenamento de relatórios. [!DNL Analytics][!DNL Analytics]Em seguida, os dados do podem ser visualizados no e no pelos relatórios do Analytics for Target (A4T).[!DNL Target] |

O diagrama a seguir ilustra a interação entre o visitante, o navegador, a at.js 2.5.0+ e o artefato de regra JSON armazenado em cache para a ocorrência de página subsequente do visitante ou a visita recorrente. Como o artefato de regras JSON já está em cache e disponível no navegador, a decisão é tomada imediatamente sem uma chamada de rede de bloqueio. Esse diagrama de fluxo captura a navegação de página subsequente ou os visitantes recorrentes.

![Diagrama de fluxo somente no dispositivo para a navegação de página subsequente e visitas repetidas](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-only-subsequent.png)

A lista a seguir corresponde aos números no diagrama:

>[!NOTE]
>
>[!DNL Adobe Target] Os servidores de administração qualificam todas as suas atividades qualificadas para decisões no dispositivo, geram o artefato de regras JSON e o propagam para o Akamai CDN. Suas atividades são continuamente monitoradas para que atualizações produzam um novo artefato de regras JSON que será propagado para o Akamai CDN.

| Etapa | Descrição |
| --- | --- |
| 1 | O [!DNL Experience Cloud Visitor ID] é recuperado do [Serviço de identidade da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | A biblioteca at.js é carregada de modo síncrono e oculta o corpo do documento.<br>A biblioteca at.js também pode ser carregada de forma assíncrona com um trecho opcional de pré-ocultação implementado na página. |
| 3 | A biblioteca at.js oculta o corpo para evitar oscilações. |
| 4 | A biblioteca at.js interpreta o artefato da regra JSON e executa a decisão na memória para recuperar a experiência. |
| 5 | Os elementos testados estão ocultos. |
| 6 | A biblioteca at.js exibe o corpo para que o restante da página possa ser carregado para que o visitante visualize. |
| 7 | A biblioteca at.js manipula o DOM para renderizar a experiência do artefato de regra JSON em cache. |
| 8 | A experiência é renderizada para o visitante. |
| 9 | A página da Web inteira é carregada. |
| 10º | Os dados do [!DNL Analytics] são enviados ao servidores de Coleção de dados. Os dados direcionados são correspondidos a [!DNL Analytics] dados por meio da SDID e são processados na variável [!DNL Analytics] armazenamento de relatórios. Em seguida, os dados do [!DNL Analytics] podem ser visualizados no [!DNL Analytics] e no [!DNL Target] pelos relatórios do [!UICONTROL Analytics for Target] (A4T). |

### Híbrido

O método de decisão [!UICONTROL híbrido] é o que deve ser definido na at.js 2.5.0+, quando a decisão no dispositivo e as atividades que exigem uma chamada de rede para a rede de borda do Adobe Target precisam ser executadas.

Ao gerenciar atividades de decisão no dispositivo e atividades no lado do servidor, você pode achar complicado e cansativo pensar em como implantar e provisionar o [!DNL Target] em suas páginas. Com o método de decisão híbrido, o [!DNL Target] sabe quando deve fazer uma chamada de servidor para a rede de borda do Adobe Target, no caso de atividades que exigem execução no lado do servidor, e quando deve apenas executar decisões no dispositivo.

O artefato de regras JSON inclui metadados para informar à at.js se uma mbox tem uma atividade do lado do servidor em execução ou uma atividade de decisão no dispositivo. Esse método de decisão garante que as atividades que você pretende entregar rapidamente sejam realizadas por meio de decisões no dispositivo e, no caso de atividades que exigem maior personalização orientada por aprendizado de máquina, essas atividades são realizadas por meio da rede de borda do Adobe Target.

O diagrama a seguir ilustra a interação entre o visitante, o navegador, a at.js 2.5.0+, a Akamai CDN e a Rede de borda da Adobe Target para um novo visitante visitar sua página pela primeira vez. A solução desse diagrama é que o artefato de regras JSON é baixado de forma assíncrona enquanto as decisões são tomadas por meio da rede Adobe Target Edge.

Essa abordagem garante que o tamanho do artefato, que pode incluir muitas atividades, não influencie negativamente a latência da decisão. Baixar o artefato de regras JSON de forma síncrona e tomar a decisão posteriormente também pode ter efeitos adversos na latência e pode ser inconsistente. Portanto, o método de decisão híbrido é uma recomendação de prática recomendada para sempre fazer uma chamada do lado do servidor para a decisão de um novo visitante, e como o artefato de regras JSON é armazenado em cache em paralelo. Para quaisquer visitas de página subsequentes e visitas de retorno, as decisões são feitas do cache e na memória por meio do artefato de regras JSON.

![Diagrama de fluxo híbrido para um visitante pela primeira vez](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/hybrid-first-time-visitor.png)

A lista a seguir corresponde aos números no diagrama:

>[!NOTE]
>
>[!DNL Adobe Target] Os servidores de administração qualificam todas as suas atividades qualificadas para decisões no dispositivo, geram o artefato de regras JSON e o propagam para o Akamai CDN. Suas atividades são continuamente monitoradas para que atualizações produzam um novo artefato de regras JSON que será propagado para o Akamai CDN.

| Etapa | Descrição |
| --- | --- |
| 1 | O [!DNL Experience Cloud Visitor ID] é recuperado do [Serviço de identidade da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | A biblioteca at.js é carregada de modo síncrono e oculta o corpo do documento.<br>A biblioteca at.js também pode ser carregada de forma assíncrona com um trecho opcional de pré-ocultação implementado na página. |
| 3 | A biblioteca at.js oculta o corpo para evitar oscilações. |
| 4 | Uma solicitação de carregamento de página é feita à Rede de borda da Adobe Target, incluindo todos os parâmetros configurados, como (ECID, ID do cliente, Parâmetros personalizados, Perfil de usuário, e assim por diante). |
| 5 | Paralelamente, a at.js faz uma solicitação para recuperar o artefato da regra JSON do Akamai CDN mais próximo ao visitante. |
| 6 | (Adobe Target Edge Network) Os scripts de perfil são executados e, em seguida, fazem o feed na Loja de perfis. A Loja de perfis solicita públicos qualificados da Biblioteca de público-alvo (por exemplo, públicos-alvo compartilhados de [!DNL Adobe Analytics], [!DNL Adobe Audience Manager]e assim por diante.). |
| 7 | O Akamai CDN responde com o artefato da regra JSON. |
| 8 | A Loja de perfis é usada para qualificação de público-alvo e segmentação para filtrar atividades. |
| 9 | O conteúdo resultante é selecionado depois que a experiência é determinada a partir do live [!DNL Target] atividades. |
| 10º | A biblioteca at.js oculta os elementos correspondentes na página que estão associados à experiência que deve ser renderizada. |
| 11º | A biblioteca at.js exibe o corpo para que o restante da página possa ser carregado para que o visitante visualize. |
| 12º | A biblioteca at.js manipula o DOM para renderizar a experiência da Rede de borda do Target. |
| 13º | A experiência é renderizada para o visitante. |
| 14. | A página da Web inteira é carregada. |
| 15 | Os dados do [!DNL Analytics] são enviados ao servidores de Coleção de dados. Os dados direcionados são correspondidos a [!DNL Analytics] dados por meio da SDID e são processados na variável [!DNL Analytics] armazenamento de relatórios. Em seguida, os dados do [!DNL Analytics] podem ser visualizados no [!DNL Analytics] e no [!DNL Target] pelos relatórios do [!UICONTROL Analytics for Target] (A4T). |

O diagrama a seguir ilustra a interação entre o visitante, o navegador, a at.js 2.5.0+ e o artefato de regras JSON armazenado em cache para uma navegação de página subsequente ou uma visita de retorno. Nesse diagrama, concentre-se apenas no caso de uso em que uma decisão no dispositivo é tomada para a navegação da página subsequente ou a visita de retorno. Lembre-se de que, dependendo de quais atividades estão ativas para determinadas páginas, uma chamada do lado do servidor pode ser feita para executar decisões do lado do servidor.

![Diagrama de fluxo híbrido para a navegação de página subsequente e visitas repetidas](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/hybrid-subsequent.png)

A lista a seguir corresponde aos números no diagrama:

>[!NOTE]
>
>[!DNL Adobe Target] Os servidores de administração qualificam todas as suas atividades qualificadas para decisões no dispositivo, geram o artefato de regras JSON e o propagam para o Akamai CDN. Suas atividades são continuamente monitoradas para que atualizações produzam um novo artefato de regras JSON que será propagado para o Akamai CDN.

| Etapa | Descrição |
| --- | --- |
| 1 | O [!DNL Experience Cloud Visitor ID] é recuperado do [Serviço de identidade da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 2 | A biblioteca at.js é carregada de modo síncrono e oculta o corpo do documento.<br>A biblioteca at.js também pode ser carregada de forma assíncrona com um trecho opcional de pré-ocultação implementado na página. |
| 3 | A biblioteca at.js oculta o corpo para evitar oscilações. |
| 4 | Uma solicitação é feita para recuperar uma experiência. |
| 5 | A biblioteca at.js confirma que o artefato da regra JSON já foi armazenado em cache e executa a decisão na memória para recuperar a experiência. |
| 6 | Os elementos testados estão ocultos. |
| 7 | A biblioteca at.js exibe o corpo para que o restante da página possa ser carregado para que o visitante visualize. |
| 8 | A biblioteca at.js manipula o DOM para renderizar a experiência do artefato de regra JSON em cache. |
| 9 | A experiência é renderizada para o visitante. |
| 10º | A página da Web inteira é carregada. |
| 11º | Os dados do [!DNL Analytics] são enviados ao servidores de Coleção de dados. Os dados direcionados são correspondidos a [!DNL Analytics] dados por meio da SDID e são processados na variável [!DNL Analytics] armazenamento de relatórios. Em seguida, os dados do [!DNL Analytics] podem ser visualizados no [!DNL Analytics] e no [!DNL Target] pelos relatórios do [!UICONTROL Analytics for Target] (A4T). |

## Como ativar a tomada de decisão no dispositivo?

A decisão no dispositivo está disponível para todos [!DNL Target] clientes que usam o At.js 2.5.0+.

Para ativar a decisão no dispositivo:

>[!NOTE]
>
>Você deve ter o [!UICONTROL Administrador] ou [!UICONTROL Aprovador] [função de usuário](/help/main/administrating-target/c-user-management/user-management.md) para ativar ou desativar o botão de opção On-Device Decisioning .

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Implementação]** > **[!UICONTROL Detalhes da conta]**.
1. Em **[!UICONTROL Detalhes da conta]**, deslize o **[!UICONTROL Decisão no dispositivo]** alterne para a posição &quot;ativada&quot;.

   ![Alternância de decisão no dispositivo](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-toggle.png)

   O &quot;[!UICONTROL Incluir todas as atividades qualificadas de decisão no dispositivo existentes no artefato]&quot; é exibida se você ativar a decisão no dispositivo.
1. (Condicional) Deslize o botão para a posição &quot;ativada&quot; se desejar que todas as atividades ativas do Target qualificadas para a tomada de decisão no dispositivo sejam incluídas automaticamente no artefato.

   Deixar essa opção desativada significa que você deve recriar e ativar todas as atividades de decisão no dispositivo para que sejam incluídas no artefato de regras gerado. Em outras palavras, qualquer atividade no estado ativo antes de ativar o [!UICONTROL Decisão no dispositivo] alternar não estão incluídos no artefato de regras.

Depois de habilitar o [!UICONTROL Decisão no dispositivo] alternar, [!DNL Target] começa a gerar e propagar [artefatos da regra](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/rule-artifact.md) para o seu cliente.

>[!IMPORTANT]
>
>Certifique-se de ativar o botão de alternância antes de inicializar o SDK do Adobe Target para usar a tomada de decisão no dispositivo. Os artefatos da regra primeiro precisam gerar e se propagar para as CDNs do Akamai para que a decisão no dispositivo funcione. A propagação pode levar de cinco a dez minutos para que o primeiro artefato de regra seja gerado e propagado para o Akamai CDN.

## Como configuro o at.js 2.5.0+ para usar a tomada de decisão no dispositivo?

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Implementação]** > **[!UICONTROL Detalhes da conta]**.
1. Em **[!UICONTROL Métodos de implementação]** > **[!UICONTROL Método de implementação principal]**, clique em **[!UICONTROL Editar]** ao lado da versão do at.js (deve ser at.js 2.5.0 ou posterior).

   ![Editar configurações do Método de implementação principal](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/main-implementation-method.png)

   >[!IMPORTANT]
   >
   >Antes de alterar essas configurações padrão, consulte o Atendimento ao cliente para não afetar sua implementação atual.

1. Selecione o método de decisão desejado:

   * [!UICONTROL Somente no lado do servidor]
   * [!UICONTROL Somente no dispositivo]
   * [!UICONTROL Híbrido]

   ![Editar o painel de configurações da at.js](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/global-settings.png)

### Configurações globais

Você pode configurar um [!UICONTROL Método de decisão] para todos [!DNL Target] decisões. Os vários métodos de decisão são [!UICONTROL Somente no lado do servidor], [!UICONTROL Somente no dispositivo]e [!UICONTROL Híbrido]. O método de decisão selecionado na interface do usuário do Target é configurado em `window.targetGlobalSettings` nos termos do `decisioningMethod` campo. Saiba mais sobre o `decisioningMethod` em [targetGlobalSettings()](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).

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

Se você definir a variável `decisioningMethod` em `window.targetGlobalSettings`, mas gostaria de substituir a variável `decisioningMethod` para cada decisão do Adobe Target de acordo com o caso de uso, você pode fazer esse procedimento especificando `decisioningMethod` em At.js2.5.0+’s [getOffers()](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) chame.

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
>Para usar &quot;no dispositivo&quot; ou &quot;híbrido&quot; como método de decisão na chamada getOffers(), verifique se a configuração global tem `decisioningMethod` como &quot;no dispositivo&quot; ou &quot;híbrido&quot;. A biblioteca at.js 2.5.0+ deve saber se o artefato de regras JSON deve ser baixado e armazenado em cache imediatamente após ser carregado na página. Se o método de decisão da configuração global estiver definido como &quot;no lado do servidor&quot; e o método de decisão &quot;no dispositivo&quot; ou &quot;híbrido&quot; for passado para a chamada getOffers(), o at.js 2.5.0+ não terá o artefato da regra JSON armazenado em cache para executar suas decisões no dispositivo.

### TTL do Cache de Artefatos

[!DNL Target] representa suas atividades qualificadas para decisão no dispositivo como um artefato que consiste em metadados, regras e condições. Esse artefato é armazenado em cache no Akamai CDN. Durante a primeira visita do usuário, o navegador do usuário baixa e armazena em cache o artefato que representa as atividades de decisão no dispositivo.

Em visitas subsequentes ao site, o navegador verifica automaticamente se ele deve baixar uma versão mais recente do artefato. Essa verificação adiciona latência. O TTL do Cache de Artefatos define o número de minutos em que você não deseja que o navegador verifique se há um artefato atualizado desde o último download bem-sucedido. Quanto maior o período, melhor o desempenho. Quanto menor o intervalo de tempo, melhor a atualização dos dados, mas ao custo de latência adicionada.

## Como sei se uma atividade está qualificada para a tomada de decisão no dispositivo?

Após criar uma atividade que é elegível para decisão no dispositivo, um rótulo que lê [!UICONTROL Decisão no dispositivo elegível], é visível no [!UICONTROL Visão geral] página.

![No dispositivo Decisioning Elegível na página Visão geral da atividade.](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-eligible-label.png)

Esse rótulo não significa que a atividade sempre será entregue por meio de decisões no dispositivo. Somente quando a at.js 2.5.0+ estiver configurada para usar a tomada de decisão no dispositivo essa atividade será executada no dispositivo. Se o at.js 2.5.0+ não estiver configurado para usar no dispositivo, essa atividade ainda será entregue por meio de uma chamada de servidor feita do at.js.

Você pode filtrar para todas as atividades que estão qualificadas para decisões no dispositivo no [!UICONTROL Atividades] por meio da [!UICONTROL Decisão no dispositivo elegível] filtro.

![On-Device Decisioning Filtro elegível na página Atividades .](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/on-device-decisioning-filter.png)

>[!NOTE]
>
>Depois de criar e ativar uma atividade que é elegível para decisão no dispositivo, ela pode levar de cinco a dez minutos antes de ser incluída no artefato de regras gerado e propagado para o ponto de presenças do Akamai CDN.

## Resumo das etapas para garantir que minhas atividades de decisão no dispositivo sejam entregues por meio da At.js 2.5.0+?

1. Acesse a interface do usuário do Adobe Target e navegue até **[!UICONTROL Administração]** > **[!UICONTROL Implementação]** > **[!DNL Account Details]** para ativar o **[!UICONTROL Decisão no dispositivo]** alternar.
1. Ative o **&quot;[!UICONTROL Incluir todas as atividades qualificadas de decisão no dispositivo existentes no artefato]&quot;** alternar.

   A primeira geração de artefatos de regras JSON pode levar até 10 minutos.

1. Crie e ative um [tipo de atividade compatível com o ON-device decisioning](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/supported-features.md)e verificar se está qualificada para decisão no dispositivo.
1. Defina as **[!UICONTROL Método de decisão]** para **[!UICONTROL &quot;Híbrido&quot;]** ou **[!UICONTROL &quot;Somente no dispositivo&quot;]** por meio da interface do usuário de configurações da at.js.
1. Baixe e implante o At.js 2.5.0+ em suas páginas.
