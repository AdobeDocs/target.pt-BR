---
keywords: notas de versão;versões;atualizações;versão futura;aprimoramentos;novos recursos;correções;atualizações;pré-lançamento;acesso antecipado;release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease;Early access
description: Saiba mais sobre os novos recursos, melhorias e correções adicionados na próxima versão do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos e melhorias que serão incluídos na próxima versão do  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: b1bde455f686c34e7a5184868ce63db0b74e2af7
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 29%

---

# Notas de versão do [!DNL Target] (pré-lançamento)

Este artigo contém informações de pré-lançamento das próximas versões do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.

**Última atualização: 19 de junho de 2025**

>[!NOTE]
>
>* As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.
>
>* Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md).
>
>* Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.6.3 (sábado, 20 de junho de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Adicionada a opção [!UICONTROL Rearrange] à interface do VEC ([!UICONTROL Visual Experience Composer]) atualizada para alinhar-se à funcionalidade disponível no VEC herdado. (TGT-46957)
* Correção de um problema em que copiar uma atividade de um espaço de trabalho para outro espaço de trabalho acionava erros como &quot;não deve ser nulo&quot; ou &quot;Algo deu errado&quot;. (TGT-52474)
* Correção de um problema em que os relatórios [!UICONTROL Automated Segments] e [!UICONTROL Important Attributes] não eram gerados para determinadas atividades. (TNT-52904)
* Correção de um problema no VEC atualizado em que o manuseio de conteúdo padrão em atividades de [!UICONTROL Automated Personalization] (AP) não correspondia à interface do usuário herdada. O sistema agora adiciona automaticamente um `optionGroup` padrão chamado &quot;Conteúdo padrão&quot; com `optionGroupLocalId = 0` quando nenhum grupo é explicitamente adicionado. Este grupo inclui a opção padrão (por exemplo, `optionLocalId: 0`). Se o conteúdo padrão for removido, o grupo de opções correspondente também será removido. (TGT-52651)
* Correção de um problema nas atividades [!UICONTROL Multivariate Test] (MVT) em que o reuso de um `experienceLocalId` de experiências removidas anteriormente não era permitido incorretamente. (TNT-52672)
* Correção de um problema em que os URLs nos locais de atividade falhavam em exibir parâmetros de consulta devido a caracteres inválidos, como barras (/). (TNT52845)
* Mensagem de erro de validação aprimorada para [!DNL A/B Test] atualizações de atividade por meio da API de back-end. Quando nomes de locais duplicados estão presentes, a mensagem agora diz claramente: &quot;Nomes duplicados não são permitidos&quot; para `locations.selectors`. (TGT-52589)
* Correção de um erro que ocorria ao atualizar uma atividade [!UICONTROL Recommendations] em tempo real devido a uma propriedade não reconhecida na carga da solicitação. O sistema agora lida corretamente com o &quot;JSON inválido. Erro &quot;Nome de propriedade não reconhecido&quot;. (TNT52723)
* Correção de um erro de validação de backend que causava um erro &quot;400 Solicitação inválida&quot; ao salvar uma atividade [!UICONTROL Recommendations]. (TNT-52716)
* Correção de um problema no [!UICONTROL Form-Based Experience Composer] em que passar o mouse sobre uma mbox com caracteres especiais no menu suspenso [!UICONTROL Location] fazia com que o editor ficasse em branco e disparasse uma &quot;Falha ao executar &#39;querySelector&#39; em &#39;Elemento&#39;.&quot; . (TGT-52717)
* Melhoria na precisão do status do feed com um novo indicador &quot;PARCIALLY_IMPORTED&quot;. Anteriormente, os feeds eram marcados como &quot;sucesso&quot; mesmo quando nem todas as linhas de um arquivo eram importadas, o que induzir em erro.
* Correção de um erro em que, após a migração para o AP V2, determinadas chamadas de API para `/admin/rest/ui/v1/campaigns` retornavam erros do lado do cliente (HTTP 4xx). (TGT-52721)

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Detalhes sobre alterações em cada versão do SDK da Web da plataforma. |
| [Detalhes da versão da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
