---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notas de versão que fornecem informações sobre recursos, melhorias e correções para as versões mais recentes ou futuras do Adobe Target DNL.
title: Notas de pré-lançamento do Adobe Target
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 25f7ce65f4f9b863ce6ebfe0a7ff8df08e561741
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 17%

---


# Notas de versão do Target (pré-lançamento){#target-release-notes-prerelease}

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização: 12 de junho de 2020**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do tempo das versões. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

>[!NOTE]
>
>* **desaprovação** da mbox.js: Em 30 de agosto de 2020, o Adobe Target não oferecerá mais suporte à biblioteca mbox.js. Após 30 de agosto de 2020, todas as chamadas feitas do mbox.js falharão e afetarão suas páginas com atividades do Público alvo em execução. Recomendamos que todos os clientes migrem para a versão mais recente da biblioteca do at.js antes dessa data para evitar possíveis problemas com seus sites. Para obter mais informações, consulte [Como o At.js funciona](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) e o Construtor de habilidades do [Adobe Target: Bate-papo no desenvolvedor, migre o mbox.js do Adobe Target para o at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
   >
   >   
   Embora a mbox.js seja atualmente compatível, não fornecemos atualizações de recursos para esta biblioteca desde julho de 2017. O mais recente at.js oferece muitas vantagens sobre o mbox.js. Entre outros benefícios, o at.js melhora o tempo de carregamento da página para implementações da Web, melhora a segurança e oferece melhores opções de implementação para aplicativos de página única.
   >
   >   
   Ao mudar todos os clientes para o at.js, nossos engenheiros e funcionários de suporte poderão fornecer novas funcionalidades e oferta do suporte que você espera da Adobe.
   >
   >
* **Anúncios** do Público alvo: Consulte a página de anúncios do Público alvo para obter informações sobre eventos futuros, incluindo sessões do Público alvo Skill Builder, bate-papos para desenvolvedores, webinars e sessões do Público alvo Coffee Break. Para obter mais informações, consulte Anúncios de [Públicos alvos](/help/r-release-notes/target-announcements.md).


## Versões at.js 1.8.2 e at.js 2.3.1 (15 de junho de 2020)

As seguintes melhorias e correções foram feitas nas bibliotecas do [!DNL Target] at.js:

### at.js 1.8.2

* Correção de um problema ao usar o CNAME e a substituição de borda, at.js 1.*O x* pode criar incorretamente o domínio do servidor, o que resultou na falha da [!DNL Target] solicitação. (TNT-35064)

### at.js 2.3.1

* A `deviceIdLifetime` configuração foi substituída por [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md). (TNT-36349)
* Correção de um problema ao usar o CNAME e a substituição de borda, at.js 2.*O x* pode criar incorretamente o domínio do servidor, o que resultou na falha da [!DNL Target] solicitação. (TNT-35065)
* Correção de um problema ao usar a [!DNL Target] extensão v2 e a [!DNL Launch][!DNL Adobe Analytics] extensão, [!DNL Launch] atrasou a [!DNL Target] [!DNL Analytics] `sendBeacon` chamada. (TNT-36407, TNT-35990, TNT-36000)

## Target Standard/Premium 20.5.1 (17 de junho de 2020)

| Recurso  / Aprimoramento | Descrição |
| --- | --- |
| Analytics for Target (A4T) suporte para a autoalocação de atividades | Com a versão de junho, a Autoalocação de testes oferecerá suporte ao [Analytics para Público alvo](/help/c-integrating-target-with-mac/a4t/a4t.md). Essa integração permite que você use o recurso de alocação automática de banco com várias armas para direcionar o tráfego para experiências vencedoras, ao mesmo tempo que usa uma métrica de objetivo do Adobe Analytics e/ou recursos de relatórios e análise do Adobe Analytics. Se você já tiver [implementado a A4T](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) para uso com atividades de teste A/B e direcionamento de experiência, todos estarão configurados! |
| Papel do editor | Essa nova função é semelhante à função atual do Observador (pode visualização atividades, mas não pode criá-las ou editá-las). No entanto, a função Editor tem permissão adicional para ativar o atividade. |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
