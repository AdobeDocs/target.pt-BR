---
keywords: notas de versão;versões;atualizações;versão futura;aprimoramentos;novos recursos;correções;atualizações;pré-lançamento;acesso antecipado;release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease;Early access
description: Saiba mais sobre os novos recursos, melhorias e correções adicionados na próxima versão do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos e melhorias que serão incluídos na próxima versão do  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 065220af5c8e3b6cc25ef7289d006a901d2e932a
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 15%

---

# Notas de versão do [!DNL Target] (pré-lançamento)

Este artigo contém informações de pré-lançamento das próximas versões do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.

**Última atualização: 22 de julho de 2025**

>[!NOTE]
>
>* As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.
>
>* Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md).
>
>* Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.7.3 (sexta-feira, 24 de julho de 2025)

Devido aos problemas recentes identificados, principalmente relacionados às personalizações complexas do cliente, esta versão inclui as seguintes correções e atualizações:

**Atividades**

+++Ver detalhes
* Correção de um problema em que o método `buildViews` na classe de construtor definia incorretamente `viewMaxLocalId` para a contagem total de exibições, em vez da maior `viewLocalId` atribuída. (TGT-53207)
* Introdução de um novo endpoint de API que permite que os usuários restaurem opções de atividades excluídas anteriormente de um banco de dados secundário. Essa funcionalidade aproveita a infraestrutura existente fornecida pelas classes `RemovedCampaignElements` e `RemovedOptionInfo`, garantindo a reintegração perfeita das opções excluídas nas atividades ativas. (TGT-52903)
* Correção de um problema na interface do usuário atualizada do [!DNL Target], em que as ofertas excluídas nas atividades do [!UICONTROL Automated Personalization] (AP) eram exibidas como `Deleted option with ID: X` em vez de seus nomes originais (por exemplo, `Offer Name [Deleted]`, como mostrado na interface do usuário herdada). Essa correção restaura a rotulagem significativa de ofertas excluídas, melhorando a clareza e tornando os relatórios mais precisos e fáceis de usar. (TGT-52921)
* Correção de um problema na camada de persistência de backend em que as opções excluídas eram armazenadas corretamente, mas não acessíveis por meio de pontos de extremidade de API existentes. Como resultado, os aplicativos de front-end não puderam recuperar nomes significativos para opções excluídas, afetando as exibições de relatórios históricos. Essa correção garante que os dados de opção excluídos preservados agora possam ser exibidos corretamente na interface do usuário. (TGT-52973)
* Correção de um problema em que algumas atividades migradas do front-end do Target para o Target Central tinham configurações de métrica inconsistentes devido a um bug de sincronização corrigido anteriormente. Especificamente, as atividades que originalmente usavam uma métrica de conversão e foram atualizadas posteriormente para uma métrica baseada em análise mantiveram valores desatualizados nos campos `primaryMetricType` e `successCriteria`. (TGT-52643)

+++

**Experience Composer baseado em formulário**

+++Ver detalhes
* Correção de um problema no [!UICONTROL Form-Based Experience Composer] que causava a falha do editor após clicar no ícone **[!UICONTROL Manage Content]** ( ![Ícone Gerenciar conteúdo](/help/main/assets/icons/Experience.svg) ) ao criar ou editar uma atividade de [!UICONTROL Automated Personalization] (AP). (TGT-53047)

+++

**Recommendations**

+++Ver detalhes
* Correção de um problema que impedia [!UICONTROL Catalog Search] de carregar resultados adicionais ao rolar a tela para a parte inferior da lista, restaurando o comportamento consistente com a interface herdada. (TGT-53088)
* Correção de um problema em que a coluna [!UICONTROL Number of Products] estava ausente na página [!UICONTROL Collections] da interface atualizada [!DNL Target]. A coluna agora é exibida corretamente, restaurando a funcionalidade esperada. (TGT-53168)
* Correção de um problema em que as regras [!UICONTROL Collection] não eram filtradas corretamente de acordo com as regras. (TGT-53254)
* Correção de um problema que bloqueava a exclusão de itens da caixa de diálogo [!UICONTROL Criteria Details]. (TGT-53245)
* Correção de um problema que impedia a abertura ou interação com produtos sem nome. Esse problema ocorria ao selecionar ambientes que retornavam resultados sem nome, impedindo o acesso aos detalhes do produto. (TGT-53007)
* Correção de um problema que causava a falha da página [!UICONTROL Catalog Search] e exibia uma tela em branco ao selecionar determinados produtos. (TGT-53087)
* Correção de um problema em que [!DNL Recommendations] atividades contendo nomes de métricas com mais de 25 caracteres não podiam ser abertas ou editadas devido a limitações de API. Essa correção garante a compatibilidade com nomes de métricas que excedem o limite de caracteres, restaurando o acesso total às atividades afetadas. (TGT-52839)
* Correção de um problema em que os usuários não conseguiam editar a atividade [!DNL Recommendation] site_cart_z1 na interface do usuário do [!DNL Target]. A tentativa de abrir a atividade disparou um erro na página [!UICONTROL Overview], bloqueando o acesso ao editor. (TGT-53221)

+++

**Relatório**

+++Ver detalhes
* Correção de um problema em que o campo sandbox no banco de dados de atividades não era limpo ao alternar a fonte de relatórios de [!DNL Customer Journey Analytics] ou [!DNL Analytics] para [!DNL Target]. Anteriormente, a interface do usuário enviava a sandbox corretamente: nulo, mas o back-end ignorava esse valor, deixando dados desatualizados da sandbox no lugar. O back-end agora limpa corretamente o campo da sandbox quando nulo é recebido. (TGT-52798)
* A camada de persistência de opções excluídas foi reimplementada no back-end do Target para oferecer suporte a relatórios históricos precisos nas atividades de [!UICONTROL Automated Personalization] (AP). Anteriormente, quando uma opção era excluída, seu nome era perdido, dificultando a interpretação de dados de desempenho anteriores.

  **Principais melhorias**:

   * As opções excluídas agora são rastreadas usando a infraestrutura `RemovedCampaignElements` e `RemovedOptionInfo` existente.
   * Quando uma opção é removida de uma atividade de AP, seus metadados (por exemplo, ID e nome) são preservados.
   * A interface do usuário de relatórios agora pode exibir o nome de opção original (por exemplo, `Option Name [Deleted]`) junto com métricas históricas, melhorando a clareza e a usabilidade.

  Essa atualização garante relatórios consistentes e significativos, mesmo depois que as opções são removidas de uma atividade. (TGT-52986)

* Implementação de um novo ponto de extremidade de migração para oferecer suporte à transferência de opções de atividades excluídas de atividades baseadas em JCR para a [!DNL Target] Central. Essa funcionalidade permite o rastreamento e a geração de relatórios consistentes em todos os sistemas. Esse recurso garante que as opções excluídas sejam preservadas e sincronizadas no front-end e back-end do [!DNL Target], melhorando a integridade dos dados e dos relatórios históricos. (TGT-53217)

+++

**Visual Experience Composer (VEC)**

+++Ver detalhes

* Correção de um problema no VEC em que a aplicação de uma modificação em uma exibição causava duplicação e acionava um erro &quot;Entrada de usuário inválida&quot;. (TGT-52886)
* Correção de um problema com a funcionalidade [!UICONTROL Undo] para as opções [!UICONTROL Insert Before] e [!UICONTROL Insert After] ao configurar ofertas de imagem no VEC.

  Anteriormente, desfazer uma ação de [!UICONTROL Insert Before] ou [!UICONTROL Insert After] em ofertas de imagem resultava em um comportamento inconsistente ou na falha ao reverter corretamente a modificação, especialmente em atividades criadas na interface herdada [!DNL Target]. Esse problema foi resolvido para garantir que as ações de desfazer agora funcionem de forma confiável para essas modificações. (TGT-52809)

* Correção de um problema em que o atributo `contentEditable` era definido involuntariamente como verdadeiro e persistia no conteúdo HTML salvo. Essa atualização garante uma saída do HTML mais limpa e esperada sem comportamento de edição não intencional. (TGT-52319)
* Para evitar a perda permanente de opções excluídas e garantir um comportamento consistente entre os serviços, a funcionalidade de exclusão reversível foi implementada para opções na interface do usuário e nos microsserviços relacionados.

  **Alterações de Chave**:

   * As opções não são mais excluídas permanentemente. Em vez disso, eles são marcados com um novo sinalizador deleted: true no objeto XML de parâmetros.
   * Esse sinalizador é usado somente pela interface atualizada do usuário [!DNL Target] para excluir opções excluídas da renderização e impedir que sejam enviadas para serviços de borda.
   * As opções excluídas permanecem como parte da carga útil da atividade durante as edições, garantindo a rastreabilidade e evitando a entrega de opções inexistentes para os clientes.

  Essa atualização melhora a integridade dos dados e se alinha às práticas recomendadas para gerenciar exclusões em sistemas distribuídos. (TGT-52726)

+++

**Espaços de trabalho**

+++Ver detalhes
* Correção de um problema ao copiar uma atividade de um espaço de trabalho não padrão para um padrão ou entre espaços de trabalho não padrão. As ofertas agora são duplicadas com rastreamento e nomenclatura aprimorados para evitar conflitos.

  **Principais melhorias**:
   * As ofertas são recriadas no espaço de trabalho de destino com IDs e metadados atualizados.
   * As ofertas copiadas são renomeadas usando o formato: &quot;Cópia do nome da oferta&quot;, além de um número aleatório ou carimbo de data e hora para garantir exclusividade.
   * O sistema atualiza os estados de oferta e atividade para refletir as novas IDs.
   * Essa funcionalidade evita erros causados por vários nomes idênticos de &quot;Cópia de oferta&quot; durante ações de cópia repetidas.
   * As ofertas podem não aparecer imediatamente na lista de ofertas do espaço de trabalho de destino, mas são processadas e exibidas adequadamente.

  Essa atualização melhora a confiabilidade e a rastreabilidade ao gerenciar ofertas em vários espaços de trabalho. (TGT-53080)

+++

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Detalhes sobre alterações em cada versão do SDK da Web da plataforma. |
| [Detalhes da versão da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
