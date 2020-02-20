---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes
description: Essas notas de versão oferecem informações sobre recursos, aprimoramentos, correções e problemas conhecidos para cada lançamento do Adobe Target Standard e do Target Premium.
title: 'Notas de versão do Target (atual) '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 5042acd5b646d3debf0d2be79bf317401a98763e

---


# Notas de versão do Target (atual){#target-release-notes-current}

Essas notas de versão oferecem informações sobre recursos, aprimoramentos e correções para cada lançamento do Target Standard e do Target Premium. Além disso, as notas de versão para APIs do Target, SDKs, biblioteca JavaScript (at.js) e outras alterações da plataforma também são incluídas, quando aplicável.

>[!NOTE]
>
>* **Alterações** de suporte a TLS:A partir de 1º de março de 2020, o Target desativará o suporte para criptografia TLS 1.1 e TLS 1.0. A Segurança da camada de transporte (TLS) é o protocolo de segurança mais amplamente implantado usado atualmente em navegadores Web e outros aplicativos que exigem dados trocados de maneira segura por meio de uma rede. Essa alteração é necessária para atender ao padrão de conformidade de segurança geralmente aceito do TLS 1.2 ou superior. Verifique qual versão TLS você está usando no momento. Se sua versão for inferior a 1.2, implemente as alterações necessárias antes de 1º de março de 2020 para continuar a usar o Target conforme esperado.
   >
   >   
   Para obter informações detalhadas sobre o possível impacto e as etapas que podem ser necessárias para atualizar sua implementação, consulte Alterações [de criptografia de](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)TLS (Transport Layer Security).
   >
   >
* **desaprovação** da mbox.js:Em 30 de agosto de 2020, o Adobe Target não oferecerá mais suporte à biblioteca mbox.js. Após 30 de agosto de 2020, todas as chamadas feitas do mbox.js falharão e afetarão suas páginas que têm atividades do Target em execução. Recomendamos que todos os clientes migrem para a versão mais recente da biblioteca do at.js antes dessa data para evitar possíveis problemas com seus sites. For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md).
   >
   >   
   Embora a mbox.js seja atualmente compatível, não fornecemos atualizações de recursos para esta biblioteca desde julho de 2017. O mais recente at.js oferece muitas vantagens sobre o mbox.js. Entre outros benefícios, o at.js melhora o tempo de carregamento da página para implementações da Web, melhora a segurança e oferece melhores opções de implementação para aplicativos de página única.
   >
   >   
   Ao mudar todos os clientes para o at.js, nossos engenheiros e funcionários de suporte poderão fornecer novas funcionalidades e oferecer o suporte que você espera da Adobe.
   >
   >
* Os números de edição entre parênteses são para uso interno da [!DNL Adobe].


## Target Standard/Premium 20.2.1 (19 de fevereiro de 2020)

>[!IMPORTANT]
>
>Consulte as informações acima sobre a desaprovação do mbox.js.

Esta versão contém os seguintes aprimoramentos e correções:

* Correção de um problema que impedia os clientes de selecionar uma coleção ao executar uma pesquisa de catálogo. (TGT-36230)
* Correção de um problema em que um critério criado por meio da API, mas não referenciado por uma atividade criada na interface do usuário do Target, podia ser excluído erroneamente da interface do usuário. (TGT-35917)
* Aprimoramentos de segurança implementados na Política de segurança de conteúdo (CSP). (TGT-36190)
* Correção de um problema que fazia com que &quot;NaN%&quot; fosse exibido ao deslizar a barra de porcentagem de Ponderação do atributo para a extremidade esquerda. (TGT-36211)
* Solução de problemas de localização para que o texto da interface em vários idiomas seja exibido corretamente.

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
