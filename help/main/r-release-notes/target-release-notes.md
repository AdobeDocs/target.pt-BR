---
keywords: notas de versão;versões;atualizações;versão futura;aprimoramentos;novos recursos;correções;atualizações;pré-lançamento;acesso antecipado;release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease;Early access
description: Saiba mais sobre os novos recursos, melhorias e correções adicionados na próxima versão do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos e melhorias que serão incluídos na próxima versão do  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 2f49a957979b4acaac7060f530b26861e1e774c9
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 27%

---

# Notas de versão do [!DNL Target] (pré-lançamento)

Este artigo contém informações de pré-lançamento das próximas versões do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.

**Última atualização: 27 de junho de 2025**

>[!NOTE]
>
>* As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.
>
>* Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md).
>
>* Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.6.4 (sexta-feira, 26 de junho de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Adicionada a opção [!UICONTROL Rearrange] à interface do VEC ([!UICONTROL Visual Experience Composer]) atualizada para alinhar-se à funcionalidade disponível no VEC herdado. (TGT-46957 e TGT-52876)
* Correção de um problema em que as modificações feitas nas experiências de variante (por exemplo, Experiência B) em uma atividade [!UICONTROL A/B Test] não eram retidas. Depois de alternar entre experiências, as alterações na variante desapareceriam. Esse problema não afetou a experiência de controle. (TGT-52664)
* Correção de um problema em que determinados clientes não podiam criar ou salvar atividades, enquanto outros podiam executar as mesmas ações sem problema. O problema era inconsistente entre as contas.(TGT-52842)
* Correção de um problema em que, no VEC atualizado, os usuários não conseguiam mover modificações para o [!UICONTROL Page Load event], um recurso que existia na interface do usuário herdada. (TGT-52617)
* Correção de um problema na interface do usuário atualizada em que os eventos [!UICONTROL page load] não estavam visíveis em [!DNL Target] ao criar alterações. Atualizações aplicadas apenas a exibições. (TGT-52604)
* Correção de um problema que impedia que algumas modificações de atividade fossem exibidas corretamente no VEC atualizado. (TGT-52818)
* Correção de uma exceção de ponteiro nulo que ocorria ao buscar dados de relatórios para [!UICONTROL Automated Personalization] atividades (AP). (TGT-52362)
* Correção de um problema que impedia que detalhes no nível da oferta fossem exibidos no arquivo .CSV para atividades de [!UICONTROL Automated Personalization] (AP). (TGT-52675)
* Correção de um problema ao aplicar modificações no VEC atualizado. As alterações inicialmente aparecem corretamente, incluindo a [!UICONTROL Experience Fragment] esperada. No entanto, ao alternar experiências ou fazer edições adicionais, algumas modificações não são aplicadas devido a problemas do seletor. (TGT-52679)
* Correção de um problema em que, quando uma nova atividade era criada por meio da clonagem de uma atividade existente, os links de controle de qualidade na atividade clonada retinham incorretamente os URLs da página da atividade original. (TGT-52775)
* Correção de um problema que impedia involuntariamente a disponibilização do [!UICONTROL On-device Decisioning] no VEC atualizado. (TGT-52371)
* Correção de um problema que impedia a edição de uma atividade do produto [!DNL Recommendations]. Ao tentar acessar o VEC por meio da interface do usuário do Target, um erro apareceu na página [!UICONTROL Overview], impedindo edições. (TGT-52823)
* Correção de um problema que impedia salvar uma atividade [!DNL Recommendations] quando os nomes de experiência excediam 50 caracteres. (TGT-52619)
* Correção de um problema em que os clientes não conseguiam salvar uma atividade do Recommendations após modificar os critérios na nova interface do usuário. O problema parece estar relacionado à permissão e não afeta todos os usuários com funções semelhantes. (TGT-52816)
* Correção de um problema em que os usuários com a função [!UICONTROL Editor] não conseguiam editar uma atividade [!DNL Recommendations]. A tentativa de alterar o design e salvar a atividade resultou em um erro 403 Proibido, informando que o privilégio &quot;[editor]&quot; era necessário, mesmo que o usuário já tivesse essa função no espaço de trabalho relevante. (TGT-52836)

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Detalhes sobre alterações em cada versão do SDK da Web da plataforma. |
| [Detalhes da versão da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
