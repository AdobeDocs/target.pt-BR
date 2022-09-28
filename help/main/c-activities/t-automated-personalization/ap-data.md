---
keywords: dados ambientais; dados de sessão; dados geográficos; dados geográficos; dados do dispositivo; dados móveis; atributos; atributos do perfil; algoritmos de personalização; algoritmos de aprendizado de máquina; algoritmos de aprendizado de máquina
description: Saiba qual Adobe de dados [!DNL Target] O coleta e usa o para criar seus algoritmos de aprendizado automatizado.
title: Quais dados são coletados para criar algoritmos de aprendizado de máquina?
feature: Automated Personalization
exl-id: 7114a6d6-4779-471e-9b91-646aa49e102a
source-git-commit: ca1f42b95399fbd136aee27ccec9ed0e38876234
workflow-type: tm+mt
source-wordcount: '2085'
ht-degree: 49%

---

# ![PREMIUM](/help/main/assets/premium.png) Dados usados por [!DNL Target] algoritmos de aprendizado automatizado

[!DNL Adobe Target] O coleta e usa automaticamente uma variedade de dados para criar seus algoritmos de personalização no [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Direcionamento automático] (AT). Quando um visitante entra em uma atividade de AP ou AT, um instantâneo das informações é enviado para um conjunto de &quot;registros de treinamento&quot; (os dados do visitante sobre os quais os algoritmos de personalização aprenderão).

Para saber mais sobre o [!DNL Target] algoritmos de personalização, consulte [Algoritmo Random Forest](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

## Padrão [!DNL Adobe Target] categorias de atributos

A tabela a seguir mostra os dados coletados por [!UICONTROL Automated Personalization] e [!UICONTROL Direcionamento automático] por padrão, sem nenhuma configuração de [!DNL Target] ou outro [!DNL Adobe] , bem como a convenção de nomenclatura usada para indicar esses atributos em [Relatórios de insights de personalização](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). É possível aumentar o conjunto de dados de entrada a qualquer momento. Para saber mais sobre como fazer upload de dados adicionais, consulte  [Upload de dados para o [!DNL Target] algoritmos de personalização](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

| Categoria de dados | Prefixo do sistema | Descrição | Exibir nome em [!UICONTROL Insights] relatórios |
| --- | --- | --- | --- |
| Parâmetros de ambiente | ENV | Informações sobre o ambiente de um usuário, incluindo sistema operacional, navegador e hora do dia/dia da semana. | Navegador - [Nome do atributo]<br>Sistema operacional - [Valor] |
| Geografia | GEO | Informações sobre a geografia de um usuário, obtidas por meio da pesquisa de IP. | Geografia - [atributo geográfico] |
| Dispositivo móvel | MOB | Informações sobre o dispositivo móvel de um usuário. | Dispositivo - [atributo do dispositivo]<br>Dispositivo móvel - [atributo móvel] |
| Segmentos de relatórios do Target | SEG | Relatórios de segmentos configurados em [!DNL Target] relatórios. | Segmento de relatório -[Nome do segmento] |
| Comportamento da sessão | SES | Informações sobre o comportamento do usuário, como o número de páginas visualizadas. | Perfil do visitante - [Nome do atributo] |

## Categorias de atributos personalizadas do Adobe Target

A tabela a seguir mostra os dados fornecidos pelo cliente coletados pelo [!UICONTROL Automated Personalization] e [!UICONTROL Direcionamento automático] atividades. Esses dados são coletados somente se você fornecê-los. Nomes de atributos específicos e valores de amostra serão específicos da configuração do sistema.

| Categoria de dados | Prefixo do sistema | Descrição | Exibir nome em [!UICONTROL Insights] relatórios |
| --- | --- | --- | --- |
| Parâmetros da página | CAIXA | Parâmetros de página personalizados (&quot;parâmetros de mbox&quot;) passados na chamada para [!DNL Target]. | Personalizado - Parâmetro Mbox - [nome do parâmetro] |
| [!DNL Target] perfil | PRO | Atributos de perfil personalizados enviados diretamente para a [!DNL Target] perfil via API ou parâmetro de página e [!DNL Target] scripts de perfil. | Personalizado - Perfil do visitante - [nome do atributo] |
| Atributos do cliente | CRS | Atributos do cliente carregados no [!DNL Target] através do [Serviço de atributos do cliente da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html){target=_blank}. | Personalizado - Perfil do visitante - [nome do atributo] |
| Parâmetros de URL | URL | URL e quaisquer parâmetros de URL da página exibida no momento. | Personalizado - Parâmetro de URL - [Parâmetro de URL] |
| URL de referência | REF | URL de referência e quaisquer parâmetros de URL para a URL de referência. | Personalizado - [Parâmetro de URL de referência] - [Valor do parâmetro] |
| Públicos-alvo compartilhados da Adobe Experience Cloud | AAM | Todos os públicos-alvo compartilhados com [!DNL Target] de outros [!DNL Adobe Experience Cloud] soluções (por exemplo, [!DNL Adobe Audience Manager] e [!DNL Adobe Analytics], por meio da [[!DNL Experience Cloud Audience Library]](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html){target=_blank}). | Personalizado - Público-alvo do Experience Cloud - [Nome do público-alvo] |
| Públicos-alvo da CDP em tempo real da Adobe Experience Platform | UPS | Públicos-alvo da CDP em tempo real da AEP compartilhados com [!DNL Target] via Destinations. |  |
| Atributos de CDP em tempo real da Adobe Experience Platform | AEP | Atributos da CDP em tempo real da AEP compartilhados com [!DNL Target] via Destinations. Esse recurso está atualmente na versão beta. |  |

## Bloquear recursos de [!DNL Target] algoritmos de aprendizado automatizado

Os recursos podem ser bloqueados de [!DNL Target] algoritmos de aprendizado automatizado, impedindo que sejam usados em [!UICONTROL Direcionamento automático] ou [!UICONTROL Automated Personalization] modelo ou atividade.

Para bloquear uma categoria de recursos do [!DNL Target] algoritmos de aprendizado automatizado, contato [Atendimento ao cliente do Adobe](/help/main/cmp-resources-and-contact-information.md#section_CC8B206F58D6495C9372D5C0D4055CF6) e especifique as categorias de recursos que deseja bloquear, usando o(s) Prefixo(s) do sistema fornecido(s) acima.

Para bloquear um ou mais recursos específicos do [!DNL Target] algoritmos de aprendizado automatizado, contato [Atendimento ao cliente do Adobe](/help/main/cmp-resources-and-contact-information.md#section_CC8B206F58D6495C9372D5C0D4055CF6) e especifique os nomes de recursos específicos que devem ser bloqueados, usando os nomes de sistema fornecidos abaixo. As seções a seguir contêm informações detalhadas sobre os vários tipos de dados, incluindo nomes de atributos, descrições e valores de amostra.

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
| Mobile - Pixel Density (ppi) | A densidade de pixels do dispositivo móvel que o visitante usou para acessar a atividade. | 1, 2, 3, etc. | MOB_targeting.mobile.displayPpi |
| Dispositivo móvel - SO – OSX (Android, Windows, etc.) | Especifica se o usuário usou um dispositivo OSX (ou Android, Windows etc.) para acessar a atividade. | 0 é Falso, 1 é Verdadeiro | MOB_targeting.mobile.os[SO]<br>Por exemplo, MOB_targeting.mobile.osOSx, MOB_targeting.mobile.osWindows, MOB_targeting.mobile.osAndroid, MOB_targeting.mobile.osLinux |
| Mobile - Screen Height (px) | A altura da tela do dispositivo móvel que o visitante usou para acessar a atividade. | 1, 2, 3, etc. | MOB_targeting.mobile.displayHeight |
| Mobile - Screen Width (px) | A largura da tela do dispositivo móvel (em pixels) que o visitante usou para acessar a atividade. | 1, 2, 3, etc. | MOB_targeting.mobile.displayWidth |

## Dados ambientais {#env}

|Nome do atributo|Descrição do atributo|Valores de amostra|Nome do sistema| | — | — | — | — | |Navegador - Dia da semana|O dia da semana em que o visitante acessou a atividade.|0 a 6.<br>(0 é domingo)|ENV_DayOfWeek| |Navegador - Hora do dia|A hora do dia em que o visitante acessou a atividade.|0 a 23<br>(0 é meia-noite)|ENV_UserHour| |Navegador - Hora da semana|A hora da semana em que o visitante acessou a atividade.|0 a 168<br>(A meia-noite de domingo é 0)|ENV_WeekHour| |Navegador - Configuração de idioma|O idioma especificado no navegador do visitante usado para acessar a atividade.|Inglês<br>Alemão|ENV_Language| |Navegador - Hora do dia|A hora do navegador do dia em que o visitante acessou a atividade.|0, 6, 12, 18<br>(0 é noite, 6 é manhã,<br>12 é tarde, 18 é noite)|ENV_LocalTimePeriod| |Browser - Timezone|O fuso horário do visitante ao acessar a atividade.|Hora do Pacífico<br>Hora do Leste<br>GMT|ENV_BrowserTimezoneOffsetMinutes| |Navegador - Tipo|O tipo de navegador que o visitante usou ao acessar a atividade.|Chrome<br>Firefox<br>Internet Explorer<br>Safari<br>Outros|ENV_Browser| |Browser - Weekday/Weekend|O status de trabalho quando o visitante acessou a atividade (fim de semana, horário de trabalho ou tempo livre semanal).|Sábado e domingo é fim de semana<br>Segunda à sexta-feira 0900 a 1800 é o horário de trabalho<br>Segunda à sexta-feira depois de 1800 até 0900 é o tempo livre da semana|ENV_UserHourType| |Browser - Window Height (px)|A altura da janela do navegador (em pixels) que o visitante usou para acessar a atividade.|1, 2, 3, etc.|ENV_BrowserHeight| |Browser - Window Width (px)|A largura da janela do navegador (em pixels) que o visitante usou para acessar a atividade.|1, 2, 3, etc.|ENV_BrowserWidth| |Dispositivo - Altura de tela (px)|A altura da tela do dispositivo que o visitante usou para acessar a atividade.|1, 2, 3, etc.|ENV_ScreenHeight| |Dispositivo - Largura de tela (px)|A largura de tela do dispositivo que o visitante usou para acessar a atividade.|1, 2, 3, etc.|ENV_ScreenWidth| |Sistema operacional|O sistema operacional no dispositivo do visitante usado para acessar a atividade.|Mac OS<br>Windows<br>Linux<br>Bot de pesquisa<br>SO desconhecido|ENV_OperatingSystem| |Sistema operacional - Versão|A versão do sistema operacional que o visitante usou para acessar a atividade.|Windows 10<br>Mac OS 10|ENV_OperatingSystemVersion| |Fontes de tráfego - URL da página de aterrissagem de referência|A primeira página que o visitante viu ao acessar seu site.|`https://www.adobe.com/ecloud.html`|ENV_Referrer|

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
| Mobile - Carrier | A operadora de celular que o visitante usou ao acessar a atividade. | Vodafone<br>T-Mobile | GEO_mobileCarrier |
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
| Visitor Profile - Hours since Last Visit | Especifica as horas desde a última visita para essa atividade em particular. | Duplo (apenas número positivo inteiro) 1, 2, 3, etc. | SES_HOURS_SINCE_LAST_VISIT |
| Visitor Profile - Impressions of Location/Content | Especifica o número de impressões para uma combinação específica de local/conteúdo em uma atividade específica. | Duplo (apenas número positivo inteiro) 1, 2, 3, etc. | SES_CUMULATIVE_ACTION_[LOCATION_ID]_[CONTENT_ID] |
| Perfil do visitante - Último [!DNL Target] Interação | Especifica a hora da última interação com o [!DNL Target]. A interação acontece em cada [!DNL Target] porque a implementação atual de [!DNL Target] atualiza o perfil em cada solicitação. | Duplo, milissegundos | SES_PROFILE_UPDATE_TIME |
| Visitor Profile - Pages Seen Before Activity | Especifica o número total de exibições de páginas (impressões), incluindo a visita/sessão atual, até o visitante entrar na atividade. | Duplo (apenas número positivo inteiro) 1, 2, 3, etc. | SES_TOTAL_PAGE_VIEWS |
| Visitor Profile - Page Views in Current Visit | Especifica o número total de exibições de páginas na visita/sessão atual, até o visitante entrar na atividade. Mais precisamente, o número de impressões. Essas impressões não são exibições de páginas reais, mas sim o número de vezes que a solicitação atingiu o Target. O Target não consegue distinguir entre limites de tempo ou quaisquer outros motivos pelos quais o usuário não recebeu ou visualizou o conteúdo. | Duplo (apenas número positivo inteiro) | SES_SESSION_POSITION |
| Visitor Profile - Start of Current Visit | Especifica o momento em que a visita/sessão atual com o Target foi iniciada. A visita com o Target pode ser iniciada sem inserir uma atividade. Tudo o que é necessário é uma chamada para qualquer [!DNL Target] solicitação. Um visitante pode levar um tempo, até inserir a atividade e o instantâneo ser tirado. | Duplo, milissegundos | SES_SESSION_START |
| Visitor Profile - Start of Most Recent Visit | Especifica o horário de quando a última visita/sessão com [!DNL Target] iniciado. Esse atributo é atualizado quando a sessão expira.<br>Se essa for a primeira sessão do visitante, ela resultará em `LAST_SESSION_START = 0.` | Duplo, milissegundos | SES_LAST_SESSION_START |
| Visitor Profile - Time Since Most Recent Visit When First Enter Activity | Especifica a duração entre a sessão anterior e a hora em que o usuário entra na atividade e o instantâneo é tirado. | Duplo, milissegundos | SES_RECENCY |
| Visitor Profile - Time in Visit Before Enter Activity | Especifica a diferença entre a última interação com [!DNL Target] e quando a visita atual começou. Esse atributo pode ser considerado duração da visita/sessão, até que o usuário entre na atividade e o instantâneo seja tirado.<br>[!DNL Target]Valores negativos ocorrem quando o início da sessão e o a hora da última atualização são acionados pela mesma chamada de Valores negativos devem ser considerados como 0 (zero). | Duplo, milissegundos | SES_SESSION_TIME |
| Perfil do visitante - Visitas totais | Especifica o número total de visitas/sessões. Isso não inclui a visita/sessão atual. | Duplo (apenas número positivo inteiro) 1, 2, 3, etc. | SES_TOTAL_SESSIONS |
| Visitor Profile - Total Visits to Activity | Especifica o número de visitas a uma atividade específica. Se não houver visita anterior, retorna 0 (zero). | Duplo (apenas número positivo inteiro) 1, 2, 3, etc. | SES_PREVIOUS_VISIT_COUNT |
| Visitor Profile - Total Visits to Activity with Conversion | Especifica o número de visitas/sessões a uma atividade específica quando houve pelo menos uma conversão durante a visita. | Dupla | SES_CUMULATIVE_SUCCESSES |
| Visitor Profile - Visits to Activity with No Conversion | Número de visitas/sessões sem conversões a uma atividade específica. Esse valor é redefinido como zero depois da conversão ou -1 se a conversão nunca tiver ocorrido. | Duplo (apenas número positivo inteiro) 1, 2, 3, etc. | SES_SUCCESS_RECENCY |
