---
keywords: Notas de versão;novos recursos;versões;atualizações;atualização;versão;aprimoramento;aprimoramentos;correções;correções de bugs;atualizações
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do [!DNL Adobe Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 9489655d18170c581f2abf8502f01c7b7e0626b7
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 53%

---

# Notas de versão do Target (atual)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium] Além disso, as notas de versão para APIs [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outras alterações de plataforma também estão incluídas, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## [!DNL Target Standard/Premium] 22.5.1 (libertação escalonada; 11-13 de maio de 2022)

Esta versão estará disponível de acordo com o seguinte agendamento:

* **11 de maio**: Região Ásia-Pacífico (APAC)
* **12 de maio**: Região da América do Norte (NA)
* **13 de maio**: Europa, Oriente Médio e África (EMEA)

Esta versão contém os seguintes aprimoramentos e correções:

* Correção de um problema que causava um erro de JavaScript e impedia que alguns clientes acessassem os detalhes da atividade para determinados [!UICONTROL Automated Personalization] (AP). (TGT-43526)
* Correção de um problema que impedia alguns clientes de adicionar (ou editar) uma oferta específica a uma atividade de AP. (TGT-43503)
* Correção de um problema no [!DNL Target] Interface do usuário que exibia a seguinte mensagem de erro: &quot;Sua mbox global pode não estar sincronizada. Tente salvá-la novamente”. Esse problema era de interface do usuário e não afetava as implementações dos clientes. (TGT-43475)
* Correção de um problema que impedia um cliente de editar refinamentos e públicos-alvo no nível da experiência para uma atividade se os refinamentos e públicos-alvo fossem criados antes da nova [!UICONTROL Públicos-alvo] A interface do usuário foi implantada. (TGT-43433)
* Correção de um problema que permitia aos clientes selecionar duplicatas [!DNL Adobe Audience Manager] (AAM) públicos-alvo ao editar públicos-alvo de relatórios para uma atividade. (TGT-43430)
* Correção de um problema que impedia os clientes de criar públicos duplicados, mas em espaços de trabalho diferentes. (TGT-43423)
* Correção de um problema que impedia os clientes de excluir locais com ofertas ad hoc em atividades criadas no [!UICONTROL Experience Composer baseado em formulário]. (TGT-43315)
* Correção de um problema que impedia os clientes de acessar ofertas de código após clicar em ofertas de imagem e atualizar a interface do usuário. (TGT-43566)
* Certifique-se de que a lista de métricas disponíveis no [!DNL Target] Interface do usuário ao criar atividades que usam [!DNL Analytics for Target] (A4T) exibe somente as métricas que foram coletadas por [!DNL Adobe Analytics]. (TGT-43294)
* Correção de um problema que fazia com que as edições nos scripts de perfil fossem revertidas para o script original não editado após o script ser editado, ativado e depois desativado. O script de perfil agora permanece no seu estado editado. (TGT-43249)
* Correção de um problema que causava o seguinte erro ao tentar mover um público para outro espaço de trabalho: &quot;Não podemos concluir sua solicitação. Entre em contato com o Atendimento ao cliente da Adobe se o problema persistir&quot;. (TGT-43212)
* Correção de um erro que causava um erro ao clonar modificações de código personalizadas para páginas de Aplicativo de página única (SPA). (TGT-43137)
* Correção de um problema que afetava a promoção original após a duplicação de uma experiência e a edição da promoção. (TGT-41775)

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
