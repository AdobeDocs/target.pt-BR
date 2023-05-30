---
keywords: notas de versão;novos recursos;versões;atualizações;atualização;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 2e6efe777925eb14e280ea38110dc1cb12264d17
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 57%

---

# Notas de versão do [!DNL Target] (atuais)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium]. Além disso, as notas de versão para APIs [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outras alterações de plataforma também estão incluídas, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## [!DNL Target] Standard/Premium 23.5.2 (31 de maio de 2023)

Essa versão conta com os seguintes aprimoramentos e correções:

* Correção de um problema que resultava na exibição de uma página em branco ao gerar um token de autorização de API de perfil. (TGT-45387 e TGT-45423)
* Correção de um problema que impedia a exibição de uma imagem no [!UICONTROL Criar design] se o nome da imagem contiver 18030 caracteres GB. (TGT-44614)
* Correção de um problema em que alguns caracteres de símbolo GB 18030 eram evitados incorretamente em Texto/HTML nas experiências. (TGT-44600)
* Correção de um problema que causava relatórios do [!UICONTROL Personalização automática] atividades a serem congeladas durante a análise. (TGT-44820)
* Correção de um problema que impedia a pesquisa de uma atividade no [!UICONTROL Atividade] se o nome da atividade contiver um colchete ( [ ou ] ). (TGT-44777)
* Correção de um problema que impedia a sincronização de uma atividade se o objetivo da atividade contivesse caracteres especiais. (TGT-44982)
* Correção de um problema que fazia com que nenhuma atividade fosse exibida no [!DNL Target] Interface do usuário do espaço de trabalho Padrão para determinados clientes. (TGT-45286)
* Atualização do comportamento do sinalizador &quot;Não permitir duplicatas&quot;. Os sinalizadores de ofertas repetitivas excluídas são atualizados para permitir ofertas repetitivas se forem a oferta de conteúdo padrão (para APIs v3, v4) e permitir opções duplicadas se as opções referenciarem a oferta de conteúdo padrão e não tiverem modelos definidos. (TNT-46617)
* Correção de um problema em que um parâmetro de consulta era adicionado a um URL que impedia o carregamento da página no [!UICONTROL Visual Experience Composer] (VEC). (TGT-44873)
* Várias correções de localização foram feitas na interface do [!DNL Target].

## [!DNL Target] Standard/Premium 23.5.1 (23 a 25 de maio de 2023)

Esta versão estará disponível de acordo com o seguinte agendamento:

23 de maio: Europa, Oriente Médio e África (EMEA) região 24 de maio: Ásia-Pacífico (APAC) região 25 de maio: região das Américas

Esta versão conta com os seguintes novos aprimoramentos e correções:

* Correção de um problema que impedia determinados clientes de criar públicos-alvo com perfis de visitante usando operadores &quot;maior que&quot; ou &quot;menor que&quot;. (TGT-45271)
* Várias correções de localização foram feitas na interface do [!DNL Target].
* Atualização da interface do usuário do Target em vários locais para uma atualização futura da interface do usuário (as alterações estão atrás de um sinalizador de recurso até que as atualizações sejam lançadas).

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da Platform. |
| [Detalhes da versão da at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Alterações na documentação, notas de versão anteriores e notas de versão da Experience Cloud

Além das notas para cada versão, os recursos a seguir oferecem informações adicionais:

| Recurso | Detalhes |
|--- |--- |
| [Alterações de documentação](/help/main/r-release-notes/doc-change.md) | Veja informações detalhadas sobre atualizações neste manual que podem não estar incluídas nas notas de versão. |
| [Notas de versões anteriores](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Veja informações sobre os novos recursos e aprimoramentos das versões anteriores do Target Standard e do Target Premium. |
| [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR){target=_blank} | Veja as notas de versão mais recentes das soluções da Adobe Experience Cloud. |

## Informações de pré-lançamento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Os recursos a seguir permitem ver as novidades previstas para a próxima versão do Target.

| Recurso | Detalhes |
|--- |--- |
| [Atualização de produtos prioritários da Adobe](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Receba notificações antecipadas sobre futuros aprimoramentos de produtos para o [!DNL Target] e outras soluções da [!DNL Adobe Experience Cloud]. |
| [Notas de versão do Target - Pré-lançamento](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Informações sobre os lançamentos do Target no mês atual, incluindo informações de pré-lançamento. |
