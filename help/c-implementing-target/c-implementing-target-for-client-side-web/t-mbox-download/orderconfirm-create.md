---
description: A mbox de confirmação de pedido registra detalhes sobre pedidos no seu site e permite a geração de relatórios baseados em receita e pedidos. A mbox de confirmação de pedido também pode impulsionar algoritmos de recomendação, como "Pessoas que compraram o produto x também compraram o produto y".
keywords: confirmação de pedido; orderConfirmPage
seo-description: A mbox de confirmação de pedido registra detalhes sobre pedidos no seu site e permite a geração de relatórios baseados em receita e pedidos. A mbox de confirmação de pedido também pode impulsionar algoritmos de recomendação, como "Pessoas que compraram o produto x também compraram o produto y".
seo-title: Criar uma mbox de confirmação de pedido - mbox.js
solution: Target
subtopic: Introdução
title: Criar uma mbox de confirmação de pedido - mbox.js
uuid: 001da2bd-2ccf-490b-ba84-ac9b9a2a5451
translation-type: tm+mt
source-git-commit: a2cdf35f37f2debdb4b6be13e2965989ee9a3f00

---


# Criar uma mbox de confirmação de pedido - mbox.js{#create-an-order-confirmation-mbox-mbox-js}

A mbox de confirmação de pedido registra detalhes sobre pedidos no seu site e permite a geração de relatórios baseados em receita e pedidos. A mbox de confirmação de pedido também pode impulsionar algoritmos de recomendação, como &quot;Pessoas que compraram o produto x também compraram o produto y&quot;.

>[!NOTE]
>
>Se usuários fazem compras no seu site, recomendamos implementar uma mbox de confirmação de pedido mesmo se você usar Analytics for Target (A4T) como seu gerador de relatórios.

>[!NOTE]
>
>Você também pode criar uma mbox de confirmação de pedido para o at.js usando o mesmo método; no entanto, o método [!DNL at.js] é preferido. Para obter mais informações, consulte [Rastrear conversões](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053).

1. Na página de detalhes do pedido, insira o script da mbox seguindo o modelo abaixo.
1. Substitua as PALAVRAS EM LETRAS MAIÚSCULAS por valores dinâmicos ou estáticos do seu catálogo.

   >[!NOTE]
   >
   >Utilize delimitação por vírgulas para separar várias IDs de produto.

   **Dica:** você também pode passar informações de pedido em qualquer mbox (ela não precisa ser chamada `orderConfirmPage`). Também é possível passar informações de pedidos em várias mboxes dentro da mesma campanha.

   ```
   <div class="mboxDefault"> 
      <!-- CONTENT TO SHOW IF NO OFFERS AVAILABLE. --> 
   </div> 
   <script type="text/javascript">    
      mboxCreate('orderConfirmPage', 
      'productPurchasedId=PRODUCT ID FROM YOUR ORDER PAGE, PRODUCT ID2, PRODUCT ID3', 
      'orderTotal=ORDER TOTAL FROM YOUR ORDER PAGE', 
      'orderId=ORDER ID FROM YOUR ORDER PAGE'); 
   </script> 
   ```

A mbox de confirmação de pedido utiliza os seguintes parâmetros:

| Parâmetro | Descrição |
|--- |--- |
| `orderId` | Valor único para identificar um pedido de contagem de conversão.<br>O `orderId` deve ser único. Pedidos duplicados são ignorados em relatórios. |
| `orderTotal` | Valor monetário para a compra.<br>Não passe o símbolo de moeda. Use um ponto (não uma vírgula) para indicar valores decimais. |
| `productPurchasedId` (Opcional) | Lista separada por vírgula de IDs de produtos comprados no pedido.<br>Essas IDs de produtos são exibidas no relatório de auditoria para suportar análises de relatório adicionais. |