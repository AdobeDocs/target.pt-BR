---
description: O Target coleta e usa automaticamente uma variedade de dados para criar algoritmos de personalização nas atividades de Personalização automatizada (AP) e Direcionamento automático (AT). Quando um visitante entra na atividade de AP ou AT, um instantâneo das informações é enviado para um conjunto de "registros de treinamento" (os dados do visitante sobre os quais os algoritmos de personalização aprenderão).
seo-description: O Target coleta e usa automaticamente uma variedade de dados para criar algoritmos de personalização nas atividades de Personalização automatizada (AP) e Direcionamento automático (AT). Quando um visitante entra na atividade de AP ou AT, um instantâneo das informações é enviado para um conjunto de "registros de treinamento" (os dados do visitante sobre os quais os algoritmos de personalização aprenderão).
seo-title: Coleta de dados para os algoritmos de personalização do Target
solution: Target
title: Coleta de dados para os algoritmos de personalização do Target
title-outputclass: premium
topic: Premium
uuid: f5ca2d84-0016-4af5-a139-bca567a3d0e8
badge: premium
translation-type: tm+mt
source-git-commit: 2baa75b6020b2f9229db68667c2e19a698954231

---


# ![PREMIUM](/help/assets/premium.png) Coleta de dados para os algoritmos de personalização do Target{#data-collection-for-the-target-personalization-algorithms}

O Target coleta e usa automaticamente uma variedade de dados para criar algoritmos de personalização nas atividades de Personalização automatizada (AP) e Direcionamento automático (AT). Quando um visitante entra na atividade de AP ou AT, um instantâneo das informações é enviado para um conjunto de &quot;registros de treinamento&quot; (os dados do visitante sobre os quais os algoritmos de personalização aprenderão).

Para saber mais sobre os algoritmos de personalização do Target, consulte [Algoritmo Random Forest](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA).

A tabela a seguir mostra os dados coletados pela Personalização automatizada por padrão, sem que o profissional de marketing precise fazer nada, além da convenção de nomenclatura usada para indicar esses atributos nos [Relatórios de informações de personalização](../../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). É possível aumentar o conjunto de dados de entrada a qualquer momento. Para saber mais sobre como fazer upload de dados adicionais, consulte [Fazer upload de dados para os algoritmos de personalização do Target](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6).

| Tipo de dados | Descrição | Convenção de nomenclatura do tipo de dados | Atributos de exemplo |
|--- |--- |--- |--- |
| Parâmetros de URL | O Target inspeciona o URL para extrair os parâmetros de URL. | `Custom - URL Parameter - [URL Parameter]` | Dados personalizados |
| Parâmetros de URL de referência | Em geral, o URL de referência é aquele que fez referência a uma determinada página que iniciou a chamada da mbox.<br>Observe que esta variável pode ser afetada pela atividade dos usuários no site, bem como pela implementação técnica do site. | `Custom - [Referring URL Parameter] - [Parameter value]` | Dados personalizados |
| Dados ambientais e de sessão | Informações sobre como e quando o usuário está acessando a atividade. | `Visitor Profile - [attribute name]`<br>`Browser - [browser attribute]`<br>`Operating System - [OS attribute]` | Perfil do visitante - Início da visita mais recente<br>Perfil do visitante -Total de visitas<br>Perfil do visitante - Tempo médio por visita<br>Navegador - Fuso horário<br>Navegador - Dia da semana<br>Navegador - Configuração de idioma<br>Navegador - Tipo<br>Sistema operacional - Versão |
| Geografia | Informações sobre onde o visitante está localizado. | `Geo - [geo attribute]` | Cidade<br>País<br>Região/estado<br>CEP<br>Latitude<br>Longitude<br>ISP ou Operadora de celular |
| Dispositivo e dados móveis | Informações específicas sobre dispositivos e dispositivos móveis. | `Device - [device attribute]`<br>`Mobile - [mobile attribute]` | Sistema operacional de dispositivo móvel<br>Tamanho da tela remota |

