---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes
description: Notas de versão que fornecem informações sobre recursos, melhorias e correções para as versões mais recentes ou futuras do Adobe Target DNL.
title: Notas de pré-lançamento do Adobe Target
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 93ffd24946ad23780b8c141bec79e4492f0e8cda

---


# Notas de versão do Target (pré-lançamento){#target-release-notes-prerelease}

Estas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para as versões mais recentes ou que serão lançadas em breve do [!DNL Adobe Target].

**Última atualização: 18 de fevereiro de 2020**

>[!NOTE]
>
>* Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio. Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser iguais ou diferentes, dependendo do tempo das versões.
   >
   >
* Os números de edição entre parênteses são para uso interno da [!DNL Adobe].
   >
   >
* A partir de 1º de março de 2020, o Target desativará o suporte para criptografia TLS 1.1 e TLS 1.0. A Segurança da camada de transporte (TLS) é o protocolo de segurança mais amplamente implantado usado atualmente em navegadores Web e outros aplicativos que exigem dados trocados de maneira segura por meio de uma rede. Essa alteração é necessária para atender ao padrão de conformidade de segurança geralmente aceito do TLS 1.2 ou superior. Verifique qual versão TLS você está usando no momento. Se sua versão for inferior a 1.2, implemente as alterações necessárias antes de 1º de março de 2020 para continuar a usar o Target conforme esperado.
   >
   >   
   Para obter informações detalhadas sobre o possível impacto e as etapas que podem ser necessárias para atualizar sua implementação, consulte Alterações [de criptografia de](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)TLS (Transport Layer Security).


## Target Standard/Premium 20.2.1 (19 de fevereiro de 2020)

Esta versão contém os seguintes aprimoramentos e correções:

* Correção de um problema que impedia os clientes de selecionar uma coleção ao executar uma pesquisa de catálogo. (TGT-36230)
* Correção de um problema em que um critério criado por meio da API, mas não referenciado por uma atividade criada na interface do usuário do Target, podia ser excluído erroneamente da interface do usuário. (TGT-35917)
* Aprimoramentos de segurança implementados na Política de segurança de conteúdo (CSP). (TGT-36190)
* Correção de um problema que fazia com que &quot;NaN%&quot; fosse exibido ao deslizar a barra de porcentagem de Ponderação do atributo para a extremidade esquerda. (TGT-36211)
* Solução de um problema que impedia os clientes de alterar o algoritmo em uma atividade de Personalização automatizada (AP) de Floresta aleatória para Variação residual. (TGT-36321)
* Solução de problemas de localização para que o texto da interface em vários idiomas seja exibido corretamente.

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
