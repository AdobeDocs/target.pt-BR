---
keywords: notas de versão;versões;atualizações;versão futura;aprimoramentos;novos recursos;correções;atualizações;pré-lançamento;acesso antecipado;release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease;Early access
description: Saiba mais sobre os novos recursos, melhorias e correções adicionados na próxima versão do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos e melhorias que serão incluídos na próxima versão do  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: ca14a94365e75704622e76ac13aab324fc836e09
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 43%

---

# Notas de versão do [!DNL Target] (pré-lançamento)

Este artigo contém informações de pré-lançamento das próximas versões do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.

**Última atualização: quinta-feira, 2 de abril de 2025**

>[!NOTE]
>
>As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.
>
>Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

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
