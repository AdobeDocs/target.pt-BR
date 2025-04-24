---
keywords: notas de versão;versões;atualizações;versão futura;aprimoramentos;novos recursos;correções;atualizações;pré-lançamento;acesso antecipado;release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease;Early access
description: Saiba mais sobre os novos recursos, melhorias e correções adicionados na próxima versão do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos e melhorias que serão incluídos na próxima versão do  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: b09796cd8464b54dcc1945ae1ec00eb914ba218c
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 31%

---

# Notas de versão do [!DNL Target] (pré-lançamento)

Este artigo contém informações de pré-lançamento das próximas versões do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.

**Última atualização: sexta-feira, 24 de abril de 2025**

>[!NOTE]
>
>As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.
>
>Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.4.5 (25 de abril de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Correção de um problema que gerava discrepâncias nas listagens de público entre a página de configurações [!UICONTROL Activity] e a página de visão geral [!UICONTROL Reporting]. (TGT-52203)
* Correção de um problema que impedia a adição de uma nova página a uma atividade devido a um erro de entrada de usuário inválido. (TGT-52263)
* Correção de um problema em que as recomendações não eram exibidas no site do cliente após ativar a atividade [!DNL Recommendations]. (TGT-52164)
* Correção de um problema que fazia com que `OptionLocalIDs` fosse incrementado incorretamente quando a opção permanecesse inalterada. (TGT-52187)
* Correção de um problema para que os arquivos de relatórios baixados mostrassem corretamente os dados presentes na interface do usuário dos relatórios. (TGT-52068)
* Correção de um problema para que as operações em lote não falhassem mais após a adição das regras de entrega de página. (TGT-52097)
* Correção de um problema que fazia com que [!DNL Target] cortasse todos os parâmetros de consulta da URL do site. (TGT-52100)
* Correção de um erro de console que impedia os clientes de criar atividades na interface do usuário do Target herdada e atualizada. (TGT-52181)
* Correção de um problema que impedia os clientes de adicionar novas páginas, causando um erro de entrada de usuário inválido. (TGT-52258)
* Correção de um problema que fazia com que as modificações desaparecessem após adicionar outras páginas e navegar de volta para a guia [!UICONTROL Experiences]. (TGT-52264)
* Correção de um problema que impedia os clientes de alterar o público-alvo em uma atividade [!UICONTROL Experience Targeting] (XT). (TGT-52191)
* Correção de um erro que impedia a edição de uma atividade de XT devido a uma regra de interface do usuário não compatível. (TGT-52273)
* Correção de um problema em que as modificações de atividade não eram exibidas na interface do usuário do [!DNL Target], apesar de serem entregues com êxito à página da Web. (TGT-52192)
* Correção de um problema no [!UICONTROL Visual Experience Composer] (VEC) atualizado em que as navegações estruturais nem sempre eram exibidas na parte inferior do editor, causando dificuldades na seleção precisa de elementos. (TGT-51169)
* Correção de um problema em que a lista suspensa [!UICONTROL Audience] não exibia todos os públicos-alvo devido à paginação. (TGT-52204)
* Correção de um problema que causava uma mensagem de entrada de usuário inválida ao adicionar novas ofertas em [!UICONTROL Automated Personalization] atividades (AP). (TGT-52210)
* Correção de um problema em que [!UICONTROL Analytics for Target] (A4T) era selecionado incorretamente como fonte de relatórios, mesmo que o cliente não tivesse acesso ao A4T. (TGT-52226)
* Correção de um problema que impedia salvar uma atividade com a métrica de URL [!UICONTROL View a Page]. (TGT-52260)
* Correção de um problema que impedia os clientes de selecionar espaços de trabalho ao criar ofertas em uma atividade. (TGT-52289)
* Correção de um problema em que as modificações de uma experiência eram exibidas incorretamente ao alternar para outra experiência. (TGT-52184)
* Correção de um problema em que a oferta padrão era exibida incorretamente na interface do usuário do [!DNL Target] ao abrir a atividade. (TGT-52198)

## Atualização de permissões do Target (22 de abril de 2025)

Essa atualização futura melhora o controle organizacional sobre as configurações da instância [!DNL Target], evitando atualizações acidentais que podem afetar a entrega da atividade em várias equipes de teste e personalização.

A partir de 22 de abril de 2025, somente [!UICONTROL Product] e [!UICONTROL Solutions] administradores poderão atualizar as configurações nas seções [!UICONTROL Administration], independentemente de suas funções nos espaços de trabalho [!DNL Target]. Os usuários sem esta permissão terão acesso somente leitura às seções [!UICONTROL Administration].

Para obter mais informações, consulte [Administrar Target](/help/main/administrating-target/start-target.md).

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da plataforma. |
| [Detalhes da versão da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
