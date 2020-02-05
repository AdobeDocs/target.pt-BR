---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes
description: Essas notas de versão oferecem informações sobre recursos, aprimoramentos, correções e problemas conhecidos para cada lançamento do Adobe Target Standard e do Target Premium.
title: 'Notas de versão do Target (atual) '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: e7a866c01b03815a2e167612d4c7922cef54a5c0

---


# Notas de versão do Target (atual){#target-release-notes-current}

Essas notas de versão oferecem informações sobre recursos, aprimoramentos e correções para cada lançamento do Target Standard e do Target Premium. Além disso, as notas de versão para APIs do Target, SDKs, biblioteca JavaScript (at.js) e outras alterações da plataforma também são incluídas, quando aplicável.

>[!IMPORTANT]
>
>A partir de 1º de março de 2020, o Target desativará o suporte para criptografia TLS 1.1 e TLS 1.0. A Segurança da camada de transporte (TLS) é o protocolo de segurança mais amplamente implantado usado atualmente em navegadores Web e outros aplicativos que exigem dados trocados de maneira segura por meio de uma rede. Essa alteração é necessária para atender ao padrão de conformidade de segurança geralmente aceito do TLS 1.2 ou superior. Verifique qual versão TLS você está usando no momento. Se sua versão for inferior a 1.2, implemente as alterações necessárias antes de 1º de março de 2020 para continuar a usar o Target conforme esperado.
>
> Para obter informações detalhadas sobre o possível impacto e as etapas que podem ser necessárias para atualizar sua implementação, consulte Alterações [de criptografia de](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)TLS (Transport Layer Security).

Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## Target Standard/Premium 20.1.1 (4 de fevereiro de 2020)

A versão Target Standard/Premium 20.1.1 é uma versão de manutenção e inclui melhorias e aprimoramentos de backend. Além disso, as seguintes correções foram incluídas:

* Corrigido um problema que fazia com que o campo do servidor de rastreamento do Adobe Analytics ficasse em branco na página Metas e configurações para atividades existentes do Adobe for Target (A4T). (TGT-35960)
* Corrigido um problema na interface do usuário que fazia com que sua seleção na segunda lista suspensa não fosse exibida ao criar um público-alvo para afinidade de categoria. (TGT-36098)

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão - APIs do servidor do Target](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Notas de versão relacionadas às APIs do servidor do Adobe Target. |
| [Notas de versão - SDK do Target Node.js](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Notas de versão relacionadas ao SDK Node.js do Adobe Target. |
| [Notas de versão - Target Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Notas de versão relacionadas ao Java SDK do Adobe Target. |
| [Detalhes da versão da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Detalhes sobre as alterações em cada versão da biblioteca JavaScript do Adobe Target at.js. |
| [Detalhes da versão da mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | Esta página mostra as alterações em cada versão da mbox.js.<br>Observe que a biblioteca mbox.js não está mais sendo desenvolvida. Todos os clientes devem migrar da mbox.js para a at.js. |

## Alterações na documentação, notas de versão anteriores e notas de versão da Experience Cloud {#section_1BC5F5208DA548E9B4344A0836E4B943}

Além das notas para cada versão, os recursos a seguir oferecem informações adicionais:

| Recurso | Detalhes |
|--- |--- |
| Alterações de documentação | Veja informações detalhadas sobre atualizações neste manual que podem não ser incluídas nas notas de versão.<br>Para obter mais informações, consulte [Alterações de documentação](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de versão para versões anteriores | Veja informações sobre os novos recursos e aprimoramentos das versões anteriores do Target Standard e do Target Premium.<br>Para obter mais informações, consulte [Notas de versões anteriores](../r-release-notes/release-notes-for-previous-releases.md). |
| Notas de versão da Adobe Experience Cloud | Veja as notas de versão mais recentes para as soluções da Adobe Experience Cloud.<br>Para obter mais informações, consulte Notas [de versão da](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)Experience Cloud. |

## Informações de pré-lançamento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Os recursos a seguir permitem ver as novidades previstas para a próxima versão do Target.

| Recurso | Detalhes |
|--- |--- |
| Lista de atualização de produtos prioritários da Adobe | Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Notas de versão futuras | Para obter informações sobre os lançamentos do Target do mês atual, incluindo informações de pré-lançamento, consulte a página [Notas de versão do Target - Pré-lançamento](/help/r-release-notes/target-release-notes.md). |
