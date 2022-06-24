---
keywords: Notas de versão;novos recursos;versões;atualizações;atualização;versão;aprimoramento;aprimoramentos;correções;correções de bugs;atualizações
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 49517f858b39a70df7643125e703f31bf45b7336
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 84%

---

# Notas de versão do Target (atual)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium] Além disso, as notas de versão para APIs [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outras alterações de plataforma também estão incluídas, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## [!DNL Target Standard/Premium] 22.6.2 (24 de junho de 2022)

Essa versão conta com os seguintes aprimoramentos e correções:

* Usuários com a função de [!UICONTROL Editor] não podem mais editar públicos em atividades ativas. (TGT-43582)
* Uma mensagem de aviso é exibida se um cliente tentar salvar um público-alvo com um ponto de exclamação ( ! ) como o primeiro caractere do nome do público-alvo (por exemplo !Londres). (TGT-43643)
* Correção de um problema que fazia com que os cartões de detalhes da definição de públicos-alvo para alguns clientes indicassem que uma atividade finalizada ainda estava ativa. (TGT-43527)

## [!DNL Target Standard/Premium] 2.6.1 (versão escalonada: (7 a 9 de junho de 2022)

Esta versão estará disponível de acordo com o seguinte agendamento:

* **7 de junho**: região Ásia-Pacífico (APAC)
* **8 de junho**: região das Américas
* **9 de junho**: região da Europa, Oriente Médio e África (EMEA)

Essa versão conta com os seguintes aprimoramentos e correções:

* Um aprimoramento foi fornecido para a nova página de [!UICONTROL Públicos] para evitar uma inconsistência entre o banco de dados antigo, em que os públicos eram armazenados no passado, e a nova arquitetura, que busca as informações diretamente no back-end. (TGT-43552)
* Correção de um problema que impedia alguns clientes de salvar públicos combinados, causado pela criação de contêineres “vazios” pela interface do Target. (TGT-43588)

## Versão da plataforma do Target (25 de maio de 2022)

Essa versão conta com os seguintes aprimoramentos e correções:

* Adicionado [Dicas do Cliente do Agente de Usuário](https://developer.adobe.com/target/implement/client-side/atjs/user-agent-and-client-hints/)Suporte para {target=_blank}.
* Correção de um problema que causava esgotamento do tempo de maneira intermitente ao renderizar [!UICONTROL Decisões de oferta] em [!UICONTROL Direcionamento de experiência] (XT). (TNT-44611)

## at.js versão 2.9.0 (27 de maio de 2022)

* Adicionado [Dicas do Cliente do Agente de Usuário](https://developer.adobe.com/target/implement/client-side/atjs/user-agent-and-client-hints/)Suporte para {target=_blank}.
* Correção de um erro em que várias solicitações de mbox na mesma página tinham IDs de impressão diferentes.

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da plataforma. |
| [Detalhes da versão da at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

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
