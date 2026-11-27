---
keywords: Visual Experience Composer;VEC;carrossel
description: Saiba como criar um carrossel que pode ser editado no Visual Experience Composer (VEC) do Adobe [!DNL Target].
title: Como criar carrosséis no Visual Experience Composer?
feature: Visual Experience Composer (VEC)
exl-id: 50bc11d2-c9fc-4b53-8218-49842b59269a
TQID: 'https://experienceleague.adobe.com/RN04MJgC49BI2-h2e-i-kgSRTejpLHzKACm-hOv2VCE'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 2%
---
# Criando carrosséis que funcionam no [!UICONTROL Visual Experience Composer] {#vec-carousels}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba como criar um carrossel que pode ser editado no **[!UICONTROL Visual Experience Composer]** (VEC).

>[!ENDSHADEBOX]

Um carrossel criado com a seguinte estrutura pode ser editado no [!DNL Adobe Target] **[!UICONTROL Visual Experience Composer]** (VEC). A estrutura mantém o seletor de cada slide válido, de modo que o [!DNL Target] sempre identifica o slide correto, mesmo quando o slide exibido muda alguns segundos após a página ser carregada no VEC.

1. Crie os slides como espaços reservados estáticos do HTML, com um slide visível e os outros slides ocultos pela classe.

   ```html
   <ul>
   <li class="show"> slide 1 </li>
   <li class="hidden"> slide 2 </li>
   <li class="hidden"> slide 3 </li>
   </ul>
   ```

1. Projete a aparência somente com CSS. Não use o JavaScript para isso.

   >[!NOTE]
   >
   >A opção **[!UICONTROL Renderizar Usando JavaScript]** não é mais suportada quando usada em conjunto com um código personalizado no **[!UICONTROL Visual Experience Composer]**.

1. Mostre o próximo slide atualizando apenas os nomes de classe: oculte os outros slides e mostre o próximo com um cronômetro ou uma animação. Nunca atualize a estrutura DOM com o JavaScript.
