---
keywords: Visual Experience Composer;VEC;carrossel
description: Saiba como criar um carrossel que pode ser editado no Visual Experience Composer (VEC) do Adobe [!DNL Target] .
title: Como criar carrosséis no Visual Experience Composer?
feature: Visual Experience Composer (VEC)
exl-id: 50bc11d2-c9fc-4b53-8218-49842b59269a
TQID: https://experienceleague.adobe.com/RN04MJgC49BI2-h2e-i-kgSRTejpLHzKACm-hOv2VCE
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 146
ht-degree: 58%

---

# Criar carrosséis que funcionam no Visual Experience Composer

Este tópico mostra como criar um carrossel que pode ser editado no [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC).

Quando seguir as etapas abaixo, o [!DNL Target] sempre saberá que o slide terá o &quot;seletor&quot; para o slide correto, mesmo se ele for alterado no Visual Experience Composer após alguns segundos.

1. Crie alocadores de espaço estáticos em HTML.

   ```html
   <ul>
   <li class="show"> slide 1 </li>
   <li class="hidden"> slide 2 </li>
   <li class="hidden"> slide 3 </li>
   </ul>
   ```

1. Adicione CSS para projetar a aparência.

   Não use JavaScript.

   >[!NOTE]
   >
   >A opção [!UICONTROL Render Using JavaScript] não tem suporte no momento se for usada em conjunto com um código personalizado no Visual Experience Composer.

1. Atualize o classNames somente para ocultar outros e exibir o próximo com temporizador/animação.

   Jamais atualize a estrutura DOM usando JavaScript.
