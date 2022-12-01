---
keywords: perguntas frequentes; perguntas frequentes; analytics para target; a4T; classificações; classificação; importador de classificações; post-tnt-action; códigos de evento
description: Encontre respostas para perguntas sobre classificações e uso [!UICONTROL Analytics para Target] (A4T).
title: Onde posso encontrar informações sobre classificações com o A4T?
feature: Analytics for Target (A4T)
exl-id: 875f6c1c-1bda-40a9-96f2-d58c00d91d20
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 21%

---

# Classificações - Perguntas frequentes sobre o A4T

Este tópico contém respostas para as perguntas mais frequentes sobre classificação e uso [!DNL Analytics] como fonte de relatórios para [!DNL Target] (A4T).

## Depois de usar o [!UICONTROL Importador de classificações] para baixar classificações, como faço para relacionar o valor de post-tnt-action com um nome de atividade? {#section_6045DAC488B248418F430E663C38D001}

+++Resposta É possível baixar as classificações da sequência A4T/TNT nas Ferramentas administrativas [Classificação do importador](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html). A variável é chamada de &quot;TNT&quot; na lista de exportação. Os dados baixados incluem os nomes amigáveis de atividades, experiências e assim por diante.

Esse arquivo de pesquisa é útil para clientes que recebem [!DNL Adobe]feed de dados de sequência de cliques do . O arquivo fornece nomes amigáveis para as colunas `post_tnt` e `post_tnt_action`.

Para padrão [!UICONTROL Teste A/B] e [!UICONTROL Direcionamento de experiência] (XT), o formato da string TNT é:

```
activityID:experienceID:targettype|event
```

Para [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] , o formato da string TNT é:

```
activityId:experienceId:targettype:algorithmId|event
```

* `targettype` = `targettype` e `algorithmId` são identificadores internos usados por [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] atividades.
* Evento = 0 representa entrada de uma experiência.
* Evento = 1 representa visita de uma experiência.
* Evento = 2 representa impressão de uma atividade.
* Evento = 3-32766 representa a id da métrica de sucesso do Analytics.
* Evento = 32767 representa conversão de uma atividade.
* O Evento -1 ou 65535 representa que o usuário é removido da atividade ou experiência. Essa situação geralmente ocorre quando o visitante é convertido. O visitante é liberado da experiência e agora está disponível para se qualificar para qualquer outra experiência.

Você pode importar o arquivo de classificação regularmente da interface do usuário usando um [importação de navegador](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-import.html?lang=en) ou [Importação de FTP](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/import-file.html?lang=en). Você também pode se envolver com os Serviços de engenharia para obter o arquivo como uma tabela de pesquisa junto com uma alimentação de dados de sequência de cliques.

+++
