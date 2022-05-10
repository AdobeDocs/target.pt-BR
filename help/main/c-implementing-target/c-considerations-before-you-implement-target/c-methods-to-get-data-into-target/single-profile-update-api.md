---
keywords: implementar; implementação; configuração; configurar; configuração; atualização de perfil único
description: Obter dados em [!DNL Target] usando a API de atualização de perfil único.
title: Como obter dados sobre [!DNL Target] Usando a API de atualização de perfil único?
feature: Implementation
role: Developer
exl-id: 8331866c-0b84-4d08-83b4-f7f82c67cd21
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 59%

---

# API de atualização de perfil único

Quase idêntica à API de atualização de perfil em massa, mas um perfil de visitante é atualizado por vez, alinhada à chamada de API em vez de um arquivo .csv.

## Formato

O visitante deve ser identificado por meio do valor mboxPC do Target ou valor de mboxThirdPartyId. A Experience Cloud ID (ECID) não é suportada.

## Exemplo de casos de uso

Você deseja atualizar o Target em tempo real quando um visitante executar alguma ação offline. As ações podem incluir acessar uma central de atendimento, um empréstimo é financiado, usando um cartão de fidelidade na loja, acessando um quiosque e assim por diante.

## Benefícios do método

Nenhum limite sobre o número de atributos de perfil.

Os atributos de perfil são enviados via site e podem ser atualizados pela API e vice-versa.

## Avisos

Limite de 1.000.000 de chamadas de API (1 milhão) por 24 horas

Perfis de atualização somente. Não é possível criar um perfil para um usuário potencia que o Target ainda precisa visualizar.

## Exemplos de código

Suporte a GET e POST.  `https://CLIENT.tt.omtrdc.net/m2/client/profile/update?mboxPC=1368007744041-575948.01_00&profile.attr1=0&profile.attr2=1...`

>[!MORELIKETHIS]
>
>* [Atualizações de perfis](https://developers.adobetarget.com/api/#updating-profiles)
