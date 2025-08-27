---
keywords: notas de versão;versões;atualizações;versão futura;aprimoramentos;novos recursos;correções;atualizações;pré-lançamento;acesso antecipado;release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease;Early access
description: Saiba mais sobre os novos recursos, melhorias e correções adicionados na próxima versão do [!DNL Target], incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos e melhorias que serão incluídos na próxima versão do  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: cc0bf794e366f304b52db309d4e3a66292d7ea32
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 20%

---

# Notas de versão do [!DNL Target] (pré-lançamento)

Este artigo contém informações de pré-lançamento das próximas versões do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.

**Última atualização: 27 de agosto de 2025**

>[!NOTE]
>
>* As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio. As informações neste artigo são atualizadas com frequência, especialmente antes das versões do.
>
>* Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md).
>
>* Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.8.4 (1º de setembro de 2025)

Esta versão inclui as seguintes atualizações e correções:

**[!UICONTROL Activities]**

+++Ver detalhes
* **Os clientes não puderam copiar os nomes de atividades ou documentos do[!UICONTROL Activity Overview]**: anteriormente, os clientes não conseguiam copiar o nome de uma atividade ou a oferta/documento associado diretamente do [!UICONTROL Activity Overview] no processo de criação de atividades atualizado. Essa limitação afetou a usabilidade, especialmente em telas menores. Agora, os clientes podem copiar facilmente os nomes das atividades e dos documentos sem soluções alternativas. (TGT-51850)
* **Assimilação proativa de dados de clientes [!DNL Target] com curadoria durante a criação da atividade**: melhoria do processo de criação da atividade ao habilitar a coleta proativa de relatórios, conteúdo e capturas de tela de clientes [!DNL Target]. Esse aprimoramento aborda as lacunas de dados identificadas em casos de uso existentes e ajuda a garantir insights mais precisos durante a atividade e a configuração de experimentos. (TGT-52415)

+++

**[!UICONTROL Recommendations]**

+++Ver detalhes
* **A lista de produtos não estava visível na caixa de diálogo [!UICONTROL View Collection]:** anteriormente, os clientes não conseguiam ver a lista de produtos ao visualizar uma coleção na guia [!UICONTROL Recommendations]. A caixa de diálogo [!UICONTROL View Collection] agora exibe corretamente os produtos associados, melhorando a transparência e a usabilidade na interface atualizada do usuário do Recommendations. (TGT-50531)
* **Correção de um problema que fazia com que a filtragem diferenciasse maiúsculas e minúsculas na [!UICONTROL Product Catalog Search] pesquisa avançada**: a filtragem de pesquisa avançada na página [!UICONTROL Product Catalog Search] agora ignora corretamente a diferenciação entre maiúsculas e minúsculas, alinhando-se ao comportamento do back-end e dos serviços do GraphQL. Essa atualização garante resultados de sugestões consistentes e precisos para os clientes, independentemente da capitalização do texto. (TGT-53585)

+++

**[!UICONTROL Reports]**

+++Ver detalhes
* **Falha ao carregar relatórios para o público-alvo da área de trabalho devido a um erro de nome de público-alvo inválido**: os clientes encontraram um erro de GraphQL ao tentar exibir relatórios para o público-alvo no processo de criação de atividade. O sistema retornou uma mensagem &quot;Nome de público-alvo inválido: XXXXX&quot;, impedindo o acesso aos dados de relatórios. Agora os relatórios são carregados corretamente para o público-alvo da Área de trabalho. (TGT-53371)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Ver detalhes
* **Falha ao clicar em &quot;Aceitar Cookies&quot; usando o [!UICONTROL Enhanced Experience Composer] (EEC) devido a uma função ausente**: os clientes relataram que tentar aceitar cookies por meio do EEC resultou em um erro de console: `handleclickAcceptAllButton is not defined`. A funcionalidade de aceitação de cookies agora funciona conforme esperado, garantindo uma experiência mais suave durante a criação da atividade na interface atualizada. (TGT-52794)
* **A nova interface do EEC falhou ao carregar determinadas páginas que eram anteriormente compatíveis com a interface do usuário herdada**: os clientes relataram que o novo EEC não pôde carregar algumas páginas, que estavam acessíveis na interface do usuário herdada, apesar do código de interrupção de iframe presente no site. O processo de criação de atividade atualizado agora oferece suporte ao carregamento dessas páginas, restaurando a compatibilidade para fluxos de trabalho de criação de atividade. (TGT-53061)
* **O VEC exibiu uma tela em branco ao editar as experiências**: os clientes de um determinado locatário relataram que a tela do VEC ficava em branco ao tentar editar experiências no VEC atualizado. Esse problema afetava atividades recém-criadas e mais antigas, impedindo a continuidade do fluxo de trabalho. O VEC agora é carregado corretamente, permitindo que os clientes editem as experiências sem interrupção. (TGT-53547)
* **O VEC falhou e exibiu uma tela em branco ao carregar determinadas atividades**: os clientes de um determinado locatário relataram que o VEC falhou ao carregar atividades específicas. O editor de experiência permaneceu preso na &quot;Aplicação de modificações iniciais&quot; antes de travar e mostrar uma tela em branco. Erros de console indicaram uma falha na leitura de propriedades indefinidas. O editor agora carrega as atividades afetadas sem erros no VEC atualizado. (TGT-53548)

+++

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Detalhes sobre alterações em cada versão do SDK da Web da plataforma. |
| [Detalhes da versão da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
