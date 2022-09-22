---
keywords: Notas de versão;novos recursos;versões;atualizações;atualização;versão;aprimoramento;aprimoramentos;correções;correções de bugs;atualizações
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 3d8da94a52046e70a89dc24d7923f743bee5c458
workflow-type: ht
source-wordcount: '632'
ht-degree: 100%

---

# Notas de versão do Target (atual)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium] Além disso, as notas de versão para APIs [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outras alterações de plataforma também estão incluídas, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## [!DNL Target] Standard/Premium 22.9.1 (lançamento escalonado de 13 a 15 de setembro de 2022)

Esta versão estará disponível de acordo com o seguinte agendamento:

* **13 de setembro**: regiões da Europa, Oriente Médio e África (EMEA)
* **14 de setembro**: região das Américas
* **15 de setembro**: região Ásia-Pacífico (APAC)

Essa versão conta com os seguintes aprimoramentos e correções:

* Adicionada uma opção [!UICONTROL Entre domínios] ao baixar a at.js 2.10.0 (e posterior) para permitir ou desativar a configuração de cookies de terceiros. (TGT-43674)
* Notificações atualizadas na interface do [!DNL Target] para informar os clientes sobre falhas na importação dos feeds do [!DNL Recommendations]. (TGT-35811)
* Correção de um problema que fazia com que as [!UICONTROL Ofertas de decisão] não funcionassem corretamente no [!UICONTROL Visual Experience Composer] (VEC). (TGT-43866)
* Correção de um problema que exibia uma mensagem de erro ao selecionar a meta de conversão [!UICONTROL Clicou em um elemento] ao criar uma atividade de [!UICONTROL teste multivariado] (MVT). (TGT-43842)
* Correção de um problema que impedia que a coluna [!UICONTROL Impressões] fosse exibida no arquivo de relatório em CSV baixado para atividades de [!UICONTROL Automated Personalization] (AP). (TGT-43780)
* Correção de um problema que impedia os clientes de editar ofertas HTML/JSON após duplicar experiências ao usar o [!UICONTROL Experience Composer baseado em formulário]. (TGT-43633)
* Correção de um problema que impedia os clientes de copiarem uma atividade de [!UICONTROL Teste A/B] de um espaço de trabalho não padrão para outro espaço de trabalho não padrão. (TGT-41910)
* Um problema foi corrigido para garantir que os clientes possam exibir apropriadamente o uso de objetos do [!DNL Recommendations] (designs, critérios, coleções e assim por diante) em atividades de [!UICONTROL Teste A/B] e [!UICONTROL Direcionamento de experiência] (XT) que contêm recomendações, permitindo também excluir objetos de critério que não estão mais sendo usados na interface do [!DNL Target] e no back-end do [!DNL Recommendations]. (TGT-42331)
* Correção de um problema que fazia com que um alerta de tempo limite de rede fosse exibido na interface do [!DNL Target] ao buscar parâmetros. (TGT-43737)
* Foram feitas atualizações na interface para garantir que determinadas ações de arrastar e soltar sejam acessíveis pelo teclado. (TGT-42969)
* Atualizações feitas na interface para garantir que as sequências de texto estejam corretamente localizadas.

## at.js versão 2.10.0 (13 de setembro de 2022)

* Adicionada uma opção [!UICONTROL Entre domínios] ao baixar a at.js 2.10.0 (e posterior) para permitir ou desativar a configuração de cookies de terceiros. (TGT-43674)

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
