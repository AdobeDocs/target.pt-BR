---
description: Se você usar um modelo de página para oferecer estrutura para as páginas, ou se as páginas contiverem elementos semelhantes, esse recurso possibilitará o teste de variações em elementos de página estruturadas de forma semelhante.
keywords: teste de modelo, modelo, mesma experiência em páginas semelhantes, teste de modelo
seo-description: Se você usar um modelo de página para oferecer estrutura para as páginas, ou se as páginas contiverem elementos semelhantes, esse recurso possibilitará o teste de variações em elementos de página estruturadas de forma semelhante.
seo-title: Incluir a mesma experiência em páginas semelhantes
solution: Target
title: Incluir a mesma experiência em páginas semelhantes
topic: Premium
uuid: 055b276e-2492-40d8-b48e-849dffa93f35
translation-type: tm+mt
source-git-commit: df79860eacc680351c6b3bdf0570b76543492570

---


# Incluir a mesma experiência em páginas semelhantes{#include-the-same-experience-on-similar-pages}

Se você usar um modelo de página para oferecer estrutura para as páginas, ou se as páginas contiverem elementos semelhantes, esse recurso possibilitará o teste de variações em elementos de página estruturadas de forma semelhante.

Para funcionar corretamente, esse recurso deve ser usado em páginas que têm uma estrutura muito semelhante. ou conter elementos de modelo que estão estruturados da mesma forma em todas as páginas.

>[!IMPORTANT]
>
>O uso desse recurso para alterar os elementos em páginas diferentes provavelmente causará resultados inesperados.

Por exemplo, você pode usar esse recurso para fazer uma das seguintes opções:

* Testar uma barra de navegação global, reorganizando ou removendo elementos
* Remover um item de todas as páginas de produtos que usam um modelo de página específico
* Adicionar um banner em todas as páginas de produtos
* Alterar o layout do modelo de artigo

O vídeo de demonstração a seguir inclui informações sobre usar um modelo:

Você pode especificar páginas que incluem os elementos de alteração ou aplicar a alteração através do site.

1. Crie uma atividade conforme descrito em [Atividades](../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).
1. Para especificar as páginas em que a experiência será exibida, no Visual Experience Composer clique no ícone de engrenagem e selecione **[!UICONTROL Entrega de página]**.
1. Clique **[!UICONTROL em Adicionar regra]** de modelo e especifique os critérios das páginas às quais deseja adicionar a experiência.

1. Especifique o intervalo de páginas. O intervalo de páginas pode ser um dos seguintes:

   * URL
   * Domínio
   * Caminho
   * Fragmento de hash (#) (Defina a parte de um URL que segue o símbolo #)
   * Consulta
   * Parâmetro

1. Escolha um operador.

   O operador especifica a forma como os itens se relacionam com o intervalo de páginas. Os operadores disponíveis são:

   * Contém
   * Não contém
   * É (diferencia maiúsculas de minúsculas)
   * Não é
   * Começa com
   * Termina com

1. Digite as sequências de caracteres que definem onde é adicionada a experiência, como o domínio ou as sequências de caracteres contidas no nome da página.

   Por exemplo, se você selecionar **[!UICONTROL Domínio]** e **[!UICONTROL É (diferencia maiúsculas de minúsculas)]**, digite o domínio onde deseja que a experiência seja adicionada a todas as páginas.

   É possível incluir vários itens.

   >[!IMPORTANT]
   >
   >Vários itens usam a lógica `OR`, ou seja, qualquer item único na lista torna a condição verdadeira.

1. Se desejar, insira critérios adicionais clicando **[!UICONTROL em Adicionar regra]** de modelo e repita o procedimento na etapa anterior.

   Múltiplos critérios são agrupados com uma lógica E. O Adobe Target adiciona a experiência para todas as páginas que correspondem aos critérios especificados.

>[!IMPORTANT]
>
> O Target não pode verificar as páginas para se certificar de que elas são exibidas conforme o esperado, por isso é sempre uma prática importante ao usar esse recurso testar as páginas afetadas antes de torná-las públicas.

## Vídeo de treinamento: Visual Experience Composer (2 de 2) (7:29)

* Renomear e duplicar uma experiência
* Criar uma experiência de redirecionamento
* Direcionar uma atividade para um único URL ou um grupo de URLs
* Criar uma atividade multipáginas
* Visualizar e criar a experiência para sites responsivos
* Use sobreposições para destacar tipos de elementos

>[!VIDEO](https://video.tv.adobe.com/v/17401)