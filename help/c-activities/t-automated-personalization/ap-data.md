---
keywords: environmental data;session data;geo data;geographical data;device data;mobile data;attributes;profile attributes
description: O Adobe Target coleta e usa automaticamente uma variedade de dados para criar algoritmos de personalização nas atividades Personalização automatizada (AP) e Direcionamento automático (AT). Quando um visitante entra na atividade de AP ou AT, um instantâneo das informações é enviado para um conjunto de "registros de treinamento" (os dados do visitante sobre os quais os algoritmos de personalização aprenderão).
title: Coleta de dados para os algoritmos de personalização do Adobe Target
feature: Automated Personalization
translation-type: tm+mt
source-git-commit: 4adade56529fb95e4400e06d04d3c6c69e120edc
workflow-type: tm+mt
source-wordcount: '1754'
ht-degree: 92%

---


# ![PREMIUM](/help/assets/premium.png) Coleta de dados para os algoritmos de personalização do Target

[!DNL Adobe Target] coleta e usa automaticamente uma variedade de dados para criar seus algoritmos de personalização nas atividades  [!UICONTROL Automated Personalization] (AP) e  [!UICONTROL Auto-Público alvo] (AT). Quando um visitante entra em uma atividade AP ou AT, um instantâneo das informações é passado para um conjunto de &quot;registros de treinamento&quot; (os dados do visitante que os algoritmos de personalização conhecerão).

Para saber mais sobre os algoritmos de personalização do Target, consulte  [Algoritmo Random Forest](/help/c-activities/t-automated-personalization/algo-random-forest.md).

A tabela a seguir mostra os dados coletados por [!UICONTROL Automated Personalization] e [!UICONTROL Público alvo automático] por padrão, sem que o comerciante tenha que fazer nada, bem como a convenção de nomenclatura usada para indicar esses atributos em [Relatórios de insights de personalização](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). É possível aumentar o conjunto de dados de entrada a qualquer momento. Para saber mais sobre como fazer upload de dados adicionais, consulte  [Fazer upload de dados para os algoritmos de personalização do Target](/help/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

| Tipo de dados | Descrição | Convenção de nomenclatura do tipo de dados | Atributos de exemplo |
| --- | --- | --- | --- |
| [Dispositivo e dados móveis](#device-mobile) | Informações específicas sobre dispositivos e dispositivos móveis.<br>Consulte &quot;Dispositivo e dados móveis&quot; a seguir. | `Device - [device attribute]`<br>`Mobile - [mobile attribute]` | SO do dispositivo móvel<br>Tamanho de tela do dispositivo móvel |
| [Dados ambientais](#env) | Informações sobre o sistema operacional do visitante e como e quando ele está acessando a atividade. | `Browser - / Operating System] - [Attribute Name]` | Browser - Type |
| Segmento da Experience Cloud | Públicos criados no Audience Manager ou Analytics e compartilhados na Experience Cloud | `Custom - Experience Cloud Audience - [Audience Name]` | Dados personalizados |
| [Dados geográficos](#geo) | Informações sobre onde o visitante está localizado.<br>Consulte &quot;Dados geográficos&quot; a seguir. | `Geo - [geo attribute]` | Cidade<br>País<br>Região/Estado<br>CEP<br>Latitude<br>Longitude<br>ISP ou Operadora de celular |
| Atributos do perfil | Scripts ou atributos de perfil carregados diretamente no perfil do Target por meio da API de atualização | `Custom - Visitor Profile - [attribute name]` | Dados personalizados |
| Parâmetros de URL de referência | Em geral, o URL de referência é o URL que se refere a uma página específica que iniciou a chamada do Público alvo.<br>Observe que esta variável pode ser afetada pela atividade dos usuários no site, bem como pela implementação técnica do site. | `Custom - [Referring URL Parameter] - [Parameter value]` | Dados personalizados |
| Segmentos de relatórios | Quaisquer segmentos definidos na configuração da atividade. | `Reporting Segment -[Segment Name]` | Dados personalizados |
| [Dados da sessão](#session) | Informações sobre o comportamento do visitante na sessão ao acessar a atividade. | `Visitor Profile - [Attribute Name]` | Visitor Profile - Start of Most Recent Visit |
| Parâmetros de URL | O Target inspeciona o URL para extrair os parâmetros de URL. | `Custom - URL Parameter - [URL Parameter]` | Dados personalizados |

As seções a seguir contêm informações detalhadas sobre os vários tipos de dados, incluindo nomes de atributos, descrições e valores de amostra.

## Dispositivo e dados móveis {#device-mobile}

| Nome do atributo | Descrição de Atributos | Valores de amostra |
| --- | --- | --- |
| Mobile - Device - Brand | A marca do dispositivo móvel que o visitante usou para acessar a atividade. | Apple |
| Mobile - Device - eReader | Especifica se o dispositivo é um eReader. | 0 é Falso, 1 é Verdadeiro |
| Mobile - Device - Game Console | Especifica se o dispositivo é um console de jogos. | 0 é Falso, 1 é Verdadeiro |
| Mobile - Device - Media Player | Especifica se o dispositivo é um tocador de mídia. | 0 é Falso, 1 é Verdadeiro |
| Mobile - Device - Mobile Phone | Especifica se o dispositivo é um tocador celular. | 0 é Falso, 1 é Verdadeiro |
| Mobile - Device - Model Name | O nome do modelo do dispositivo móvel que o visitante usou para acessar a atividade. | iPhone XS |
| Device - Set-Top Box | Especifica se o dispositivo é um conversor. | 0 é Falso, 1 é Verdadeiro |
| Mobile - Device - Tablet | Especifica se o dispositivo é um tablet. | 0 é Falso, 1 é Verdadeiro |
| Mobile - Pixel Density (ppi) | A densidade de pixels do dispositivo móvel que o visitante usou para acessar a atividade. | 1, 2, 3, etc. |
| Dispositivo móvel - SO – OSX (Android, Windows, etc.) | Especifica se o usuário usou um dispositivo OSX (ou Android, Windows etc.) para acessar a atividade. | 0 é Falso, 1 é Verdadeiro |
| Mobile - Screen Height (px) | A altura da tela do dispositivo móvel que o visitante usou para acessar a atividade. | 1, 2, 3, etc. |
| Mobile - Screen Width (px) | A largura da tela do dispositivo móvel (em pixels) que o visitante usou para acessar a atividade. | 1, 2, 3, etc. |

## Dados ambientais{#env}

| Nome do atributo | Descrição de Atributos | Valores de amostra |
| --- | --- | --- |
| Browser - Day of Week | O dia da semana em que o visitante acessou a atividade. | 0 a 6.<br>(0 é domingo) |
| Browser - Hour of Day | A hora do dia em que o visitante acessou a atividade. | 0 a 23<br>(0 é meia-noite) |
| Browser - Hour of Week | A hora da semana em que o visitante acessou a atividade. | 0 a 168<br>(a meia-noite de domingo é 0) |
| Browser - Language Setting | O idioma especificado no navegador do visitante usado para acessar a atividade. | English<br>German |
| Browser - Screen Height (px) | A altura da tela do navegador do dispositivo que o visitante usou para acessar a atividade. | 1, 2, 3, etc. |
| Browser - Time of Day | A hora do navegador do dia em que o visitante acessou a atividade. | 0, 6, 12, 18<br>(0 é noite, 6 é de manhã,<br>12 é de tarde, 18 é fim do dia) |
| Browser - Timezone | O fuso horário do visitante ao acessar a atividade. | Pacific Time<br>Eastern Time<br>GMT |
| Navegador - Tipo | O tipo de navegador usado pelo visitante ao acessar a atividade. | Chrome<br>Firefox<br>Internet Explorer<br>Safari<br>Other |
| Browser - Weekday/Weekend | O status de trabalho quando o visitante acessou a atividade (fim de semana, horário de trabalho ou tempo livre durante a semana). | Sábado e domingo é fim de semana<br>Segunda à sexta-feira 0900 a 1800 é o horário de trabalho<br>Segunda feira depois de 1800 até 0900 é o tempo livre da semana |
| Browser - Window Height (px) | A altura da janela do navegador (em pixels) que o visitante usou para acessar a atividade. | 1, 2, 3, etc. |
| Browser - Window Width (px) | A largura da janela do navegador (em pixels) que o visitante usou para acessar a atividade. | 1, 2, 3, etc. |
| Device - Screen Height | A altura da tela do dispositivo que o visitante usou para acessar a atividade. | 1, 2, 3, etc. |
| Device - Screen Width | A largura da tela do dispositivo que o visitante usou para acessar a atividade. | 1, 2, 3, etc. |
| Sistema operacional | O sistema operacional no dispositivo que o visitante usou para acessar a atividade. | Mac OS<br>Windows<br>Linux<br>Search Bot<br>OS Unknown |
| Operating System - Version | A versão do sistema operacional no dispositivo que o visitante usou para acessar a atividade. | Windows 10<br>Mac OS 10 |
| Traffic Sources - Referring Landing Page URL | A primeira página que o visitante viu ao acessar seu site. | `https://www.adobe.com/ecloud.html` |

## Dados geográficos {#geo}

| Nome do atributo | Descrição de Atributos | Valores de amostra |
| --- | --- | --- |
| Geo - City | A cidade da qual o visitante acessou a atividade. | São Francisco |
| Geo - Country | O país do qual o visitante acessou a atividade. | Alemanha |
| Geo - DMA | A Área de marketing designada (DMA) da qual o visitante acessou a atividade. | Charlottesville |
| Geo - Latitude | A latitude da qual o visitante acessou a atividade. | 47,269<br>Arredondado para três casas decimais (precisão de aproximadamente 100 metros) |
| Geo - Longitude | A longitude da qual o visitante acessou a atividade. | -122.269<br>Arredondado para três casas decimais (precisão de aproximadamente 100 metros) |
| Geo - State/Region | O estado do qual o visitante acessou a atividade. | Utah<br>New South Wales |
| Geo - Zip Code | O CEP do qual o visitante acessou a atividade. | 84004 |
| Mobile - Carrier | A operadora de celular que o visitante usou ao acessar a atividade. | Vodafone<br>T-Mobile |
| Network - Connection Speed | A velocidade da conexão de rede do dispositivo quando o visitante acessou a atividade. | Broadband<br>Cable<br>DSL<br>Mobile<br>Wireless<br>Satellite |
| Network - Domain Name | O nome do domínio de rede do qual o visitante acessou a atividade. | `nnt.net` |
| Network - ISP | A rede da qual o visitante acessou a atividade. | nnt communications corporation |

## Dados da sessão {#session}

| Nome do atributo | Descrição de Atributos | Valores de amostra |
| --- | --- | --- |
| Visitor Profile - Activity Lifetime Order Value | Especifica a soma de todos os valores de pedidos em todas as visitas/sessões para uma atividade específica. | Dupla |
| Visitor Profile - Activity Lifetime Time on Site | Especifica o tempo total do visitante no site, excluindo a sessão atual e é atualizado quando a sessão expira. | Duplo, milissegundos |
| Visitor Profile -Average Page Views per Visit during Activity | Especifica o número médio de exibições de páginas por sessão, excluindo a sessão atual. | Dupla |
| Visitor Profile - Average Time per Visit | Especifica o tempo médio gasto por visita/sessão. Isso não inclui a sessão atual. | Duplo, milissegundos |
| Visitor Profile - First Visit | Especifica a hora da primeira visita que o usuário interagiu com o Target. | Duplo, milissegundos |
| Visitor Profile - Hours since Last Visit | Especifica as horas desde a última visita para essa atividade em particular. | Duplo (apenas número positivo inteiro) 1, 2, 3, etc. |
| Visitor Profile - Impressions of Location/Content | Especifica o número de impressões para uma combinação específica de local/conteúdo em uma atividade específica. | Duplo (apenas número positivo inteiro) 1, 2, 3, etc. |
| Visitor Profile - Last Target Interaction | Especifica a hora da última interação com o Target. A interação ocorre em cada solicitação [!DNL Target] porque a implementação atual de [!DNL Target] atualiza o perfil em cada solicitação. | Duplo, milissegundos |
| Visitor Profile - Pages Seen Before Activity | Especifica o número total de exibições de páginas (impressões), incluindo a visita/sessão atual, até o visitante entrar na atividade. | Duplo (apenas número positivo inteiro) 1, 2, 3, etc. |
| Visitor Profile - Page Views in Current Visit | Especifica o número total de exibições de páginas na visita/sessão atual, até o visitante entrar na atividade. Mais precisamente, o número de impressões. Essas impressões não são exibições de páginas reais, mas sim o número de vezes que a solicitação atingiu o Target. O Target não consegue distinguir entre limites de tempo ou quaisquer outros motivos pelos quais o usuário não recebeu ou visualizou o conteúdo. | Duplo (apenas número positivo inteiro) |
| Visitor Profile - Start of Current Visit | Especifica o momento em que a visita/sessão atual com o Target foi iniciada. A visita com o Target pode ser iniciada sem inserir uma atividade. Tudo o que é necessário é uma chamada para qualquer solicitação [!DNL Target]. Um visitante pode levar um tempo, até inserir a atividade e o instantâneo ser tirado. | Duplo, milissegundos |
| Perfil do visitante - Start da visita mais recente | Especifica o momento em que a última visita/sessão atual com o Target foi iniciada. Esse atributo é atualizado quando a sessão expira.<br>Se essa for a primeira sessão do visitante, ela resultará em `LAST_SESSION_START = 0.` | Duplo, milissegundos |
| Visitor Profile - Time Since Most Recent Visit When First Enter Activity | Especifica a duração entre a sessão anterior e a hora em que o usuário entra na atividade e o instantâneo é tirado. | Duplo, milissegundos |
| Visitor Profile - Time in Visit Before Enter Activity | Especifica a diferença entre a última interação com o Target e quando a visita atual começou. Esse atributo pode ser considerado duração da visita/sessão, até que o usuário entre na atividade e o instantâneo seja tirado.<br>[!DNL Target]Valores negativos ocorrem quando o início da sessão e o a hora da última atualização são acionados pela mesma chamada de Valores negativos devem ser considerados como 0 (zero). | Duplo, milissegundos |
| Perfil do visitante - Visitas totais | Especifica o número total de visitas/sessões. Isso não inclui a visita/sessão atual. | Duplo (apenas número positivo inteiro) 1, 2, 3, etc. |
| Visitor Profile - Total Visits to Activity | Especifica o número de visitas a uma atividade específica. Se não houver visita anterior, retorna 0 (zero). | Duplo (apenas número positivo inteiro) 1, 2, 3, etc. |
| Visitor Profile - Total Visits to Activity with Conversion | Especifica o número de visitas/sessões a uma atividade específica quando houve pelo menos uma conversão durante a visita. | Dupla |
| Visitor Profile - Visits to Activity with No Conversion | Número de visitas/sessões sem conversões a uma atividade específica. Esse valor é redefinido como zero depois da conversão ou -1 se a conversão nunca tiver ocorrido. | Duplo (apenas número positivo inteiro) 1, 2, 3, etc. |
