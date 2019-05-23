---
description: Use o Visual Experience Composer para criar as ofertas que você deseja incluir no teste.
seo-description: Use o Visual Experience Composer para criar as ofertas que você deseja incluir no teste.
seo-title: Criar combinações
title: Criar combinações
uuid: 2ee47bf5-f8b3-41e2-b9a5-0ff4ab175373
translation-type: tm+mt
source-git-commit: 761771a48c0ae957d455974b1f04fa3a8350a8a0

---


# Criar combinações{#create-combinations}

Use o Visual Experience Composer para criar as ofertas que você deseja incluir no teste.

>[!NOTE]
>
>Você pode clicar em **[!UICONTROL Expandir seleção]** ao selecionar objetos na página para selecionar o elemento pai, além do elemento selecionado originalmente. Ao selecionar qualquer elemento pai, todos os filhos desse elemento serão selecionados automaticamente. Você pode expandir a seleção várias vezes.

Com o Visual Experience Composer é possível editar ofertas, nomes de ofertas e nomes de locais. Uma sobreposição é exibida para mostrar onde foram feitas as alterações.

![](assets/overlay.png)

## Ofertas de imagem {#section_A48333211DB149ED926AE467D0032914}

Teste várias ofertas de imagem dentro de um local para determinar qual imagem é mais bem sucedida.

1. Clique em uma imagem na página e selecione **[!UICONTROL Alterar imagem]**.

   ![](assets/changeimage.png)

1. Selecione todas as imagens que deseja incluir no teste e clique em **[!UICONTROL Salvar]**.

   ![](assets/addimage.png)

Cada imagem se torna uma experiência separada nesse local.

## Ofertas HTML {#section_DF016101AFA9412C9B99862C23DE77B1}

Teste várias ofertas em Texto/HTML de um local para determinar qual é mais bem-sucedida.

1. Clique na oferta em Texto/HTML na sua página e depois em **[!UICONTROL Alterar Texto/HTML]**.

   ![](assets/changehtml.png)

1. Clique em **[!UICONTROL Adicionar oferta em Texto/HTML]**, nomeie a oferta e digite ou cole o código para a oferta em Texto/HTML.

   ![](assets/editoffers.png)

   >[!NOTE]
   >
   >O Internet Explorer 10 não oferece suporte para espaços reservados na entrada de HTML5. Como resultado, se usar o IE10, o texto do espaço reservado &quot;Adicionar conteúdo&quot; permanecerá no campo de Texto ao inserir o conteúdo.

   Repita o procedimento para qualquer oferta em Texto/HTML adicional que queira incluir.

1. Clique em **[!UICONTROL Salvar]**.

Cada oferta em Texto/HTML se torna uma experiência separada nesse local.

## Práticas recomendadas {#section_2E98C23D2F1A460FA732A31799CE6291}

* Não inclua mais locais do que o necessário para o teste. Cada experiência incluída no teste aumenta significativamente a quantidade de tráfego e tempo necessário para atingir resultados aceitáveis. Por exemplo, se você tiver elementos de página com três ofertas cada um, existem nove combinações possíveis (3x3). Três elementos, com duas delas contendo três ofertas possíveis e uma com duas ofertas, oferecem 18 opções (3x3x2). Os números aumentam substancialmente com cada elemento e oferta adicional.
* Ao criar testes multivariados, é possível excluir mais de 10% das experiências do teste, desde que você reconheça o aviso de que deve usar relatórios offline para análise.
* Aproveite os recursos de visualização para evitar combinações indesejadas de conteúdo. Por exemplo, você pode ter duas imagens que oferecem descontos diferentes sobre o mesmo item ou serviço. Mostrar as duas imagens na mesma página é ilógico e poderá criar uma confusão.
* Use o Avaliador de tráfego para garantir que o teste foi criado para a quantidade de tráfego que sua página recebe. Verifique se o Avaliador de tráfego aceita a configuração do teste para que você possa obter os resultados que deseja.
* Você deve ter pelo menos três elementos para testar. Se tiver menos, execute uma série de  Testes A/B.
* Recomendamos que as alternativas de cada elemento sejam diferentes entre si.
* Embora não seja obrigatório, é uma boa prática que cada elemento tenha o mesmo número de alternativas.

