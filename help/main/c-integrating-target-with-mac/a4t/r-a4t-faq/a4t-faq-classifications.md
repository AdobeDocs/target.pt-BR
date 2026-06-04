---
keywords: perguntas frequentes;perguntas frequentes;analytics para target;a4T;classificações;classificação;importador de classificações;post-tnt-action;códigos de evento
description: Encontre respostas para perguntas sobre classificações e uso do [!UICONTROL Analytics for Target] (A4T).
title: Onde posso encontrar informações sobre classificações com o A4T?
feature: Analytics for Target (A4T)
exl-id: 875f6c1c-1bda-40a9-96f2-d58c00d91d20
TQID: https://experienceleague.adobe.com/-BIklVbPaO9QGmnjN0eQdbLFXGA7c2sR-3s6OUli8BM
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 336
ht-degree: 25%

---

# Classificações - Perguntas frequentes sobre o A4T

Este tópico contém respostas para as perguntas mais frequentes sobre classificação e uso do [!DNL Analytics] como fonte de relatórios para o [!DNL Target] (A4T).

## Depois de usar o [!UICONTROL Importador de classificações] para baixar classificações, como faço para relacionar o valor de post-tnt-action com o nome de uma atividade? {#section_6045DAC488B248418F430E663C38D001}

+++Resposta
Você pode baixar as classificações para a cadeia de caracteres A4T/TNT do [Importador de classificação das Ferramentas administrativas](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html). A variável é chamada de &quot;TNT&quot; na lista de exportação. Os dados baixados incluem os nomes amigáveis de atividades, experiências e assim por diante.

Esse arquivo de pesquisa é útil para clientes que recebem o feed de dados de sequência de cliques de [!DNL Adobe]. O arquivo fornece nomes amigáveis para as colunas `post_tnt` e `post_tnt_action`.

Para atividades padrão de [!UICONTROL Teste A/B] e [!UICONTROL Direcionamento de experiência] (XT), o formato da cadeia de caracteres TNT é:

```
activityID:experienceID:targettype|event
```

Para atividades de [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático], o formato da cadeia de caracteres TNT é:

```
activityId:experienceId:targettype:algorithmId|event
```

* `targettype` = `targettype` e `algorithmId` são identificadores internos usados pelas atividades [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático].
* Evento = 0 representa entrada de uma experiência.
* Evento = 1 representa visita de uma experiência.
* Evento = 2 representa impressão de uma atividade.
* Evento = 3-32766 representa a ID da métrica de sucesso do Analytics.
* Evento = 32767 representa conversão de uma atividade.
* O evento -1 ou 65535 representa que o usuário foi removido da atividade ou experiência. Essa situação geralmente acontece quando o visitante converte. O visitante é liberado da experiência e agora está disponível para se qualificar para qualquer outra experiência.

É possível importar o arquivo de classificação regularmente da interface do usuário usando uma [importação do navegador](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-import.html?lang=en) ou uma [importação do FTP](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/import-file.html?lang=en). Você também pode se envolver com os Serviços de engenharia para obter o arquivo como uma tabela de pesquisa junto com uma alimentação de dados de sequência de cliques.

+++
