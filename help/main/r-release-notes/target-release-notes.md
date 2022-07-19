---
keywords: notas de versão;versões;atualizações;versão futura;melhorias;novos recursos;correções;atualizações;pré-lançamento
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na próxima versão do Adobe Target, incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais novos recursos e melhorias serão incluídos na próxima versão?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: a5d2c07105b1d0fac6115fe507537be6a36799e9
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 33%

---

# Notas de versão do Target (pré-lançamento)

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização: 19 de julho de 2022**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## [!DNL Target Standard/Premium] 22.7.1 (20 de julho de 2022)

Essa versão conta com os seguintes recursos, aprimoramentos e correções:

| Recurso | Descrição |
| --- | --- |
| Melhoria na precisão da avaliação do público-alvo e na latência do usuário final por meio do suporte a IPv6 | As localizações geográficas dos visitantes agora são determinadas por endereços IPv6, se disponíveis, em vez de somente endereços IPv4. As APIs de entrega também suportam parâmetros de entrada IPv6. A filtragem e a lista de permissões são compatíveis com endereços IPv4 e IPv6. Este suporte a IPv6 nesta versão significa que os visitantes serão incluídos com mais precisão nos públicos-alvo (qualificados para atividades com mais precisão ou incluídos nos critérios de filtragem). Também melhora a latência de dados, já que os clientes IPv6 rotearão diretamente, evitando a sobrecarga do gateway IPv6 para IPv4. |
| Aprimoramento do gerenciamento de carga no lado do cliente do A4T | Com a integração do lado do servidor A4T, se o Adobe Target identificar uma solicitação como proveniente de um bot, ela não encaminhará a carga para o Analytics e não haverá um evento mod_stats gravado na variável [!DNL Target] logs. Antes desta versão, as integrações do lado do cliente A4T encaminhariam a carga para o [!DNL Analytics], mesmo quando foi identificado como tráfego de bot. Essa inconsistência entre o servidor e o cliente levaria a discrepâncias, já que os relatórios do A4T para o último incluíam o tráfego de bot. Além disso, o tráfego de bot não foi necessariamente identificado nem sinalizado, o que significa que não foi possível desambiguar ou remover o tráfego de bot do resto do tráfego. E mesmo que um cliente tenha contabilizado tráfego de bot por conta própria, ele não corresponderia necessariamente ao conjunto de tráfego que [!DNL Target] identificado e excluído como tráfego de bot, resultando em discrepâncias divididas ou outros problemas. Com esta versão, o registro do lado do cliente A4T foi aprimorado para que o comportamento relacionado à carga do A4T seja o mesmo que com o lado do servidor A4T: Os visitantes identificados como bots são excluídos do [!DNL Target] contagem/relatórios, para implementações do lado do servidor e do lado do cliente. |


## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
