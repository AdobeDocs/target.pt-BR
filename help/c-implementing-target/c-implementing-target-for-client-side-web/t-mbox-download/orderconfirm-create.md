---
keywords: order confirmation;orderConfirmPage
description: A mbox de confirmação de pedido registra detalhes sobre pedidos no seu site e permite a geração de relatórios baseados em receita e pedidos. A mbox de confirmação de pedido também pode impulsionar algoritmos de recomendação, como "Pessoas que compraram o produto x também compraram o produto y".
title: Criar uma mbox de confirmação de pedido - mbox.js
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 85%

---


# Criar uma mbox de confirmação de pedido - mbox.js{#create-an-order-confirmation-mbox-mbox-js}

A mbox de confirmação de pedido registra detalhes sobre pedidos no seu site e permite a geração de relatórios baseados em receita e pedidos. A mbox de confirmação de pedido também pode impulsionar algoritmos de recomendação, como &quot;Pessoas que compraram o produto x também compraram o produto y&quot;.

>[!NOTE]
>
>* Se usuários fazem compras no seu site, recomendamos implementar uma mbox de confirmação de pedido mesmo se você usar Analytics for Target (A4T) como seu gerador de relatórios.
   >
   >
* Você também pode criar uma mbox de confirmação de pedido para at.js 1.*x* utilizando o mesmo método; no entanto, o [!DNL at.js] método é preferido. Para obter mais informações, consulte [Rastrear conversões](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053).
   >
   >
* Se você estiver usando o at.js 2.*x*, não `mboxCreate` é mais suportado. Para confirmação de pedido usando at.js 2.*x*, use as seguintes APIs relacionadas a rastreamento: [trackEvent()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md) e [sendNotifications()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md).


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