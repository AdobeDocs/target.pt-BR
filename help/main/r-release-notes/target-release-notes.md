---
keywords: notas de versão;versões;atualizações;versão futura;melhorias;novos recursos;correções;atualizações;pré-lançamento
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na próxima versão do Adobe Target, incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais novos recursos e melhorias serão incluídos na próxima versão?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: b7258ae154ae2b354e70349d8d878a1338128417
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 31%

---

# Notas de versão do Target (pré-lançamento)

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização: 23 de maio de 2022**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## at.js versão 2.9.0 (25 de maio de 2022)

* Adição do suporte a Dicas do cliente do agente do usuário.
* Correção de um erro em que várias solicitações de mbox na mesma página tinham IDs de impressão diferentes.

## [!DNL Target Standard/Premium] 22.5.1 (libertação escalonada; 11-13 de maio de 2022)

Esta versão estará disponível de acordo com o seguinte agendamento:

* **11 de maio**: Região Ásia-Pacífico (APAC)
* **12 de maio**: Região das Américas
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
* Correção de um problema que fazia com que as edições nos scripts de perfil fossem revertidas para o script original não editado após o script ser editado, ativado e depois desativado. O script de perfil agora permanece no seu estado editado. (TGT-43249)
* Correção de um problema que causava o seguinte erro ao tentar mover um público para outro espaço de trabalho: &quot;Não podemos concluir sua solicitação. Entre em contato com o Atendimento ao cliente da Adobe se o problema persistir&quot;. (TGT-43212)
* Correção de um erro que causava um erro ao clonar modificações de código personalizadas para páginas de Aplicativo de página única (SPA). (TGT-43137)
* Correção de um problema que afetava a promoção original após a duplicação de uma experiência e a edição da promoção. (TGT-41775)

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outros [!DNL Adobe Experience Cloud] soluções, cadastre-se para a [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
