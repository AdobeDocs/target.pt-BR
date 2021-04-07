---
keywords: implementar, implementação, configuração, configurar, parâmetro de página, tomcat, url codificado, atributo de perfil na página, parâmetro mbox, atributos de perfil na página, atributo de perfil de script, API de atualização de perfil em massa, API de atualização de arquivo único, atributos de cliente, provedores de dados, dataprovider, provedor de dados
description: Obtenha dados no Target (parâmetros de página, atributos de perfil, atributos de perfil de script, provedores de dados, APIs de atualização de perfil único e em massa, atributos do cliente).
title: Como posso obter dados no Target?
feature: Implementação
role: Developer
exl-id: b42eb846-d423-4545-a8fe-0b8048ab689e
translation-type: tm+mt
source-git-commit: 70d4c5b4166081751246e867d90d43b67efa5469
workflow-type: tm+mt
source-wordcount: '1082'
ht-degree: 89%

---

# Visão geral dos métodos

Informações sobre os diferentes métodos que você pode usar para inserir dados em [!DNL Adobe Target].

Os métodos disponíveis incluem:

| Método | Detalhes |
| --- | --- |
| [](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/page-parameters.md)<br>Parâmetros da página (também denominados &quot;parâmetros de mbox&quot;) | Os parâmetros de página são pares de nome/valor enviados diretamente pelo código de página que não são armazenados no perfil do visitante para uso futuro.<br>Os parâmetros de página são úteis para enviar dados de página adicionais ao Target, que não precisam ser armazenados no perfil do visitante para uso de direcionamento futuro. Esses valores são usados para descrever a página ou a ação que o usuário fez na página específica. |
| [](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/in-page-profile-attributes.md)<br>Os atributos de perfil na página (também chamados &quot;atributos de perfil in-mbox&quot;) | Os atributos de perfil na página são pares de nome/valor enviados diretamente pelo código de página que são armazenados no perfil do visitante para uso futuro.<br>Os atributos de perfil na página permitem que os dados específicos do usuário sejam armazenados no perfil do Target para direcionamento e segmentação posteriores. |
| [Atributos de perfil de script](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/script-profile-attributes.md) | Atributos de perfil de script são pares de nome/valor definidos na solução Target. O valor é determinado na execução de um snippet do JavaScript no servidor Target, a cada chamada do servidor.<br>Os usuários gravam pequenos snippets de código que são executados de acordo com a chamada de mbox e antes de um visitante ser avaliado para associação de público-alvo e atividade. |
| [Provedores de dados](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/data-providers.md) | Os provedores de dados são um recurso que permite transmitir dados de terceiros facilmente para o Target. |
| API de atualização de perfil em massa | Via API, envia um arquivo .csv ao Target com atualizações de perfil de visitante para muitos visitantes. Cada perfil do visitante pode ser atualizado com vários atributos de perfil na página em uma chamada. |
| API de atualização de perfil único | Quase idêntica à API de atualização de perfil em massa, mas um perfil de visitante é atualizado por vez, alinhada à chamada de API em vez de um arquivo .csv. |
| Atributos do cliente | Os atributos do cliente permitem que você carregue os dados de perfil do visitante via FTP à Experience Cloud. Após o upload, aproveite os dados no Adobe Analytics e no Adobe Target. |







## API de atualização de perfil em massa {#section_92AB4820A5624C669D9A1F1B6220D4FA}

Via API, envia um arquivo .csv ao Target com atualizações de perfil de visitante para muitos visitantes. Cada perfil do visitante pode ser atualizado com vários atributos de perfil na página em uma chamada.

Essa opção é muito parecida com Atributos do cliente, contendo algumas diferenças:

* Os Atributos do cliente usam um carregamento de FTP, enquanto a API de atualização de perfil em massa do Target usa uma API HTTP POST.
* Os dados de atributo do cliente podem ser compartilhados com o Analytics. A Atualização de perfil em massa é utilizável somente no Target.
* Os Atributos do cliente suportam a criação de um perfil para um usuário que o Target ainda não visualizou. A API de atualização do perfil em massa atualiza somente os perfis existentes do Target.
* Os Atributos do cliente necessitam do uso de uma Experience Cloud ID (ECID). A API de atualização do perfil em massa requer ID de TNT ou `mbox3rdPartyId`.
* Não é possível enviar os seguintes caracteres em `mbox3rdPartyID`: sinal de adição (+) e barra invertida (/).

### Formato

O arquivo .csv deve fazer referência a cada visitante por meio de Target PCID ou mboxThirdPartyId. A Experience Cloud ID (ECID) não é suportada. Todos os atributos/valores de perfil são criados e atualizados via API. Os detalhes de formato estão disponíveis na documentação da API.

### Exemplo de casos de uso

Seu CRM ou outro sistema interno armazena dados importantes sobre seus visitantes, que devem ser consistentemente atualizados no Target, sem expor os dados de perfil na implementação da página.

### Benefícios do método

Nenhum limite sobre o número de atributos de perfil.

Os atributos de perfil são enviados via site e podem ser atualizados pela API e vice-versa.

### Avisos

O tamanho do arquivo em lote deve ser menor que 50 MB. Além disso, o número total de linhas não deve ultrapassar 500.000 por carregamento.

Não há limite em relação ao número ou linhas que você pode carregar em um período de 24 horas em lotes subsequentes. No entanto, o processo de ingestão pode ter o fluxo controlado em horário comercial, para garantir que outros processos sejam executados com eficiência.

As [chamadas de atualização em lote V2 consecutivas](https://developers.adobetarget.com/api/#updating-profiles) sem chamadas da mbox entre as mesmas thirdPartyIds substituindo as propriedades atualizadas na primeira chamada de atualização em lote.

### Exemplo de código

Consulte [Atualização de perfis](https://developers.adobetarget.com/api/#updating-profiles).

### Links para informações relevantes

[Atualizações de perfis](https://developers.adobetarget.com/api/#updating-profiles)

## API de atualização de perfil único {#section_5D7A9DD7019F40E9AEF2F66F7F345A8D}

Quase idêntica à API de atualização de perfil em massa, mas um perfil de visitante é atualizado por vez, alinhada à chamada de API em vez de um arquivo .csv.

### Formato

O visitante deve ser identificado por meio do valor mboxPC do Target ou valor de mboxThirdPartyId. A Experience Cloud ID (ECID) não é suportada.

### Exemplo de casos de uso

Você deseja atualizar o Target em tempo real quando um visitante realiza alguma ação offline, como acessar uma central de atendimento, um empréstimo é financiado, uso de cartão de fidelidade na loja, acesso a um quiosque e assim por diante.

### Benefícios do método

Nenhum limite sobre o número de atributos de perfil.

Os atributos de perfil são enviados via site e podem ser atualizados pela API e vice-versa.

### Avisos

Limite de 1.000.000 de chamadas de API (1 milhão) por 24 horas

Perfis de atualização somente. Não é possível criar um perfil para um usuário potencia que o Target ainda precisa visualizar.

### Exemplo de código

Suporte a GET e POST.   `https://CLIENT.tt.omtrdc.net/m2/client/profile/update?mboxPC=1368007744041-575948.01_00&profile.attr1=0&profile.attr2=1...`

### Links para informações relevantes

[Atualizações de perfis](https://developers.adobetarget.com/api/#updating-profiles)

## Atributos do cliente {#section_C47FC7980A9A4608BD1A5F0BD900FA70}

Os atributos do cliente permitem que você carregue os dados de perfil do visitante via FTP à Experience Cloud. Após o upload, aproveite os dados no Adobe Analytics e no Adobe Target.

Os clientes do Target Standard podem utilizar 5 atributos, os clientes do Target Premium podem utilizar 200 atributos.

### Formato

Um arquivo .csv com Experience Cloud IDs (ECIDs) e os pares de nome/valor de atributo são carregados por FTP ou manualmente na interface de usuário da Experience Cloud.

### Exemplo de casos de uso

Seu CRM ou outros sistemas internos armazenam informações valiosas que deseja compartilhar com a Adobe Experience Cloud, incluindo Target e Analytics.

### Benefícios do método

Carregar os dados do cliente cria uma entrada de perfil para que o visitante no Target, mesmo se o Target ainda precisar visualizar o visitante.

Os mesmos dados estão automaticamente disponíveis no Target e no Analytics.

O FTP pode ser um método de implementação mais simples que a API.

### Avisos

Os clientes do Target Standard podem utilizar 5 atributos, os clientes do Target Premium podem utilizar 200 atributos

Podem atualizar valores via Atributos do cliente, não nas páginas.

Requer a implementação da Experience Cloud ID (ECID).

### Exemplo de código

Os detalhes podem ser encontrados em [Criar uma fonte de atributo do cliente e fazer upload do arquivo de dados](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).

### Links para informações relevantes

[Crie uma fonte de atributo do cliente e faça upload do arquivo de dados](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).
