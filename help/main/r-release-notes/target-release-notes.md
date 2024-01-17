---
keywords: notas de versão;versões;atualizações;versão futura;melhorias;novos recursos;correções;atualizações;pré-lançamento
description: Saiba mais sobre os novos recursos, melhorias e correções adicionados na próxima versão do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos e melhorias que serão incluídos na próxima versão do  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: b76a0541b181ee5ebe88f2d11f5556c6c7b91126
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 50%

---

# Notas de versão do [!DNL Target] (pré-lançamento)

Este artigo contém informações de pré-lançamento das próximas versões do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.

**Última atualização: quarta-feira, 16 de janeiro de 2024**

>[!NOTE]
>
>As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.
>
>Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## Substituição do iPad e do iPhone pelo atributo de público-alvo do navegador (30 de abril de 2024)

| Substituição | Detalhes |
|--- |--- |
| [!DNL iPad] e [!DNL iPhone] a ser descontinuado do [Atributo do navegador](/help/main/c-target/c-audiences/c-target-rules/browser.md) usado ao criar públicos.<p>Data de desativação:<P>quarta-feira, 30 de abril de 2024 | [!DNL Adobe Target] permite [direcionar em qualquer um dos vários atributos de categoria](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), incluindo os usuários que utilizam um [opções do navegador ou do navegador](/help/main/c-target/c-audiences/c-target-rules/browser.md) quando visitarem sua página.<P><B>A partir de 30 de abril de 2024, o iPad e o iPhone serão removidos do disponível [!UICONTROL Navegador] digite a lista suspensa ao criar categorias para públicos-alvo.</b><P>Se você tiver públicos-alvo que direcionem iPads ou iPhones usando o [!UICONTROL Navegador] você deve alterar essas configurações antes de 30 de abril de 2024 para garantir que esses públicos-alvo continuem a funcionar conforme esperado.<P>As seguintes configurações devem ser usadas a partir de agora:<ul><li>[!UICONTROL Dispositivo móvel] > [!UICONTROL é tablet]<P>![dispositivo móvel é tablet](/help/main/r-release-notes/assets/is-tablet.png)</li><li>[!UICONTROL Dispositivo móvel] > [!UICONTROL Nome de comercialização do dispositivo] [!UICONTROL corresponde a] [!DNL iPad]<P>![iPad](/help/main/r-release-notes/assets/ipad.png)</li><li>[!UICONTROL Dispositivo móvel] > [!UICONTROL Nome de comercialização do dispositivo] [!UICONTROL corresponde a] [!DNL iPhone]<p>![iPhone](/help/main/r-release-notes/assets/iphone.png)</li></ul> |

## [!DNL Target] Standard/Premium 24.1.1 (22, 23 e 25 de janeiro de 2024)

Este lançamento está previsto para os seguintes dias:

* **22 de janeiro**: regiões da Europa, Oriente Médio e África (EMEA)
* **23 de janeiro**: região da Ásia-Pacífico (APAC)
* **25 de janeiro**: região das Américas

Essa versão conta com os seguintes aprimoramentos e correções:

* Correção de um problema que fazia com que os intervalos de datas do relatório não funcionassem corretamente. (TGT-47396)
* Correção de um problema que fazia com que o status incorreto fosse exibido no [!UICONTROL Todas as atividades] depois que os clientes ativaram ou desativaram uma atividade usando o [!UICONTROL Mais ações] ícone. (TGT-47367)
* Correção de um problema que causava a [!UICONTROL Atributos importantes] relatório que não será exibido para um cliente. (TGT-47272)
* Correção de um problema que exibia a mensagem &quot;Carga inválida&quot; quando um cliente tentava habilitar &quot;Requer autenticação&quot;. (TGT-47195)
* Atualização de várias strings localizadas no [!DNL Target] IU.

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da Platform. |
| [Detalhes da versão da at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
