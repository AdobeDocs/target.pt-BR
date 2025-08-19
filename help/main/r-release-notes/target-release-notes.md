---
keywords: notas de versão;versões;atualizações;versão futura;aprimoramentos;novos recursos;correções;atualizações;pré-lançamento;acesso antecipado;release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease;Early access
description: Saiba mais sobre os novos recursos, melhorias e correções adicionados na próxima versão do [!DNL Target], incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos e melhorias que serão incluídos na próxima versão do  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 3b80ca92a445bbdab6202a28c03130d24920dfd0
workflow-type: tm+mt
source-wordcount: '893'
ht-degree: 16%

---

# Notas de versão do [!DNL Target] (pré-lançamento)

Este artigo contém informações de pré-lançamento das próximas versões do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.

**Última atualização: 19 de agosto de 2025**

>[!NOTE]
>
>* As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio. As informações neste artigo são atualizadas com frequência, especialmente antes das versões do.
>
>* Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md).
>
>* Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.8.3 (21 de agosto de 2025)

Esta versão inclui as seguintes atualizações e correções:

**Decisões de oferta**

+++Ver detalhes
* **Correção de um problema que impedia os clientes de editar ofertas de decisão e selecionar elementos de página específicos na interface atualizada**: no processo de criação de atividades atualizado, os clientes não conseguiam editar ofertas de decisão existentes ou selecionar elementos de página específicos no Visual Experience Composer (VEC). As ofertas de decisão eram exibidas incorretamente como ofertas do HTML e as alterações feitas durante a edição não eram salvas. Além disso, determinados URLs regionais, como o site do Japão, não foram carregados corretamente no VEC, bloqueando a criação e as atualizações da atividade. (TGT-53425)
* **Correção de um problema em que [!UICONTROL Offer Decision] seletores não podiam ser modificados e alterados inesperadamente após salvar**: no processo de criação de atividade atualizado, os clientes não conseguiam modificar o seletor [!UICONTROL Offer Decision] conforme pretendido. As tentativas de alterar o seletor não tiveram êxito e o seletor foi revertido para um valor incorreto após salvar. Isso fez com que a oferta de decisão desaparecesse do Visual Experience Composer (VEC), bloqueando mais edições. (TGT-53433)
* **Correção de um problema em que [!UICONTROL Offer Decisions] desaparecia da atividade após salvar**: [!UICONTROL Offer Decisions] adicionados durante o processo de criação da atividade não eram retidos após salvar e reabrir a atividade. Esse problema ocorria ao editar conteúdo dinâmico e inserir [!UICONTROL Offer Decisions] com seletores e propriedades específicos. (TGT-53434)

+++

**Recommendations**

+++Ver detalhes
* **Correção de um problema na interface do usuário Recs em que o download do CSV de critérios personalizados retornava o erro 404**: correção de um problema em que os clientes não conseguiam baixar o CSV de critérios personalizados no processo de criação de atividades. (TGT-51966)
* **Correção de um carregamento de imagem inconsistente em[!UICONTROL Catalog Search]**: correção de um problema em que as miniaturas e imagens em [!UICONTROL &#x200B; Catalog Search] não eram carregadas de forma consistente no processo de criação da atividade. As imagens não eram exibidas a menos que a coluna &quot;URL da miniatura&quot; estivesse visível e algumas imagens do produto fossem carregadas parcialmente ou não fossem carregadas após as ações de navegação ou pesquisa. (TGT-52778)
* **Correção de um problema em que a edição de uma recomendação em uma experiência duplicada afetava a experiência original**: os clientes relataram que a modificação de uma recomendação em uma experiência duplicada alterava involuntariamente a experiência original. Especificamente, após a duplicação da Experiência B no processo de criação de atividade e a edição do design ou dos critérios, as mesmas alterações foram refletidas na Experiência B original, apesar de serem entidades separadas. (TGT-53369)
* **Correção de um problema em que as alterações em uma experiência duplicada afetavam involuntariamente a experiência original em uma atividade:** Os clientes relataram que, ao duplicar uma experiência em uma atividade e atribuir um novo público-alvo, todas as alterações feitas no design ou nos critérios da experiência duplicada também eram refletidas na experiência original. Isso ocorria mesmo sem edições feitas diretamente na versão original, afetando a capacidade de criar variações independentes na mesma atividade. (TGT-53361)
* **Correção de um problema em que [!UICONTROL Recommendation Catalog] falhava intermitentemente em exibir dados completos de atributos de produto**: na interface do usuário atualizada [!DNL Recommendations], os clientes tinham um problema em que determinados atributos de produto, como mensagem, não eram exibidos de forma consistente nos resultados da pesquisa no catálogo, mesmo que os dados existissem no feed. Esse problema exigia que os clientes reconfigurassem manualmente a visibilidade da coluna para recuperar os valores ausentes. (TGT-52769)
+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Ver detalhes
* **Correção de um problema no processo de criação de atividade que bloqueava a progressão para a etapa [!UICONTROL Targeting] nas atividades de AP**: correção de um problema no processo de criação de atividade em que os clientes não conseguiam prosseguir para a etapa [!UICONTROL Targeting] nas atividades de [!UICONTROL Automated Personalization] (AP), a menos que dois locais fossem adicionados. Esse comportamento foi diferente da experiência anterior, onde um único local com várias ofertas era suficiente. O requisito foi corrigido, permitindo que os clientes continuem usando configurações de local único como parte de seus workflows de AP. (TGT-53426)
* **Correção de um problema em que o novo processo de criação de atividade não definia o parâmetro fmt=png-alpha para imagens transparentes**: na interface atualizada, as imagens inseridas durante o processo de criação da atividade não incluíam mais o parâmetro `fmt=png-alpha` por padrão, resultando em perda de transparência. Esse comportamento foi diferente da interface anterior, que anexava automaticamente o parâmetro aos URLs de imagem, preservando planos de fundo transparentes. (TGT-52615)

+++

**[!UICONTROL Workspaces]**

+++Ver detalhes
* **Correção de um problema em que um cliente restrito a um único espaço de trabalho poderia exibir atividades de outros espaços de trabalho**: clientes com acesso limitado a um espaço de trabalho podiam exibir inesperadamente atividades em todos os espaços de trabalho ao selecionar [!UICONTROL All Workspaces] no processo de criação de atividade. Essa visibilidade apresentava um risco de alterações não intencionais em atividades ativas em outros espaços de trabalho, possivelmente afetando o desempenho do site. (TGT-53101)
* **Correção de um problema em que um cliente podia exibir atividades de [!UICONTROL Default Workspace] sem ter acesso:** Um cliente com acesso limitado ao espaço de trabalho de preparo podia exibir atividades de [!UICONTROL Default Workspace] por meio do processo de criação de atividades. Isso ocorria apesar da configuração correta do back-end e dos direitos de acesso. (TGT-53297)

+++

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Detalhes sobre alterações em cada versão do SDK da Web da plataforma. |
| [Detalhes da versão da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
