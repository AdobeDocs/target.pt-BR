---
keywords: perguntas frequentes; perguntas frequentes; analytics para target; a4T; classificações; classificação; importador de classificações; post-tnt-action
description: Encontre respostas para perguntas sobre classificações e como usar o Analytics para Públicos alvos (A4T). O A4T permite que você use o relatórios do Analytics para atividades do Público alvo.
title: Onde posso encontrar informações sobre classificações com A4T?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 55%

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
