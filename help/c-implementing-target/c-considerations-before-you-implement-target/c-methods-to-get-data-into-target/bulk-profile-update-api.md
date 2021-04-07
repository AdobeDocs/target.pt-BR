---
keywords: implementar; implementação; configuração; configurar; atualização de perfil em massa
description: Obtenha dados no Target usando a API de atualização de perfil em massa.
title: Como obtenho dados no Target usando a API de atualização de perfil em massa?
feature: Implementação
role: Developer
translation-type: tm+mt
source-git-commit: e8c25685341319fea4381386cad1ce0c5b80face
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 78%

---

# API de atualização de perfil em massa

Por meio da API, envie um arquivo .csv para [!DNL Adobe Target] com atualizações de perfil do visitante para muitos visitantes. Cada perfil do visitante pode ser atualizado com vários atributos de perfil na página em uma chamada.

Essa opção é semelhante aos Atributos do cliente, com algumas diferenças:

* Os Atributos do cliente usam um carregamento de FTP, enquanto a API de atualização de perfil em massa do Target usa uma API HTTP POST.
* Os dados de atributo do cliente podem ser compartilhados com o Analytics. A Atualização de perfil em massa é utilizável somente no Target.
* Os Atributos do cliente suportam a criação de um perfil para um usuário que o Target ainda não visualizou. A API de atualização do perfil em massa atualiza somente os perfis existentes do Target.
* Os Atributos do cliente necessitam do uso de uma Experience Cloud ID (ECID). A API de atualização do perfil em massa requer ID de TNT ou `mbox3rdPartyId`.
* Não é possível enviar os seguintes caracteres em `mbox3rdPartyID`: sinal de adição (+) e barra invertida (/).

## Formato

O arquivo .csv deve fazer referência a cada visitante por meio de Target PCID ou mboxThirdPartyId. A Experience Cloud ID (ECID) não é suportada. Todos os atributos/valores de perfil são criados e atualizados via API. Os detalhes de formato estão disponíveis na documentação da API.

## Exemplo de casos de uso

Seu CRM ou outro sistema interno armazena dados importantes sobre seus visitantes, que devem ser consistentemente atualizados no Target, sem expor os dados de perfil na implementação da página.

## Benefícios do método

Nenhum limite sobre o número de atributos de perfil.

Os atributos de perfil são enviados via site e podem ser atualizados pela API e vice-versa.

## Avisos

O tamanho do arquivo em lote deve ser menor que 50 MB. Além disso, o número total de linhas não deve ultrapassar 500.000 por carregamento.

Não há limite em relação ao número ou linhas que você pode carregar em um período de 24 horas em lotes subsequentes. No entanto, o processo de ingestão pode ter o fluxo controlado em horário comercial, para garantir que outros processos sejam executados com eficiência.

As [chamadas de atualização em lote V2 consecutivas](https://developers.adobetarget.com/api/#updating-profiles) sem chamadas da mbox entre as mesmas thirdPartyIds substituindo as propriedades atualizadas na primeira chamada de atualização em lote.

## Exemplos de código

Consulte [Atualização de perfis](https://developers.adobetarget.com/api/#updating-profiles).

### Links para informações relevantes

[Atualizações de perfis](https://developers.adobetarget.com/api/#updating-profiles)