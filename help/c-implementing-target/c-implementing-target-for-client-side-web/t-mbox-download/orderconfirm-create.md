---
keywords: confirmação de pedido; orderConfirmPage
description: Saiba mais sobre a implementação herdada da mbox.js do Adobe Target. Migrar para o SDK da Web da Adobe Experience Platform (AEP Web SDK) ou para a versão mais recente da at.js.
title: Como faço para criar uma mbox de confirmação de pedido usando a mbox.js?
feature: 'at.js '
role: Desenvolvedor
exl-id: 952c2d1b-1ee8-4e9b-bce3-1c439127bb9b
translation-type: tm+mt
source-git-commit: 0a685427a047bfc0a2f5e81525b32df70af6d69f
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 59%

---

# Criar uma mbox de confirmação de pedido - mbox.js

A mbox de confirmação de pedido registra detalhes sobre pedidos no seu site e permite a geração de relatórios baseados em receita e pedidos. A mbox de confirmação de pedido também pode impulsionar algoritmos de recomendação, como &quot;Pessoas que compraram o produto x também compraram o produto y&quot;.

>[!IMPORTANT]
>
>**Fim da vida útil** da mbox.js: A partir de 31 de março de 2021, o  [!DNL Adobe Target] não será mais compatível com a biblioteca mbox.js. Após 31 de março de 2021, todas as chamadas feitas da mbox.js normalmente falharão e afetarão suas páginas que têm [!DNL Target] atividades em execução ao veicular conteúdo padrão.
>
>Recomendamos que todos os clientes migrem para a versão mais recente da nova [!DNL Adobe Experience Platform Web SDK] ou da biblioteca at.js de JavaScript antes dessa data para evitar possíveis problemas com seus sites. Para obter mais informações, consulte [Visão geral: implementar o Target para web do lado do cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

>[!NOTE]
>
>* Se usuários fazem compras no seu site, recomendamos implementar uma mbox de confirmação de pedido mesmo se você usar Analytics for Target (A4T) como seu gerador de relatórios.
   >
   >
* Você também pode criar uma mbox de confirmação de pedido para o at.js 1.** usando o mesmo método; no entanto, o  [!DNL at.js] método é preferido. Para obter mais informações, consulte [Rastrear conversões](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053).
   >
   >
* Se estiver usando a at.js 2.*x*, não  `mboxCreate` é mais compatível. Para confirmação de pedido usando at.js 2.*x*, use as seguintes APIs relacionadas a rastreamento:  [trackEvent()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md) e  [sendNotifications()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md).


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
