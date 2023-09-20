---
keywords: notas de versão;versões;atualizações;versão futura;melhorias;novos recursos;correções;atualizações;pré-lançamento
description: Saiba mais sobre os novos recursos, melhorias e correções adicionados na próxima versão do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos e melhorias que serão incluídos na próxima versão do  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 11b5915d75b72a3891572d841de0a353f68dcbf3
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 72%

---

# Notas de versão do [!DNL Target] (pré-lançamento)

Este artigo contém informações de pré-lançamento das próximas versões do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.

**Última atualização: 18 de setembro de 2023**

>[!NOTE]
>
>As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.
>
>Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## [!DNL Target] Standard/Premium 23.9.3 (18 de setembro de 2023)

Essa versão conta com os seguintes aprimoramentos e correções:

* Aprimoramento do [!UICONTROL Visual Experience Composer] (VEC) para oferecer suporte a Componentes Web Lightning (Light DOM). (TGT-45422)
* Correção de um problema que fazia com que as ações do VEC fossem aplicadas na ordem incorreta. Em alguns casos, o VEC aplicou algumas modificações de forma assíncrona e adicionar modificações extras a um elemento causou erros se esse elemento fosse exibido após um [!UICONTROL Inserir] ação. Também corrige o URL do VEC que agora é atualizado ao clicar em links âncora. (TGT-45983)
* Correção de um problema com o VEC [!UICONTROL Sobreposição] recurso, que agora oferece suporte a elementos em DOMs Sombra. (TGT-45202 e TGT-45262)
* Correção de um problema ao abrir uma página de Aplicativo de página única (SPA) no VEC e acessar [!UICONTROL Procurar] fazia com que as setas para trás e para a frente não funcionassem corretamente. (TGT-45956)
* Correção de um problema que impedia o carregamento de algumas páginas da Web no VEC. (TGT-45983)

## [!DNL Target] Standard/Premium 23.9.2 (12 a 14 de setembro de 2023)

Esta versão estará disponível de acordo com o seguinte cronograma:

* **12 de setembro**: região das Américas
* **13 de setembro**: região Ásia-Pacífico (APAC)
* **14 de setembro**: regiões da Europa, Oriente Médio e África (EMEA)

Essa versão conta com os seguintes aprimoramentos e correções:

* Alteração da API do [!DNL Analytics] para a nova API versão 2.0 do [!DNL Analytics]. (TGT-45345)
* Correção de problemas que afetavam atividades da [!UICONTROL Automated Personalization] (AP) para alguns clientes, incluindo a sincronização oportuna da atividade no back-end do [!DNL Target] e a entrega da experiência esperada nos links de visualização. (TGT-46202)

## [!DNL Target] Standard/Premium 23.9.1 (6 a 11 de setembro de 2023)

Esta versão estará disponível de acordo com o seguinte cronograma:

* **6 de setembro**: região das Américas
* **7 de setembro**: regiões da Europa, Oriente Médio e África (EMEA)
* **11 de setembro**: região Ásia-Pacífico (APAC)

Essa versão conta com os seguintes aprimoramentos e correções:

* Correção de um problema que causava inconsistência nos dados de relatórios na interface do [!DNL Target] e do [!DNL Adobe Analytics] para atividades de [!UICONTROL Alocação automática] que usam o [!UICONTROL Analytics for Target] (A4T) como fonte de relatórios. (TGT-46112)
* O tempo limite das chamadas de PUT para a API de entrega do Target foi aumentado para 15 segundos para evitar erros de tempo limite. (TGT-46091)
* Correção de um problema que impedia a atualização consistente do URL ao navegar por um site de aplicativo de página única (SPA). (TGT-45417)

## [!DNL Target] Standard/Premium 23.5.2 (data a ser determinada)

Essa versão conta com os seguintes aprimoramentos e correções:

* Seleção de critérios de otimização ativada para [!DNL Adobe Analytics] métricas.
* Ativação da sincronização de públicos externos usando trabalhos do sling.
* Correção de um problema em que os conjuntos de relatórios do SC contendo um caractere de ponto no nome não eram compatíveis.
* Ativação da funcionalidade para permitir que os clientes excluam e editem públicos-alvo integrados.

## [!DNL Target] Standard/Premium 23.5.3 (data a ser determinada)

Esta versão inclui as seguintes melhorias:

| Recurso | Detalhes |
|--- |--- |
| [!UICONTROL Modo de controle de qualidade] para atividades do [!UICONTROL Automated Personalization] | O [!UICONTROL Modo de controle de qualidade] do [!DNL Adobe Target] agora está disponível para as atividades do [!UICONTROL Automated Personalization], substituindo a funcionalidade de [!UICONTROL Links de visualização].<P>Para obter mais informações, consulte [Controle de qualidade da atividade.](/help/main/c-activities/c-activity-qa/activity-qa.md) |

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da Platform. |
| [Detalhes da versão da at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
