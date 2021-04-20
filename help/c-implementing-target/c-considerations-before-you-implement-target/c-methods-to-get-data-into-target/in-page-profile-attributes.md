---
keywords: implementar; implementação; configuração; configurar; parâmetro de página
description: Obtenha dados no Target usando atributos de perfil na página.
title: Como obtenho dados no Target usando atributos de perfil na página?
feature: Implementation
role: Developer
exl-id: c6000720-a862-4e9c-96a5-055963a79544
translation-type: tm+mt
source-git-commit: 20daf4510e754d77cd16be64770105932178fec5
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 56%

---

# Atributos de perfil na página

Os atributos de perfil na página em [!DNL Adobe Target] (também chamados &quot;atributos de perfil in-mbox&quot;) são pares de nome/valor passados diretamente pelo código de página que são armazenados no perfil do visitante para uso futuro.

Os atributos de perfil na página permitem que os dados específicos do usuário sejam armazenados no perfil do Target para direcionamento e segmentação posteriores.

## Formato

Os atributos de perfil na página são enviados ao Target por uma chamada de servidor como par de nome/valor com o prefixo &quot;profile&quot;. antes do nome do Atributo.

Os nomes e valores do atributo são personalizáveis (embora alguns sejam &quot;nomes reservados&quot; para usos específicos).

### Exemplos

* `profile.membershipLevel=silver`
* `profile.visitCount=3`

## Exemplo de casos de uso

* **Informações de login**: compartilha dados que não são PII (Informações de identificação pessoal) com o Target com base no login do usuário. Esses dados podem ser status de associação, histórico do pedido ou muito mais.
* **Armazenar informações**: rastreia qual loja é a localização preferencial deste usuário.
* **Interações anteriores**: rastreia o que o usuário fez no site antes para informar sobre personalizações futuras.

## Benefícios do método

Os dados são enviados ao Target em tempo real e podem ser usados na mesma chamada de servidor em que os dados são recebidos.

## Avisos

Precisa de atualizações do código da página (diretamente ou por meio de um sistema de gerenciamento de tags).

Os atributos e valores estão visíveis nas chamadas do servidor, para que um visitante possa ver os valores. Se estiver compartilhando informações, como intervalos de crédito ou outras informações potencialmente privadas, esse método pode não ser a melhor abordagem.

## Exemplos de código

targetPageParamsAll (anexa os atributos a todas as chamadas de mbox na página):

`function targetPageParamsAll() { return "profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

targetPageParams (anexa os atributos ao mbox global na página):

`function targetPageParams() { return profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

Atributos no código mboxCreate:

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','profile.param1=value1','profile.param2=value2'); </script>`

## Links para informações relevantes

[Atributos do perfil](/help/c-target/c-visitor-profile/profile-parameters.md#concept_01A30B4762D64CD5946B3AA38DC8A201)

[Perfil do visitante](/help/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)
