---
keywords: Visual Experience Composer;VEC;carousel
description: Este tópico mostra como criar um carrossel que pode ser editado no Visual Experience Composer (VEC).
title: Criar carrosséis que funcionam no Visual Experience Composer
feature: vec
subtopic: Multivariate Test
topic: Standard
uuid: 19538f6e-445c-49ca-9f0d-b49fc330b721
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 100%

---


# Criação de carrosséis aceitos pelo Visual Experience Composer{#creating-carousels-that-work-in-the-visual-experience-composer}

Este tópico mostra como criar um carrossel que pode ser editado no Visual Experience Composer (VEC).

Quando seguir as etapas abaixo, o [!DNL Target] sempre saberá que o slide terá o &quot;seletor&quot; para o slide correto, mesmo se ele for alterado no Visual Experience Composer após alguns segundos.

1. Crie alocadores de espaço estáticos em HTML.

   ```
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