---
keywords: Notas de versão;novos recursos;versões;atualizações;atualização;versão;aprimoramento;aprimoramentos;correções;correções de bugs;atualizações
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: d54f3c4c75031788316a94acf3d14a8db2a17366
workflow-type: tm+mt
source-wordcount: '966'
ht-degree: 100%

---

# Notas de versão do Target (atual)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium] Além disso, as notas de versão para APIs [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outras alterações de plataforma também estão incluídas, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## Versão da plataforma do [!DNL Target] (20 de julho de 2022)

Essa versão conta com os seguintes recursos, aprimoramentos e correções:

| Recurso | Descrição |
| --- | --- |
| Melhoria na precisão da avaliação de público-alvo e redução da latência do usuário final por meio da compatibilidade com IPv6 (TNT-43364, TNT-44692) | As localizações geográficas dos visitantes agora são determinadas por endereços IPv6, se disponíveis, em vez de somente endereços IPv4. As APIs de entrega também são compatíveis com parâmetros de entrada IPv6. A filtragem e a lista de permissões são compatíveis com endereços IPv4 e IPv6. A compatibilidade com IPv6 nesta versão significa que os visitantes serão incluídos com maior precisão nos públicos-alvo (qualificados para atividades com maior precisão ou incluídos nos critérios de filtragem). Ela também melhora a latência de dados, já que os clientes IPv6 rotearão diretamente, evitando a sobrecarga do gateway IPv6 para IPv4. |
| Correção de um problema de manipulação de conteúdo do lado do cliente no A4T (TNT-44926) | Com a integração no lado do servidor do A4T, ao identificar uma solicitação como proveniente de um bot, o Adobe Target não encaminhará o conteúdo para o Analytics e não haverá a gravação de um evento mod_stats nos logs do [!DNL Target]. Com esta versão, o registro no lado do cliente do A4T foi aprimorado para que o comportamento relacionado ao conteúdo do A4T seja o mesmo do lado do servidor: os visitantes identificados como bots são excluídos da contagem/relatório do [!DNL Target]. (Observe que o problema em questão se limitava a implementações que usavam o gerenciamento de conteúdo do lado do cliente; o lado do servidor não foi afetado. Com esta versão, o comportamento agora é consistente para o gerenciamento de conteúdo do lado do servidor e do lado do cliente.) |

## [!DNL Target Standard/Premium] 22.6.2 (30 de junho de 2022)

Essa versão conta com os seguintes recursos, aprimoramentos e correções:

| Recurso | Descrição |
| --- | ---  |
| Notificações no produto | Obtenha as seguintes notificações relevantes no produto:<ul><li>**Atividades**: notificações para todos os tipos de atividade quando uma atividade é aprovada ou desativada manualmente ou quando atinge sua data inicial ou final. A notificação inclui o nome da atividade com um link para a página de visão geral da atividade.</li><li>**Scripts de perfil**: notificações quando um script de perfil é ativado ou desativado manualmente ou pelo Target.</li><li>**Feeds do Recommendations**: notificações quando um feed do Recommendations é ativado ou desativado manualmente ou pelo Target. Notificações também são enviadas quando um feed do Recommendations falha.</li></ul> Por padrão, as notificações são recebidas por administradores de produtos, editores e aprovadores. As notificações podem ser configuradas nas preferências da Experience Cloud.<br>Para obter mais informações, consulte [Notificações e anúncios](/help/main/c-intro/understand-the-target-ui.md#notifications-announcements). |
| *Guia do desenvolvedor do Adobe Target* | O *Guia do desenvolvedor do Adobe Target* consolida todo o conteúdo para desenvolvedores do [!DNL Target] em um guia conveniente. O guia inclui informações sobre a implementação do [!DNL Target] e [!DNL Recommendations], SDKs do [!DNL Target] e APIs do [!DNL Target].<br>Para obter mais informações, consulte [Guia do desenvolvedor do Adobe Target](https://developer.adobe.com/target/){target=_blank}. |

* Usuários com a função de [!UICONTROL Editor] não podem mais editar públicos em atividades ativas. (TGT-43582)
* Uma mensagem de aviso é exibida se um cliente tentar salvar um público-alvo com um ponto de exclamação (! ) como o primeiro caractere do nome do público-alvo (por exemplo, !Londres). (TGT-43643)
* Correção de um problema que fazia com que os cartões de detalhes da definição de públicos-alvo de alguns clientes indicassem que uma atividade finalizada ainda estava ativa. (TGT-43527)

## [!DNL Target Standard/Premium] 22.6.1 (versão escalonada: 7 a 9 de junho de 2022)

Esta versão estará disponível de acordo com o seguinte agendamento:

* **7 de junho**: região Ásia-Pacífico (APAC)
* **8 de junho**: região das Américas
* **9 de junho**: região da Europa, Oriente Médio e África (EMEA)

Essa versão conta com os seguintes aprimoramentos e correções:

* Um aprimoramento foi fornecido para a nova página de [!UICONTROL Públicos] para evitar uma inconsistência entre o banco de dados antigo, em que os públicos eram armazenados no passado, e a nova arquitetura, que busca as informações diretamente no back-end. (TGT-43552)
* Correção de um problema que impedia alguns clientes de salvar públicos combinados, causado pela criação de contêineres “vazios” pela interface do Target. (TGT-43588)

## Versão da plataforma do Target (25 de maio de 2022)

Essa versão conta com os seguintes aprimoramentos e correções:

* Adicionada compatibilidade com [User Agent Client Hints](https://developer.adobe.com/target/implement/client-side/atjs/user-agent-and-client-hints/){target=_blank}.
* Correção de um problema que causava esgotamento do tempo de maneira intermitente ao renderizar [!UICONTROL Decisões de oferta] em [!UICONTROL Direcionamento de experiência] (XT). (TNT-44611)

## at.js versão 2.9.0 (27 de maio de 2022)

* Adicionada compatibilidade com [User Agent Client Hints](https://developer.adobe.com/target/implement/client-side/atjs/user-agent-and-client-hints/){target=_blank}.
* Correção de um erro em que várias solicitações de mbox na mesma página tinham IDs de impressão diferentes.

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da Platform. |
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
