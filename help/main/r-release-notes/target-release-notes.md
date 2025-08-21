---
keywords: notas de versão;versões;atualizações;versão futura;aprimoramentos;novos recursos;correções;atualizações;pré-lançamento;acesso antecipado;release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease;Early access
description: Saiba mais sobre os novos recursos, melhorias e correções adicionados na próxima versão do [!DNL Target], incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos e melhorias que serão incluídos na próxima versão do  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 95d8bd994ffdb1d256b7eb0aea1a2462b40ce530
workflow-type: tm+mt
source-wordcount: '2221'
ht-degree: 7%

---

# Notas de versão do [!DNL Target] (pré-lançamento)

Este artigo contém informações de pré-lançamento das próximas versões do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.

**Última atualização: 21 de agosto de 2025**

>[!NOTE]
>
>* As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio. As informações neste artigo são atualizadas com frequência, especialmente antes das versões do.
>
>* Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md).
>
>* Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.8.3 (21 de agosto de 2025)

Esta versão inclui as seguintes atualizações e correções:

**[!UICONTROL Activities]**

+++Ver detalhes
* **Correção de um problema em que o salvamento de atividades acionava um erro de entrada de usuário inválido devido a dados de propriedade malformados**: os clientes encontraram um erro crítico ao tentar salvar atividades existentes. A mensagem de erro indicava uma entrada de usuário inválida, referenciando especificamente um conteúdo de nome de propriedade não reconhecido na carga JSON. Notavelmente, novas atividades usando a mesma propriedade foram salvas com sucesso, sugerindo que o problema foi isolado aos dados de atividade herdados. O processo de criação de atividade agora lida corretamente com configurações de propriedade herdadas, evitando erros de entrada inválidos e garantindo um comportamento de salvamento consistente em atividades novas e existentes. (TGT-53507)
* **Correção de um problema que impedia os clientes de salvar uma atividade devido a um erro de InvalidProperty.Json**: os clientes encontraram um erro ao tentar salvar uma atividade na interface atualizada, mesmo sem fazer modificações. A mensagem de erro indicou uma estrutura JSON inválida: &quot;Json inválido. Nome de propriedade &#39;content&#39; não reconhecido. Local: linha - 1, coluna - 432.&quot; Esse problema foi causado por uma propriedade não reconhecida na carga da solicitação e agora foi resolvido. Os clientes podem salvar as atividades com sucesso sem encontrar esse erro. (TGT-53513)
* **Correção de um problema em que as atividades agendadas exibiam incorretamente um status [!UICONTROL Live] até a atualização da página**: os clientes observavam que, ao agendar uma atividade para entrar em funcionamento em uma data e hora futuras, o status aparecia imediatamente como [!UICONTROL Live] em vez de [!UICONTROL Scheduled]. Isso causava confusão, mesmo que a mensagem de confirmação indicasse corretamente que a atividade estava programada. Atualizar a página corrigiu a exibição de status. Esse problema foi resolvido e as atividades agendadas mostram corretamente o status Agendado sem exigir uma atualização. (TGT-52937)

+++

**[!UICONTROL Analytics for Target](A4T)**

+++Ver detalhes
* **Correção de um problema em que os clientes não podiam digitar nomes de conjunto de relatórios durante o processo de criação de atividade**: os clientes que usavam [!DNL Adobe Analytics] como fonte de relatórios durante o processo de criação de atividade não podiam digitar na lista suspensa [!UICONTROL Report Suite] para procurar conjuntos de relatórios específicos. Isso afetou os fluxos de trabalho de organizações com um grande número de conjuntos de relatórios, em que a rolagem manual atrasava significativamente a configuração. A lista suspensa não era ordenada alfabeticamente e não respondia consistentemente à entrada digitada, dificultando a localização de conjuntos de relatórios como &quot;Office + Store - Web - Prod&quot;. Esse problema foi resolvido e os clientes agora podem pesquisar com eficiência digitando nomes de conjuntos de relatórios. (TGT-53345)

+++

**[!UICONTROL Audiences]**

+++Ver detalhes
* **Correção de um problema em que públicos-alvo com &quot;Intervalo de tempo&quot; expirados bloqueavam a gravação de atividades mesmo após a remoção**: os clientes não conseguiam salvar atividades na interface atualizada devido a um erro relacionado a públicos-alvo com &quot;Intervalo de tempo&quot; expirados. Mesmo após a remoção do público-alvo afetado, a mensagem de erro persistia: &quot;A atividade contém público-alvo com intervalo de tempo inválido&quot;. Esse problema ocorria porque o sistema continuava validando o público somente atividade, mesmo quando não estava mais em uso. O comportamento foi ainda mais complicado por discrepâncias de fuso horário. A lógica de validação foi corrigida e os clientes agora podem salvar atividades sem encontrar esse erro. (TGT-53517)

+++

**[!UICONTROL Experience Fragment]s**

+++Ver detalhes
* **Correção de um problema que impedia os clientes de inserir Fragmentos de Experiência usando [!UICONTROL Insert Before] ou [!UICONTROL Insert After] na interface do usuário** Os clientes encontraram um erro ao tentar inserir [!UICONTROL Experience Fragments] em uma atividade usando as opções &quot;Inserir Antes&quot; ou &quot;Inserir Depois&quot; na interface do usuário atualizada. A mensagem de erro exibida foi: &quot;O conteúdo da oferta deve conter exatamente um elemento HTML&quot;. Esse problema era específico da interface atualizada e não ocorria na versão anterior. Esse problema foi resolvido e os clientes podem inserir [!UICONTROL Experience Fragments] com êxito sem encontrar esse erro. (TGT-53442)

+++

**[!UICONTROL Offer decisions]**

+++Ver detalhes
* **Correção de um problema que impedia os clientes de editar ofertas de decisão e selecionar elementos de página específicos na interface atualizada**: no processo de criação de atividades atualizado, os clientes não conseguiam editar ofertas de decisão existentes ou selecionar elementos de página específicos no Visual Experience Composer (VEC). As ofertas de decisão eram exibidas incorretamente como ofertas do HTML e as alterações feitas durante a edição não eram salvas. Além disso, determinados URLs regionais, como o site do Japão, não foram carregados corretamente no VEC, bloqueando a criação e as atualizações da atividade. As ofertas de decisão agora são exibidas corretamente, os elementos da página podem ser selecionados conforme esperado e os URLs regionais são carregados corretamente no VEC, restaurando a funcionalidade de edição completa. (TGT-53425)
* **Correção de um problema em que [!UICONTROL Offer Decision] seletores não podiam ser modificados e alterados inesperadamente após salvar**: no processo de criação de atividade atualizado, os clientes não conseguiam modificar o seletor [!UICONTROL Offer Decision] conforme pretendido. As tentativas de alterar o seletor não tiveram êxito e o seletor foi revertido para um valor incorreto após salvar. Esse comportamento fez com que a oferta de decisão desaparecesse do Visual Experience Composer (VEC), bloqueando mais edições. As alterações no seletor agora são preservadas corretamente e as ofertas de decisão permanecem visíveis e editáveis no VEC após salvar.(TGT-53433)
* **Correção de um problema em que [!UICONTROL Offer Decisions] desaparecia da atividade após salvar**: [!UICONTROL Offer Decisions] adicionados durante o processo de criação da atividade não eram retidos após salvar e reabrir a atividade. Esse problema ocorria ao editar conteúdo dinâmico e inserir [!UICONTROL Offer Decisions] com seletores e propriedades específicos. [!UICONTROL Offer Decisions] agora persiste corretamente após salvar e os seletores permanecem intactos, garantindo um comportamento consistente de direcionamento e edição. (TGT-53434)

+++

**[!DNL Recommendations]**

+++Ver detalhes
* **Correção de um problema na interface do usuário [!DNL Recommendations] em que o download do CSV de critérios personalizados retornava o erro 404**: correção de um problema em que os clientes não conseguiam baixar o CSV de critérios personalizados no processo de criação de atividades. O link de download agora funciona corretamente, permitindo que os clientes exportem critérios personalizados conforme esperado. (TGT-51966)
* **Correção de um carregamento de imagem inconsistente em[!UICONTROL Catalog Search]**: correção de um problema em que as miniaturas e imagens em [!UICONTROL  Catalog Search] não eram carregadas de forma consistente no processo de criação da atividade. As imagens não eram exibidas a menos que a coluna &quot;URL da miniatura&quot; estivesse visível e algumas imagens do produto fossem carregadas parcialmente ou não fossem carregadas após as ações de navegação ou pesquisa. O comportamento de carregamento da imagem foi estabilizado e as miniaturas agora são exibidas de forma confiável, independentemente das ações de visibilidade da coluna ou de navegação. (TGT-52778)
* **Correção de um problema em que a edição de uma recomendação em uma experiência duplicada afetava a experiência original**: os clientes relataram que a modificação de uma recomendação em uma experiência duplicada alterava involuntariamente a experiência original. Especificamente, após a duplicação da Experiência B no processo de criação de atividade e a edição do design ou dos critérios, as mesmas alterações foram refletidas na Experiência B original, apesar de serem entidades separadas. As experiências duplicadas agora mantêm configurações separadas, garantindo que as edições em uma experiência não afetem a original. (TGT-53369)
* **Correção de um problema em que as alterações em uma experiência duplicada afetavam involuntariamente a experiência original em uma atividade**: os clientes relatavam que, ao duplicar uma experiência em uma atividade e atribuir um novo público-alvo, todas as alterações feitas no design ou nos critérios da experiência duplicada também eram refletidas na experiência original. Esse problema ocorria mesmo se nenhuma edição fosse feita diretamente na versão original, afetando a capacidade de criar variações independentes na mesma atividade. O processo de criação de atividade agora isola corretamente as experiências duplicadas, garantindo que as edições feitas em uma experiência não afetem a original. (TGT-53361)
* **Correção de um problema em que [!UICONTROL Recommendation Catalog] falhava intermitentemente em exibir dados completos de atributos de produto**: na interface do usuário atualizada [!DNL Recommendations], os clientes tinham um problema em que determinados atributos de produto, como mensagem, não eram exibidos de forma consistente nos resultados [!UICONTROL Catalog Search], mesmo que os dados existissem no feed. Esse problema exigia que os clientes reconfigurassem manualmente a visibilidade da coluna para recuperar os valores ausentes. [!UICONTROL Catalog Search] agora exibe de forma confiável todos os atributos configurados, eliminando a necessidade de redefinições manuais de colunas. (TGT-52769)
* **Correção de um problema em que [!UICONTROL Front Promotion] não podia ser desabilitado em uma atividade online**: as tentativas de desabilitar [!UICONTROL Front Promotion] em uma atividade online não foram salvas. Após selecionar [!UICONTROL Change Promotion] e desabilitá-lo, a promoção permaneceu ativa ao editar novamente a atividade, impedindo atualizações nas configurações de recomendação. As configurações de promoção agora são salvas corretamente, permitindo que os clientes desativem ou modifiquem promoções em atividades ativas, conforme esperado. (TGT-53231)
* **Correção de um problema em que a habilitação de [!DNL Recommendations] [!UICONTROL Promotion] sem dados acionava uma mensagem de erro não clara**: a habilitação de [!UICONTROL Front] ou [!UICONTROL Back Promotion] em uma atividade [!DNL Recommendations] sem especificação dos valores necessários resultava em uma mensagem genérica de &quot;Erro de entrada inválido&quot;. O problema subjacente era um campo de configuração ausente, mas a mensagem de erro não indicava claramente a causa, dificultando a solução de problemas. O processo de criação de atividades agora fornece uma mensagem de erro clara e acionável quando campos obrigatórios, como `collectionId` ou regras, estão ausentes, ajudando os clientes a identificar e resolver rapidamente problemas de configuração. (TGT-52616)
* **Correção de um problema que impedia a exibição da lista [!UICONTROL Product] no modal [!UICONTROL Edit] da guia [!UICONTROL Recommendations]**: Os clientes não conseguiam exibir a lista de produtos filtrada ao editar um [!UICONTROL collection] ou [!UICONTROL exclusion] na guia [!UICONTROL Recommendations]. Esperava-se que a lista fosse atualizada em tempo real com base nas regras aplicadas, mas ela não parecia como esperado. Esse problema foi resolvido e a lista de produtos agora é exibida corretamente e atualizada dinamicamente à medida que as regras são modificadas. (TGT-53481)
* **Correção de um problema com o layout da caixa de diálogo Exibir Detalhes na interface do usuário atualizada**: o layout da modal Exibir Detalhes na interface do usuário atualizada foi modificado para melhorar a clareza e a usabilidade. A caixa de diálogo agora inclui duas guias:
   * Guia [!UICONTROL Details]: exibe todas as informações relevantes do item selecionado.
   * Guia [!UICONTROL Inventory]: mostra todos os produtos filtrados pelas regras atuais de coleta e exclusão.

  Esse aprimoramento ajuda os clientes a navegar e entender com mais facilidade os dados específicos do item e o contexto do inventário no processo de criação da atividade. (TGT-53503)

   * **Correção de um problema em que as promoções removidas nas atividades de recomendação reapareciam após o salvamento**: Os clientes relataram que quando [!UICONTROL front] ou [!UICONTROL back] promoções eram removidas das atividades [!DNL Recommendations] e a atividade era salva, as promoções continuavam a aparecer após a reabertura. Esse problema ocorria nos ambientes de preparo e produção e afetava o processo de criação de atividade atualizado. O problema foi resolvido. As promoções removidas de uma atividade agora persistem corretamente após salvar. (TGT-53490)

+++

**Relatórios**

+++Ver detalhes
* **Correção de um problema em que o relatório [!UICONTROL Automated Segments] exibia valores nulos de público-alvo**: os clientes relataram que [!UICONTROL Automated Segments] nos relatórios de atividade mostravam valores nulos para dados de público-alvo, impedindo uma análise precisa do desempenho do segmento. Este problema ocorria ao acessar a seção [!UICONTROL Reports] e selecionar [!UICONTROL Automated Segments], mesmo que dados válidos de público-alvo fossem esperados. [!UICONTROL Automated Segments] agora exibe corretamente os valores de público-alvo, garantindo informações confiáveis de relatórios e segmentação. (TGT-52793)

+++

**Aplicativos de Página Única (SPAs)**

+++Ver detalhes
* **Correção de um problema em que a alternância entre os modos [!UICONTROL Browse] e [!UICONTROL Design] redefinia o estado do SPA na interface do usuário atualizada**: os clientes relataram que a alternância entre os modos [!UICONTROL Browse] e [!UICONTROL Design] na interface do usuário atualizada fazia com que o editor da Web fosse recarregado, redefinindo o estado dos SPAs. Esse problema interrompeu os fluxos de trabalho e exigiu que os clientes inserissem as informações novamente. O problema foi resolvido. O estado do SPA agora é preservado ao alternar entre modos, garantindo uma experiência mais suave e consistente durante a criação da atividade. (TGT-53074)

+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++Ver detalhes
* **Correção de um problema no processo de criação de atividade que bloqueava a progressão para a etapa [!UICONTROL Targeting] nas atividades de AP**: correção de um problema no processo de criação de atividade em que os clientes não conseguiam prosseguir para a etapa [!UICONTROL Targeting] nas atividades de [!UICONTROL Automated Personalization] (AP), a menos que dois locais fossem adicionados. Esse comportamento foi diferente da experiência anterior, onde um único local com várias ofertas era suficiente. O requisito foi corrigido, permitindo que os clientes continuem usando configurações de local único como parte de seus workflows de AP. (TGT-53426)
* **Correção de um problema em que o novo processo de criação de atividade não definia o parâmetro fmt=png-alpha para imagens transparentes**: na interface atualizada, as imagens inseridas durante o processo de criação da atividade não incluíam mais o parâmetro `fmt=png-alpha` por padrão, resultando em perda de transparência. Esse comportamento foi diferente da interface anterior, que anexava automaticamente o parâmetro aos URLs de imagem, preservando planos de fundo transparentes. O processo de criação de atividade agora aplica corretamente o parâmetro `fmt=png-alpha` a URLs de imagem quando a transparência é necessária, garantindo uma renderização consistente de ativos transparentes. (TGT-52615)
* **Correção de um problema que impedia os clientes de pesquisar conjuntos de relatórios na interface atualizada**: Na interface atualizada, a lista suspensa [!UICONTROL Report Suites] na seção [!UICONTROL Goals & Settings] não permitia que os clientes digitassem e pesquisassem, dificultando a localização de conjuntos de relatórios específicos, especialmente para locatários com um grande número de entradas. Diferentemente da interface anterior, a lista não era classificada e não tinha filtragem baseada em entrada. Esse problema foi resolvido. Agora os clientes podem digitar para pesquisar e filtrar conjuntos de relatórios, restaurando a funcionalidade disponível na interface herdada. (TGT-53514)

+++

**[!UICONTROL Workspaces]**

+++Ver detalhes
* **Correção de um problema em que um cliente restrito a um único espaço de trabalho poderia exibir atividades de outros espaços de trabalho**: clientes com acesso limitado a um espaço de trabalho podiam exibir inesperadamente atividades em todos os espaços de trabalho ao selecionar [!UICONTROL All Workspaces] no processo de criação de atividade. Essa visibilidade apresentava um risco de alterações não intencionais em atividades ativas em outros espaços de trabalho, possivelmente afetando o desempenho do site. Os controles de acesso do Workspace foram reforçados para garantir que os clientes possam visualizar e interagir somente com as atividades no espaço de trabalho atribuído. (TGT-53101)
* **Correção de um problema em que um cliente podia exibir atividades de [!UICONTROL Default Workspace] sem ter acesso:** Um cliente com acesso limitado ao espaço de trabalho de preparo podia exibir atividades de [!UICONTROL Default Workspace] por meio do processo de criação de atividades. Esse comportamento ocorreu apesar da configuração correta do back-end e dos direitos de acesso. Os controles de acesso do Workspace foram reforçados para garantir que os clientes possam visualizar as atividades somente no espaço de trabalho atribuído.(TGT-53297)

+++

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Detalhes sobre alterações em cada versão do SDK da Web da plataforma. |
| [Detalhes da versão da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
