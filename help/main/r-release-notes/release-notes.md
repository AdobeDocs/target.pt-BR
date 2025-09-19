---
keywords: notas de versão;novos recursos;versões;atualizações;atualizar;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações;atualizações atuais;release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates;current updates
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 098415849152065b734cbebbab8dcf1d0805e202
workflow-type: tm+mt
source-wordcount: '1779'
ht-degree: 14%

---

# Notas de versão do [!DNL Target] (atuais)

Explore os recursos, aprimoramentos e correções mais recentes no [!DNL Adobe Target]. Essas notas de versão também abrangem atualizações para APIs do [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outros componentes da plataforma, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## Atualizações sensíveis ao tempo que você precisa saber {#time-sensitive}

[!BADGE Importante]{type=Informative}

Para atualizações com limite de tempo relacionadas ao [!DNL Adobe Target] e à sua implementação, o [!DNL Adobe] fornece notas de versão e documentação detalhadas por meio do [!UICONTROL Experience League]. Estes são alguns destaques importantes para sua implementação:

### Desativação da alternância de versão da interface do usuário [!DNL Target]

+++Ver detalhes
A equipe do [!DNL Target] está oferecendo um recurso temporário que permite alternar entre a interface atualizada do usuário do [!DNL Target] e a versão herdada usando um botão de alternância. Essa opção está disponível somente durante a fase final de implantação da interface.

![Alternância da versão da interface do usuário de destino](/help/main/r-release-notes/assets/toggle.png)

Quando a implantação for concluída, o botão de alternância será removido e todos os usuários farão a transição permanentemente para a interface atualizada. A [!DNL Adobe] recomenda um planejamento antecipado, pois esse recurso será eliminado em breve.

#### Linha do tempo de descontinuação

Devido aos problemas recentes identificados, relacionados principalmente a personalizações complexas de clientes, a equipe do [!DNL Target] ajustou a linha do tempo de desativação:

* **17 de junho de 2025**: todas as Organizações IMS foram habilitadas para a interface do usuário [!DNL Target] atualizada, para usuários específicos ou em toda a organização, para começar a testar a nova experiência.

* **30 de junho de 2025**: a [interface atualizada [!DNL Target] 4&rbrace; se tornou a experiência padrão para todas as organizações IMS que habilitaram a alternância de versão da interface do usuário.](/help/main/c-intro/understand-the-target-ui.md)

   * Os clientes que atualmente veem a interface herdada, por padrão, agora veem a interface atualizada ao fazer logon.
   * O botão de alternância da versão da interface do usuário permanece disponível até o final de julho, permitindo que os usuários alternem de volta, se necessário.

  >[!IMPORTANT]
  >
  > A [!DNL Adobe] recomenda o uso da interface atualizada do usuário do [!DNL Target]. Retorne à interface herdada somente se ocorrer um problema de bloqueador devido a [limitações do comportamento de alternância](#limitations).

* **15 de julho a 30 de julho de 2025**: o botão de alternância da versão da interface do usuário será desabilitado permanentemente em fases. As organizações IMS afetadas não podem mais reverter para a interface do usuário herdada.

   * As exceções são analisadas caso a caso.
   * Atrasos na desativação do botão de alternância são concedidos apenas brevemente (alguns dias), enquanto problemas de bloqueador são resolvidos.

Entre em contato com o [Atendimento ao cliente da Adobe](/help/main/cmp-resources-and-contact-information.md#/help/main/cmp-resources-and-contact-information.md) se tiver dúvidas ou se antecipar problemas durante essa transição.

#### Limitações do comportamento de alternância da interface {#limitations}

As informações a seguir descrevem as limitações que você deve conhecer ao optar por usar a opção de versão:

* **Visibilidade das novas atividades**: as atividades criadas na interface atualizada não estarão visíveis se você voltar para a interface herdada.
* **Editar atividades existentes**: as alterações feitas nas atividades existentes (originalmente criadas na interface herdada) ao usar a interface atualizada são publicadas no seu site. No entanto, essas atualizações não estarão visíveis na interface herdada se você voltar; somente as últimas atualizações feitas na interface herdada aparecerão lá.
* **Consistência dos detalhes da atividade**: as alterações mais recentes, independentemente da interface do usuário usada, são refletidas em seu site ativo. No entanto, a interface herdada mostra apenas as alterações mais recentes feitas nessa versão. Essa situação pode causar confusão se as atividades editadas na interface atualizada forem diferentes do que você vê na interface herdada.

#### Mais recursos para saber mais sobre a interface atualizada

* [[!DNL Target] Perguntas frequentes sobre atualização da interface do usuário](/help/main/c-intro/updated-ui-faq.md): estas perguntas frequentes abordam perguntas comuns sobre a nova interface do usuário do [!DNL Target] e do [!UICONTROL Visual Experience Composer] (VEC), incluindo alterações na navegação, locais de recursos e substituição da versão temporária da interface do usuário. Seja você um profissional de marketing, desenvolvedor ou administrador, essas Perguntas frequentes ajudarão a fazer a transição descomplicada e a aproveitar ao máximo a interface atualizada.
* Notas de versão do [[!DNL Target Standard/Premium] 25.2.1 (17 de fevereiro de 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2): fornece um resumo das principais alterações na interface do usuário do [!DNL Target] para [!UICONTROL Activities], [!UICONTROL Recommendations] e o [!UICONTROL Visual Experience Composer] (VEC).
* Notas de versão do [[!DNL Target Standard/Premium] 25.1.1 (9 de janeiro de 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1): fornece um resumo das principais alterações na interface do usuário do [!DNL Target] para o [!UICONTROL Offers Library].
* [Compreender a [!DNL Target] Interface](/help/main/c-intro/understand-the-target-ui.md): fornece uma breve visão geral para ajudá-lo a se familiarizar com o [!DNL Target] e fornece links para informações mais detalhadas e instruções passo a passo.
* [[!UICONTROL Visual Experience Composer] alterações](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): a versão [!DNL Adobe Target Standard/Premium] 25.2.1 (17 de fevereiro de 2015) introduz um [!UICONTROL Visual Experience Composer] (VEC) atualizado. Este artigo explica as diferenças entre as versões herdadas e atualizadas do VEC.
* [[!UICONTROL Visual Experience Composer] opções](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md): este artigo explica a interface do usuário do VEC atualizada e suas opções.

+++

## Atualizações de sequência de dados (19 de setembro de 2025)

A combinação da ID da sequência de dados e da sandbox deve ser exclusiva para [!DNL Adobe Target] conexões de destino.

Atualização da lógica de validação para conexões de destino [!DNL Target] para impor que a combinação da ID da sequência de dados e do nome da sandbox seja exclusiva em uma Organização IMS. Isso significa:

* O mesmo par de ID de fluxo de dados + nome de sandbox não pode ser reutilizado em várias conexões de destino [!DNL Target].
* A mesma ID de fluxo de dados pode ser usada para conexões diferentes somente se estiverem configuradas em sandboxes diferentes.
* Essa regra se aplica a todas as seleções de sequência de dados, incluindo quando &quot;Nenhum&quot; é selecionado.

Essa atualização garante uma configuração consistente e evita conflitos em ambientes de várias sandboxes. Para obter mais informações, consulte [conexão com o Adobe Target](https://experienceleague.adobe.com/pt-br/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection){target=_blank} no guia *Destinos do Experience Platform*.

## [!DNL Target Standard/Premium] 25.9.1 (5 de setembro de 2025)

Esta versão inclui as seguintes atualizações e correções:

**[!UICONTROL Experience Fragments]**

+++Ver detalhes
* **Atribuição de usuário aprimorada para [!UICONTROL AEM Experience Fragment] ofertas.** Solução de um problema no VEC em que o campo &quot;[!UICONTROL Last updated]&quot; de [!UICONTROL AEM Experience Fragment] (XF) oferece uma ID de Código exibida incorretamente em vez do nome de usuário. Essa discrepância ocorreu durante a seleção da oferta na interface atualizada, criando inconsistência com a interface herdada e as ofertas do HTML, que mostravam corretamente o nome do último editor. Essa correção garante uma atribuição consistente do usuário em todos os tipos de oferta, melhorando a transparência e o alinhamento com o comportamento esperado. (TGT-52880 e TGT-52898)

+++

**Offer Decisioning**

+++Ver detalhes
* **Erro do Offer Decision resolvido para ofertas ODE.** Correção de um problema em que as ofertas de Mecanismo do Offer Decision (ODE) inseridas por meio de [!DNL Target] retornavam um erro 400 devido à ausência de metadados de formato. A mensagem de erro indicou que o tipo MIME era nulo, impedindo o processamento bem-sucedido de decisões de oferta. Essa correção garante o manuseio adequado de metadados de oferta, restaurando a funcionalidade para a entrega de conteúdo personalizado e permitindo a execução ininterrupta de campanhas de marketing. (TGT-53635)
* **Problema de renderização de oferta ODS resolvido.** Solução de um problema em que as ofertas do [!DNL Offer Decision Service] (ODS) criadas via [!DNL Adobe Journey Optimizer] (AJO) não eram renderizadas quando as atividades eram compiladas usando o VEC na interface atualizada. A mesma configuração funcionava corretamente na interface herdada, gerando confusão e bloqueando a execução da campanha. Essa correção garante uma entrega de oferta consistente em ambas as versões da interface do usuário, restaurando o comportamento esperado para personalização orientada pela AJO.

+++

**Relatórios**

+++Ver detalhes
* **Opção de download restaurada na seção de relatórios da interface de visão geral de relatórios atualizada.** Correção de um problema na nova interface de visão geral em que o botão [!UICONTROL Download] não estava na seção Relatórios, impedindo que os usuários exportassem pontuações de importância do atributo. Essa atualização restaura a funcionalidade completa de exportação, permitindo o acesso simplificado a dados para download para análise e relatórios. (TGT-53222)
* Botão **[!UICONTROL Download full CSV report]restaurado na exibição [!UICONTROL Important attributes].** Solução de um problema na interface de criação de atividade atualizada em que o botão [!UICONTROL Download full CSV report] estava ausente da seção [!UICONTROL Important Attributes] no modo de exibição de relatórios. Essa correção restaura o acesso a insights baixáveis, garantindo uma funcionalidade consistente nas interfaces atualizadas e herdadas. (TGT-53238)
* **Solução de problemas de interface do usuário que afetam os relatórios do [!UICONTROL Auto Target] na interface do usuário de visão geral atualizada.** Correção de vários problemas de interface do usuário na interface de visão geral atualizada que afetavam o relatório de atividades [!UICONTROL Auto Target]. Essas correções incluem:

   * Métricas de aumento e confiança ausentes nos relatórios de resumo
   * Indicador de cor incorreto para a caixa de seleção &quot;modelos criados&quot;
   * Relatório de gráfico não funcional apesar da variação de dados em [!DNL Analytics]
   * Link de download ausente para os relatórios [!UICONTROL Automated Segments] e [!UICONTROL Important Attributes]
   * Exibição do relatório [!UICONTROL Automated Segments] interrompida

  Essas correções restauram o comportamento esperado dos relatórios e melhoram a visibilidade do desempenho do [!UICONTROL Auto Target] na interface atualizada. (TGT-53484)

+++

**[!UICONTROL Visual Experience Composer]**

+++Ver detalhes
* **Validação de formulário corrigida para condições de presença de parâmetro na interface atualizada.** Correção de um problema na interface do usuário atualizada em que selecionar &quot;[!UICONTROL Custom mbox parameter value is present]&quot; ou &quot;[!UICONTROL Parameter is present]&quot; exigia incorretamente que os clientes inserissem um valor. Esse comportamento entrou em conflito com a lógica pretendida, que simplesmente verifica a existência de um parâmetro independentemente de seu valor. A correção alinha a validação do formulário ao comportamento esperado, permitindo uma configuração de atividade mais suave e a adoção total da interface atualizada. (TGT-53638)
* **Lógica de formulário corrigida para regras de presença de parâmetro na entrega da página.&quot;** Correção de um problema na interface do usuário atualizada em que a seleção de regras de entrega de página, como &quot;[!UICONTROL Parameter is present]&quot;, &quot;[!UICONTROL Parameter is not present],&quot;[!UICONTROL Parameter value is present]&quot; ou &quot;[!UICONTROL Parameter value is not present]&quot;, exigia incorretamente que os usuários inserissem um valor de parâmetro adicional. Esse comportamento era inconsistente com a interface herdada e contradizia a lógica pretendida de detectar a presença de parâmetros sem especificar um valor. Essa correção restaura o comportamento esperado de configuração da regra, simplificando a configuração da atividade e melhorando a usabilidade. (TGT-53640)
* **Lógica de validação aprimorada para o construtor de regras de várias páginas na interface atualizada.** Solução de vários problemas de validação no construtor de regras de várias páginas na interface atualizada. Essas correções incluem:

   * Como impedir a criação de regras quando o parâmetro da mbox está vazio
   * Exibição de mensagens de erro apropriadas para estados de regras inválidas
   * Correção da lógica de validação para operadores unários e baseados em parâmetros que não exigem valores de operando
   * Ativar regras de fragmento de hash com operadores unários restaurando a funcionalidade de salvar

  Essas atualizações garantem uma configuração de regra precisa e melhoram a usabilidade em cenários complexos de entrega de página. (TGT-53722)
* **Problema de renomeação de local resolvido em atividades A/B e MVT.** Correção de um bug na interface do usuário atualizada em que a renomeação de um local em uma atividade [!UICONTROL A/B Test] ou [!UICONTROL Multivariate Test] (MVT) não persistia após a navegação entre a lista de locais, o direcionamento e a versão posterior. Essa atualização garante que as alterações no nome da localização sejam salvas e refletidas de forma consistente em todo o fluxo de trabalho da atividade. (TGT-52367)
* **Persistência do nome do local corrigida para atividades MVT e AP na interface atualizada.** Correção de um problema na interface do usuário atualizada em que os nomes de locais editados nas atividades [!UICONTROL Multivariate Test] (MVT) e [!UICONTROL Automated Personalization] (AP) não eram salvos corretamente. Após renomear um local, a navegação entre guias, como [!UICONTROL Targeting] e [!UICONTROL Experiences], fez com que os nomes fossem revertidos para seu estado anterior. Essa correção garante uma nomenclatura de localização consistente entre guias e melhora a confiabilidade durante a configuração da atividade. (TGT-52927)
* **O rótulo de local foi corrigido no painel Gerenciar experiências para atividades MVT.** Correção de um problema na interface do usuário atualizada em que o painel [!UICONTROL Manage Experiences] nas atividades [!UICONTROL Multivariate Test] (MVT) exibia uma numeração de local inconsistente. Essa correção garante que os rótulos de localização sejam sequenciais e alinhados corretamente com as modificações definidas pelo usuário, melhorando a clareza e a usabilidade durante a configuração da experiência. (TGT-52929)

+++

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da plataforma. |
| [Detalhes da versão da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Alterações na documentação, notas de versão anteriores e notas de versão da Experience Cloud

Além das notas para cada versão, os recursos a seguir oferecem informações adicionais:

| Recurso | Detalhes |
|--- |--- |
| [Alterações de documentação](/help/main/r-release-notes/doc-change.md) | Veja informações detalhadas sobre atualizações neste manual que podem não estar incluídas nas notas de versão. |
| [Notas de versões anteriores](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Veja informações sobre os novos recursos e aprimoramentos das versões anteriores do Target Standard e do Target Premium. |
| [Notas de versão do Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR){target=_blank} | Veja as notas de versão mais recentes das soluções da Adobe Experience Cloud. |

## Informações de pré-lançamento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Os recursos a seguir permitem ver as novidades previstas para a próxima versão do Target.

| Recurso | Detalhes |
|--- |--- |
| [Atualização de produtos prioritários da Adobe](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Receba notificações antecipadas sobre futuros aprimoramentos de produtos para o [!DNL Target] e outras soluções da [!DNL Adobe Experience Cloud]. |
| [Notas de versão do Target - Pré-lançamento](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Informações sobre os lançamentos do Target no mês atual, incluindo informações de pré-lançamento. |
