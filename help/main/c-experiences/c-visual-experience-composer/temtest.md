---
keywords: teste de modelo, modelo, mesma experiência em páginas semelhantes, teste de modelo
description: Saiba como usar o Visual Experience Composer (VEC) do Adobe [!DNL Target] para incluir a mesma experiência em várias páginas estruturadas de forma semelhante ou que contêm os mesmos elementos de modelo.
title: Posso incluir a mesma experiência em páginas semelhantes?
feature: Experiences and Offers
exl-id: 4ea95794-496c-4eff-96ec-8a9d1f732c4a
TQID: 'https://experienceleague.adobe.com/zk7U6g7gk7XkpWsEFQbwuCm7xbpIb1lCaZefxjn-39g'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
subfeature_v2:
  - id: ef98a6e0-f26c-4870-9bd4-e6b72e9cc699
    internal-label: Experiences and offers
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 17%
---
# Incluir a mesma experiência em páginas semelhantes {#similar-pages}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba como usar as regras de entrega de página no [!UICONTROL Visual Experience Composer] (VEC) para incluir a mesma experiência em páginas com estrutura semelhante.

>[!ENDSHADEBOX]

Um modelo de página em [!DNL Adobe Target] fornece estrutura para páginas. Quando as páginas contêm elementos semelhantes, as variações nesses elementos de página estruturados de forma semelhante podem ser testadas em várias páginas ou em um domínio inteiro.

Para funcionar corretamente, esse recurso deve ser usado em páginas com uma estrutura semelhante ou conter elementos de modelo estruturados da mesma forma em todas as páginas.

>[!IMPORTANT]
>
>O uso desse recurso para alterar elementos em páginas diferentes provavelmente causa resultados inesperados.

Esse recurso pode ser usado, por exemplo, para executar um dos seguintes procedimentos:

* Testar uma barra de navegação global, reorganizando ou removendo elementos
* Remover um item de todas as páginas de produtos que usam um modelo de página específico
* Adicionar um banner em todas as páginas de produtos
* Alterar o layout do modelo de artigo

## Especificar as páginas de uma experiência {#specify-pages}

As páginas em que uma experiência é exibida são especificadas com as regras de entrega da página. As regras podem incluir páginas específicas ou aplicar a alteração no site ou domínio.

1. Crie ou edite uma atividade conforme descrito em [Atividades](/help/main/c-activities/activities.md).

1. No [!UICONTROL Visual Experience Composer] (VEC), clique no ícone **[!UICONTROL Configurar]** ( ![ícone Configurar](/help/main/assets/icons/Setting.svg) ) e selecione **[!UICONTROL Entrega de página]**.

   ![Atividades](assets/vec_edit_1.png)

1. Clique em **[!UICONTROL Adicionar regra]** e especifique os critérios para as páginas nas quais adicionar a experiência.

1. Especifique o intervalo de páginas: **[!UICONTROL URL]**, **[!UICONTROL Domínio]**, **[!UICONTROL Caminho]**, **[!UICONTROL Hash (#) Fragmento]** (a parte de uma URL que segue o símbolo #), **[!UICONTROL Consulta]** ou **[!UICONTROL Personalizado]**.

   Para obter mais informações sobre como [!DNL Target] avalia URLs, consulte [Perguntas frequentes sobre direcionamentos e público-alvo](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).

   ![Atividades](assets/vec_edit_2.png)

1. Escolha um operador. O operador especifica a forma como os itens se relacionam com o intervalo de páginas.

1. Digite as sequências de caracteres que definem onde é adicionada a experiência, como o domínio ou as sequências de caracteres contidas no nome da página.

   Por exemplo, se **[!UICONTROL Domínio]** e **[!UICONTROL É (diferencia maiúsculas de minúsculas)]** forem selecionados, digite o domínio em que a experiência é adicionada para todas as páginas.

   Vários itens podem ser incluídos. Vários itens usam a lógica OR, ou seja, qualquer item único na lista torna a condição verdadeira.

1. (Opcional) Clique em **[!UICONTROL Adicionar regra]** e repita as etapas de 3 a 6 para inserir critérios adicionais.

   Múltiplos critérios são agrupados com uma lógica E. [!DNL Target] adiciona a experiência a todas as páginas que correspondem aos critérios especificados.

>[!IMPORTANT]
>
>O [!DNL Target] não pode verificar as páginas para se certificar de que elas são exibidas conforme o esperado, portanto, é sempre uma prática importante ao usar este recurso testar as páginas afetadas antes de torná-las públicas.

## Casos de uso {#use-cases}

As regras de modelo podem ser usadas em um site de maneiras diferentes, conforme mostrado no caso de uso a seguir.

### Renderizar a mesma atividade em todo o domínio {#entire-domain}

As regras de modelo podem renderizar a mesma atividade em todo o domínio, por exemplo:

* Para incluir um cabeçalho ou rodapé global
* Para incluir um banner global (por exemplo, anúncios de COVID-19)
* Para incluir uma promoção global de frete grátis

1. Crie ou edite uma atividade conforme descrito em [Atividades](/help/main/c-activities/activities.md).

1. Para especificar o domínio onde a experiência aparece, no [!UICONTROL Visual Experience Composer], clique no ícone **[!UICONTROL Configurar]** ( ![ícone Configurar](/help/main/assets/icons/Setting.svg) ) e selecione **[!UICONTROL Entrega de página]**.

1. Clique em **[!UICONTROL Adicionar regra]** > **[!UICONTROL domínio]**.

1. No menu suspenso **[!UICONTROL Escolher avaliador]**, selecione **[!UICONTROL Contém]** e especifique o domínio.

   ![Atividades](assets/vec_edit_3.png)
