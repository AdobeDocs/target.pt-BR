---
keywords: notas de versão;versões;atualizações;versão futura;melhorias;novos recursos;correções;atualizações;pré-lançamento
description: Saiba mais sobre os novos recursos, melhorias e correções adicionados na próxima versão do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos e melhorias que serão incluídos na próxima versão do  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 99152f66217f66174e8b6a5a7319f11b22c74b8e
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 96%

---

# Notas de versão do [!DNL Target] (pré-lançamento)

Este artigo contém informações de pré-lançamento das próximas versões do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.

**Última atualização: terça-feira, 22 de janeiro de 2024**

>[!NOTE]
>
>As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.
>
>Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## Descontinuação do iPad e iPhone do atributo de público-alvo do navegador (30 de abril de 2024)

| Descontinuação | Detalhes |
|--- |--- |
| [!DNL iPad] e [!DNL iPhone] serão descontinuados do [atributo do navegador](/help/main/c-target/c-audiences/c-target-rules/browser.md) usado ao criar públicos-alvo.<p>Data da descontinuação:<P>30 de abril de 2024 | O [!DNL Adobe Target] permite [segmentar qualquer um dos vários atributos de categoria](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), incluindo usuários que usam um [navegador específico ou opções de navegador](/help/main/c-target/c-audiences/c-target-rules/browser.md) quando visitam sua página.<P><B>A partir de 30 de abril de 2024, o iPad e o iPhone serão removidos da lista suspensa do tipo [!UICONTROL Navegador] disponível ao criar categorias para públicos-alvo.</b><P>Se você tiver públicos-alvo que visam iPads ou iPhones usando o atributo [!UICONTROL Navegador], será necessário alterar essas configurações antes de 30 de abril de 2024 para garantir que esses públicos-alvo continuem funcionando conforme o esperado.<p>Para obter exemplos de configurações alternativas, consulte [Substituição do iPad e do iPhone pelo atributo de público-alvo do navegador (30 de abril de 2024)](/help/main/c-target/c-audiences/c-target-rules/browser.md#deprecation). |

## [!DNL Target] Standard/Premium 24.1.1 (22, 23 e 25 de janeiro de 2024)

Este lançamento está previsto para os seguintes dias:

* **22 de janeiro**: regiões da Europa, Oriente Médio e África (EMEA)
* **23 de janeiro**: região da Ásia-Pacífico (APAC)
* **25 de janeiro**: região das Américas

Essa versão conta com os seguintes aprimoramentos e correções:

* As atividades do [!UICONTROL Analytics for Target] (A4T) com métricas de meta de receita não exibiam “Receita” como o nome da coluna e a métrica de receita não era exibida no formato ($) no relatório. Era um problema superficial que foi corrigido. (TGT-46995)
* Correção de um problema que fazia com que os intervalos de datas do relatório não funcionassem corretamente. (TGT-47396)
* Correção de um problema que fazia com que um status incorreto fosse exibido na página [!UICONTROL Todas as atividades] depois que os clientes ativavam ou desativavam uma atividade usando o ícone [!UICONTROL Mais ações]. (TGT-47367)
* Correção de um problema que fazia com que o relatório [!UICONTROL Atributos importantes] não fosse exibido para um cliente. (TGT-47272)
* Correção de um problema que fazia com que uma mensagem “Conteúdo inválido” fosse exibida quando um único cliente tentava habilitar a opção “Exigir autenticação”. (TGT-47195)
* Atualização de várias strings localizadas na interface do [!DNL Target].

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da Platform. |
| [Detalhes da versão da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
