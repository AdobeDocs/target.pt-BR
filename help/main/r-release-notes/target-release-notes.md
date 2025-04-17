---
keywords: notas de versão;versões;atualizações;versão futura;aprimoramentos;novos recursos;correções;atualizações;pré-lançamento;acesso antecipado;release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease;Early access
description: Saiba mais sobre os novos recursos, melhorias e correções adicionados na próxima versão do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos e melhorias que serão incluídos na próxima versão do  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: cd25bda52b7a1b916a73ca5e531a7134ba8cef4e
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 43%

---

# Notas de versão do [!DNL Target] (pré-lançamento)

Este artigo contém informações de pré-lançamento das próximas versões do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.

**Última atualização: sexta-feira, 17 de abril de 2025**

>[!NOTE]
>
>As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.
>
>Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.4.4 (17 de abril de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Adição de uma mensagem de erro para orientar os usuários sobre a resolução de opções de duplicação em uma atividade. (TGT-51927)
* Correção de um problema em que `ClickTrack` seletores não eram removidos ao excluir páginas ou experiências com ofertas de redirecionamento. (TGT-51952)
* Correção de um problema causado pela permissão de seletores `ClickTrack` vazios. [!DNL Target] agora exige que o campo seletor não esteja em branco. (TGT-52107)
* Correção de um problema que permitia incorretamente métricas com nomes duplicados. Métricas agora exigem nomes exclusivos. (TGT-52201)
* Correção de um problema em que as definições de público-alvo não estavam visíveis ao editar o direcionamento no nível de oferta nas atividades de [!UICONTROL Automated Personalization] (AP). (TGT-52148)
* Correção de um problema que impedia clientes com direitos de [!UICONTROL Editor] de salvar atividades. (TGT-52227)
* `OptionLocalIDs` não incrementa mais incorretamente quando a opção permanece inalterada. (TGT-52139)
* Correção de um problema que causava uma mensagem &quot;Inválido `optionLocalIds`&quot; ao tentar criar uma atividade. (TGT-52154)
* Foram corrigidas discrepâncias entre `OptionLocalIDs` definidas para uma atividade e aquelas usadas para definir experiências. (TGT-52215)
* Correção de um problema que causava uma falha de validação que ocorria ao tentar criar uma atividade A/B. (TGT-51923)

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
