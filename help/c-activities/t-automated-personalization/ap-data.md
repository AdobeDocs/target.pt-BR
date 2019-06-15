---
description: O Target coleta e usa automaticamente uma variedade de dados para criar algoritmos de personalização nas atividades de Personalização automatizada (AP) e Direcionamento automático (AT). Quando um visitante entra na atividade de AP ou AT, um instantâneo das informações é enviado para um conjunto de "registros de treinamento" (os dados do visitante sobre os quais os algoritmos de personalização aprenderão).
seo-description: O Adobe Target coleta e usa automaticamente uma variedade de dados para criar algoritmos de personalização em atividades de Personalização automatizada (AP) e Auto-Target (AT). Quando um visitante entra na atividade de AP ou AT, um instantâneo das informações é enviado para um conjunto de "registros de treinamento" (os dados do visitante sobre os quais os algoritmos de personalização aprenderão).
seo-title: Coleta de dados para algoritmos de personalização do Adobe Target
solution: Target
title: Coleta de dados para os algoritmos de personalização do Target
title-outputclass: premium
topic: Premium
uuid: f5ca2d84-0016-4af5-a139-bca567a3d0e8
badge: premium
translation-type: tm+mt
source-git-commit: 1662c5e83a3712626536a659e5001cd537343883

---


# ![PREMIUM](/help/assets/premium.png) Coleta de dados para os algoritmos de personalização do Target{#data-collection-for-the-target-personalization-algorithms}

O Target coleta e usa automaticamente uma variedade de dados para criar algoritmos de personalização nas atividades de Personalização automatizada (AP) e Direcionamento automático (AT). Quando um visitante entra na atividade de AP ou AT, um instantâneo das informações é enviado para um conjunto de &quot;registros de treinamento&quot; (os dados do visitante sobre os quais os algoritmos de personalização aprenderão).

Para saber mais sobre os algoritmos de personalização do Target, consulte [Algoritmo Random Forest](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA).

A tabela a seguir mostra os dados coletados pela Personalização automatizada por padrão, sem que o profissional de marketing precise fazer nada, além da convenção de nomenclatura usada para indicar esses atributos nos [Relatórios de informações de personalização](../../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). É possível aumentar o conjunto de dados de entrada a qualquer momento. Para saber mais sobre como fazer upload de dados adicionais, consulte [Fazer upload de dados para os algoritmos de personalização do Target](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6).

| Tipo de dados | Descrição | Convenção de nomenclatura do tipo de dados | Atributos de exemplo |
| --- | --- | --- | --- |
| Parâmetros de URL | O Target inspeciona o URL para extrair os parâmetros de URL. | `Custom - URL Parameter - [URL Parameter]` | Dados personalizados |
| Parâmetros de URL de referência | Em geral, o URL de referência é aquele que fez referência a uma determinada página que iniciou a chamada da mbox.<br>Observe que esta variável pode ser afetada pela atividade dos usuários no site, bem como pela implementação técnica do site. | `Custom - [Referring URL Parameter] - [Parameter value]` | Dados personalizados |
| Dados ambientais e de sessão | Informações sobre como e quando o usuário está acessando a atividade.<br>Consulte &quot;Dados de ambiente e sessão&quot; abaixo. | `Visitor Profile - [attribute name]`<br>`Browser - [browser attribute]`<br>`Operating System - [OS attribute]` | Perfil do visitante - Início da visita mais recente<br>Perfil do visitante -Total de visitas<br>Perfil do visitante - Tempo médio por visita<br>Navegador - Fuso horário<br>Navegador - Dia da semana<br>Navegador - Configuração de idioma<br>Navegador - Tipo<br>Sistema operacional - Versão |
| Geográfico | Informações sobre onde o visitante está localizado.<br>Consulte &quot;Dados geográficos&quot; abaixo. | `Geo - [geo attribute]` | Citycountryregion<br><br>/statezip<br>codelatitudelongitudeisp<br><br><br>ou Operadora de celular |
| Dispositivo e dados móveis | Informações específicas sobre dispositivos e dispositivos móveis.<br>Consulte &quot;Dispositivo de dispositivo e dispositivo móvel&quot; abaixo. | `Device - [device attribute]`<br>`Mobile - [mobile attribute]` | Tamanho de tela do dispositivo<br>móvel osmobile |

As seções a seguir contêm informações detalhadas sobre os vários tipos de dados, incluindo nomes de atributos, descrições e valores de amostra.

>[!NOTE]
>
>Alguns valores nas tabelas a seguir foram arredondados para o número inteiro mais próximo ou hora.

## Dados de ambiente e sessão

| Nome do atributo | Descrição do atributo | Valores de amostra |
| --- | --- | --- |
| Navegador - Dia da semana | O dia da semana quando o visitante acessou a atividade. | 0 a 6.<br>(0 é domingo) |
| Navegador - Hora do dia | A hora do dia em que o visitante acessou a atividade. | 0 a 23<br>(0 é meia-noite) |
| Navegador - Hora da semana | A hora da semana quando o visitante acessou a atividade. | 0 a 168<br>(a meia-noite de domingo é 0) |
| Navegador - Configuração de idioma | O idioma especificado no navegador do visitante usado para acessar a atividade. | Inglês alemão<br> |
| Navegador - Altura de tela (px) | A altura da tela do navegador do dispositivo (em pixels) que o visitante usou para acessar a atividade. | 1, 2, 3, etc. |
| Navegador - Hora do dia | A hora do navegador do dia em que o visitante acessou a atividade. | 0, 6, 12, 18<br>(0 é noite, 6 é a manhã, 12 é tarde, 18 é à noite) |
| Navegador - Fuso horário | O fuso horário do visitante ao acessar a atividade. | Pacífico timeetheast<br>timegmt<br> |
| Navegador - Tipo | O tipo de navegador usado pelo visitante ao acessar a atividade. | Chromefirefoxinternet<br><br>explorersafariother<br><br> |
| Navegador - Dia da semana/Fim de semana | O status de trabalho quando o visitante acessou a atividade (fim de semana, horário de trabalho ou tempo de semana da semana). | Sábado e domingo é o fim de semana<br>até sexta-feira, 0900 para o 1800, está trabalhando timemonday<br>até sexta-feira depois de 1800, até que 0900 seja um horário de semana gratuito |
| Navegador - Altura da janela (px) | A altura da janela do navegador (em pixels) que o visitante usou para acessar a atividade. | 1, 2, 3, etc. |
| Navegador - Largura da janela (px) | A largura da janela do navegador (em pixels) que o visitante usou para acessar a atividade. | 1, 2, 3, etc. |
| Dispositivo - Altura da tela | A altura de tela do dispositivo usada para acessar a atividade. | 1, 2, 3, etc. |
| Dispositivo - Largura da tela | A largura da tela do dispositivo que o visitante usou para acessar a atividade. | 1, 2, 3, etc. |
| Dispositivo móvel &gt; Densidade de pixels (ppi) | A densidade de pixels do dispositivo móvel que o visitante usou para acessar a atividade. | 1, 2, 3, etc. |
| Sistema operacional | O sistema operacional no dispositivo do visitante usado para acessar a atividade. | Mac oswindowslinuxsearch<br><br><br>botunknown<br>OS |
| Sistema operacional - Versão | A versão do sistema operacional utilizada pelo visitante para acessar a atividade. | Windows 10<br>Mac OS 10 |
| Fontes de tráfego - URL da página de aterrissagem de referência | A primeira página que o visitante viu ao acessar seu site. | `https://www.adobe.com/ecloud.html` |

## Dados geográficos

| Nome do atributo | Descrição do atributo | Valores de amostra |
| --- | --- | --- |
| Geo - Cidade | A cidade da qual o visitante acessou a atividade. | São Francisco |
| Geo - País | O país do qual o visitante acessou a atividade. | Alemanha |
| Geo - DMA | A Área de marketing designada (DMA) a partir da qual o visitante acessou a atividade. | Charlottesville |
| Geo - Latitude | A latitude da qual o visitante acessou a atividade. | 47.269<br>Arredondado para places casas decimais (aproximadamente accuracy 00 meters precisão) |
| Geo - Longitude | A longitude da qual o visitante acessou a atividade. | -122.269<br>Arredondado para 3 casas decimais (aproximadamente accuracy 00 meters precisão) |
| Geografia - estado/região | O estado ou região a partir do qual o visitante acessou a atividade. | Utahnew<br>South Wales |
| Geo - CEP | O CEP do qual o visitante acessou a atividade. | 84004 |
| Dispositivo móvel - Operadora | A operadora de celular que o visitante usou ao acessar a atividade. | Vodafonet<br>-Mobile |
| Rede - Velocidade da conexão | A velocidade de conexão de rede do dispositivo quando o visitante acessou a atividade. | Broadbandcabledslmobilewirelesssatellite<br><br><br><br><br> |
| Rede - Nome do domínio | O nome do domínio de rede do qual o visitante acessou a atividade. | `nnt.net` |
| Rede - ISP | A rede da qual o visitante acessou a atividade. | nnt communications corporation |

## Dados de dispositivo e dispositivo móvel

| Nome do atributo | Descrição do atributo | Valores de amostra |
| --- | --- | --- |
| Dispositivo móvel - Dispositivo - Marca | A marca do dispositivo móvel que o visitante usou para acessar a atividade. | Apple |
| Dispositivo móvel - Dispositivo - Nome do modelo | O nome do modelo do dispositivo móvel usado pelo visitante para acessar a atividade. | Iphone XS |
| Mobile - SO - OSX | Especifica se o usuário usou um dispositivo OSX para acessar a atividade. | 0 é False, 1 é Verdadeiro |
| Dispositivo móvel - Altura de tela (px) | A altura da tela do dispositivo móvel (em pixels) que o visitante usou para acessar a atividade. | 1, 2, 3, etc. |
| Dispositivo móvel - Largura da tela (px) | A largura da tela do dispositivo móvel (em pixels) que o visitante usou para acessar a atividade. | 1, 2, 3, etc. |