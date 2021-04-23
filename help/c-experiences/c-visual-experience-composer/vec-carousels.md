---
keywords: Visual Experience Composer;VEC;carrossel
description: Saiba como criar um carrossel que pode ser editado no Adobe [!DNL Target] Visual Experience Composer (VEC).
title: Como crio carrosséis no Visual Experience Composer?
feature: Visual Experience Composer (VEC)
exl-id: 50bc11d2-c9fc-4b53-8218-49842b59269a
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 71%

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
   >A opção [!UICONTROL Renderizar usando JavaScript] não é mais suportada se usada em conjunto com um código personalizado no Visual Experience Composer.

1. Atualize o classNames somente para ocultar outros e exibir o próximo com tempo/animação.

   Jamais atualize a estrutura DOM usando JavaScript.
