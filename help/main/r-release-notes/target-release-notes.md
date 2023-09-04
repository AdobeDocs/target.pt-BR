---
keywords: notas de versão;versões;atualizações;versão futura;melhorias;novos recursos;correções;atualizações;pré-lançamento
description: Saiba mais sobre os novos recursos, melhorias e correções adicionados na próxima versão do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos e melhorias que serão incluídos na próxima versão do  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 362fac25f04028dff0fb0233d418ef9ce88e53d6
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 56%

---

# Notas de versão do [!DNL Target] (pré-lançamento)

Este artigo contém informações de pré-lançamento das próximas versões do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.

**Última atualização: 4 de setembro de 2023**

>[!NOTE]
>
>As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.
>
>Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## [!DNL Target] Standard/Premium 23.9.1 (6-11 de setembro de 2023)

Esta versão estará disponível de acordo com o seguinte cronograma:

* **6 de setembro**: região das Américas
* **7 de setembro**: regiões da Europa, Oriente Médio e África (EMEA)
* **11 de setembro**: região Ásia-Pacífico (APAC)

Essa versão conta com os seguintes aprimoramentos e correções:

* Correção de um problema que causava dados de relatórios inconsistentes no [!DNL Target] A interface do usuário e o [!DNL Adobe Analytics] Interface do usuário para [!UICONTROL Alocação automática] atividades que usam [!UICONTROL Analytics for Target] (A4T) como fonte de relatórios. (TGT-46112)
* O tempo limite das chamadas de PUT para a API de entrega do Target foi aumentado para 15 segundos para evitar erros de tempo limite. (TGT-46091)
* Correção de um problema que exibia o nome de relatório incorreto ao alternar entre a variável [!UICONTROL Exibição de tabela] e a variável [!UICONTROL Segmentos automatizados] e [!UICONTROL Atributos importantes] relatórios. (TGT-46040)
* Aprimoramento do [!UICONTROL Visual Experience Composer] (VEC) para oferecer suporte ao Lightning DOM (Componentes da Web). (TGT-45422)
* Correção de um problema que fazia com que as ações do VEC fossem aplicadas na ordem incorreta. Em alguns casos, o VEC aplicou algumas modificações de forma assíncrona e adicionar modificações extras a um elemento causou erros se esse elemento fosse exibido após um [!UICONTROL Inserir] ação. (TGT-45983)
* Adição da capacidade de especificar um seletor de CSS no VEC. (TGT-45958 e TGT-46017)
* Correção de um problema ao abrir uma página de Aplicativo de página única (SPA) no VEC e, em seguida, ir para o modo Procurar, fazia com que as setas Voltar e Encaminhar não funcionassem corretamente. (TGT-45956)
* Correção de um problema que impedia a atualização consistente do URL ao navegar por um site de Aplicativo de página única (SPA). (TGT-45417)

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da Platform. |
| [Detalhes da versão da at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
