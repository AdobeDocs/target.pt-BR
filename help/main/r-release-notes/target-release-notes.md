---
keywords: notas de versão;versões;atualizações;versão futura;aprimoramentos;novos recursos;correções;atualizações;pré-lançamento;acesso antecipado;release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease;Early access
description: Saiba mais sobre os novos recursos, melhorias e correções adicionados na próxima versão do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos e melhorias que serão incluídos na próxima versão do  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 203c0ca94b198ee7ce8379731d31d32b27cb8a0d
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 31%

---

# Notas de versão do [!DNL Target] (pré-lançamento)

Este artigo contém informações de pré-lançamento das próximas versões do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.

**Última atualização: quinta-feira, 2 de abril de 2025**

>[!NOTE]
>
>As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.
>
>Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## Atualização de permissões do Target (22 de abril de 2025)

Essa atualização futura melhora o controle organizacional sobre as configurações da instância [!DNL Target], evitando atualizações acidentais que podem afetar a entrega da atividade em várias equipes de teste e personalização.

A partir de 22 de abril de 2025, somente [!UICONTROL Product] e [!UICONTROL Solutions] administradores poderão atualizar as configurações nas seções [!UICONTROL Administration], independentemente de suas funções nos espaços de trabalho [!DNL Target]. Os usuários sem esta permissão terão acesso somente leitura às seções [!UICONTROL Administration].

Para obter mais informações, consulte [Administrar Target](/help/main/administrating-target/start-target.md).

## [!DNL Target Standard/Premium] 25.4.3 (10 de abril de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Correção de um problema em que o link [!UICONTROL Activity QA] em [!UICONTROL Form-Based Experience Composer] era redirecionado incorretamente para a página inicial [!DNL Adobe Experience Cloud]. (TGT-52055)
* Adição de uma mensagem de erro para orientar os usuários sobre a resolução de opções de duplicação em uma atividade. (TGT-51927)

## [!DNL Target Standard/Premium] 25.4.2 (8 de abril de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Correção de um problema em que páginas adicionais adicionadas à atividade [!UICONTROL A/B Test] não eram mantidas após salvar e reabrir. (TGT-51994)
* Correção de um problema que impedia os clientes de excluir estilos na seção de estilo em linha. (TGT-52070)
* Restaurado o acesso a [cartões de definição de público-alvo](/help/main/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) na caixa de diálogo [!UICONTROL Activity QA], semelhante à interface herdada. (TGT-52056)
* A interface atualizada não salva páginas ou públicos-alvo sem modificações. Se os clientes adicionaram novas páginas ou públicos-alvo a uma atividade, mas não fizeram alterações, [!DNL Target] descartou os públicos-alvo não modificados ao salvar. Foram adicionadas notificações em locais relevantes para informar os usuários sobre esse comportamento. (TGT-52104)

## [!DNL Target Standard/Premium] 25.4.1 (2 de abril de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Correção de um problema que fazia com que os públicos-alvo da experiência desaparecessem das atividades. (TGT-52003)
* Correção de um problema que causava elementos inesperados durante a entrega. (TGT-52011)
* Correção de um problema que impedia os clientes de visualizar o público-alvo no gráfico de direcionamento na página Mover[!UICONTROL r]exibir e durante a edição da atividade. (TGT-52050)
* Correção de um problema que impedia os clientes de reordenar as experiências em ordem de prioridade nas atividades [!UICONTROL Experience Targeting] (XT). (TGT-52054)
* Correção de um problema que causava renderização incorreta ao desfazer alterações no estilo do texto. (TGT-51876)
* Correção de um problema que, ao modificar uma oferta de redirecionamento, [!DNL Target] também removia todos os seletores [!UICONTROL ClickTrack] associados a essa oferta. (TGT-51936)
* Correção de um problema que fazia com que [!DNL Target] salvasse incorretamente o seletor ao cancelar [!UICONTROL ClickTrack]. (TGT-51937)
* Correção de um problema que acionava um erro de nome inválido após abrir e fechar o seletor de mbox na página [!UICONTROL Goals & Settings] sem fazer alterações. (TGT-51983)
* Correção de um problema que bloqueava a edição de ofertas ad hoc criadas na interface herdada do usuário [!DNL Target]. (TGT-51984)
* Correção de um problema que bloqueava atividades de edição com ofertas ad hoc que continham código personalizado. (TGT-51995)
* Correção de um problema que fazia com que as regras de exclusão fossem exibidas como regras de inclusão ao editar definições combinadas de público-alvo. (TGT-51999)
* Correção de um problema que impedia a exibição correta do código personalizado durante a edição da experiência. (TGT-52005)
* Correção de um problema que tornava a opção [!UICONTROL Insert Before] indisponível para inserir conteúdo antes da barra de navegação. (TGT-52031)
* Correção de um problema que impedia o realce correto da experiência padrão nos relatórios. (TGT-51716)
* Correção de um problema que acionava uma mensagem `default message [Invalid optionLocalIds: xx]]` ao criar uma atividade. (TGT-52038)

<!-- 
## [!DNL Target Standard/Premium] 24.10.2 (October 21, 2024)

This release contains the following fixes:

* Fixed an issue that prevented [!UICONTROL Recommendations] activities from loading in [!UICONTROL Compose] and [!UICONTROL Browse] modes. (TGT-50709)
* Fixed an issue with the new [[!DNL Google Chrome] [!UICONTROL Visual Editing Helper] extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) that caused a redirect from the [!UICONTROL Visual Experience Composer] (VEC) to the [!UICONTROL Activities Library] after clicking Cancel. Before this fix, customers needed to refresh the [!UICONTROL Activities Library] before being able to create new activities. (TGT-49980)-->

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da Platform. |
| [Detalhes da versão da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
