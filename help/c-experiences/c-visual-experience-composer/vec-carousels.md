---
keywords: Visual Experience Composer;VEC;carrossel
description: Este tópico mostra como criar um carrossel que pode ser editado no Visual Experience Composer (VEC).
title: Criar carrosséis que funcionam no Visual Experience Composer
subtopic: Teste multivariado
topic: Padrão
uuid: 19538f6e-445c-49ca-9f0d-b49fc330b721
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Criação de carrosséis aceitos pelo Visual Experience Composer{#creating-carousels-that-work-in-the-visual-experience-composer}

Este tópico mostra como criar um carrossel que pode ser editado no Visual Experience Composer (VEC).

Quando seguir as etapas abaixo, o [!DNL Target] sempre saberá que o slide terá o "seletor" para o slide correto, mesmo se ele for alterado no Visual Experience Composer após alguns segundos.

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