---
keywords: notas de versão;versões;atualizações;versão futura;aprimoramentos;novos recursos;correções;atualizações;pré-lançamento;acesso antecipado;release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease;Early access
description: Saiba mais sobre os novos recursos, melhorias e correções adicionados na próxima versão do [!DNL Target], incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos e melhorias que serão incluídos na próxima versão do  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: d09e02db4ea94671e2450d1748b07def932916d9
workflow-type: tm+mt
source-wordcount: '1378'
ht-degree: 11%

---

# Notas de versão do [!DNL Target] (pré-lançamento)

Este artigo contém informações de pré-lançamento das próximas versões do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.

**Última atualização: 24 de julho de 2025**

>[!NOTE]
>
>* As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.
>
>* Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md).
>
>* Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.8.2 (14 de agosto de 2025)

Esta versão do inclui as seguintes correções e atualizações:

**[!UICONTROL Activities]**

+++Ver detalhes
* **Correção de um problema de carregamento de atividade na [!DNL Target] interface atualizada**: correção de um problema na [!DNL Target] interface atualizada em que determinadas atividades não eram carregadas ao tentar editar. Esse problema fazia com que os clientes deixassem os usuários em uma tela de carregamento indefinida. Esse problema afetou várias atividades e foi relatado para ocorrer de forma inconsistente entre os clientes. Com essa correção, as atividades afetadas agora são carregadas corretamente, permitindo uma edição perfeita e reduzindo a interrupção dos workflows de atividades. (TGT-53209)
* **Correção de um erro de salvamento no processo de criação de atividade devido à `optionLocalId` validação**: correção de um problema no processo de criação de atividade que impedia os clientes de salvar alterações devido a um erro de validação de back-end: `OptionLocalIdReferentialIntegrity.ABActivity - Invalid optionLocalIds:` Esse problema ocorria ao modificar elementos específicos em uma atividade, resultando em uma falha na operação de salvamento. A correção garante que as referências do `optionLocalId` agora sejam validadas corretamente, permitindo que os clientes salvem as atividades sem encontrar esse erro. (TGT-53293)
* **Correção de uma falha no processo de criação de atividade causada por referências de opção inválidas ao alternar páginas**: correção de um problema no processo de criação de atividade que causava uma falha na interface do usuário após alternar páginas três vezes durante a edição. A falha foi acionada por referências de opção inválidas, resultando em erros de console, como &quot;Opção com localId &#39;7&#39; não encontrada&quot;. Com essa atualização, os clientes agora podem alternar entre páginas e aplicar modificações sem encontrar falhas ou interrupções do sistema. (TGT-53295)
* **Correção de um erro de salvamento no processo de criação de atividade causado por entradas de usuário inválidas ao editar experiências**: correção de um problema no processo de criação de atividade em que os clientes não conseguiam salvar as alterações em uma atividade devido a um erro de entrada de usuário inválido. O erro ocorria ao modificar experiências na interface atualizada, impedindo que as atualizações fossem confirmadas. A atividade agora pode ser salva com sucesso, permitindo que os clientes editem e publiquem sem interrupção. (TGT-53267)
* **Correção de um problema de carregamento no processo de criação de atividade que bloqueava a edição na interface atualizada**: correção de um problema no processo de criação de atividade em que os clientes não conseguiam editar atividades na interface atualizada devido a uma tela de carregamento contínuo. Agora, os clientes podem abrir e modificar atividades sem encontrar falhas de carregamento. (TGT-53415)

+++

**Fragmentos de experiência (XFs)**

+++Ver detalhes
* **Correção de um problema no processo de criação de atividades que permitia a edição não intencional de fragmentos exportados pelo AEM pelo HTML**: correção de um problema no processo de criação de atividades que permitia aos clientes editar o HTML de [!DNL Experience Fragments] (XFs) exportado do [!DNL Adobe Experience Manager] (AEM) no [!DNL Target]. Esse comportamento não foi intencional, pois os XFs devem permanecer bloqueados para edição depois de publicados no AEM. A correção garante que a opção &quot;Editar HTML&quot; não esteja mais disponível para fragmentos exportados pelo AEM, preservando a integridade do conteúdo e o controle esperado. (TGT-53286)

+++

**Modo de controle de qualidade**

+++Ver detalhes
* **Correção de um problema no processo de criação de atividade em que os espaços à esquerda nas URLs causavam links de controle de qualidade com falha**: correção de um problema no processo de criação de atividade em que os espaços à esquerda na URL da atividade não eram cortados corretamente ao salvar. Isso causava links de controle de qualidade inválidos e formatação incorreta no back-end. Após a atualização, os URLs agora são salvos corretamente, evitando links quebrados e melhorando a confiabilidade dos fluxos de trabalho de controle de qualidade para os clientes. (TGT-53427)

+++

**[!UICONTROL Recommendations]**

+++Ver detalhes
* **Correção de um problema na interface de pesquisa de catálogo em que a pesquisa avançada não fornecia sugestões**: correção de um problema na nova interface de usuário [!UICONTROL Catalog Search] em que o recurso [!UICONTROL Advanced Search] não fornecia sugestões. Os usuários precisavam inserir valores exatos com ortografia precisa, tornando a experiência de pesquisa complicada e sujeita a erros. Com essa correção, o [!UICONTROL Advanced Search] agora oferece sugestões relevantes à medida que os usuários digitam, melhorando a usabilidade e reduzindo o atrito na localização de produtos. (TGT-52008)
* **Solução de vários problemas de filtragem e interface de usuário para melhorar a capacidade de resposta e a interação com a entidade**: solução de vários problemas, incluindo capacidade insuficiente de resposta dos detalhes dos critérios em dispositivos de tela pequena, falta de resultados ao selecionar &quot;Todos os grupos de hosts&quot; no filtro Ambiente e incapacidade de interagir com entidades sem nome. Essas correções melhoram a usabilidade em tamanhos de tela, garantem uma filtragem precisa e permitem a interação total com todas as entidades do produto, melhorando a experiência geral para os usuários. (TGT-52992)
* **Correção de IDs de produtos ausentes na exibição detalhada do Recommendations durante a criação da atividade**: correção de um problema no processo de criação de atividades do [!DNL Recommendations], em que as IDs de produtos estavam ausentes na tela de detalhes do produto, dificultando aos clientes a cópia ou a referência às IDs de produtos durante fluxos de trabalho. As IDs de produto agora aparecem claramente na visualização de detalhes, melhorando a visibilidade e oferecendo suporte a um gerenciamento de produtos mais eficiente para os clientes. (TGT-51964)
* **Correção de um problema no processo de criação de atividade em que as mensagens do produto não eram exibidas na exibição de recomendações**: correção de um problema no processo de criação de atividade em que a coluna [!UICONTROL Message] na exibição [!DNL Recommendations] não exibia os dados do produto, mesmo que as mensagens estivessem presentes. Os clientes tinham que remover e adicionar novamente a coluna manualmente para revelar temporariamente o conteúdo, que muitas vezes desaparecia novamente ao rolar ou pesquisar. Essa atualização restaura a visibilidade consistente das mensagens do produto, melhorando a navegação no catálogo e os workflows de revisão. (TGT-52777)
* **Correção de um problema no processo de criação de atividade em que a seleção de &#39;Todos os grupos de hosts&#39; não retornava resultados na exibição de recomendações**: correção de um problema no processo de criação de atividade em que a seleção do ambiente &quot;Todos os grupos de hosts&quot; na exibição [!DNL Recommendations] não retornava resultados. Os clientes agora podem visualizar os dados do produto em todos os grupos de hosts conforme esperado, melhorando a visibilidade e a precisão do filtro durante a configuração da atividade. (TGT-53006)
* **Correção de um problema no processo de criação de atividade em que a alternância de promoção frontal não persistia após salvar**: correção de um problema no processo de criação de atividade em que a desabilitação da alternância de promoção frontal nas configurações de atividade não persistia após salvar. Os clientes que tentaram remover a promoção principal descobriram que o botão de alternância era reativado ao revisitar a atividade, impedindo a personalização adequada. Essa atualização permite que as alterações sejam salvas de forma confiável, dando aos clientes controle total sobre as configurações de promoção. (TGT-53215)

+++

**Visual Experience Composer (VEC)**

+++Ver detalhes
* **Correção do carregamento de atividades e de [!UICONTROL Cancel] problemas de botões no processo de criação de atividades**: correção de um problema no processo de criação de atividades em que determinadas atividades não eram carregadas, impossibilitando o acesso de clientes a modificações. Além disso, o botão [!UICONTROL Cancel] não respondia, impedindo os clientes de interromper o processo de carregamento ou sair do modo de edição. Essa correção garante que as atividades agora sejam carregadas de forma confiável, e que o botão [!UICONTROL Cancel] funcione conforme esperado, melhorando a estabilidade geral e a experiência do usuário no Visual Experience Composer. (VEC)(TGT-53218)
* **Correção de um problema de alternância de experiência na interface do VEC atualizada que bloqueava a edição e desabilitava o botão [!UICONTROL Cancel]**: correção de um problema na interface do VEC atualizada em que as modificações falhavam ao carregar ao alternar entre experiências em uma atividade de Direcionamento de Experiência (XT). Os clientes não puderam editar experiências além da que inseriram inicialmente, e o botão [!UICONTROL Cancel] estava ausente ou sem resposta. Essa correção garante que as modificações agora sejam carregadas corretamente em todas as experiências e que o botão [!UICONTROL Cancel] funcione de maneira confiável, mesmo sem a extensão Auxiliar, melhorando a edição de fluxos de trabalho e reduzindo a frustração. (TGT-53256)
* **Correção de um problema de tela branca ao alternar entre várias experiências no processo de criação de atividade**: correção de um problema em que a alternância entre várias experiências causava uma tela branca. Também foi corrigido um problema no processo de criação de atividade em que os clientes encontravam uma tela branca ao tentar modificar várias experiências em uma atividade. Esse problema ocorria após aplicar alterações em duas experiências e selecionar uma terceira experiência, impedindo mais edições. A atualização garante transições tranquilas entre experiências, permitindo que os clientes façam modificações sem interrupção. (TGT-53266)
* **Correção de um problema no VEC em que as alterações de código personalizado não eram salvas de forma confiável nas sessões de edição**: correção de um problema em que as modificações de código personalizado feitas no Visual Experience Composer (VEC) não eram salvas de forma confiável em uma única tentativa. Os clientes relataram que alterações, como atualizações de estilo ou edição do HTML, estavam ausentes intermitentemente do site e das URLs de controle de qualidade, mesmo após o uso dos botões [!UICONTROL Edit Content] e [!UICONTROL Save] final. Essa regressão foi resolvida, garantindo que todas as alterações no código personalizado persistam conforme esperado em todas as sessões de edição.** (TGT-53418)

+++

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Detalhes sobre alterações em cada versão do SDK da Web da plataforma. |
| [Detalhes da versão da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
