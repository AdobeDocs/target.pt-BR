---
keywords: dados ambientais;dados de sessão;dados geográficos;dados geográficos;dados do dispositivo;dados móveis;atributos;atributos de perfil;algoritmos de personalização;algoritmos de aprendizado de máquina;algoritmos de aprendizado de máquina
description: Saiba quais dados [!DNL Adobe Target] O coleta e usa o para criar seus algoritmos de aprendizado de máquina do.
title: Quais dados são coletados para criar algoritmos de aprendizado de máquina do?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Automated Personalization
exl-id: 7114a6d6-4779-471e-9b91-646aa49e102a
source-git-commit: 3f64da1c9a1146e4d2d9389d6d5ce764764d2d9c
workflow-type: tm+mt
source-wordcount: '2024'
ht-degree: 52%

---

# Dados usados por algoritmos de aprendizado de máquina do [!DNL Target]

[!DNL Adobe Target] O coleta e usa automaticamente vários dados para criar algoritmos de personalização no [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Direcionamento automático] (AT) atividades. Quando um visitante entra em um [!UICONTROL Automated Personalization] ou [!UICONTROL Direcionamento automático] atividade, um instantâneo das informações é enviado para um conjunto de &quot;registros de treinamento&quot; (os dados do visitante sobre os quais os algoritmos de personalização aprendem).

Para saber mais sobre o [!DNL Target] algoritmos de personalização, consulte [Algoritmo Random Forest](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

## Padrão [!DNL Target] categorias de atributo

A tabela a seguir mostra os dados coletados pelo [!UICONTROL Automated Personalization] e [!UICONTROL Direcionamento automático] atividades por padrão, sem qualquer configuração de [!DNL Target] ou outro [!DNL Adobe] soluções. A tabela também inclui a convenção de nomenclatura usada para indicar esses atributos em [Relatórios de insights de personalização](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). É possível aumentar o conjunto de dados de entrada a qualquer momento. Para saber mais sobre como fazer upload de dados adicionais, consulte  [Fazer upload de dados para o [!DNL Target] algoritmos de personalização](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

| Categoria de dados | Prefixo do sistema | Descrição | Nome de exibição em [!UICONTROL Insights] relatórios |
| --- | --- | --- | --- |
| Parâmetros de ambiente | ENV | Informações sobre o ambiente de um usuário, incluindo sistema operacional, navegador e hora do dia/dia da semana. | Navegador - [Nome do atributo]<br>Sistema operacional - [Valor] |
| Geografia | GEO | Informações sobre a geografia de um usuário, obtidas por pesquisa de IP. | Geo - [atributo geográfico] |
| Dispositivo móvel | MOB | Informações sobre o dispositivo móvel de um usuário. | Dispositivo - [atributo do dispositivo]<br>Dispositivo móvel - [atributo móvel] |
| [!DNL Target] relatórios de segmentos | SEG | Relatórios de segmentos configurados no [!DNL Target] relatórios. | Segmento de relatório -[Nome do segmento] |
| Comportamento da sessão | SES | Informações sobre o comportamento do usuário, como o número de páginas visualizadas. | Perfil do visitante - [Nome do atributo] |

## Personalizado [!DNL Target] categorias de atributo

A tabela a seguir mostra os dados fornecidos pelo cliente coletados pelo [!UICONTROL Automated Personalization] e [!UICONTROL Direcionamento automático] atividades. Esses dados serão coletados somente se você fornecê-los. Nomes de atributos específicos e valores de amostra são específicos da configuração do sistema.

| Categoria de dados | Prefixo do sistema | Descrição | Nome de exibição em [!UICONTROL Insights] relatórios |
| --- | --- | --- | --- |
| Parâmetros da página | CAIXA | Parâmetros de página personalizados (&quot;parâmetros mbox&quot;) passados na chamada para [!DNL Target]. | Personalizado - Parâmetro de mbox - [nome do parâmetro] |
| [!DNL Target] perfil | PRO | Os atributos personalizados do perfil são carregados diretamente no [!DNL Target] perfil por meio da API ou do parâmetro de página e [!DNL Target] scripts de perfil. | Personalizado - Perfil do visitante - [nome do atributo] |
| Atributos do cliente | CRS | Atributos do cliente carregados na [!DNL Target] perfil por meio da [[!DNL Adobe Experience Cloud Customer Attributes Service]](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html){target=_blank}. | Personalizado - Perfil do visitante - [nome do atributo] |
| Parâmetros de URL | URL | URL e parâmetros de URL da página exibida no momento. | Personalizado - Parâmetro de URL - [Parâmetro de URL] |
| URL de referência | REF | URL de referência e quaisquer parâmetros de URL para o URL de referência. | Personalizado - [Parâmetro de URL de referência] - [Valor do parâmetro] |
| [!DNL Adobe Experience Cloud] públicos-alvo compartilhados | AAM | Todos os públicos-alvo compartilhados com [!DNL Target] de outro [!DNL Adobe Experience Cloud] soluções (por exemplo, [!DNL Adobe Audience Manager] e [!DNL Adobe Analytics], por meio da [[!DNL Experience Cloud Audience Library]](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html){target=_blank}). | Personalizado - Público-alvo do Experience Cloud - [Nome do público] |
| [!DNL Adobe Experience Platform Real-time CDP] audiences | UPS | Públicos da CDP em tempo real da Platform compartilhados com [!DNL Target] via [!UICONTROL Destinos]. |  |
| [!DNL Adobe Experience Platform Real-time CDP] atributos | AEP | Atributos da CDP em tempo real da Platform compartilhados com [!DNL Target] via [!UICONTROL Destinos]. |  |

## Bloqueando recursos de [!DNL Target] algoritmos de aprendizado de máquina do

Os recursos podem ser bloqueados de [!DNL Target] algoritmos de aprendizado automatizado, impedindo que sejam usados em qualquer [!UICONTROL Automated Personalization] ou [!UICONTROL Direcionamento automático] modelo ou atividade.

Para obter mais informações, consulte [Visão geral da API de modelos (Incluir na lista de bloqueios)](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api.html){target=_blank} no *[!DNL Adobe Target]Guia do desenvolvedor*.

## Dispositivo e dados móveis {#device-mobile}

| Nome do atributo | Descrição de Atributos | Valores de amostra | Nome do sistema |
| --- | --- | --- | --- |
| Mobile - Device - Brand | A marca do dispositivo móvel que o visitante usou para acessar a atividade. | Apple | MOB_targeting.mobile.vendor |
| Mobile - Device - eReader | Especifica se o dispositivo é um eReader. | 0 é Falso, 1 é Verdadeiro | MOB_targeting.mobile.ereader |
| Mobile - Device - Game Console | Especifica se o dispositivo é um console de jogos. | 0 é Falso, 1 é Verdadeiro | MOB_targeting.mobile.gamesConsole |
| Mobile - Device - Media Player | Especifica se o dispositivo é um tocador de mídia. | 0 é Falso, 1 é Verdadeiro | MOB_targeting.mobile.mediaPlayer |
| Mobile - Device - Mobile Phone | Especifica se o dispositivo é um tocador celular. | 0 é Falso, 1 é Verdadeiro | MOB_targeting.mobile.mobilePhone |
| Mobile - Device - Model Name | O nome do modelo do dispositivo móvel que o visitante usou para acessar a atividade. | iPhone XS | MOB_targeting.mobile.model |
| Device - Set-Top Box | Especifica se o dispositivo é um conversor. | 0 é Falso, 1 é Verdadeiro | MOB_targeting.mobile.setTopBox |
| Mobile - Device - Tablet | Especifica se o dispositivo é um tablet. | 0 é Falso, 1 é Verdadeiro | MOB_targeting.mobile.tablet |
| Mobile - Pixel Density (ppi) | A densidade de pixels do dispositivo móvel que o visitante usou para acessar a atividade. | 1, 2, 3 e assim por diante. | MOB_targeting.mobile.displayPpi |
| Mobile - OS - OS X ([!DNL Android], [!DNL Windows]e assim por diante) | Especifica se o usuário usou um dispositivo OSX (ou [!DNL Android], [!DNL Windows]e assim por diante) para acessar a atividade. | 0 é Falso, 1 é Verdadeiro | MOB_targeting.mobile.os[SO]<br>Por exemplo, MOB_targeting.mobile.osOSx, MOB_targeting.mobile.osWindows, MOB_targeting.mobile.osAndroid, MOB_targeting.mobile.osLinux |
| Mobile - Screen Height (px) | A altura da tela do dispositivo móvel que o visitante usou para acessar a atividade. | 1, 2, 3 e assim por diante. | MOB_targeting.mobile.displayHeight |
| Mobile - Screen Width (px) | A largura da tela do dispositivo móvel (em pixels) que o visitante usou para acessar a atividade. | 1, 2, 3 e assim por diante. | MOB_targeting.mobile.displayWidth |

## Dados ambientais {#env}

| Nome do atributo | Descrição de Atributos | Valores de amostra | Nome do sistema |
| --- | --- | --- | -- |
| Browser - Day of Week | O dia da semana em que o visitante acessou a atividade. | 0 – 6.<br>(0 é domingo) | ENV_DayOfWeek |
| Browser - Hour of Day | A hora do dia em que o visitante acessou a atividade. | 0 - 23<br>(0 é meia-noite) | ENV_UserHour |
| Browser - Hour of Week | A hora da semana em que o visitante acessou a atividade. | 0 - 168<br>(domingo à meia-noite é 0) | ENV_WeekHour |
| Browser - Language Setting | O idioma especificado no navegador do visitante usado para acessar a atividade. | English<br>German | ENV_Language |
| Browser - Time of Day | A hora do navegador do dia em que o visitante acessou a atividade. | 0, 6, 12, 18<br>(0 é noite, 6 é de manhã,<br>12 é de tarde, 18 é fim do dia) | ENV_LocalTimePeriod |
| Browser - Timezone | O fuso horário do visitante ao acessar a atividade. | Pacific Time<br>Eastern Time<br>GMT | ENV_BrowserTimezoneOffsetMinutes |
| Browser - Type | O tipo de navegador usado pelo visitante ao acessar a atividade. | [!DNL Chrome]<br>[!DNL Firefox]<br>[!DNL Internet Explorer]<br>[!DNL Safari]<br>Outras | ENV_Browser |
| Browser - Weekday/Weekend | O status de trabalho quando o visitante acessou a atividade (fim de semana, horário de trabalho ou tempo livre durante a semana). | Sábado e domingo são fim de semana<br>Segunda a sexta-feira 0900 - 1800 é o horário de trabalho<br>Segunda a sexta depois de 1800 até 0900 é o tempo livre da semana | ENV_UserHourType |
| Browser - Window Height (px) | A altura da janela do navegador (em pixels) que o visitante usou para acessar a atividade. | 1, 2, 3 e assim por diante, | ENV_BrowserHeight |
| Browser - Window Width (px) | A largura da janela do navegador (em pixels) que o visitante usou para acessar a atividade. | 1, 2, 3 e assim por diante, | ENV_BrowserWidth |
| Device - Screen Height (px) | A altura da tela do dispositivo que o visitante usou para acessar a atividade. | 1, 2, 3 e assim por diante, | ENV_ScreenHeight |
| Device - Screen Width (px) | A largura da tela do dispositivo que o visitante usou para acessar a atividade. | 1, 2, 3 e assim por diante, | ENV_ScreenWidth |
| Sistema operacional | O sistema operacional no dispositivo que o visitante usou para acessar a atividade. | [!DNL Mac OS]<br>[!DNL Windows]<br>[!DNL Linux]<br>Pesquisar bot<br>SO desconhecido | ENV_OperatingSystem |
| Operating System - Version | A versão do sistema operacional no dispositivo que o visitante usou para acessar a atividade. | [!DNL Windows] 10<br>[!DNL Mac OS] 10 | ENV_OperatingSystemVersion |
| Traffic Sources - Referring Landing Page URL | A primeira página que o visitante viu ao acessar seu site. | `https://www.adobe.com/ecloud.html` | ENV_Referrer |

## Dados geográficos {#geo}

| Nome do atributo | Descrição de Atributos | Valores de amostra | Nome do sistema |
| --- | --- | --- | --- |
| Geo - City | A cidade da qual o visitante acessou a atividade. | São Francisco | Geo_City |
| Geo - Country | O país do qual o visitante acessou a atividade. | Alemanha | Geo_Country |
| Geo - DMA | A Área de marketing designada (DMA) da qual o visitante acessou a atividade. | Charlottesville | Geo_DMA |
| Geo - Latitude | A latitude da qual o visitante acessou a atividade. | 47,269<br>Arredondado para três casas decimais (precisão de aproximadamente 100 metros) | GEO_Latitude |
| Geo - Longitude | A longitude da qual o visitante acessou a atividade. | -122.269<br>Arredondado para três casas decimais (precisão de aproximadamente 100 metros) | GEO_Longitude |
| Geo - State/Region | O estado do qual o visitante acessou a atividade. | Utah<br>New South Wales | GEO_State<br>GEO_Region |
| Geo - Zip Code | O CEP do qual o visitante acessou a atividade. | 84004 | GEO_ZipCode |
| Mobile - Carrier | A operadora de celular que o visitante usou ao acessar a atividade. | [!DNL Vodafone]<br>[!DNL T-Mobile] | GEO_mobileCarrier |
| Network - Connection Speed | A velocidade da conexão de rede do dispositivo quando o visitante acessou a atividade. | Broadband<br>Cable<br>DSL<br>Mobile<br>Wireless<br>Satellite | GEO_ConnectionSpeed |
| Network - Domain Name | O nome do domínio de rede do qual o visitante acessou a atividade. | `nnt.net` | GEO_DomainName |
| Network - ISP | A rede da qual o visitante acessou a atividade. | nnt communications corporation | GEO_IspName |

## Dados da sessão {#session}

| Nome do atributo | Descrição de Atributos | Valores de amostra | Nome do sistema |
| --- | --- | --- | --- |
| Visitor Profile - Activity Lifetime Order Value | Especifica a soma de todos os valores de pedidos em todas as visitas/sessões para uma atividade específica. | Dupla | SES_CUMULATIVE_ORDER_VALUE |
| Visitor Profile - Activity Lifetime Time on Site | Especifica o tempo total do visitante no site, excluindo a sessão atual e é atualizado quando a sessão expira. | Duplo, milissegundos | SES_TOTAL_TIME |
| Visitor Profile -Average Page Views per Visit during Activity | Especifica o número médio de exibições de páginas por sessão, excluindo a sessão atual. | Dupla | SES_REQUESTS_PER_SESSION |
| Visitor Profile - Average Time per Visit | Especifica o tempo médio gasto por visita/sessão. Isso não inclui a sessão atual. | Duplo, milissegundos | SES_TIME_PER_SESSION |
| Visitor Profile - First Visit | Especifica a hora da primeira visita que o usuário interagiu com o [!DNL Target]. | Duplo, milissegundos | SES_PROFILE_CREATION_TIME |
| Visitor Profile - Hours since Last Visit | Especifica as horas desde a última visita para essa atividade em particular. | Duplo (apenas número positivo inteiro) 1, 2, 3 e assim por diante. | SES_HOURS_SINCE_LAST_VISIT |
| Visitor Profile - Impressions of Location/Content | Especifica o número de impressões para uma combinação específica de local/conteúdo em uma atividade específica. | Duplo (apenas número positivo inteiro) 1, 2, 3 e assim por diante. | SES_CUMULATIVE_ACTION_[LOCATION_ID]_[CONTENT_ID] |
| Perfil do visitante - Último [!DNL Target] Interação | Especifica a hora da última interação com o [!DNL Target]. A interação acontece em cada [!DNL Target] devido à atual implementação do [!DNL Target] O atualiza o perfil em cada solicitação. | Duplo, milissegundos | SES_PROFILE_UPDATE_TIME |
| Visitor Profile - Pages Seen Before Activity | Especifica o número total de exibições de página (impressões), incluindo a visita/sessão atual, até o visitante entrar na atividade. | Duplo (apenas número positivo inteiro) 1, 2, 3 e assim por diante. | SES_TOTAL_PAGE_VIEWS |
| Visitor Profile - Page Views in Current Visit | Especifica o número de exibições de página na visita/sessão atual, até o visitante entrar na atividade. Mais precisamente, o número de impressões. Essas impressões não são exibições de páginas reais, mas sim o número de vezes que a solicitação atingiu o [!DNL Target]. [!DNL Target] O não consegue distinguir entre tempos limite ou quaisquer outros motivos pelos quais o usuário não recebeu ou visualizou o conteúdo. | Duplo (apenas número positivo inteiro) | SES_SESSION_POSITION |
| Visitor Profile - Start of Current Visit | Especifica o momento em que a visita/sessão atual com [!DNL Target] iniciado. A visita com [!DNL Target] pode ser iniciado sem inserir uma atividade. Basta uma chamada para qualquer [!DNL Target] solicitação. Um visitante pode levar algum tempo até inserir a atividade e o instantâneo ser tirado. | Duplo, milissegundos | SES_SESSION_START |
| Visitor Profile - Start of Most Recent Visit | Especifica o momento em que a última visita/sessão com [!DNL Target] iniciado. Esse atributo é atualizado quando a sessão expira.<br>Se essa for a primeira sessão do visitante, ela resultará em `LAST_SESSION_START = 0.` | Duplo, milissegundos | SES_LAST_SESSION_START |
| Visitor Profile - Time Since Most Recent Visit When First Enter Activity | Especifica a duração entre a sessão anterior e a hora em que o usuário entra na atividade e o instantâneo é tirado. | Duplo, milissegundos | SES_RECENCY |
| Visitor Profile - Time in Visit Before Enter Activity | Especifica a diferença entre a última interação com [!DNL Target] e quando a visita atual começou. Esse atributo pode ser considerado duração da visita/sessão, até que o usuário entre na atividade e o instantâneo seja tirado.<br>Valores negativos ocorrem quando o início da sessão e o a hora da última atualização são acionados pela mesma [!DNL Target] chame. Valores negativos devem ser considerados como 0 (zero). | Duplo, milissegundos | SES_SESSION_TIME |
| Perfil do visitante - Visitas totais | Especifica o número total de visitas/sessões. Isso não inclui a visita/sessão atual. | Duplo (apenas número positivo inteiro) 1, 2, 3 e assim por diante. | SES_TOTAL_SESSIONS |
| Visitor Profile - Total Visits to Activity | Especifica o número de visitas a uma atividade específica. Se não houver visita anterior, retorna 0 (zero). | Duplo (apenas número positivo inteiro) 1, 2, 3 e assim por diante. | SES_PREVIOUS_VISIT_COUNT |
| Visitor Profile - Total Visits to Activity with Conversion | Especifica o número de visitas/sessões a uma atividade específica quando houve pelo menos uma conversão durante a visita. | Dupla | SES_CUMULATIVE_SUCCESS |
| Visitor Profile - Visits to Activity with No Conversion | Número de visitas/sessões sem conversões a uma atividade específica. Esse valor é redefinido como zero depois da conversão ou -1 se a conversão nunca tiver ocorrido. | Duplo (apenas número positivo inteiro) 1, 2, 3 e assim por diante. | SES_SUCCESS_RECENCY |
