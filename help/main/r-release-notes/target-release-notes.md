---
keywords: notas de versão;versões;atualizações;versão futura;aprimoramentos;novos recursos;correções;atualizações;pré-lançamento;acesso antecipado;release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease;Early access
description: Saiba mais sobre os novos recursos, melhorias e correções adicionados na próxima versão do [!DNL Target], incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos e melhorias que serão incluídos na próxima versão do  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 1f8fa78c2b88e179f021128a8fd3dac177dfa3dd
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 37%

---

# Notas de versão do [!DNL Target] (pré-lançamento)

Este artigo contém informações de pré-lançamento das próximas versões do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.

**Última atualização: 15 de agosto de 2025**

>[!NOTE]
>
>* As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio. As informações neste artigo são atualizadas com frequência, especialmente antes das versões do.
>
>* Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md).
>
>* Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.8.3 (21 de agosto de 2025)

Esta versão inclui as seguintes atualizações e correções:

**Recommendations**

+++Ver detalhes
* **Correção de um problema na interface do usuário Recs em que o download do CSV de critérios personalizados retornava o erro 404**: correção de um problema em que os clientes não conseguiam baixar o CSV de critérios personalizados no processo de criação de atividades.
* **Correção de um carregamento de imagem inconsistente em[!UICONTROL Catalog Search]**: correção de um problema em que as miniaturas e imagens em [!UICONTROL &#x200B; Catalog Search] não eram carregadas de forma consistente no processo de criação da atividade. As imagens não eram exibidas a menos que a coluna &quot;URL da miniatura&quot; estivesse visível e algumas imagens do produto fossem carregadas parcialmente ou não fossem carregadas após as ações de navegação ou pesquisa. (TGT-52778)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Ver detalhes
* **Correção de um problema no processo de criação de atividade que bloqueava a progressão para a etapa [!UICONTROL Targeting] nas atividades de AP**: correção de um problema no processo de criação de atividade em que os clientes não conseguiam prosseguir para a etapa [!UICONTROL Targeting] nas atividades de [!UICONTROL Automated Personalization] (AP), a menos que dois locais fossem adicionados. Esse comportamento foi diferente da experiência anterior, onde um único local com várias ofertas era suficiente. O requisito foi corrigido, permitindo que os clientes continuem usando configurações de local único como parte de seus workflows de AP. (TGT-53426)

+++

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Detalhes sobre alterações em cada versão do SDK da Web da plataforma. |
| [Detalhes da versão da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
