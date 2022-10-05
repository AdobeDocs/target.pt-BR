---
keywords: Notas de versão;novos recursos;versões;atualizações;atualização;versão;aprimoramento;aprimoramentos;correções;correções de bugs;atualizações
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 7f5b4265adbb0e98b7250f99b0268ba5b70dec7c
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 81%

---

# Notas de versão do Target (atual)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium] Além disso, as notas de versão para APIs [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outras alterações de plataforma também estão incluídas, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## [!DNL Target] Standard/Premium 22.10.1 (lançamento escalonado de 10 a 13 de outubro de 2022)

Esta versão estará disponível de acordo com o seguinte agendamento:

* **10 de outubro**: região da Ásia-Pacífico (APAC)
* **11 de outubro**: região das Américas
* **13 de outubro**: região da Europa, Oriente Médio e África (EMEA)

Essa versão contém os seguintes novos recursos, aprimoramentos e correções:

| Recurso | Detalhes |
| --- | --- |
| [!DNL Adobe Experience Manager] (AEM) fragmentos de experiência | As atualizações da funcionalidade de fragmentos de experiência AEM incluem o seguinte:<ul><li>Adição da capacidade de filtrar AEM fragmentos de experiência por tipo (HTML ou JSON) no [!UICONTROL Ofertas] lista. (TGT-43121)</li><li>Correção de um problema que permitia aos clientes inserir ofertas de [!UICONTROL fragmento de experiência] JSON ao usar o VEC, apesar de não serem compatíveis. As ofertas JSON podem ser inseridas somente ao usar o [!UICONTROL Experience Composer baseado em formulários]. (TGT-43846)</li></ul>Para obter mais informações, consulte AEM [fragmentos de experiência](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md). |
| Nova extensão do [!UICONTROL Visual Experience Composer] para Google Chrome | Uma nova extensão do [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) para o Chrome está disponível na loja da web do Chrome.<br>A partir de janeiro de 2023, a extensão auxiliar do [!DNL Target] VEC atual deixará de funcionar no Google Chrome porque o Google não permitirá extensões que usam Manifest V2. Baixe a nova extensão para continuar a organizar visualmente seus sites no [!DNL Target] a partir do novo ano.<br>Os links a seguir mostram as duas extensões na loja da web do Chrome:<ul><li>[Nova extensão](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}</li><li>[Extensão antiga](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak){target=_blank}</li></ul>Para obter mais informações, consulte [Extensão do Visual Editing Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). |
| Atualizações de documentação | As principais atualizações de documentação incluem:<ul><li>Novo e atualizado [Documentação da API de administração e relatórios do Adobe Target](https://developer.adobe.com/target/administer/admin-api/)O {target=_blank} inclui uma cobertura abrangente dos endpoints da API de Administração e Relatório, incluindo propriedades, ofertas, hosts, ambientes, clientes, públicos-alvo, atividades e muito mais.<br>Veja isso e o conteúdo adicional do desenvolvedor no [[!DNL Adobe Target] [!UICONTROL Guia do desenvolvedor]](https://developer.adobe.com/target/){target=_blank}.</li><li>[Cálculos estatísticos em testes A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md)<br>Este artigo documenta os cálculos estatísticos detalhados usados nos testes manuais A/Bn em [!DNL Adobe Target].<br>As informações contidas neste artigo substituem a variável *Cálculos do Adobe Target para testes A/B* arquivo pdf anteriormente disponível para download neste site.</li></ul> |

* Correção de um problema que impedia a exibição correta das informações da regra de público-alvo na janela de informações de [!UICONTROL Refinamentos de públicos-alvo]. (TGT-43917)
* Melhoria no desempenho da interface do [!DNL Target] ao carregar públicos-alvo que se aproximam do [limite recomendado de regras de direcionamento](/help/main/r-troubleshooting-target/target-limits.md#targeting-rules). (TGT-43675)
* Correção de um problema que fazia com que alguns componentes não fossem exibidos corretamente no painel [!UICONTROL Modificações] da página [!UICONTROL Experiências] ao criar ou editar atividades no VEC após alternar do modo [!UICONTROL Compor] para o modo [!UICONTROL Procurar]. (TGT-43300)
* Correção de um problema que impedia que os clientes arquivassem algumas atividades de [!UICONTROL Teste A/B] que usam [!UICONTROL Direcionamento automático]. (TGT-40978)
* Adição da capacidade de usar automaticamente uma única oferta em vários locais em um único grupo de relatórios. (TGT-40689)

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
