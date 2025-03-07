---
keywords: notas de versão;versões;atualizações;versão futura;aprimoramentos;novos recursos;correções;atualizações;pré-lançamento;acesso antecipado;release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease;Early access
description: Saiba mais sobre os novos recursos, melhorias e correções adicionados na próxima versão do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos e melhorias que serão incluídos na próxima versão do  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 7196b966c46043db536313c7841fe8611268d373
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 36%

---

# Notas de versão do [!DNL Target] (pré-lançamento)

Este artigo contém informações de pré-lançamento das próximas versões do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.

**Última atualização: sábado, 7 de março de 2025**

>[!NOTE]
>
>As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.
>
>Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.3.4 (7 de março de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Solução de um problema em que públicos somente atividade não estavam visíveis no painel [!UICONTROL Audiences], impedindo sua edição ou reutilização. (TGT-51860)
* Correção de um problema que impedia [!DNL Target Standard] clientes de criar atividades usando os relatórios do [!UICONTROL Analytics for Target] (A4T). (TGT-51854)
* Correção de um problema que excluía os contadores de ID local da carga durante as operações de criação e edição de lote. (TGT-51867)
* Relatórios de acessibilidade aprimorados ao integrar o [!DNL Axe Developer Hub], melhorando a cobertura, os relatórios, a colaboração em equipe, o suporte a testes manuais, os padrões de conformidade e a experiência do usuário.

## [!DNL Target Standard/Premium] 25.3.2 (6 de março de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Correção de um problema em que a cópia de uma atividade com um público-alvo somente de atividade não criava uma nova atividade, usando erroneamente o público-alvo da atividade original. (TGT-51855)
* Correção de um problema que impedia a edição de [!UICONTROL Experience Targeting] atividades (XT) com públicos somente atividade. (TGT-51846)
* Correção de um problema em que o [!UICONTROL Visual Experience Composer] (VEC) não aplicava modificações em uma experiência corretamente na primeira edição. (TGT-51843)
* Correção de um problema que acionava um erro de &quot;ID&quot; ao clicar em determinados elementos no VEC. (TGT-51814)
* Atualização do tratamento de erros no VEC durante a criação da atividade. (TGT-51759)
* Correção de um problema em que a ausência de um modo de exibição no painel [!UICONTROL Modifications] causava um erro de &quot;entrada de usuário inválida&quot; ao salvar a atividade. (TGT-51827)
* Correção de um problema que impedia a criação de critérios de recomendações. (TGT-51834)
* Adição de uma mensagem de confirmação antes de redirecionar para um URL diferente. (TGT-51703)
* Correção de problemas com testes de integração do GraphQL em ofertas e pastas. (TGT-51839)

## [!DNL Target Standard/Premium] 25.3.1 (3 de março de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Um público-alvo combinado pode incluir subgrupos, cada um contendo vários públicos-alvo. Esta versão corrigiu um problema que impedia que públicos-alvo de subgrupos fossem exibidos na caixa de diálogo [!UICONTROL Rules]. (TGT-51813)
* Solução de um problema em que alguns públicos-alvo de experiência eram substituídos por [!UICONTROL All Visitors] ao abrir atividades mais antigas. (TGT-51812)
* Solução de um problema que impedia a edição de atividades com públicos somente atividade. (TGT-51807)
* Solução de um problema que impedia a edição de modificações no cabeçalho da página na interface atualizada do usuário do [!DNL Target]. (TGT-51797)
* Correção de um erro nulo que ocorria ao duplicar uma experiência, excluir outra experiência e tentar salvar a atividade. (TGT-51796)
* Correção de um problema que impedia a exibição de regras de exclusão de público-alvo no painel de informações do público-alvo durante a etapa [!UICONTROL Targeting] da criação de atividades. (TGT-51579)
* Mensagens de erro atualizadas localizadas em coreano. (TGT-51701 e TGT-51699)

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
