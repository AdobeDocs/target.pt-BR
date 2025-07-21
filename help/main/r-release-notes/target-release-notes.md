---
keywords: notas de versão;versões;atualizações;versão futura;aprimoramentos;novos recursos;correções;atualizações;pré-lançamento;acesso antecipado;release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease;Early access
description: Saiba mais sobre os novos recursos, melhorias e correções adicionados na próxima versão do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos e melhorias que serão incluídos na próxima versão do  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: b91abbd3b7418fd4d1444d96f160c3d9017f3bf8
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 34%

---

# Notas de versão do [!DNL Target] (pré-lançamento)

Este artigo contém informações de pré-lançamento das próximas versões do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.

**Última atualização: 21 de julho de 2025**

>[!NOTE]
>
>* As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.
>
>* Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md).
>
>* Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.7.3 (sexta-feira, 24 de julho de 2025)

Devido aos problemas recentes identificados, principalmente relacionados às personalizações complexas do cliente, esta versão inclui as seguintes correções e atualizações:

**Atividades**

+++Ver detalhes
* Correção de um problema em que o método `buildViews` na classe de construtor definia incorretamente `viewMaxLocalId` para a contagem total de exibições, em vez da maior `viewLocalId` atribuída. (TGT-53207)

+++

**Experience Composer baseado em formulário**

+++Ver detalhes
* Correção de um problema no [!UICONTROL Form-Based Experience Composer] que causava a falha do editor após clicar no ícone **[!UICONTROL Manage Content]** ( ![Ícone Gerenciar conteúdo](/help/main/assets/icons/Experience.svg) ) ao criar ou editar uma atividade de [!UICONTROL Automated Personalization] (AP). (TGT-53047)

+++

**Recommendations**

+++Ver detalhes
* Correção de um problema que impedia [!UICONTROL Catalog Search] de carregar resultados adicionais ao rolar a tela para a parte inferior da lista, restaurando o comportamento consistente com a interface herdada. (TGT-53088)
* Correção de um problema em que a coluna [!UICONTROL Number of Products] estava ausente na página [!UICONTROL Collections] da interface atualizada [!DNL Target]. A coluna agora é exibida corretamente, restaurando a funcionalidade esperada. (TGT-53168)
* Correção de um problema em que as regras [!UICONTROL Collection] não eram filtradas corretamente de acordo com as regras. (TGT-53254)
* Correção de um problema que bloqueava a exclusão de itens da caixa de diálogo [!UICONTROL Criteria Details]. (TGT-53245)
* Correção de um problema que impedia a abertura ou interação com produtos sem nome. Esse problema ocorria ao selecionar ambientes que retornavam resultados sem nome, impedindo o acesso aos detalhes do produto. (TGT-53007)
* Correção de um problema que causava a falha da página [!UICONTROL Catalog Search] e exibia uma tela em branco ao selecionar determinados produtos. (TGT-53087)

+++

**Visual Experience Composer (VEC)**

+++Ver detalhes

* Correção de um problema no VEC em que a aplicação de uma modificação em uma exibição causava duplicação e acionava um erro &quot;Entrada de usuário inválida&quot;. (TGT-52886)
* Correção de um problema com a funcionalidade [!UICONTROL Undo] para as opções [!UICONTROL Insert Before] e [!UICONTROL Insert After] ao configurar ofertas de imagem no VEC.

  Anteriormente, desfazer uma ação de [!UICONTROL Insert Before] ou [!UICONTROL Insert After] em ofertas de imagem resultava em um comportamento inconsistente ou na falha ao reverter corretamente a modificação, especialmente em atividades criadas na interface herdada [!DNL Target]. Esse problema foi resolvido para garantir que as ações de desfazer agora funcionem de forma confiável para essas modificações. (TGT-52809)

+++

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Detalhes sobre alterações em cada versão do SDK da Web da plataforma. |
| [Detalhes da versão da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
