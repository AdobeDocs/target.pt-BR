---
keywords: Notas de versão;novos recursos;versões;atualizações;atualização;versão;aprimoramento;aprimoramentos;correções;correções de bugs;atualizações
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do [!DNL Adobe Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 7d21394391899744121b0c86405413f91cee1b15
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 70%

---

# Notas de versão do Target (atual)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium] Além disso, as notas de versão para APIs do Target, SDKs, [!DNL Adobe Experience Platform Web SDK], at.js e outras alterações de plataforma também estão incluídas, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe].)

## Versão 2.8.1 da at.js (28 de janeiro de 2022)

* Fixo `pageLoad` não estar sendo mapeado para target-global-mbox em [!UICONTROL No Device Decisioning] (ODD) modo de execução híbrido.
* Correção de um problema com detalhes de análise para solicitação de mbox.
* Atualização das dependências de desenvolvimento para corrigir vulnerabilidades de segurança.

## [!DNL Target Standard/Premium] 22.1.2 (26 de janeiro de 2022)

| Recurso | Detalhes |
| --- | --- |
| [!DNL Adobe Experience Platform] públicos-alvo em [!DNL Target] | Agora você pode consumir e usar [!DNL Adobe Experience Platform] públicos-alvo em [!DNL Target]. O [!DNL Target] equipe, [!DNL Experience Platform] [!DNL Destinations] e a [!DNL Unified Profile Service] A equipe tem o prazer de anunciar a disponibilidade geral dos casos de uso de &quot;Mesma página/Próxima personalização de página&quot;.<br>Uso de públicos-alvo criados em [!DNL Adobe Experience Platform] forneça dados mais avançados do cliente, o que resulta em personalização mais impactante. O [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html){target=_blank} (RTCP), criado em [!DNL Adobe Experience Platform] O ajuda as empresas a unirem dados conhecidos e anônimos de várias fontes corporativas para criar perfis de clientes que possam ser usados para fornecer experiências personalizadas de clientes em todos os canais e dispositivos em tempo real.<br>Para obter mais informações, consulte [Usar públicos-alvo do Adobe Experience Platform](/help/c-target/c-audiences/audiences.md#aep) em *Criar públicos-alvo*.<br>Leia o Adobe e assista ao vídeo: [[!DNL Adobe] announces Same Page Enhanced Personalization with [!DNL Adobe Target] e [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}. |
| Atualização da interface do usuário de [!UICONTROL públicos-alvo] | Como parte do esforço contínuo da equipe do [!DNL Adobe Target] em melhorar a experiência para usuários do [!DNL Target], esta versão atualiza as páginas [!UICONTROL Públicos-alvo] e [!UICONTROL Scripts de perfil] na interface do [!DNL Target]. Essa atualização unifica e uniformiza os padrões de design que eram inconsistentes anteriormente, além de adicionar novas melhorias, como:<ul><li>A capacidade de selecionar e excluir vários públicos-alvo simultaneamente</li><li>Um [design do criador de público-alvo](/help/c-target/c-audiences/create-audience.md) atualizado</li><li>Suporte à regras de exclusão no criador de regras da Biblioteca de [!UICONTROL público-alvo]</li><li>Um novo filtro de “Origem de público-alvo”, para permitir a descoberta mais rápida do público-alvo</li><li>Opções de filtro e pesquisa persistentes na sessão</li><li>A capacidade de mover públicos-alvo entre espaços de trabalho para [!DNL Target Premium] clientes.</li></ul>Para obter mais informações, consulte [Públicos](/help/c-target/target.md).<br>**OBSERVAÇÃO**: Esse recurso será lançado para clientes em diferentes regiões nas próximas oito semanas. |
| Atualização da interface dos [!UICONTROL Scripts de Perfil] | A biblioteca de [!UICONTROL Scripts de Perfil] também foi atualizada e inclui uma interface renovada, além de várias atualizações de produtividade:<ul><li>A capacidade de selecionar e excluir vários scripts de perfil simultaneamente</li><li>Um novo editor de código para scripts de perfil</li><li>Realce da sintaxe e verificação de erros no editor de código</li><li>Parâmetros de tokens de preenchimento automático (mbox ou perfil) por meio de atalhos no teclado</li></ul>Para obter mais informações, consulte [Perfis do visitante](/help/c-target/c-visitor-profile/visitor-profile.md).<br>**OBSERVAÇÃO**: Esse recurso será lançado para clientes em diferentes regiões nas próximas oito semanas. |

## [!DNL Target Standard/Premium] 22.1.1 (12 de janeiro de 2022)

Esta versão inclui correções de erros e recursos pré-requisitos para integrações futuras.

## Versão 2.8.0 da at.js (7 de janeiro de 2022)

A biblioteca JavaScript at.js do [!DNL Target] agora coleta dados de uso de recursos e de telemetria de desempenho. Os dados pessoais não são coletados. A opção de recusa para este recurso está disponível ao configurar `telemetryEnabled` para falso em `targetGlobalSettings`. Para mais informações, consulte [telemetryEnabled em targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#telemetry).

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da plataforma. |
| [Detalhes da versão da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Alterações na documentação, notas de versão anteriores e notas de versão da Experience Cloud

Além das notas para cada versão, os recursos a seguir oferecem informações adicionais:

| Recurso | Detalhes |
|--- |--- |
| Alterações de documentação | Veja informações detalhadas sobre atualizações neste manual que podem não estar incluídas nas notas de versão.<br>Para obter mais informações, consulte [Alterações de documentação](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de versão para versões anteriores | Veja informações sobre os novos recursos e aprimoramentos das versões anteriores do Target Standard e do Target Premium.<br>Para obter mais informações, consulte [Notas de versões anteriores](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Notas de versão da Adobe Experience Cloud | Veja as notas de versão mais recentes para as soluções da Adobe Experience Cloud.<br>Para obter mais informações, consulte as [Notas de versão da Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR). |

## Informações de pré-lançamento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Os recursos a seguir permitem ver as novidades previstas para a próxima versão do Target.

| Recurso | Detalhes |
|--- |--- |
| Atualização de produtos prioritários da Adobe | Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Notas de versão futuras | Para obter informações sobre os lançamentos do Target do mês atual, incluindo informações de pré-lançamento, consulte a página [Notas de versão do Target - Pré-lançamento](/help/r-release-notes/target-release-notes.md). |
