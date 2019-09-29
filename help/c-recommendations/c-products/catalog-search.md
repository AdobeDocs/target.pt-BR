---
description: A pesquisa no catálogo ajuda a localizar os produtos ou conteúdo no catálogo.
keywords: catálogo, pesquisa
seo-description: A pesquisa de catálogo no Adobe Target ajuda a localizar os produtos ou conteúdo no catálogo.
seo-title: Pesquisa de catálogo no Adobe Target
solution: Target
title: Pesquisa no catálogo
title-outputclass: premium
topic: Premium
uuid: e0876963-5905-4850-a615-953e435f26e9
badge: premium
translation-type: tm+mt
source-git-commit: afb87e3e23b44133982e55fdc7650250e6bf8b3a

---


# ![PREMIUM](/help/assets/premium.png) Pesquisa no catálogo {#catalog-search}

A pesquisa no catálogo ajuda a localizar os produtos ou conteúdo no catálogo.

Para acessar a pesquisa de catálogo, clique em **[!UICONTROL Recommendations]** &gt; Pesquisa **[!UICONTROL de]** catálogo.

Você pode refinar a pesquisa selecionando uma opção de pesquisa no menu de opções, que é exibido ao clicar na seta para baixo no campo de pesquisa.

![](assets/searchproductsmenu.png)

As opções de pesquisa incluem:

* TODAS
* Nome
* Marca
* Categoria
* ID
* Mensagem

**[!UICONTROL TODAS]** as pesquisas em todos os outros critérios de pesquisa, usando a lógica OU.

Nos resultados da pesquisa, você pode clicar no filtro de **[!UICONTROL Ambiente]** para especificar o ambiente de produção do grupo de hosts cujo catálogo você está exibindo. [](/help/administrating-target/hosts.md) Você também pode usar a rolagem através dos itens nos resultados da pesquisa para exibir miniaturas e outras informações do produto.

O número que aparece ao lado de "Produtos" é o número de produtos que combinam com o termo de pesquisa, do total disponível no ambiente especificado.

O catálogo é atualizado automaticamente quando as atualizações são recebidas por meio de arquivos de feed, API ou atualizações de mbox. As atualizações normalmente são concluídas em uma hora. Se as atualizações estiverem em andamento, o horário em que a atualização mais recente começou será exibido. Se nenhuma atualização estiver em andamento, o tempo em que a atualização mais recente começou e terminou será exibido.

## Criar uma coleção ou exclusão com base na Pesquisa avançada

You can create [collections](/help/c-recommendations/c-products/collections.md) or [exclusions](/help/c-recommendations/c-products/exclusions.md) using Advanced Search on the Catalog Search page ([!UICONTROL Recommendations] &gt; [!UICONTROL Catalog Search] &gt; [!UICONTROL Advanced Search]).

![Salvar como](/help/c-recommendations/c-products/assets/save-as.png)

Após criar uma pesquisa usando "id &gt; contains" Por exemplo, você pode clicar em [!UICONTROL Salvar como] &gt; [!UICONTROL Coleção ou Exclusão].

>[!IMPORTANT]
>
>A funcionalidade de Pesquisa avançada não faz distinção entre maiúsculas e minúsculas; contudo, os produtos devolvidos no momento da entrega baseiam-se na pesquisa sensível a maiúsculas e minúsculas. Essa não correspondência pode levar à confusão. Certifique-se de considerar a sensibilidade a maiúsculas e minúsculas quando você cria coleções ou exclusões baseadas em resultados usando a funcionalidade Pesquisa avançada. Por exemplo, se você realiza uma busca para "Feriado", essa busca inicial lista os resultados contendo "Feriado" e "feriado". Em seguida, se você criar um catálogo com a intenção de encontrar produtos contendo "feriado", somente os produtos contendo "feriado" serão exibidos. Os produtos contendo "Feriado" não serão exibidos. As exclusões são tratadas de maneira semelhante.
