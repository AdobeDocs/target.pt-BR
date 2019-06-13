---
description: Este tópico mostra como criar um carrossel que pode ser editado no Visual Experience Composer (VEC).
keywords: Visual Experience Composer;VEC;carrossel
seo-description: Este tópico mostra como criar um carrossel que pode ser editado no Visual Experience Composer (VEC).
seo-title: Criar carrosséis que funcionam no Visual Experience Composer
solution: Target
subtopic: Teste multivariado
title: Criar carrosséis que funcionam no Visual Experience Composer
topic: Padrão
uuid: 19538f6e-445c-49ca-9f0d-b49fc330b721
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

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