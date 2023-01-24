---
keywords: Notas de versão;novos recursos;versões;atualizações;atualização;versão;aprimoramento;aprimoramentos;correções;correções de bugs;atualizações
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 33d85fcbfc971c188f4154cca5b4d21103b4dbb7
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 94%

---

# Notas de versão do [!DNL Target] (atuais)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium]. Além disso, as notas de versão para APIs [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outras alterações de plataforma também estão incluídas, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## [!DNL Target] Standard/Premium 22.13.3 (25 de janeiro de 2023)

Essa versão contém os seguintes novos recursos, aprimoramentos e correções:

| Recurso | Detalhes |
| --- | --- |
| Automated Personalization (AP) | Adição de suporte para ofertas JSON em atividades do [!UICONTROL Automated Personalization] (AP) usando o Experience Composer baseado em formulário.<br>Para obter mais informações, consulte [Criar ofertas JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md). (TGT-41460) |
| Recommendations | Nomes amigáveis em [!UICONTROL Analytics para Target] Os relatórios do A4T agora estão disponíveis. Anteriormente, o [!DNL Target] listava somente IDs de experiência. Esse aprimoramento alinha os relatórios do [!DNL Adobe Analytics] e [!DNL Target] e ajuda os clientes a simplificar a criação de relatórios no A4T. (TGT-41853) |
| Controle de qualidade da atividade | Implementado [Modo de controle de qualidade](/help/main/c-activities/c-activity-qa/activity-qa.md) para atividades de AP para clientes selecionados. Essa funcionalidade estará disponível para todos os clientes após uma fase de teste inicial. (TGT-44341) |

* Correção de um problema que causava um &quot;erro 500&quot; no [!UICONTROL Teste A/B] e em atividades de [!UICONTROL Direcionamento de experiência] (XT) que contêm recomendações. Esse problema era causado quando o [!DNL Target] falhava ao excluir corretamente os objetos de critérios da interface do [!DNL Target] e do back-end do [!DNL Recommendations] que não estão mais em uso. (TGT-44383)
* Remoção do local do nome de oferta exibido no relatório de [!UICONTROL Nível da oferta] das atividades em [!UICONTROL Automated Personalization]. Essa alteração torna o relatório mais legível. (TGT-44294)
* A opção “[!UICONTROL Fragmento de experiência]” foi renomeada no fluxo de trabalho do [!UICONTROL Visual Experience Composer] (VEC). A opção agora é “[!UICONTROL HTML XF]”. (TGT-44132)
* As opções de calendário de 45 dias e 90 dias foram removidas do AP e dos relatórios de [!UICONTROL Direcionamento automático], [!UICONTROL Insights de personalização] e [!UICONTROL Atributos importantes] na interface do [!DNL Target]. Devido aos padrões de uso e para melhorar o desempenho, esses intervalos de datas foram removidos. A interface será atualizada para refletir os intervalos permitidos no momento: 15, 30 e 60 dias. (TGT-39357)
* Remoção da capacidade de alterar a configuração [!UICONTROL Igual à meta de otimização] na página [!UICONTROL Metas e configurações] após a ativação da atividade. (TGT-43923)
* Correção de um problema que causava problemas com o local de trabalho padrão no back-end do [!DNL Target] ao atualizar do [!DNL Target Standard] para o [!DNL Target Premium]. (TGT-44081 e TGT-44306)
* Alteração do link na página de [!UICONTROL Implementação] ([!UICONTROL Administração] > [!UICONTROL Implementação]) para os &quot;Métodos de implementação com decisão no dispositivo&quot; para apontar para a página que explica como usar a decisão no dispositivo para todos os SDKs compatíveis: Node.js, Java, .NET e Python. Para obter mais informações, consulte [Introdução aos SDKs de Target](https://developer.adobe.com/target/implement/server-side/sdk-guides/getting-started/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.
* Correção de um problema que causava problemas de upload de arquivo ao usar o [!DNL Scene7] e o [!DNL Target].
* Aprimoramento da acessibilidade da interface do [!DNL Target] para pessoas com deficiência usando resultados de uma auditoria interna de usabilidade. Essas melhorias de acessibilidade incluem recursos que antes não eram acessíveis por meio do teclado, melhorias no texto alternativo, a capacidade de ampliar partes da interface para serem mais utilizáveis, foco do teclado aprimorado e muito mais.   (TGT-42759)
* Várias correções de localização foram feitas na interface do [!DNL Target].

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da Platform. |
| [Detalhes da versão da at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Alterações na documentação, notas de versão anteriores e notas de versão da Experience Cloud

Além das notas para cada versão, os recursos a seguir oferecem informações adicionais:

| Recurso | Detalhes |
|--- |--- |
| Alterações de documentação | Veja informações detalhadas sobre atualizações neste manual que podem não estar incluídas nas notas de versão.<br>Para obter mais informações, consulte [Alterações de documentação](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de versão para versões anteriores | Veja informações sobre os novos recursos e aprimoramentos das versões anteriores do Target Standard e do Target Premium.<br>Para obter mais informações, consulte [Notas de versões anteriores](/help/main/r-release-notes/release-notes-for-previous-releases.md). |
| Notas de versão da Adobe Experience Cloud | Veja as notas de versão mais recentes para as soluções da Adobe Experience Cloud.<br>Para obter mais informações, consulte as [Notas de versão da Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR). |

## Informações de pré-lançamento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Os recursos a seguir permitem ver as novidades previstas para a próxima versão do Target.

| Recurso | Detalhes |
|--- |--- |
| Atualização de produtos prioritários da Adobe | Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Notas de versão futuras | Para obter informações sobre os lançamentos do Target do mês atual, incluindo informações de pré-lançamento, consulte a página [Notas de versão do Target - Pré-lançamento](/help/main/r-release-notes/target-release-notes.md). |
