---
keywords: notas de versão;versões;atualizações;versão futura;aprimoramentos;novos recursos;correções;atualizações;pré-lançamento;acesso antecipado;release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease;Early access
description: Saiba mais sobre os novos recursos, melhorias e correções adicionados na próxima versão do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos e melhorias que serão incluídos na próxima versão do  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 7e23eea48abdebd60f37ad1bf453813a63779d33
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 28%

---

# Notas de versão do [!DNL Target] (pré-lançamento)

Este artigo contém informações de pré-lançamento das próximas versões do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.

**Última atualização: sexta-feira, 10 de abril de 2025**

>[!NOTE]
>
>As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.
>
>Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## Atualização de permissões do Target (22 de abril de 2025)

Essa atualização futura melhora o controle organizacional sobre as configurações da instância [!DNL Target], evitando atualizações acidentais que podem afetar a entrega da atividade em várias equipes de teste e personalização.

A partir de 22 de abril de 2025, somente [!UICONTROL Product] e [!UICONTROL Solutions] administradores poderão atualizar as configurações nas seções [!UICONTROL Administration], independentemente de suas funções nos espaços de trabalho [!DNL Target]. Os usuários sem esta permissão terão acesso somente leitura às seções [!UICONTROL Administration].

Para obter mais informações, consulte [Administrar Target](/help/main/administrating-target/start-target.md).

## [!DNL Target Standard/Premium] 25.4.4 (15 de abril de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Adição de uma mensagem de erro para orientar os usuários sobre a resolução de opções de duplicação em uma atividade. (TGT-51927)
* Correção de um problema em que os seletores ClickTrack não eram removidos ao excluir páginas ou experiências com ofertas de redirecionamento. (TGT-51952)
* Correção de um problema em que [!DNL Target] não detectava corretamente um caractere &quot;#&quot; na URL da atividade. (TGT-52093)
* Correção de um problema em que as definições de público-alvo não estavam visíveis ao editar o direcionamento no nível de oferta nas atividades de [!UICONTROL Automated Personalization] (AP). (TGT-52148)
* Correção de um problema em que os refinamentos de público-alvo e os públicos-alvo de direcionamento de atividades eram revertidos na interface do usuário. (TGT-52158)

## [!DNL Target Standard/Premium] 25.4.3 (10 de abril de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Correção de um erro que impedia os clientes de abrirem o pop-up de informações de público-alvo para determinadas atividades do [!UICONTROL Experience Targeting] (XT). (TGT-52049)
* Correção de um problema que impedia os clientes de inserir um [!UICONTROL Experience Fragment] no espaço de trabalho padrão. (TGT-52073)
* Correção de um problema em que uma oferta era exibida como &quot;Conteúdo não encontrado&quot; e não era exibida na página [!UICONTROL Offers] para uma atividade [!UICONTROL Automated Personalization] (AP). (TGT-52150)
* Adição da capacidade de permitir públicos-alvo duplicados em uma atividade. (TGT-51200)
* Correção de um problema em que o nome incorreto da mbox era exibido na página [!UICONTROL Goals & Settings] para uma atividade XT após a edição. (TGT-52026)
* Correção de um problema em que `defaultContent` era exibido nas opções, apesar de não estar em `experiences/optionLocations`. (TGT-52036)
* Correção de um problema para garantir que cadeias de caracteres vazias não fossem convertidas em valores nulos. (TGT-52037)
* Correção de um problema que exigia que os clientes reconfigurassem o [!UICONTROL Optimization Goal] em [!UICONTROL Reporting Settings] na página [!UICONTROL Goals & Settings] após as edições. (TGT-52071)
* Correção de um problema em que uma atividade sem regras de entrega de página exibia várias regras na página [!UICONTROL Overview]. (TGT-52084)
* Adição de uma mensagem de erro para usuários que tentam salvar uma oferta com caracteres fora do plano multilíngue básico, como emojis. (TGT-52105)
* Correção de um problema em que a abertura de uma atividade acionava a mensagem de erro: &quot;Esta atividade está usando um ou mais públicos-alvo excluídos na origem&quot;. (TGT-52120)
* Correção de um problema em que as métricas ClickTrack não eram exibidas no [!UICONTROL Visual Experience Composer] (VEC) atualizado durante a edição. (TGT-52152)
* Correção de um problema em que um URL com um parâmetro de consulta como o local da atividade não exibia o parâmetro de consulta na página [!UICONTROL Overview] da atividade. (TGT-51635)
* Correção de um problema que impedia que a URL de toda a experiência fosse exibida no [!UICONTROL Browse mode] no [!UICONTROL Visual Experience Composer] (VEC). (TGT-52101)
* Correção de um problema em que a edição de uma atividade fazia com que a entrega da página adicionasse &quot;/&quot; ao final do URL, tornando-a inválida. (TGT-52114)
* Correção de um problema em que o link [!UICONTROL Activity QA] em [!UICONTROL Form-Based Experience Composer] era redirecionado incorretamente para a página inicial [!DNL Adobe Experience Cloud]. (TGT-52055)
* Correção de um problema em que páginas adicionais adicionadas à atividade [!UICONTROL A/B Test] não eram mantidas após salvar e reabrir. (TGT-51994)
* Correção de um problema que impedia os clientes de excluir estilos na seção de estilo em linha. (TGT-52070)
* Restaurado o acesso a [cartões de definição de público-alvo](/help/main/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) na caixa de diálogo [!UICONTROL Activity QA], semelhante à interface herdada. (TGT-52056)
* A interface atualizada não salva páginas ou públicos-alvo sem modificações. Se os clientes adicionaram novas páginas ou públicos-alvo a uma atividade, mas não fizeram alterações, [!DNL Target] descartou os públicos-alvo não modificados ao salvar. Foram adicionadas notificações em locais relevantes para informar os usuários sobre esse comportamento. (TGT-52104)

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da Platform. |
| [Detalhes da versão da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
