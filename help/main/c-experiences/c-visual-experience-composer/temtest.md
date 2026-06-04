---
keywords: teste de modelo, modelo, mesma experiência em páginas semelhantes, teste de modelo
description: Saiba como usar o Visual Experience Composer (VEC) do Adobe [!DNL Target]  para incluir a mesma experiência em várias páginas estruturadas de forma semelhante ou que contêm os mesmos elementos de modelo.
title: Posso incluir a mesma experiência em páginas semelhantes?
feature: Experiences and Offers
exl-id: 4ea95794-496c-4eff-96ec-8a9d1f732c4a
TQID: https://experienceleague.adobe.com/zk7U6g7gk7XkpWsEFQbwuCm7xbpIb1lCaZefxjn-39g
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 564
ht-degree: 23%

---

# Incluir a mesma experiência em páginas semelhantes

Use um modelo de página no [!DNL Adobe Target] para fornecer estrutura às suas páginas, ou, se as páginas contiverem elementos semelhantes, para testar variações em elementos de página estruturadas de forma semelhante ou em todo o domínio.

Para funcionar corretamente, esse recurso deve ser usado em páginas com uma estrutura semelhante ou conter elementos de modelo estruturados da mesma forma em todas as páginas.

>[!IMPORTANT]
>
>O uso desse recurso para alterar elementos em páginas diferentes provavelmente causa resultados inesperados.

Por exemplo, você pode usar esse recurso para fazer uma das seguintes opções:

* Testar uma barra de navegação global, reorganizando ou removendo elementos
* Remover um item de todas as páginas de produtos que usam um modelo de página específico
* Adicionar um banner em todas as páginas de produtos
* Alterar o layout do modelo de artigo

Você pode especificar páginas que incluem os elementos de alteração ou aplicar a alteração através do site ou domínio.

1. Crie ou edite uma atividade conforme descrito em [Atividades](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. Para especificar as páginas em que a experiência é exibida, no [!UICONTROL Visual Experience Composer] (VEC), clique no ícone [!UICONTROL Configurar] ( ![ícone Configurar](/help/main/assets/icons/Setting.svg) ) e selecione **[!UICONTROL Entrega de página]**.

1. Clique em **[!UICONTROL Adicionar regra]** e especifique os critérios para as páginas nas quais deseja adicionar a experiência.

1. Especifique o intervalo de páginas. O intervalo de páginas pode ser um dos seguintes:

   * [!UICONTROL URL] (Para obter mais informações sobre como [!DNL Target] avalia URLs, consulte [Perguntas frequentes sobre direcionamentos e público-alvo](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
   * [!UICONTROL Domínio]
   * [!UICONTROL Caminho]
   * [!UICONTROL Fragmento de hash (#)] (direcione à parte de uma URL que segue o símbolo #.)
   * [!UICONTROL Consulta]
   * [!UICONTROL Personalizado]

1. Escolha um operador.

   O operador especifica a forma como os itens se relacionam com o intervalo de páginas. Os operadores disponíveis incluem:

   * [!UICONTROL Contém]
   * [!UICONTROL Não contém]
   * [!UICONTROL É (diferencia maiúsculas de minúsculas)]
   * [!UICONTROL Não]
   * [!UICONTROL Começa com]
   * [!UICONTROL Termina com]

1. Digite as sequências de caracteres que definem onde é adicionada a experiência, como o domínio ou as sequências de caracteres contidas no nome da página.

   Por exemplo, se você selecionar **[!UICONTROL Domínio]** e **[!UICONTROL É (diferencia maiúsculas de minúsculas)]**, digite o domínio em que deseja adicionar a experiência para todas as páginas.

   É possível incluir vários itens.

   >[!IMPORTANT]
   >
   >Vários itens usam a lógica OR, ou seja, qualquer item único na lista torna a condição verdadeira.

1. Se desejar, insira critérios adicionais, clicando em **[!UICONTROL Adicionar regra]** e repita o procedimento das etapas anteriores.

   Múltiplos critérios são agrupados com uma lógica E. [!DNL Target] adiciona a experiência a todas as páginas que correspondem aos critérios especificados.

>[!IMPORTANT]
>
> O [!DNL Target] não pode verificar as páginas para se certificar de que elas são exibidas conforme o esperado, portanto, é sempre uma prática importante ao usar este recurso testar as páginas afetadas antes de torná-las públicas.

## Casos de uso

Analise os seguintes casos de uso para encontrar maneiras de usar as regras de modelo no site:

### Renderizar a mesma atividade em todo o domínio

Você pode considerar o uso de regras de modelo para renderizar a mesma atividade em todo o domínio para os seguintes casos de uso:

* Para incluir um cabeçalho ou rodapé global
* Para incluir um banner global (por exemplo, anúncios de COVID-19)
* Para incluir uma promoção global de frete grátis

1. Crie ou edite uma atividade conforme descrito em [Atividades](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. Para especificar o domínio onde a experiência aparece, no [!UICONTROL Visual Experience Composer], clique no ícone [!UICONTROL Configurar] ( ![ícone Configurar](/help/main/assets/icons/Setting.svg) ) e selecione **[!UICONTROL Entrega de página]**.

1. Clique em **[!UICONTROL Adicionar regra]** > **[!UICONTROL domínio]**.

1. No menu suspenso **[!UICONTROL Escolher avaliador]**, selecione **[!UICONTROL Contém]** e especifique o domínio.
