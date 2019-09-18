---
description: Este tópico contém respostas para as perguntas mais frequentes sobre classificação e uso do Analytics como fonte de geração de relatórios para o Target (A4T).
keywords: perguntas frequentes; perguntas frequentes; analytics para target; a4T; classificações; classificação; importador de classificações; post-tnt-action
seo-description: Este tópico contém respostas para as perguntas mais frequentes sobre classificação e uso do Analytics como fonte de geração de relatórios para o Target (A4T).
seo-title: Classificações - Perguntas frequentes sobre o A4T
solution: Target
title: Classificações - Perguntas frequentes sobre o A4T
topic: Padrão
uuid: 4b42adbc-4fa8-4b62-86c8-bb8f8bec7e54
translation-type: tm+mt
source-git-commit: 8dc94ca1ed48366e6b3ac7a75b03c214f1db71d9

---


# Classificações - Perguntas frequentes do A4T{#classifications-a-t-faq}

Este tópico contém respostas para as perguntas mais frequentes sobre classificação e uso do Analytics como fonte de geração de relatórios para o Target (A4T).

## Depois de usar o Importador de classificações para baixar classificações, como faço para relacionar o valor de post-tnt-action com o nome de uma atividade? {#section_6045DAC488B248418F430E663C38D001}

Você pode baixar as classificações para a cadeia de caracteres A4T/TNT do [Importador de classificação das Ferramentas administrativas](https://docs.adobe.com/content/help/en/analytics/components/classifications/classifications-importer/c-working-with-saint.html). A variável é chamada "TNT" na lista de exportação. Os dados baixados incluem os nomes amigáveis de atividades, experiências e assim por diante.

Este arquivo de pesquisa é útil para clientes que recebem a alimentação de dados de sequência de cliques da Adobe. O arquivo fornece nomes amigáveis para as colunas `post_tnt` e `post_tnt_action`.

O formato da string da variável TNT é `activityID:experienceID:targettype|event`.

* o tipo de direcionamento será sempre 0 para A4T.
* Evento = 0 representa entrada de uma experiência.
* Evento = 1 representa visita de uma experiência.
* Evento = 2 representa impressão de uma atividade.
* Evento = 32767 representa conversão de uma atividade.

You can import the classification file on a frequent basis from the UI using a [browser import](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/browser-import.html) or an [FTP import](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/import-file.html). Você também pode se envolver com os Serviços de engenharia para obter o arquivo como uma tabela de pesquisa junto com uma alimentação de dados de sequência de cliques.
