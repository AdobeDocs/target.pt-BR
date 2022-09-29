---
keywords: notas de versão;versões;atualizações;versão futura;melhorias;novos recursos;correções;atualizações;pré-lançamento
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na próxima versão do Adobe Target, incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais novos recursos e melhorias serão incluídos na próxima versão?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 0c6d2df47a9115bcbd3c0d8a5ea7d401df29d6c8
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 28%

---

# Notas de versão do Target (pré-lançamento)

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização em 29 de setembro de 2022**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## [!DNL Target] Standard/Premium 22.10.1 (lançamento escalonado de 4 a 6 de outubro de 2022)

Esta versão estará disponível de acordo com o seguinte agendamento:

* **Outubro 4**: Europa, Oriente Médio e África (EMEA)
* **5 de outubro**: Região Ásia-Pacífico (APAC)
* **6 de outubro**: Região das Américas

Esta versão contém os seguintes novos recursos, aprimoramentos e correções:

| Recurso | Detalhes |
| --- | --- |
| [!DNL Adobe Experience Manager] (AEM) fragmentos de experiência | As atualizações da funcionalidade de fragmentos de experiência AEM incluem o seguinte:<ul><li>Adição da capacidade de filtrar AEM fragmentos de experiência por tipo (HTML ou JSON) no [!UICONTROL Ofertas] lista. (TGT-43121)</li><li>Correção de um problema que permitia aos clientes inserir JSON [!UICONTROL Fragmento de experiência] ofertas ao usar o VEC, que não é compatível. As ofertas JSON podem ser inseridas somente ao usar a variável [!UICONTROL Experiência baseada em formulário] compositor. (TGT-43846)</li></ul>Para obter mais informações, consulte AEM [fragmentos de experiência](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md). |
| Novo [!UICONTROL Visual Experience Composer] extensão para Google Chrome | Um novo [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] A extensão (VEC) para o Chrome está disponível na Chrome Web Store.<br>A partir de janeiro de 2023, a variável [!DNL Target] A extensão VEC Helper deixará de funcionar no Google Chrome porque o Google não permitirá extensões usando o Manifest V2. Baixe a nova extensão para continuar a criar visualmente seus sites em [!DNL Target] a partir do novo ano.<br>Os links a seguir mostram as duas extensões na Chrome Web Store:<ul><li>[Nova extensão](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}</li><li>[Extensão Antiga](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak){target=_blank}</li></ul>Para obter mais informações, consulte [Extensão do Visual Editing Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). |
| Métricas otimizadas do A4T para [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático]<br>(Data exata de lançamento a ser determinada.) | Esteja ciente das seguintes alterações:<ul><li>Adição de suporte para métricas binárias e de maximização no [!UICONTROL Analytics para Target] Relatórios do A4T para [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] atividades</li><li>Comportamento preservado para atividades existentes até 20 de fevereiro de 2023. Após essa data, as atividades serão descontinuadas para forçar a migração de atividades existente para um novo comportamento</li><li>A partir de 20 de fevereiro de 2023, o suporte para `averagetimespentonsite`, `bouncerate`e `entries` métricas em [!DNL Target] As atividades do serão substituídas.</li></ul> |

* Correção de um problema que impedia a exibição correta das informações da regra de público-alvo na [!UICONTROL Refinamentos de públicos-alvo] janela de informações. (TGT-43917)
* Aprimorado o desempenho do [!DNL Target] Interface do usuário ao carregar públicos que se aproximam da [limite recomendado de regras de direcionamento](/help/main/r-troubleshooting-target/target-limits.md#targeting-rules). (TGT-43675)
* Correção de um problema que fazia com que alguns componentes não fossem exibidos corretamente no [!UICONTROL Modificações] no painel [!UICONTROL Experiências] ao criar ou editar atividades no VEC após alternar de [!UICONTROL Compor] para [!UICONTROL Procurar] modo. (TGT-43300)
* Correção de um problema que impedia o arquivamento de alguns clientes [!UICONTROL Teste A/B] atividades que usam [!UICONTROL Direcionamento automático]. (TGT-40978)
* Adição da capacidade de usar automaticamente uma única oferta em vários locais em um único grupo de relatórios. (TGT-40689)

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
