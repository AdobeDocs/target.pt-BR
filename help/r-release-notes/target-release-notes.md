---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notas de versão que fornecem informações sobre recursos, melhorias e correções para as versões mais recentes ou futuras do Adobe Target DNL.
title: Notas de pré-lançamento do Adobe Target
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 578f71f84f4db06dbc91679562007450166a8a22

---


# Notas de versão do Target (pré-lançamento){#target-release-notes-prerelease}

Estas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para as versões mais recentes ou que serão lançadas em breve do [!DNL Adobe Target].

**Última atualização: 9 de março de 2020**

>[!NOTE]
>
>* Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio. Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser iguais ou diferentes, dependendo do tempo das versões.
   >
   >
* Os números de edição entre parênteses são para uso interno da [!DNL Adobe].
   >
   >
* **Alterações** de suporte a TLS: A partir de 1º de março de 2020, o Target desativará o suporte para criptografia TLS 1.1 e TLS 1.0. A Segurança da camada de transporte (TLS) é o protocolo de segurança mais amplamente implantado usado atualmente em navegadores Web e outros aplicativos que exigem dados trocados de maneira segura por meio de uma rede. Essa alteração é necessária para atender ao padrão de conformidade de segurança geralmente aceito do TLS 1.2 ou superior. Verifique qual versão do TLS você está usando no momento. Se sua versão for inferior a 1.2, implemente as alterações necessárias antes de 1º de março de 2020 para continuar a usar o Target conforme esperado.
   >
   >   
   Para obter informações detalhadas sobre o possível impacto e as etapas que podem ser necessárias para atualizar sua implementação, consulte Alterações [de criptografia de](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)TLS (Transport Layer Security).
   >
   >
* **desaprovação** da mbox.js: Em 30 de agosto de 2020, o Adobe Target não oferecerá mais suporte à biblioteca mbox.js. Após 30 de agosto de 2020, todas as chamadas feitas do mbox.js falharão e afetarão suas páginas que têm atividades do Target em execução. Recomendamos que todos os clientes migrem para a versão mais recente da biblioteca do at.js antes dessa data para evitar possíveis problemas com seus sites. For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md).
   >
   >   
   Embora a mbox.js seja atualmente compatível, não fornecemos atualizações de recursos para esta biblioteca desde julho de 2017. O mais recente at.js oferece muitas vantagens sobre o mbox.js. Entre outros benefícios, o at.js melhora o tempo de carregamento da página para implementações da Web, melhora a segurança e oferece melhores opções de implementação para aplicativos de página única.
   >
   >   
   Ao mudar todos os clientes para o at.js, nossos engenheiros e funcionários de suporte poderão fornecer novas funcionalidades e oferecer o suporte que você espera da Adobe.


## Target Standard/Premium 20.2.1 (A Ser Determinado)

Verifique aqui a data exata em que essas informações se tornam disponíveis.

>[!IMPORTANT]
>
>Consulte as informações acima sobre a desaprovação do mbox.js.

Esta versão contém os seguintes aprimoramentos, correções e alterações:

* Correção de um problema que impedia os clientes de selecionar uma coleção ao executar uma pesquisa de catálogo. (TGT-36230)
* Correção de um problema em que um critério criado por meio da API, mas não referenciado por uma atividade criada na interface do usuário do Target, podia ser excluído erroneamente da interface do usuário. (TGT-35917)
* Aprimoramentos de segurança implementados na Política de segurança de conteúdo (CSP). (TGT-36190)
* Correção de um problema que fazia com que &quot;NaN%&quot; fosse exibido ao deslizar a barra de porcentagem de Ponderação do atributo para a extremidade esquerda. (TGT-36211)
* Solução de problemas de localização para que o texto da interface em vários idiomas seja exibido corretamente.
* As seguintes métricas do Adobe Analytics não são mais suportadas pelo Analytics para Target (A4T) em vigor na versão de março de 2020 do Target:
   * averagvisitdepth
   * bots
* As métricas a seguir não são mais suportadas e são convertidas automaticamente em novas versões da métrica na primeira vez que um usuário modifica uma atividade que contém a métrica:

   | Métrica obsoleta | Nova métrica |
   |--- |--- |
   | `averagetimespentonpage` | `averagetimespentonsite` (nota: medido em minutos em vez de segundos) |
   | `instances` | `occurrences` |
   | `singleaccess` | `singlepagevisits` |
   | `uniquevisitors` | `visitors` |
   | `visitorsdaily`, `visitorshourly`, `visitorsmonthly`, `visitorsquarterly`, `visitorsweekly`, `visitorsyearly` | `visitors` |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
