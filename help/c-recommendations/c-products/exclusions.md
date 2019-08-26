---
description: Criar uma lista de exclusão para impedir que itens sejam recomendados.
keywords: exclusões
seo-description: Crie uma lista de exclusão no Adobe Target para impedir que itens sejam recomendados.
seo-title: Exclusões no Adobe Target
solution: Target
title: Exclusões
topic: Premium
uuid: 1970846e-37d8-4b69-a0d9-ff45bb840bef
translation-type: tm+mt
source-git-commit: 12953606c44d4545e5f9a65e6473fc172bb9ca73

---


# Exclusões{#exclusions}

Criar uma lista de exclusão para impedir que itens sejam recomendados.

>[!IMPORTANT]
>
>As regras de exclusão estáticas e dinâmicas são recursos poderosos que podem ajudá-lo com seus esforços de marketing. Para obter informações detalhadas, exemplos e cenários de caso de uso, consulte [Usar as regras de inclusão estática e dinâmica](../../c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

**Para criar uma exclusão:**

1. Clique em **[!UICONTROL Recommendations]** &gt; **[!UICONTROL Exclusões]** para exibir a lista de exclusões existentes.

   ![](assets/exclusions_list.png)

   O “Número de itens” relatado para cada exclusão na exibição de lista das [!UICONTROL Exclusões] é o número de produtos que correspondem às regras da exclusão no [grupo de hosts](/help/administrating-target/hosts.md) (ambiente) padrão configurado no Recommendations. Consulte [Configurações](../../c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84) para alterar o grupo de hosts padrão.

1. Clique em **[!UICONTROL Criar exclusão]**.

1. (Condicional) Escolha um ambiente no filtro **[!UICONTROL Ambiente]** ao criar (ou atualizar) uma exclusão para visualizar o conteúdo da exclusão no ambiente. Por padrão, os resultados do grupo de hosts padrão são exibidos.

   ![Criar exclusão](/help/c-recommendations/c-products/assets/CreateExclusion.png)

1. Digite um **[!UICONTROL Nome]** de exclusão e insira uma descrição opcional.

1. Use o criador de regras para criar suas exclusões.

   Selecione um parâmetro na lista Regras, selecione um operador e, em seguida, insira um ou mais valores para identificar os produtos. Separe vários valores com vírgulas.

1. Clique em **[!UICONTROL Salvar]**.

## Criar uma exclusão usando a Pesquisa avançada

Você também pode criar exclusões usando Pesquisa avançada na página Pesquisa no catálogo ([!UICONTROL Recommendations] &gt; [!UICONTROL Pesquisa no catálogo] &gt; [!UICONTROL Pesquisa avançada]).

[Salvar como](/help/c-recommendations/c-products/assets/save-as.png)

Após criar uma pesquisa usando "id &gt; contains" Por exemplo, você pode clicar em [!UICONTROL Salvar como] &gt; [!UICONTROL Exclusão]. Para obter mais informações, consulte [Pesquisa de catálogo](/help/c-recommendations/c-products/catalog-search.md).

>[!IMPORTANT]
>
>A funcionalidade de Pesquisa avançada não faz distinção entre maiúsculas e minúsculas; contudo, os produtos devolvidos no momento da entrega baseiam-se na pesquisa sensível a maiúsculas e minúsculas. Essa não correspondência pode levar à confusão. Certifique-se de considerar a sensibilidade a maiúsculas e minúsculas quando você cria exclusões baseadas em resultados usando a funcionalidade Pesquisa avançada. Por exemplo, se você realiza uma busca para "Feriado", essa busca inicial lista os resultados contendo "Feriado" e "feriado". Em seguida, se você criar uma exclusão com a intenção de excluir produtos contendo "feriado", somente os produtos contendo "feriado" são excluídos. Os produtos contendo "Feriado" não são excluídos.

## Vídeo de treinamento: Criar coleções e exclusões no Recommendations (7:05)

Este vídeo contém as seguintes informações:

* Criar uma coleção
* Criar uma exclusão

>[!VIDEO](https://video.tv.adobe.com/v/27689?captions=por_br)