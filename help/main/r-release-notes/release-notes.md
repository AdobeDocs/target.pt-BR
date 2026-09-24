---
keywords: notas de versão;novos recursos;versões;atualizações;atualizar;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações;atualizações atuais;release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates;current updates
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do [!DNL Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
TQID: https://experienceleague.adobe.com/-Unx6cVsw3wch2LJgPtvBYPe-10rdpiJ4v9F7tMSP08
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 4d083419d76b0287c3c254a0fc382abc7444cc75
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 32%
---
# Notas de versão do [!DNL Target] (atuais)

Explore os recursos, aprimoramentos e correções mais recentes no [!DNL Adobe Target]. Essas notas de versão também abrangem atualizações para APIs do [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outros componentes da plataforma, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## [!DNL Target Standard/Premium] 26.9.6 (24 de setembro de 2026)

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Ver detalhes

* **Loop de redirecionamento infinito ao acessar uma página autenticada por SSO por meio do Visual Experience Composer**. Quando um URL de página carregado no Visual Experience Composer passou por um fluxo de redirecionamento de SSO/logon, o Visual Experience Composer inseriu um loop de redirecionamento infinito e nunca chegou à página desejada. (TGT-56233)

+++

## [!DNL Target Standard/Premium] 26.9.5 (21 de setembro de 2026)

### Recurso

<table>
<thead>
<tr>
<th><strong>Pré-ocultação de conteúdo</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>A pré-ocultação de conteúdo ajuda a reduzir a cintilação da página, ocultando apenas as seções que a personalização do Adobe Target está prestes a alterar, fornecendo uma experiência mais suave enquanto o conteúdo é carregado. Essa abordagem evita ocultar a página inteira e ajuda a minimizar o esforço de implementação quando novas atividades são iniciadas.</p>
<p>Anteriormente lançado com disponibilidade limitada, esse recurso agora está disponível para todos os ambientes (disponibilidade geral).</p>
<p>Para obter mais informações, consulte a <a href="../administrating-target/content-pre-hiding.md">documentação detalhada</a>.</p>
</td>
</tr>
</tbody>
</table>

### Melhorias

**[!UICONTROL Análises para Destino]**

+++Ver detalhes

* **Link de relatório do A4T não gerado na [!DNL Target] interface**. Para atividades de [!DNL A4T], o link do relatório não foi gerado na seção **[!UICONTROL Relatórios]**, mesmo que os dados subjacentes do relatório estivessem visíveis na interface do usuário do [!DNL Target] e na interface do usuário do [!DNL Adobe Analytics]. (TGT-56247)

+++

## [!DNL Target Standard/Premium] 26.9.4 (17 de setembro de 2026)

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Ver detalhes

* O controle **[!UICONTROL Inserir Antes de] está inacessível para [!DNL Experience Fragments] no elemento de página mais alto**. No Visual Experience Composer, selecionar o elemento mais alto em uma página rolou a página para cima, fazendo com que o controle **[!UICONTROL Inserir antes]** renderize acima do visor visível, onde não pôde ser selecionado. (TGT-55829)

+++

## [!DNL Target Standard/Premium] 26.9.3 (16 de setembro de 2026)

**[!UICONTROL Relatório]**

+++Ver detalhes

* **Valores de [!UICONTROL Lift] e [!UICONTROL Confidence] ausentes em alguns [!DNL A4T Auto-Target] relatórios**. Para atividades do [!DNL A4T Auto-Target] usando a meta de otimização **[!UICONTROL Maximizar Taxa de Conversão de Visitas]**, a métrica de relatório padrão **[!UICONTROL Minha Métrica Primária]** não foi resolvida corretamente, deixando o **[!UICONTROL Aumento]** e a **[!UICONTROL Confiança]** em branco. (TGT-56137)

+++

**[!UICONTROL Análises para Destino]**

+++Ver detalhes

* O campo **[!UICONTROL Source de relatórios] agora é somente leitura para atividades online sem acesso de [!DNL Analytics]**. Anteriormente, quando o proprietário de uma atividade ao vivo não tinha acesso a [!DNL Adobe Analytics], o campo **[!UICONTROL Source de relatórios]** e seu campo relacionado permaneciam editáveis. (TGT-56089)

+++

## [!DNL Target Standard/Premium] 26.9.2 (8 de setembro de 2026)


**[!UICONTROL Recomendações]**

+++Ver detalhes

* **[!DNL New]a interface codifica incorretamente as URLs de feed**. Ao criar um feed do Recommendations a partir de uma URL na nova interface do [!DNL Target], a URL do feed era codificada incorretamente, causando falha na criação do feed com um erro desconhecido. (TGT-56084)

+++

**[!UICONTROL Relatório]**

+++Ver detalhes

* **O relatório de Segmentos automatizados não exibe de forma consistente os valores de atributo**. O relatório de Segmentos automatizados exibia de forma inconsistente valores e intervalos de atributos para atividades de [!DNL Automated Personalization] e [!DNL Auto-Target]. Alguns segmentos automatizados mostravam apenas o nome do atributo em vez do valor ou intervalo associado. (TGT-55855)

+++

## [!DNL Target Standard/Premium] 26.9.1 (1º de setembro de 2026)

**[!UICONTROL Público-alvo]**

+++Ver detalhes

* **Falha ao salvar** a cópia de uma atividade com um público somente atividade. Quando uma atividade A/B usa uma regra de público-alvo somente atividade (com escopo local) e uma modificação de Código personalizado, copiá-la e salvar a cópia falha com um erro &quot;IDs de público-alvo inválidas&quot;. (TGT-55785)

+++

Servidor MCP **[!DNL Adobe Target]— Ferramentas do Recommendations (Beta público)**

+++Ver detalhes

O servidor MCP do [!DNL Adobe Target] agora expõe as ferramentas do Recommendations, permitindo listar, inspecionar, criar e atualizar critérios, coleções, designs, promoções e exclusões e pesquisar o catálogo de produtos diretamente no assistente de IA.

Este recurso requer um locatário habilitado para o Recommendations com o **Target Premium**; ele não está disponível em contas que não sejam Premium.

Para obter mais informações, consulte [Referência de ferramentas do servidor MCP](../c-integrating-target-with-mac/mcp/target-mcp-tools-reference.md).

+++

## Atualizações sensíveis ao tempo que você precisa saber {#time-sensitive}

[!BADGE Importante]{type=Informative}

Para atualizações com limite de tempo relacionadas ao [!DNL Adobe Target] e à sua implementação, o [!DNL Adobe] fornece notas de versão e documentação detalhadas por meio do [!UICONTROL Experience League]. Estes são alguns destaques importantes para sua implementação:

### Desativação da alternância de versão da interface do usuário [!DNL Target]

Para obter mais informações, consulte [[!DNL Target] Perguntas frequentes sobre atualização da interface](/help/main/c-intro/updated-ui-faq.md).

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
| [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR){target=_blank} | Veja as notas de versão mais recentes das soluções da Adobe Experience Cloud. |

## Informações de pré-lançamento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Os recursos a seguir permitem ver as novidades previstas para a próxima versão do Target.

| Recurso | Detalhes |
|--- |--- |
| [Atualização de produtos prioritários da Adobe](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Receba notificações antecipadas sobre futuros aprimoramentos de produtos para o [!DNL Target] e outras soluções da [!DNL Adobe Experience Cloud]. |
| [Notas de versão do Target - Pré-lançamento](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Informações sobre os lançamentos do Target no mês atual, incluindo informações de pré-lançamento. |
