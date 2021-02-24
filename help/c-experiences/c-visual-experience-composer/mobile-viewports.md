---
keywords: responsive;mobile viewports;viewport;devices;mobile;responsive web design;rwd
description: Os visores móveis ajudam você a ver a aparência das atividades Adobe Target em telas de vários tamanhos. Encontre uma lista de resoluções e tamanhos populares de visor de dispositivo.
title: Como uso o Mobile Viewports para experiências responsivas?
feature: Visual Experience Composer (VEC)
translation-type: tm+mt
source-git-commit: 69677b9d384d9817a39386fc1388a4aa42121713
workflow-type: tm+mt
source-wordcount: '1166'
ht-degree: 36%

---


# Visualizações móveis para experiências responsivas

Os visores móveis permitem que você pré-visualização suas atividades [!DNL Adobe Target] em telas de vários tamanhos.

O recurso de pré-visualização do visor móvel foi projetado para sites responsivos que são bem renderizados em vários dispositivos, janelas e tamanhos de tela. Sites responsivos ajustam-se e adaptam-se automaticamente a qualquer tamanho de tela, incluindo desktops, laptops, tablets ou telefones celulares.

>[!NOTE]
>
> * Use visores móveis se o seu site for responsivo e os mesmos elementos na sua página de desktop forem usados na sua página móvel em uma configuração diferente. Se você tiver um site móvel separado com uma estrutura separada, como `m.mysite.com`, use uma [atividade de várias páginas](/help/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48) em vez disso.
   >
   >
* Os visores móveis não estarão disponíveis se sobrepostos por uma oferta de redirecionamento.


Uma visor é definido pelo tamanho do retângulo preenchido por uma página da Web na sua tela. O visor é do tamanho da janela do navegador, menos as barras de rolagem e as barras de ferramentas. Os navegadores usam &quot;pixels CSS&quot;. Em vários dispositivos, como os com telas de retina, o visor é menor que a resolução de dispositivo anunciada.

Abaixo estão os pontos de vista e as resoluções para dispositivos populares. Lembre-se de usar um tamanho de visor no [!DNL Target].

>[!NOTE]
>
>Vários sites listam os tamanhos da janela de visualização de dispositivos populares. Por exemplo, consulte [https://viewportsizer.com/devices/](https://viewportsizer.com/devices/). Consulte o site do fabricante do dispositivo para obter as informações mais precisas e atualizadas.

| Dispositivo | Tamanho do visor (largura x altura) | Resolução do dispositivo (largura x altura) |
|---|---|---|
| iPhone 12 | 390 x 844 | 1170 x 2532 |
| iPhone 12 Mini | 360 x 780 | 1080 x 2340 |
| iPhone 12 Pro | 390 x 844 | 1170 x 2532 |
| iPhone 12 Pro máx | 428 x 926 | 1248 x 2778 |
| iPhone SE | 214 x 379 | 640 x 1136 |
| iPhone 11 Pro máx | 414 x 896 | 1242 x 2688 |
| iPhone 11 Xs Max | 414 x 896 | 1242 x 2688 |
| iPhone 11 | 414 x 896 | 828 x 1792 |
| iPhone 11 Xr | 414 x 896 | 828 x 1792 |
| iPhone 12 Pro | 375 x 812 | 1125 x 2436 |
| iPhone 11 X | 375 x 812 | 1125 x 2436 |
| iPhone 11 Xs | 375 x 812 | 1125 x 2436 |
| iPhone X | 375 x 812 | 1125 x 2436 |
| iPhone 8 Plus | 414 x 736 | 1080 x 1920 |
| iPhone 8 | 375 x 667 | 750 x 1334 |
| iPhone 7 Plus | 414 x 736 | 1080 x 1920 |
| iPhone 7 | 375 x 667 | 750 x 1334 |
| iPhone 6s Plus | 414 x 736 | 1080 x 1920 |
| iPhone 6s | 375 x 667 | 750 x 1334 |
| iPhone 6 Plus | 414 x 736 | 1080 x 1920 |
| iPhone 6 | 375 x 667 | 750 x 1334 |
| iPad  Pro | 1024 x 1366 | 2048 x 2732 |
| iPad de terceira e quarta generação | 768 x 1024 | 1536 x 2048 |
| iPad Air 1 e 2 | 768 x 1024 | 1536 x 2048 |
| iPad Mini | 768 x 1024 | 768 x 1024 |
| iPad Mini 2 e 3 | 768 x 1024 | 1536 x 2048 |
| Nexus 6P | 411 x 731 | 1440 x 2560 |
| Nexus 5X | 411 x 731 | 1080 x 1920 |
| Google Pixel | 411 x 731 | 1080 x 1920 |
| Google Pixel XL | 411 x 731 | 1440 x 2560 |
| Google Pixel 2 | 411 x 731 | 1080 x 1920 |
| Google Pixel 2 XL | 411 x 823 | 1440 x 2880 |
| Samsung Galaxy Note 5 | 480 x 853 | 1440 x 2560 |
| LG G5 | 360 sem x 640 | 1440 x 2560 |
| LG G4 | 360 sem x 640 | 1440 x 2560 |
| LG G3 | 360 sem x 640 | 1440 x 2560 |
| One Plus 3 | 480 x 853 | 1080 x 1920 |
| Samsung Galaxy S9 | 360 x 740 | 1440 x 2960 |
| Samsung Galaxy S9+ | 360 x 740 | 1440 x 2960 |
| Samsung Galaxy S8 | 360 x 740 | 1440 x 2960 |
| Samsung Galaxy S8+ | 360 x 740 | 1440 x 2960 |
| Samsung Galaxy S7 | 360 x 640 | 1440 x 2560 |
| Samsung Galaxy S7 Edge | 360 x 640 | 1440 x 2560 |
| Nexus 7 (2013) | 600 x 960 | 1200 x 1920 |
| Nexus 9 | 768 x 1024 | 1536 x 2048 |
| Samsung Galaxy Tab 10 | 800 x 1280 | 800 x 1280 |
| Chromebook Pixel | 1280 x 850 | 2560 x 1700 |

Para fornecer uma atividade aos visitantes em um determinado dispositivo, escolha a audiência apropriada para esse dispositivo no diagrama da atividade. Use o Mobile Web Composer para editar a página na atividade daquele dispositivo. Para executar uma atividade em toda a sua experiência digital para garantir que ela fique boa em todos os dispositivos, não aplique o direcionamento. Em vez disso, use visores móveis para pré-visualização da atividade em cada tamanho de tela.

Para sites responsivos, normalmente o site é projetado para abrir em uma visualização diferente quando acessado por um dispositivo com um tamanho de tela específico. Esses tamanhos de tela que acionam as novas exibições são conhecidas como pontos de interrupção de CSS. Os pontos de interrupção CSS são pontos em que o conteúdo do site responde dependendo da largura do dispositivo para exibir o layout ideal para os visitantes. Os pontos de interrupção CSS também são chamados de [query de mídia](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries).

Salve os pontos de interrupção CSS em [!DNL Target] para que você possa pré-visualização suas experiências para cada visualização definida. Cada uma dessas experiências é exibida em um visor móvel na interface [!DNL Target]. Abra a exibição em cada tamanho de tela ao clicar no visor ao longo da parte superior do visor.

Se o site não estiver respondendo, use o Mobile Web Composer para visualização em um site se a atividade estiver direcionada a um dispositivo específico.

>[!IMPORTANT]
>
>Você pode editar uma experiência em visualizações móveis. No entanto, essas alterações se aplicam a todos os visualizadores e dispositivos, não apenas ao visor no qual você está trabalhando. Da mesma forma, editar uma experiência na exibição de desktop normal altera a página para todos os tamanhos de tela, não somente a exibição de desktop atual. Atualmente, [!DNL Target] não suporta alterações de página específicas do viewport.

## Configuração do visor móvel {#task_B4B161499DC0470584ED922A4D20FCAB}

Configure os visores móveis que você deseja disponibilizar ao criar suas experiências.

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Visual Experience Composer]**.
1. Na seção **[!UICONTROL Configuração do visualizador móvel]**, clique em **[!UICONTROL Adicionar]**.

   ![Adicionar visor](/help/c-experiences/c-visual-experience-composer/assets/viewpoert_add.png)

   Ou

   Para alterar a configuração de um visor móvel existente, selecione esse visor e clique no ícone [!UICONTROL Editar] (lápis).

1. Digite um nome para a janela de visualização móvel.

   Use um nome descritivo que seja fácil de reconhecer. O nome pode ter até 36 caracteres.

1. Especifique o tamanho da tela do dispositivo móvel, largura e altura.

   A largura pode ser de 150 a 968 pixels. A altura pode ser de 150 a 1280 pixels.

1. (Opcional) Selecione o sistema operacional do dispositivo.

   Opções:

   * Android
   * iOS
   * Windows
   * Symbian
   * BlackBerry

   Se você usa o [Enhanced Experience Composer](/help/c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D) e selecionar um sistema operacional, o emula aquele dispositivo quando você visualiza a página. [!DNL Target] Por exemplo, se houver uma aparência diferente para o Android e para o iOS em seu site responsivo, [!DNL Target] imitará esse comportamento.

1. Clique em **[!UICONTROL Salvar]**.

>[!NOTE]
>
>Se você tentar excluir um visor móvel que esteja em uso, a seguinte mensagem será exibida: &quot;Atualmente, esse visor está associado a uma ou várias atividades. Você precisa remover o visor dessas atividades antes de poder excluí-lo.&quot;

## Crie uma experiência responsiva {#task_D6332438B5EE48CCA8AF199270F1CAEF}

Adicione visores móveis às suas [!DNL Target] atividades para criar experiências responsivas para telas móveis.

1. Crie a [atividade desejada](/help/c-activities/activities.md).
1. No [!UICONTROL Visual Experience Composer] (VEC), clique no ícone de engrenagem **[!UICONTROL Settings]** e selecione **[!UICONTROL Adicionar Visualizações Móveis]**.

   ![Opção Adicionar visualizações móveis](/help/c-experiences/c-visual-experience-composer/assets/add-mobile-viewports.png)

1. Clique no ícone **[!UICONTROL Dispositivos]** e ative cada dispositivo com um visor móvel.

   ![Ativar visualizações móveis](/help/c-experiences/c-visual-experience-composer/assets/mobileviewports.png)

   As janelas de visualização móvel estão listadas da menor para a maior de acordo com a largura.

1. Edite as janelas de visualização móvel conforme desejado.

   Quaisquer alterações feitas na experiência são aplicadas à experiência em todos os dispositivos. Por exemplo, você altera o texto em um cabeçalho.

   Passe o mouse sobre o nome de uma janela para ver o tamanho da janela.

   ![Experiência responsiva máxima do iPhone 11 Pro](/help/c-experiences/c-visual-experience-composer/assets/iphone11.png)

1. Se desejar, alterne entre os modos retrato e paisagem clicando no ícone de orientação desejado.

   ![Opções de orientação](/help/c-experiences/c-visual-experience-composer/assets/orientation.png)

## Vídeos de treinamento

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste artigo.

### Visual Experience Composer (2 de 2) (7:29)  ![Etiqueta de visão geral](/help/assets/overview.png)

O vídeo de demonstração a seguir inclui informações sobre o uso do Visual Experience Composer para funcionar com visores móveis:

* Renomear e duplicar uma experiência
* Criar uma experiência de redirecionamento
* Direcionar uma atividade para um único URL ou um grupo de URLs
* Criar uma atividade multipáginas
* Visualizar e criar a experiência para sites responsivos
* Use sobreposições para destacar tipos de elementos

>[!VIDEO](https://video.tv.adobe.com/v/17401)

### Preferências de conta no emblema ![Visão geral do Adobe Target](/help/assets/overview.png)

Este vídeo inclui informações sobre como configurar visualizações móveis, começando às 4:40 do vídeo.

>[!VIDEO](https://video.tv.adobe.com/v/17379)