---
keywords: Click tracking;track clicks;clicks;AppMeasurement
description: O Target permite monitorar os cliques em um elemento como uma métrica de sucesso.
title: Rastreamento de cliques
feature: null
subtopic: Getting Started
topic: Standard
uuid: 4a8fbb23-93d8-49f3-aca3-dbbdd6da0178
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 97%

---


# Rastreamento de cliques{#click-tracking}

O Target permite monitorar os cliques em um elemento como uma métrica de sucesso.

>[!NOTE]
>
>O rastreamento de cliques não é suportado na solicitação de Público alvo global quando é usado como um local em uma atividade baseada em formulário.

## Configuração do rastreamento de cliques {#section_5540C5A533114E57BAE022A600B02E72}

1. Ao definir suas metas na página [!UICONTROL Metas e configurações] para a atividade, selecione a métrica de sucesso de **[!UICONTROL Conversão]**.
1. Para ação, selecione **[!UICONTROL Clicou em um elemento]** e clique em **[!UICONTROL Selecionar elementos]**.

   A página é aberta no [!UICONTROL Visual Experience Composer] (VEC).

1. Selecione os elementos que deseja rastrear.

   Consulte a seção Considerações abaixo para obter dicas sobre como selecionar elementos.

1. Clique na marca de seleção na parte superior da tela para salvar suas seleções.

Quando um participante da atividade clica em um elemento selecionado, esse clique é contado como uma conversão.

## Painel Elementos selecionados {#selected-elements}

Para atividades Teste A/B, de Experiência de direcionamento (XT), Personalização automatizada (AP) e Teste multivariado (MVT), um painel [!UICONTROL Elementos selecionados] lista todos os elementos selecionados para o rastreamento de cliques no lado direito.

Painel ![Elementos selecionados](/help/c-activities/r-success-metrics/assets/selected-elements.png)

Há várias ações que podem ser aplicadas quando você passa o mouse sobre um elemento no painel [!UICONTROL Elementos selecionados]. A tabela a seguir descreve cada ação que pode ser executada em um elemento:

| Ação | Descrição |
| --- | --- |
| Informações | Exibe o tipo de elemento e o caminho DOM completo para o seletor. |
| Editar | Permite editar o seletor de CSS. |
| Excluir | Exclui o elemento. |

### Adicionar elemento

Se já conhece o caminho DOM para o seletor, você pode adicioná-lo manualmente ao clicar no ícone de adição localizado na parte superior do painel.

![Ícone Adicionar elemento](/help/c-activities/r-success-metrics/assets/add-element.png)

### Pop-up de passagem do mouse de elementos selecionados

Depois de selecionar vários elementos para o rastreamento de cliques, você pode clicar no link [!UICONTROL Elementos selecionados] na etapa [!UICONTROL Metas e configurações] da atividade para ver a lista completa de elementos selecionados para rastreamento de cliques. A lista contém o caminho DOM completo para o elemento, para ajudar a validar se o elemento selecionado deve ser usado para o rastreamento de cliques.

![Link Elementos Selecionados](/help/c-activities/r-success-metrics/assets/elements-selected-link.png)

## Considerações {#considerations}

Há várias coisas a considerar ao selecionar elementos:

* O recurso de caminho DOM está disponível ao configurar o rastreamento de cliques. Ao clicar em um elemento na página, o menu de opções de VEC é exibido. Além disso, o caminho DOM correspondente é exibido na parte inferior da página. Você pode usar o caminho DOM para ver rapidamente as informações sobre o elemento selecionado (tipo, ID e classe) e mover para cima ou para baixo o caminho DOM para selecionar o elemento desejado.

   ![Ilustração do caminho DOM](/help/c-activities/r-success-metrics/assets/click-tracking-dom.png)

   Assim como na Etapa 1, ao criar experiências no fluxo de trabalho de criação da atividade, o seletor de caminho DOM, na parte inferior da página, permite escolher um elemento. Ao selecionar um elemento do caminho DOM, o elemento correspondente no VEC será exibido como &quot;Selecionado&quot;. Para desmarcar um elemento selecionado, clique novamente no elemento do seletor de caminho DOM ou na caixa &quot;Selecionado&quot; do VEC.

   Para obter mais informações, consulte [Navegar pelos elementos usando o caminho DOM](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) nas *Opções do Visual Experience Composer*.

* É possível navegar para uma página diferente para rastrear cliques em uma página em que talvez você não esteja alterando o conteúdo. Esta página diferente deve ser incluída na atividade usando o  [recurso multipágina](../../c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48) e [!DNL at.js] ou [!DNL mbox.js] devem ser implementadas nela.
* Se selecionar mais de um elemento, caso um participante clique em um dos elementos escolhidos, o clique será contado. Para contar cada item separadamente, configure métricas de sucesso individuais para cada elemento.
* Certifique-se de selecionar o nível do elemento que deseja rastrear. Por exemplo, ao especificar um botão, certifique-se de selecionar o link e não o texto do botão.
* Os eventos de clique são enviados para o [!DNL Target] na mesma página de destino do clique.
* Se a métrica de rastreamento de cliques for a métrica de meta de uma atividade do A4T, o visitante deverá clicar nesse elemento dentro de 60 segundos do carregamento da página para que a métrica seja rastreada.
* O rastreamento de cliques não funciona em elementos que incluem caracteres ignorados em seus seletores, incluindo os seguintes:

   | Caractere | Descrição |
   |---|---|
   | # | Sinal numérico  ou hash |
   | : | Dois-pontos |
   | . | Ponto |
   | $ | Símbolo de moeda |
   | `[ ]` | Colchetes |

* Se usar o rastreamento de cliques [!DNL at.js] e também o Analytics AppMeasurement, o rastreamento de cliques [!DNL at.js] cancelará todos os outros manipuladores de eventos de clique. Como resultado, o manipulador de cliques do AppMeasurement nunca é executado.

   [!DNL at.js] tem um processamento especial para o rastreamento de cliques quando o elemento subjacente é uma tag `A`A (link) ou `FORM`.

   As seguintes etapas são executadas pela [!DNL at.js] quando o evento de rastreamento de cliques é adicionado uma tag `A`A (link) ou `FORM`:

   1. Chame `event.preventDefault()`.

   1. Acione a solicitação do Target.

   1. Na chamada de retorno de sucesso ou erro da solicitação do Target, execute o comportamento padrão:

      * Tag `A` (link): o comportamento padrão é navegar até o URL definido pela atributo HREF.
      * Tag `FORM`: o comportamento padrão é enviar o formulário.

   Este comportamento padrão pode interferir no rastreamento de cliques do Analytics. Se estiver usando o Analytics, deverá confiar nele para o rastreamento de cliques em vez do Target.

* O rastreamento de cliques não é registrado quando a página e o URL da atividade pertencerem a propriedades diferentes. As permissões de usuário do Enterprise são um recurso do Target Premium. Para obter mais informações, consulte [Permissões de usuário do Enterprise](/help/administrating-target/c-user-management/property-channel/property-channel.md).

## Vídeo de Treinamento {#section_36607204DAE146E3B8E2C609D244EDB1}

Este vídeo inclui informações sobre a criação de métricas de sucesso de rastreamento de cliques.

* Compreender métricas de &quot;meta&quot;
* Entender e construir métricas de conversão, receita e envolvimento
* Criar uma métrica de rastreamento de cliques

>[!VIDEO](https://video.tv.adobe.com/v/17380)