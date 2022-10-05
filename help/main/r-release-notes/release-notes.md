---
keywords: Notas de versão;novos recursos;versões;atualizações;atualização;versão;aprimoramento;aprimoramentos;correções;correções de bugs;atualizações
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: dea956fe5d28200515a9638306a7d879585cb794
workflow-type: tm+mt
source-wordcount: '841'
ht-degree: 43%

---

# Notas de versão do Target (atual)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium] Além disso, as notas de versão para APIs [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outras alterações de plataforma também estão incluídas, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## [!DNL Target] Standard/Premium 22.10.1 (lançamento escalonado de 5 a 7 de outubro de 2022)

Esta versão estará disponível de acordo com o seguinte agendamento:

* **5 de outubro**: Região Ásia-Pacífico (APAC)
* **6 de outubro**: Região das Américas
* **7 de outubro**: Europa, Oriente Médio e África (EMEA)

Esta versão contém os seguintes novos recursos, aprimoramentos e correções:

| Recurso | Detalhes |
| --- | --- |
| [!DNL Adobe Experience Manager] (AEM) fragmentos de experiência | As atualizações da funcionalidade de fragmentos de experiência AEM incluem o seguinte:<ul><li>Adição da capacidade de filtrar AEM fragmentos de experiência por tipo (HTML ou JSON) no [!UICONTROL Ofertas] lista. (TGT-43121)</li><li>Correção de um problema que permitia aos clientes inserir JSON [!UICONTROL Fragmento de experiência] ofertas ao usar o VEC, que não é compatível. As ofertas JSON podem ser inseridas somente ao usar a variável [!UICONTROL Experiência baseada em formulário] compositor. (TGT-43846)</li></ul>Para obter mais informações, consulte AEM [fragmentos de experiência](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md). |
| Novo [!UICONTROL Visual Experience Composer] extensão para Google Chrome | Um novo [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] A extensão (VEC) para o Chrome está disponível na Chrome Web Store.<br>A partir de janeiro de 2023, a variável [!DNL Target] A extensão VEC Helper deixará de funcionar no Google Chrome porque o Google não permitirá extensões usando o Manifest V2. Baixe a nova extensão para continuar a criar visualmente seus sites em [!DNL Target] a partir do novo ano.<br>Os links a seguir mostram as duas extensões na Chrome Web Store:<ul><li>[Nova extensão](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}</li><li>[Extensão Antiga](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak){target=_blank}</li></ul>Para obter mais informações, consulte [Extensão do Visual Editing Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). |
| Métricas otimizadas do A4T para [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático]<br>(Data exata de lançamento a ser determinada.) | Esteja ciente das seguintes alterações:<ul><li>Adição de suporte para métricas binárias e de maximização no [!UICONTROL Analytics para Target] Relatórios do A4T para [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] atividades</li><li>Comportamento preservado para atividades existentes até 20 de fevereiro de 2023. Após essa data, as atividades serão descontinuadas para forçar a migração de atividades existente para um novo comportamento</li><li>A partir de 20 de fevereiro de 2023, o suporte para `averagetimespentonsite`, `bouncerate`e `entries` métricas em [!DNL Target] As atividades do serão substituídas.</li></ul> |
| Atualizações de documentação | As principais atualizações de documentação incluem:<ul><li>Novo e atualizado [Documentação da API de administração e relatórios do Adobe Target](https://developer.adobe.com/target/administer/admin-api/)O {target=_blank} inclui uma cobertura abrangente dos endpoints da API de Administração e Relatório, incluindo propriedades, ofertas, hosts, ambientes, clientes, públicos-alvo, atividades e muito mais.<br>Veja isso e o conteúdo adicional do desenvolvedor no [[!DNL Adobe Target] [!UICONTROL Guia do desenvolvedor]](https://developer.adobe.com/target/){target=_blank}.</li><li>[Cálculos estatísticos em testes A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md)<br>Este artigo documenta os cálculos estatísticos detalhados usados nos testes manuais A/Bn em [!DNL Adobe Target].<br>As informações contidas neste artigo substituem a variável *Cálculos do Adobe Target para testes A/B* arquivo pdf anteriormente disponível para download neste site.</li></ul> |

* Correção de um problema que impedia a exibição correta das informações da regra de público-alvo na [!UICONTROL Refinamentos de públicos-alvo] janela de informações. (TGT-43917)
* Aprimorado o desempenho do [!DNL Target] Interface do usuário ao carregar públicos que se aproximam da [limite recomendado de regras de direcionamento](/help/main/r-troubleshooting-target/target-limits.md#targeting-rules). (TGT-43675)
* Correção de um problema que fazia com que alguns componentes não fossem exibidos corretamente no [!UICONTROL Modificações] no painel [!UICONTROL Experiências] ao criar ou editar atividades no VEC após alternar de [!UICONTROL Compor] para [!UICONTROL Procurar] modo. (TGT-43300)
* Correção de um problema que impedia o arquivamento de alguns clientes [!UICONTROL Teste A/B] atividades que usam [!UICONTROL Direcionamento automático]. (TGT-40978)
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
