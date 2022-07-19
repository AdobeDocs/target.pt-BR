---
keywords: notas de versão;versões;atualizações;versão futura;melhorias;novos recursos;correções;atualizações;pré-lançamento
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na próxima versão do Adobe Target, incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais novos recursos e melhorias serão incluídos na próxima versão?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: d0b6f81507cc5d5bc17d029c3d8f5b36c2c71a29
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 56%

---

# Notas de versão do Target (pré-lançamento)

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização: 18 de julho de 2022**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## [!DNL Target Standard/Premium] 22.7.1 (20 de julho de 2022)

Essa versão conta com os seguintes recursos, aprimoramentos e correções:

| Recurso | Descrição |
| --- | --- |
| Melhoria na precisão da avaliação do público-alvo e na latência do usuário final por meio do suporte a IPv6 | As localizações geográficas dos visitantes agora são determinadas por endereços IPv6, se disponíveis, em vez de somente endereços IPv4. As APIs de entrega também suportam parâmetros de entrada IPv6. A filtragem e a lista de permissões são compatíveis com endereços IPv4 e IPv6. Este suporte a IPv6 nesta versão significa que os visitantes serão incluídos com mais precisão nos públicos-alvo (qualificados para atividades com mais precisão ou incluídos nos critérios de filtragem). Também melhora a latência de dados, já que os clientes IPv6 rotearão diretamente, evitando a sobrecarga do gateway IPv6 para IPv4. |
| Aprimoramento do gerenciamento de carga no lado do cliente do A4T | Com a integração do lado do servidor A4T, se o Adobe Target identificar uma solicitação como proveniente de um bot, ela não encaminhará a carga para o Analytics e não haverá um evento mod_stats gravado nos logs do Target. Antes desta versão, as integrações do lado do cliente do A4T encaminhariam a carga para o Analytics, mesmo quando ela tivesse sido identificada como tráfego de bot. Essa inconsistência entre o servidor e o cliente levaria a discrepâncias, já que os relatórios do A4T para o último incluíam o tráfego de bot. Além disso, o tráfego de bot não foi necessariamente identificado nem sinalizado, o que significa que não foi possível desambiguar ou remover o tráfego de bot do resto do tráfego. E mesmo que um cliente tenha contabilizado o tráfego de bot por conta própria, ele não necessariamente corresponderia ao conjunto de tráfego que o Target identificou e excluiu como tráfego de bot, resultando em discrepâncias de divisão ou outros problemas. Com esta versão, o registro do lado do cliente A4T foi aprimorado para que o comportamento relacionado à carga do A4T seja o mesmo que com o lado do servidor A4T: Os visitantes identificados como bots são excluídos da contagem/relatório do Target, para implementações do lado do servidor e do lado do cliente. |

## [!DNL Target Standard/Premium] 22.6.2 (30 de junho de 2022)

Essa versão conta com os seguintes recursos, aprimoramentos e correções:

| Recurso | Descrição |
| --- | ---  |
| Notificações no produto | Obtenha as seguintes notificações relevantes no produto:<ul><li>**Atividades**: notificações para todos os tipos de atividade quando uma atividade é aprovada ou desativada manualmente ou quando atinge sua data inicial ou final. A notificação inclui o nome da atividade com um link para a página de visão geral da atividade.</li><li>**Scripts de perfil**: notificações quando um script de perfil é ativado ou desativado manualmente ou pelo Target.</li><li>**Feeds do Recommendations**: notificações quando um feed do Recommendations é ativado ou desativado manualmente ou pelo Target. Notificações também são enviadas quando um feed do Recommendations falha.</li></ul> Por padrão, as notificações são recebidas por administradores de produtos, editores e aprovadores. As notificações podem ser configuradas nas preferências da Experience Cloud.<br>Para obter mais informações, consulte [Notificações e anúncios](/help/main/c-intro/understand-the-target-ui.md#notifications-announcements). |
| *Guia do desenvolvedor do Adobe Target* | O *Guia do desenvolvedor do Adobe Target* consolida todo o conteúdo para desenvolvedores do [!DNL Target] em um guia conveniente. O guia inclui informações sobre a implementação do [!DNL Target] e [!DNL Recommendations], SDKs do [!DNL Target] e APIs do [!DNL Target].<br>Para obter mais informações, consulte [Guia do desenvolvedor do Adobe Target](https://developer.adobe.com/target/){target=_blank}. |

* Usuários com a função de [!UICONTROL Editor] não podem mais editar públicos em atividades ativas. (TGT-43582)
* Uma mensagem de aviso é exibida se um cliente tentar salvar um público-alvo com um ponto de exclamação (! ) como o primeiro caractere do nome do público-alvo (por exemplo, !Londres). (TGT-43643)
* Correção de um problema que fazia com que os cartões de detalhes da definição de públicos-alvo de alguns clientes indicassem que uma atividade finalizada ainda estava ativa. (TGT-43527)

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
