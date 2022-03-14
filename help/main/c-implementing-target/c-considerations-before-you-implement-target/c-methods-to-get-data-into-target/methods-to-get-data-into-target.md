---
keywords: implementar, implementação, configuração, configurar, parâmetro de página, tomcat, url codificado, atributo de perfil na página, parâmetro mbox, atributos de perfil na página, atributo de perfil de script, API de atualização de perfil em massa, API de atualização de arquivo único, atributos de cliente, provedores de dados, dataprovider, provedor de dados
description: Obter dados em [!DNL Target] (parâmetros de página, atributos de perfil, atributos de perfil de script, provedores de dados, APIs de atualização de perfil único e em massa, Atributos do cliente).
title: Como posso obter dados no Target?
feature: Implementation
role: Developer
exl-id: b42eb846-d423-4545-a8fe-0b8048ab689e
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 71%

---

# Visão geral dos métodos

Informações sobre os diferentes métodos que você pode usar para obter dados no [!DNL Adobe Target].

Os métodos disponíveis incluem:

| Método | Detalhes |
| --- | --- |
| [Parâmetros da página](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/page-parameters.md)<br>(Também denominados &quot;parâmetros mbox&quot;) | Os parâmetros de página são pares de nome/valor enviados diretamente pelo código de página que não são armazenados no perfil do visitante para uso futuro.<br>Os parâmetros de página são úteis para enviar dados de página para o Target, que não precisam ser armazenados com o perfil do visitante para uso futuro de direcionamento. Esses valores são usados para descrever a página ou a ação que o usuário fez na página específica. |
| [Atributos de perfil na página](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/in-page-profile-attributes.md)<br>(Também chamado de &quot;atributos de perfil in-mbox&quot;) | Os atributos de perfil na página são pares de nome/valor enviados diretamente pelo código de página que são armazenados no perfil do visitante para uso futuro.<br>Os atributos de perfil na página permitem que os dados específicos do usuário sejam armazenados no perfil do Target para direcionamento e segmentação posteriores. |
| [Atributos de perfil de script](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/script-profile-attributes.md) | Atributos de perfil de script são pares de nome/valor definidos na solução Target. O valor é determinado na execução de um snippet do JavaScript no servidor Target, a cada chamada do servidor.<br>Os usuários gravam pequenos snippets de código que são executados de acordo com a chamada de mbox e antes de um visitante ser avaliado para associação de público-alvo e atividade. |
| [Provedores de dados](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/data-providers.md) | Os provedores de dados permitem que você transfira facilmente os dados de terceiros para o Target. |
| [API de atualização de perfil em massa](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/bulk-profile-update-api.md) | Via API, envia um arquivo .csv ao Target com atualizações de perfil de visitante para muitos visitantes. Cada perfil do visitante pode ser atualizado com vários atributos de perfil na página em uma chamada. |
| [API de atualização de perfil único](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/single-profile-update-api.md) | Quase idêntica à API de atualização de perfil em massa, mas um perfil de visitante é atualizado por vez, alinhada à chamada de API em vez de um arquivo .csv. |
| [Atributos do cliente](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/customer-attributes.md) | Os atributos do cliente permitem que você carregue os dados de perfil do visitante via FTP à Experience Cloud. Após o upload, use os dados no Adobe Analytics e no Adobe Target. |












