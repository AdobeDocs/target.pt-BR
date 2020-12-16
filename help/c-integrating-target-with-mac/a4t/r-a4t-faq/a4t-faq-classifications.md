---
keywords: faq;frequently asked questions;analytics for target;a4T;classifications;classification;classifications importer;post-tnt-action
description: Este tópico contém respostas para as perguntas mais frequentes sobre classificação e uso do Analytics como fonte de geração de relatórios para o Target (A4T).
title: Classificações - Perguntas frequentes sobre o A4T
feature: a4t troubleshooting
translation-type: tm+mt
source-git-commit: 403a56da912fa143cf6c20b078c0bba63c6f4420
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 65%

---


# Classificações - Perguntas frequentes do A4T{#classifications-a-t-faq}

Este tópico contém respostas a perguntas frequentes sobre classificações e o uso de [!DNL Analytics] como fonte de relatórios para [!DNL Target] (A4T).

## Depois de usar o Importador de classificações para baixar classificações, como faço para relacionar o valor de post-tnt-action com o nome de uma atividade? {#section_6045DAC488B248418F430E663C38D001}

Você pode baixar as classificações para a cadeia de caracteres A4T/TNT do [Importador de classificação das Ferramentas administrativas](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html). A variável é chamada &quot;TNT&quot; na lista de exportação. Os dados baixados incluem os nomes amigáveis de atividades, experiências e assim por diante.

Este arquivo de pesquisa é útil para clientes que recebem a alimentação de dados de sequência de cliques da Adobe. O arquivo fornece nomes amigáveis para as colunas `post_tnt` e `post_tnt_action`.

O formato da string da variável TNT é `activityID:experienceID:targettype|event`.

* targettype = 0 (controle/aleatório) ou 1 (direcionado) para [!UICONTROL Autoalocar] e [!UICONTROL Público alvo automático] atividades.
* Evento = 0 representa entrada de uma experiência.
* Evento = 1 representa visita de uma experiência.
* Evento = 2 representa impressão de uma atividade.
* Evento = 3-32766 representa a ID da métrica de sucesso do Analytics.
* Evento = 32767 representa conversão de uma atividade.

Você pode importar o arquivo de classificação frequentemente da interface do usuário usando [importação do navegador](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/browser-import.html) ou [importação FTP](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/import-file.html). Você também pode se envolver com os Serviços de engenharia para obter o arquivo como uma tabela de pesquisa junto com uma alimentação de dados de sequência de cliques.
