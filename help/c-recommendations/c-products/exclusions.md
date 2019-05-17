---
description: Criar uma lista de exclusão para impedir que itens sejam recomendados.
keywords: exclusões
seo-description: Criar uma lista de exclusão para impedir que itens sejam recomendados.
seo-title: Exclusões
solution: Target
title: Exclusões
topic: Premium
uuid: 1970846e-37d8-4b69-a0d9-ff45bb840bef
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Exclusões{#exclusions}

Criar uma lista de exclusão para impedir que itens sejam recomendados.

>[!IMPORTANT]
>
>As regras de exclusão estáticas e dinâmicas são recursos poderosos que podem ajudá-lo com seus esforços de marketing. Para obter informações detalhadas, exemplos e cenários de caso de uso, consulte [Usar as regras de inclusão estática e dinâmica](../../c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

1. Clique em **[!UICONTROL Recommendations]** &gt; **[!UICONTROL Exclusões]** para exibir a lista de exclusões existentes.

   O “Número de itens” relatado para cada exclusão na exibição de lista das [!UICONTROL Exclusões] é o número de produtos que correspondem às regras da exclusão no [grupo de hosts](/help/administrating-target/hosts.md) (ambiente) padrão configurado no Recommendations. Consulte [Configurações](../../c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84) para alterar o grupo de hosts padrão.

   ![](assets/exclusions_list.png)

1. Clique em **[!UICONTROL Criar exclusão]**.

1. (Condicional) Escolha um ambiente no filtro **[!UICONTROL Ambiente]** ao criar (ou atualizar) uma exclusão para visualizar o conteúdo da exclusão no ambiente. Por padrão, os resultados do grupo de hosts padrão são exibidos.

   ![Criar exclusão](/help/c-recommendations/c-products/assets/CreateExclusion.png)

1. Digite um **[!UICONTROL Nome]** de exclusão e insira uma descrição opcional.

1. Use o criador de regras para criar suas exclusões.

   Selecione um parâmetro na lista Regras, selecione um operador e, em seguida, insira um ou mais valores para identificar os produtos. Separe vários valores com vírgulas.

1. Clique em **[!UICONTROL Salvar]**.

   Você também pode criar exclusões usando Pesquisa avançada na página Pesquisa no catálogo ([!UICONTROL Recommendations] &gt; [!UICONTROL Pesquisa no catálogo] &gt; [!UICONTROL Pesquisa avançada]). Após criar uma pesquisa usando &quot;id &gt; contains&quot; Por exemplo, você pode clicar em [!UICONTROL Salvar como] &gt; [!UICONTROL Exclusão].

>[!IMPORTANT]
>
>A funcionalidade de Pesquisa avançada não faz distinção entre maiúsculas e minúsculas; contudo, os produtos devolvidos no momento da entrega baseiam-se na pesquisa sensível a maiúsculas e minúsculas. Essa não correspondência pode levar à confusão. Certifique-se de considerar a sensibilidade a maiúsculas e minúsculas quando você cria exclusões baseadas em resultados usando a funcionalidade Pesquisa avançada. Por exemplo, se você realiza uma busca para &quot;Feriado&quot;, essa busca inicial lista os resultados contendo &quot;Feriado&quot; e &quot;feriado&quot;. Em seguida, se você criar uma exclusão com a intenção de excluir produtos contendo &quot;feriado&quot;, somente os produtos contendo &quot;feriado&quot; são excluídos. Os produtos contendo &quot;Feriado&quot; não são excluídos.