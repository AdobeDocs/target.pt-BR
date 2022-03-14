---
keywords: Notas de versão;novos recursos;versões;atualizações;atualização;versão;aprimoramento;aprimoramentos;correções;correções de bugs;atualizações
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do [!DNL Adobe Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 100%

---

# Notas de versão do Target (atual)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium] Além disso, as notas de versão para APIs do Target, SDKs, [!DNL Adobe Experience Platform Web SDK], at.js e outras alterações de plataforma também estão incluídas, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## Target Standard/Premium 22.2.1 (1 de fevereiro de 2022)

Esta versão de manutenção contém as seguintes correções e aprimoramentos para a nova interface de [!UICONTROL Públicos-alvo] anunciada na versão 22.1.2 do Target Standard/Premium que estará sendo lançada para clientes em todas as regiões nas próximas seis semanas. Essas correções alinham a funcionalidade de públicos-alvo criados no [!DNL Adobe Target Standard/Premium].

* Correção de um problema que impedia públicos-alvo importados da [!DNL Adobe Experience Platform], [!DNL Adobe Experience Cloud] e do [!DNL Adobe Target Classic] de serem atribuídos como públicos-alvo de relatórios. (TGT-43140)
* Adicionada a opção [!UICONTROL Excluir] na lista de [!UICONTROL Públicos-alvo] para públicos-alvo importados da [!DNL Adobe Experience Platform], [!DNL Adobe Experience Cloud] e do [!DNL Adobe Target Classic]. Também foi adicionada a funcionalidade de exclusão em massa. (TGT-42914)

## Versão 2.8.1 da at.js (28 de janeiro de 2022)

* Correção do `pageLoad` que não era mapeado para a target-global-mbox no modo de execução híbrido [!UICONTROL On Device Decisioning] (ODD).
* Correção de um problema com detalhes de análise para a solicitação de mbox.
* As dependências de desenvolvimento foram atualizadas para corrigirem vulnerabilidades de segurança.

## [!DNL Target Standard/Premium] 22.1.2 (26 de janeiro de 2022)

| Recurso | Detalhes |
| --- | --- |
| Públicos-alvo da [!DNL Adobe Experience Platform] no [!DNL Target] | Agora você pode consumir e usar públicos-alvo da [!DNL Adobe Experience Platform] no [!DNL Target]. As equipes do [!DNL Target], [!DNL Experience Platform] [!DNL Destinations] e [!DNL Unified Profile Service] têm o prazer de anunciar a disponibilidade geral dos casos de uso de “Personalização de mesma página/próxima página”.<br>O uso de públicos-alvo criados na [!DNL Adobe Experience Platform] fornece dados do cliente mais avançados, o que resulta em uma personalização mais impactante. O [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=pt-BR){target=_blank} (RTCDP), integrado na [!DNL Adobe Experience Platform], ajuda as empresas a unirem dados conhecidos e anônimos de várias fontes corporativas para criar perfis de clientes que possam ser usados para fornecer experiências personalizadas em todos os canais e dispositivos em tempo real.<br>Para obter mais informações, consulte [Usar públicos-alvo da Adobe Experience Platform](/help/main/c-target/c-audiences/audiences.md#aep) em *Criar públicos-alvo* e [Casos de uso de personalização de mesma página e próxima página](https://www.adobe.com/go/destinations-edge-personalization-en){target=_blank} na guia *Visão geral dos Destinos*. |
| Atualização da interface do usuário de [!UICONTROL públicos-alvo] | Como parte do esforço contínuo da equipe do [!DNL Adobe Target] em melhorar a experiência para usuários do [!DNL Target], esta versão atualiza as páginas [!UICONTROL Públicos-alvo] e [!UICONTROL Scripts de perfil] na interface do [!DNL Target]. Essa atualização unifica e uniformiza os padrões de design que eram inconsistentes anteriormente, além de adicionar novas melhorias, como:<ul><li>A capacidade de selecionar e excluir vários públicos-alvo simultaneamente</li><li>Um [design do criador de público-alvo](/help/main/c-target/c-audiences/create-audience.md) atualizado</li><li>Suporte à regras de exclusão no criador de regras da Biblioteca de [!UICONTROL público-alvo]</li><li>Um novo filtro de “Origem de público-alvo”, para permitir a descoberta mais rápida do público-alvo</li><li>Opções de filtro e pesquisa persistentes na sessão</li><li>A capacidade de mover públicos-alvo entre espaços de trabalho para clientes do [!DNL Target Premium].</li></ul>Para obter mais informações, consulte [Públicos-alvo](/help/main/c-target/target.md).<br>**OBSERVAÇÃO**: Esse recurso será lançado para clientes em diferentes regiões nas próximas oito semanas. |
| Atualização da interface dos [!UICONTROL Scripts de Perfil] | A biblioteca de [!UICONTROL Scripts de Perfil] também foi atualizada e inclui uma interface renovada, além de várias atualizações de produtividade:<ul><li>A capacidade de selecionar e excluir vários scripts de perfil simultaneamente</li><li>Um novo editor de código para scripts de perfil</li><li>Realce da sintaxe e verificação de erros no editor de código</li><li>Parâmetros de tokens de preenchimento automático (mbox ou perfil) por meio de atalhos no teclado</li></ul>Para obter mais informações, consulte [Perfis do visitante](/help/main/c-target/c-visitor-profile/visitor-profile.md).<br>**OBSERVAÇÃO**: Esse recurso será lançado para clientes em diferentes regiões nas próximas oito semanas. |

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da plataforma. |
| [Detalhes da versão da at.js](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Alterações na documentação, notas de versão anteriores e notas de versão da Experience Cloud

Além das notas para cada versão, os recursos a seguir oferecem informações adicionais:

| Recurso | Detalhes |
|--- |--- |
| Alterações de documentação | Veja informações detalhadas sobre atualizações neste manual que podem não estar incluídas nas notas de versão.<br>Para obter mais informações, consulte [Alterações de documentação](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de versão para versões anteriores | Veja informações sobre os novos recursos e aprimoramentos das versões anteriores do Target Standard e do Target Premium.<br>Para obter mais informações, consulte [Notas de versões anteriores](/help/main/r-release-notes/release-notes-for-previous-releases.md). |
| Notas de versão da Adobe Experience Cloud | Veja as notas de versão mais recentes para as soluções da Adobe Experience Cloud.<br>Para obter mais informações, consulte as [Notas de versão da Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR). |

## Informações de pré-lançamento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Os recursos a seguir permitem ver as novidades previstas para a próxima versão do Target.

| Recurso | Detalhes |
|--- |--- |
| Atualização de produtos prioritários da Adobe | Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Notas de versão futuras | Para obter informações sobre os lançamentos do Target do mês atual, incluindo informações de pré-lançamento, consulte a página [Notas de versão do Target - Pré-lançamento](/help/main/r-release-notes/target-release-notes.md). |
