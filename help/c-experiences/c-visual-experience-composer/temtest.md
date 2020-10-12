---
keywords: template testing;template;same experience on similar pages;template test
description: Use um modelo de página no Adobe Target para fornecer estrutura para suas páginas, ou se suas páginas contêm elementos semelhantes, para testar variações em elementos de página estruturados de forma semelhante.
title: Inclua a mesma experiência em páginas semelhantes usando o Adobe Target
feature: experiences
uuid: 055b276e-2492-40d8-b48e-849dffa93f35
translation-type: tm+mt
source-git-commit: bd13fee3a0a2ef675d121a9832583c3aa125865d
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 45%

---


# Incluir a mesma experiência em páginas semelhantes

Use um modelo de página em [!DNL Adobe Target] para fornecer estrutura para suas páginas, ou se suas páginas contêm elementos semelhantes, para testar variações em elementos de página estruturados de forma semelhante ou em todo o seu domínio.

Para funcionar corretamente, esse recurso deve ser usado em páginas que tenham uma estrutura semelhante ou que contenham elementos de modelo que estejam estruturados da mesma forma em todas as páginas.

>[!IMPORTANT]
>
>O uso desse recurso para alterar os elementos em páginas diferentes provavelmente causará resultados inesperados.

Por exemplo, você pode usar esse recurso para fazer uma das seguintes opções:

* Testar uma barra de navegação global, reorganizando ou removendo elementos
* Remover um item de todas as páginas de produtos que usam um modelo de página específico
* Adicionar um banner em todas as páginas de produtos
* Alterar o layout do modelo de artigo

Você pode especificar páginas que incluem os elementos de alteração ou aplicar a alteração em seu site ou domínio.

1. Create  or edit an activity as described in [Activities](../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. To specify the pages where the experience will appear, in the [!UICONTROL Visual Experience Composer] (VEC) click the gear icon, then select **[!UICONTROL Page Delivery]**.

   ![Ícone de engrenagem > Delivery de página](/help/c-experiences/c-visual-experience-composer/assets/icon-gear.png)

1. Clique em **[!UICONTROL Adicionar regra de modelo]** e especifique os critérios para as páginas nas quais deseja adicionar a experiência.

1. Especifique o intervalo de páginas. O intervalo de páginas pode ser um dos seguintes:

   * URL (Para obter mais informações sobre como o Público alvo avalia URLs, consulte Perguntas frequentes sobre [Públicos alvos e audiências](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
   * Domínio
   * Caminho
   * Fragmento de hash (#) (público alvo a parte de um URL que segue o símbolo #).
   * Consulta
   * Parâmetro

1. Escolha um operador.

   O operador especifica a forma como os itens se relacionam com o intervalo de páginas. Os operadores disponíveis incluem:

   * Contém
   * Não contém
   * É (diferencia maiúsculas de minúsculas)
   * Não é
   * Começa com
   * Termina com

1. Digite as sequências de caracteres que definem onde é adicionada a experiência, como o domínio ou as sequências de caracteres contidas no nome da página.

   Por exemplo, se você selecionar **[!UICONTROL Domínio]** e **[!UICONTROL É (diferencia maiúsculas de minúsculas)]**, digite o domínio em que deseja adicionar a experiência para todas as páginas.

   É possível incluir vários itens.

   >[!IMPORTANT]
   >
   >Vários itens usam a lógica OU, o que significa que qualquer item na lista torna a condição verdadeira.

1. If desired, enter additional criteria by clicking **[!UICONTROL Add Template Rule]** and repeating the procedure in the previous steps.

   Múltiplos critérios são agrupados com uma lógica E. [!DNL Target]O adiciona a experiência para todas as páginas que correspondem aos critérios especificados.

>[!IMPORTANT]
>
> [!DNL Target]O não pode verificar as páginas para se certificar de que elas são exibidas conforme o esperado, por isso é sempre uma prática importante ao usar esse recurso testar as páginas afetadas antes de torná-las públicas.

## Casos de uso

Analise os seguintes casos de uso para saber como usar regras de modelo em seu site:

### Renderizar a mesma atividade em todo o domínio

Você pode considerar o uso de regras de modelo para renderizar a mesma atividade em todo o seu domínio para os seguintes casos de uso:

* Para incluir um cabeçalho ou rodapé global
* Para incluir um banner global (por exemplo, anúncios COVID-19)
* Para incluir uma promoção global de entrega livre

1. Create or edit an activity as described in [Activities](../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. To specify the domain where the experience will appear, in the Visual Experience Composer click the gear icon, then select **[!UICONTROL Page Delivery]**.

1. Clique em **[!UICONTROL Adicionar regra]** de modelo > **[!UICONTROL Domínio]**.

1. Na lista suspensa **[!UICONTROL Escolher avaliador]** , selecione **[!UICONTROL Contém]** e especifique o domínio.

   ![O domínio contém](/help/c-experiences/c-visual-experience-composer/assets/domain-template-rule.png)

## Training video: Visual Experience Composer (2 of 2) (7:29) ![Tutorial badge](/help/assets/tutorial.png)

* Renomear e duplicar uma experiência
* Criar uma experiência de redirecionamento
* Direcionar uma atividade para um único URL ou um grupo de URLs
* Criar uma atividade multipáginas
* Visualizar e criar a experiência para sites responsivos
* Use sobreposições para destacar tipos de elementos

>[!VIDEO](https://video.tv.adobe.com/v/17401)