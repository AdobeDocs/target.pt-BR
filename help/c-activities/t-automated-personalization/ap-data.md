---
description: O Adobe Target coleta e usa automaticamente uma variedade de dados para criar algoritmos de personalização em atividades de Personalização automatizada (AP) e Auto-Target (AT). Quando um visitante entra na atividade de AP ou AT, um instantâneo das informações é enviado para um conjunto de "registros de treinamento" (os dados do visitante sobre os quais os algoritmos de personalização aprenderão).
keywords: dados ambientais; dados de sessão; dados geográficos; dados geográficos; dados do dispositivo; dados móveis; atributos; atributos do perfil
seo-description: O Adobe Target coleta e usa automaticamente uma variedade de dados para criar algoritmos de personalização em atividades de Personalização automatizada (AP) e Auto-Target (AT). Quando um visitante entra na atividade de AP ou AT, um instantâneo das informações é enviado para um conjunto de "registros de treinamento" (os dados do visitante sobre os quais os algoritmos de personalização aprenderão).
seo-title: Coleta de dados para algoritmos de personalização do Adobe Target
solution: Target
title: Coleta de dados para os algoritmos de personalização do Target
title-outputclass: premium
topic: Premium
uuid: f5ca2d84-0016-4af5-a139-bca567a3d0e8
badge: premium
translation-type: tm+mt
source-git-commit: 156587a0375fe2dbf8c461e310b2eae04b491b57

---


# ![PREMIUM](/help/assets/premium.png) Coleta de dados para os algoritmos de personalização do Target{#data-collection-for-the-target-personalization-algorithms}

O Target coleta e usa automaticamente uma variedade de dados para criar algoritmos de personalização nas atividades de Personalização automatizada (AP) e Direcionamento automático (AT). Quando um visitante entra na atividade de AP ou AT, um instantâneo das informações é enviado para um conjunto de "registros de treinamento" (os dados do visitante sobre os quais os algoritmos de personalização aprenderão).

Para saber mais sobre os algoritmos de personalização do Target, consulte [Algoritmo Random Forest](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA).

The following table shows the data collected by Automated Personalization and Auto-Target by default, without the marketer having to do anything, as well as the naming convention used to indicate these attributes in [Personalization Insights Reports](../../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). É possível aumentar o conjunto de dados de entrada a qualquer momento. Para saber mais sobre como fazer upload de dados adicionais, consulte [Fazer upload de dados para os algoritmos de personalização do Target](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6).

| Tipo de dados | Descrição | Convenção de nomenclatura do tipo de dados | Atributos de exemplo |
| --- | --- | --- | --- |
| [Dados de dispositivo e dispositivos móveis](#device-mobile) | Informações específicas sobre dispositivos e dispositivos móveis.<br>Consulte "Dispositivo de dispositivo e dispositivo móvel" abaixo. | `Device - [device attribute]`<br>`Mobile - [mobile attribute]` | Mobile Device OS<br>Mobile Screen Size |
| [Dados de ambiente](#env) | Informações sobre o sistema operacional do visitante e como e quando o visitante está acessando a atividade. | `Browser - / Operating System] - [Attribute Name]` | Navegador - Tipo |
| Segmento da Experience Cloud | Públicos-alvo criados no Audience Manager ou Analytics e compartilhados na Experience Cloud | `Custom - Experience Cloud Audience - [Audience Name]` | Dados personalizados |
| [Dados geográficos](#geo) | Informações sobre onde o visitante está localizado.<br>Consulte "Dados geográficos" abaixo. | `Geo - [geo attribute]` | City<br>Country<br>Region/State<br>Zip Code<br>Latitude<br>Longitude<br>ISP or Mobile Carrier |
| Atributos do perfil | Scripts ou atributos de perfil carregados diretamente no perfil do Target por meio da API de atualização | `Custom - Visitor Profile - [attribute name]` | Dados personalizados |
| Parâmetros de URL de referência | Em geral, o URL de referência é aquele que fez referência a uma determinada página que iniciou a chamada da mbox.<br>Observe que esta variável pode ser afetada pela atividade dos usuários no site, bem como pela implementação técnica do site. | `Custom - [Referring URL Parameter] - [Parameter value]` | Dados personalizados |
| Relatórios de relatórios | Quaisquer segmentos configurados na configuração da atividade. | `Reporting Segment -[Segment Name]` | Dados personalizados |
| [Dados da sessão](#session) | Informações sobre o comportamento do visitante na sessão ao acessar a atividade. | `Visitor Profile - [Attribute Name]` | Perfil do visitante - Início da visita mais recente |
| Parâmetros de URL | O Target inspeciona o URL para extrair os parâmetros de URL. | `Custom - URL Parameter - [URL Parameter]` | Dados personalizados |

As seções a seguir contêm informações detalhadas sobre os vários tipos de dados, incluindo nomes de atributos, descrições e valores de amostra.

## Device and Mobile data {#device-mobile}

| Nome do atributo | Descrição do atributo | Valores de amostra |
| --- | --- | --- |
| Dispositivo móvel - Dispositivo - Marca | A marca do dispositivo móvel que o visitante usou para acessar a atividade. | Apple |
| Dispositivo móvel - Dispositivo - ereader | Especifica se o dispositivo é um ereader. | 0 é False, 1 é Verdadeiro |
| Dispositivo móvel - Dispositivo - Console de jogos | Especifica se o dispositivo é um console de jogos. | 0 é False, 1 é Verdadeiro |
| Dispositivo móvel - Dispositivo - Media Player | Especifica se o dispositivo é um player de mídia. | 0 é False, 1 é Verdadeiro |
| Dispositivo móvel - Dispositivo - Telefone móvel | Especifica se o dispositivo é um telefone celular. | 0 é False, 1 é Verdadeiro |
| Dispositivo móvel - Dispositivo - Nome do modelo | O nome do modelo do dispositivo móvel usado pelo visitante para acessar a atividade. | Iphone XS |
| Dispositivo - Set-Top Box | Especifica se o dispositivo é uma caixa set-top. | 0 é False, 1 é Verdadeiro |
| Dispositivo móvel - Dispositivo - Tablet | Especifica se o dispositivo é um tablet. | 0 é False, 1 é Verdadeiro |
| Dispositivo móvel - Densidade de pixels (ppi) | A densidade de pixels do dispositivo móvel que o visitante usou para acessar a atividade. | 1, 2, 3, etc. |
| Mobile - SO - OSX (Android, Windows, etc.) | Especifica se o usuário usou um OSX (ou Android, Windows etc.) para acessar a atividade. | 0 é False, 1 é Verdadeiro |
| Dispositivo móvel - Altura de tela (px) | A altura da tela do dispositivo móvel (em pixels) que o visitante usou para acessar a atividade. | 1, 2, 3, etc. |
| Dispositivo móvel - Largura da tela (px) | A largura da tela do dispositivo móvel (em pixels) que o visitante usou para acessar a atividade. | 1, 2, 3, etc. |

## Environmental data {#env}

| Nome do atributo | Descrição do atributo | Valores de amostra |
| --- | --- | --- |
| Navegador - Dia da semana | O dia da semana quando o visitante acessou a atividade. | 0 a 6.<br>(0 é domingo) |
| Navegador - Hora do dia | A hora do dia em que o visitante acessou a atividade. | 0 to 23<br>(0 is midnight) |
| Navegador - Hora da semana | A hora da semana quando o visitante acessou a atividade. | 0 to 168<br>(Sunday midnight is 0) |
| Navegador - Configuração de idioma | O idioma especificado no navegador do visitante usado para acessar a atividade. | English<br>German |
| Navegador - Altura de tela (px) | A altura da tela do navegador do dispositivo (em pixels) que o visitante usou para acessar a atividade. | 1, 2, 3, etc. |
| Navegador - Hora do dia | A hora do navegador do dia em que o visitante acessou a atividade. | 0, 6, 12, 18<br>(0 is night, 6 is morning,<br>12 is afternoon, 18 is evening) |
| Navegador - Fuso horário | O fuso horário do visitante ao acessar a atividade. | Pacific Time<br>Eastern Time<br>GMT |
| Navegador - Tipo | O tipo de navegador usado pelo visitante ao acessar a atividade. | Chrome<br>Firefox<br>Internet Explorer<br>Safari<br>Other |
| Navegador - Dia da semana/Fim de semana | O status de trabalho quando o visitante acessou a atividade (fim de semana, horário de trabalho ou tempo de semana da semana). | Saturday and Sunday is weekend<br>Monday-Friday 0900 to 1800 is work time<br>Monday-Friday after 1800 until 0900 is weekday free time |
| Navegador - Altura da janela (px) | A altura da janela do navegador (em pixels) que o visitante usou para acessar a atividade. | 1, 2, 3, etc. |
| Navegador - Largura da janela (px) | A largura da janela do navegador (em pixels) que o visitante usou para acessar a atividade. | 1, 2, 3, etc. |
| Dispositivo - Altura da tela | A altura de tela do dispositivo usada para acessar a atividade. | 1, 2, 3, etc. |
| Dispositivo - Largura da tela | A largura da tela do dispositivo que o visitante usou para acessar a atividade. | 1, 2, 3, etc. |
| Sistema operacional | O sistema operacional no dispositivo do visitante usado para acessar a atividade. | Mac OS<br>Windows<br>Linux<br>Search Bot<br>Unknown OS |
| Sistema operacional - Versão | A versão do sistema operacional utilizada pelo visitante para acessar a atividade. | Windows 10<br>Mac OS 10 |
| Fontes de tráfego - URL da página de aterrissagem de referência | A primeira página que o visitante viu ao acessar seu site. | `https://www.adobe.com/ecloud.html` |

## Geographical data {#geo}

| Nome do atributo | Descrição do atributo | Valores de amostra |
| --- | --- | --- |
| Geo - Cidade | A cidade da qual o visitante acessou a atividade. | São Francisco |
| Geo - País | O país do qual o visitante acessou a atividade. | Alemanha |
| Geo - DMA | A Área de marketing designada (DMA) a partir da qual o visitante acessou a atividade. | Charlottesville |
| Geo - Latitude | A latitude da qual o visitante acessou a atividade. | 47.269<br>Rounded to 3 decimal places (approximately 100 meters accuracy) |
| Geo - Longitude | A longitude da qual o visitante acessou a atividade. | -122.269<br>Rounded to 3 decimal places (approximately 100 meters accuracy) |
| Geografia - estado/região | O estado ou região a partir do qual o visitante acessou a atividade. | Utah<br>New South Wales |
| Geo - CEP | O CEP do qual o visitante acessou a atividade. | 84004 |
| Dispositivo móvel - Operadora | A operadora de celular que o visitante usou ao acessar a atividade. | Vodafone<br>T-Mobile |
| Rede - Velocidade da conexão | A velocidade de conexão de rede do dispositivo quando o visitante acessou a atividade. | Broadband<br>Cable<br>DSL<br>Mobile<br>Wireless<br>Satellite |
| Rede - Nome do domínio | O nome do domínio de rede do qual o visitante acessou a atividade. | `nnt.net` |
| Rede - ISP | A rede da qual o visitante acessou a atividade. | nnt communications corporation |

## Session data {#session}

| Nome do atributo | Descrição do atributo | Valores de amostra |
| --- | --- | --- |
| Perfil do visitante - Valor do pedido de duração da atividade | Especifica a soma de todos os valores de pedido em todas as visitas/sessões a uma atividade específica. | Dupla |
| Perfil do visitante - Tempo de vida da atividade no site | Especifica o tempo total do visitante gasto no site, excluindo a sessão atual e é atualizado quando a sessão expira. | Duplo, milissegundos |
| Perfil do visitante - Exibições de página médias por visita durante a atividade | Especifica o número médio de exibições de página por sessão, excluindo a sessão atual. | Dupla |
| Perfil do visitante - Tempo médio por visita | Especifica o tempo médio gasto por visita/sessão. Isso não inclui a sessão atual. | Duplo, milissegundos |
| Perfil do visitante - Primeira visita | Especifica a hora da primeira visita que o usuário interagiu com o Target. | Duplo, milissegundos |
| Perfil do visitante - Horas desde a última visita | Especifica as horas desde a última visita a esta atividade em particular. | Duplo (número positivo inteiro) 1, 2, 3, etc. |
| Perfil do visitante - Impressões de localização/conteúdo | Especifica o número de impressões a uma combinação específica de localização/conteúdo em uma atividade específica. | Duplo (número positivo inteiro) 1, 2, 3, etc. |
| Perfil do visitante - Interação do último Target | Especifica a hora da última interação com o Target. A interação ocorre em cada solicitação de mbox porque a implementação atual do Target atualiza o perfil em cada solicitação. | Duplo, milissegundos |
| Perfil do visitante - Páginas visualizadas antes da atividade | Especifica o número de exibições de página totais (impressões), incluindo a visita/sessão atual até o visitante digitar a atividade. | Duplo (número positivo inteiro) 1, 2, 3, etc. |
| Perfil do visitante - Exibições de página na visita atual | Especifica o número de exibições de página na visita/sessão atual até que o visitante insira a atividade. Com mais precisão, o número de impressões. Essas impressões não são exibições de página reais, e isso é o número de vezes que a solicitação atingiu o Target. O Target não é capaz de distinguir entre limites de tempo ou quaisquer outros motivos pelos quais o usuário não recebeu ou visualizou o conteúdo. | Duplo (número positivo somente inteiro) |
| Perfil do visitante - Início da visita atual | Especifica o momento em que a visita/sessão atual com o Target começou. A visita com o Target pode ser iniciada sem inserir uma atividade. Tudo o que é necessário é uma chamada para qualquer mbox. Um visitante pode levar aenquanto até inserir a atividade e o instantâneo é realizado. | Duplo, milissegundos |
| Perfil do visitante - Início da visita mais recente | Especifica o horário de início da última visita/sessão com o Target. Esse atributo é atualizado quando a sessão expira.<br>Se esta for a primeira sessão do visitante, resultará em `LAST_SESSION_START = 0.` | Duplo, milissegundos |
| Perfil do visitante - Tempo desde a última visita da atividade na primeira entrada | Especifica a duração entre a sessão anterior e a hora em que o usuário digita a atividade e o instantâneo é executado. | Duplo, milissegundos |
| Perfil do visitante - Tempo na visita antes da entrada na atividade | Especifica a diferença entre a última interação com o Target e quando a visita atual começou. Esse atributo pode ser considerado duração da visita/sessão até que o usuário digite a atividade e o instantâneo seja executado.<br>Valores negativos ocorrem quando o início da sessão e o último tempo de atualização são acionados pela mesma chamada de mbox. Valores negativos devem ser considerados como 0 (zero). | Duplo, milissegundos |
| Perfil do visitante - Visitas totais | Especifica o número total de visitas/sessões. Não inclui a visita/sessão atual. | Duplo (número positivo inteiro) 1, 2, 3, etc. |
| Perfil do visitante - Total de visitas à atividade | Especifica o número de visitas a uma atividade específica. Se não houver visita anterior, retorna 0 (zero). | Duplo (número positivo inteiro) 1, 2, 3, etc. |
| Perfil do visitante - Total de visitas à atividade com conversão | Especifica o número de visitas/sessões a uma atividade específica quando havia pelo menos uma conversão durante a visita. | Dupla |
| Perfil do visitante - Visitas à atividade sem conversão | Número de visitas/sessões sem conversões a uma atividade específica. Esse valor é redefinido como zero após a conversão ou -1 se a conversão nunca tiver ocorrido. | Duplo (número positivo inteiro) 1, 2, 3, etc. |
