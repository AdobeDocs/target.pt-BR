---
keywords: responsive;mobile viewports;viewport;devices;mobile;responsive web design;rwd
description: Os visores móveis ajudam você a pré-visualização de como suas atividades Adobe Target aparecem em telas de vários tamanhos.
title: Visualizações móveis para experiências responsivas
feature: vec
uuid: 86a74584-4a4d-428b-9d29-f7ebdf0cef2a
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '1402'
ht-degree: 71%

---


# Mobile Viewports for responsive experiences{#mobile-viewports-for-responsive-experiences}

Mobile viewports help you preview how your [!DNL Target] activities appear on screens of various sizes.

O recurso de pré-visualização do visor móvel foi projetado para sites responsivos que são bem renderizados em vários dispositivos, janelas ou tamanhos de tela. Sites responsivos ajustam-se e adaptam-se automaticamente a qualquer tamanho de tela, incluindo desktops, laptops, tablets ou telefones celulares.

>[!NOTE]
>
> * Use visores móveis se o seu site for responsivo e os mesmos elementos na sua página de desktop forem usados na sua página móvel em uma configuração diferente. If you have a separate mobile site with a separate structure, such as `m.mysite.com`, use a [multipage activity](../../c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48) instead.
   >
   >
* Os visores móveis não estarão disponíveis se sobrepostos por uma oferta de redirecionamento.


Uma visor é definido pelo tamanho do retângulo preenchido por uma página da Web na sua tela. É o tamanho da janela do navegador, menos as barras de rolagem e as barras de ferramentas. Os navegadores usam &quot;pixels CSS&quot;. Em vários dispositivos, como os com telas de retina, o visor é menor que a resolução de dispositivo anunciada.

Abaixo, estão visores e resoluções para alguns dispositivos populares. Lembre-se de usar um tamanho de visor no [!DNL Target]. Vários sites listam os tamanhos da janela de visualização de dispositivos populares. Por exemplo, consulte [https://viewportsizer.com/devices/](https://viewportsizer.com/devices/) ou consulte o site do fabricante do dispositivo.

| Dispositivo | Tamanho do visor | Resolução do dispositivo |
|---|---|---|
| iPhone SE | 375 de largura x 667 de altura | 750 de largura x 1334 de altura |
| iPhone 11 Pro máx | 414 de largura x 896 de altura | 1242 de largura x 2688 de altura |
| iPhone 11 Xs Max | 414 de largura x 896 de altura | 1242 de largura x 2688 de altura |
| iPhone 11 | 414 de largura x 896 de altura | 828 de largura x 1792 de altura |
| iPhone 11 Xr | 414 de largura x 896 de altura | 828 de largura x 1792 de altura |
| iPhone 11 Pro | 375 de largura x 812 de altura | 1125 de largura x 2436 de altura |
| iPhone 11 X | 375 de largura x 812 de altura | 1125 de largura x 2436 de altura |
| iPhone 11 Xs | 375 de largura x 812 de altura | 1125 de largura x 2436 de altura |
| iPhone X | 375 de largura x 812 de altura | 1125 de largura x 2436 de altura |
| iPhone 8 Plus | 414 de largura x 736 de altura | 1080 de largura x 1920 de altura |
| iPhone 8 | 375 de largura x 667 de altura | 750 de largura x 1334 de altura |
| iPhone 7 Plus | 414 de largura x 736 de altura | 1080 de largura x 1920 de altura |
| iPhone 7 | 375 de largura x 667 de altura | 750 de largura x 1334 de altura |
| iPhone 6s Plus | 414 de largura x 736 de altura | 1080 de largura x 1920 de altura |
| iPhone 6s | 375 de largura x 667 de altura | 750 de largura x 1334 de altura |
| iPhone 6 Plus | 414 de largura x 736 de altura | 1080 de largura x 1920 de altura |
| iPhone 6 | 375 de largura x 667 de altura | 750 de largura x 1334 de altura |
| iPad  Pro | 1024 de largura x 1366 de altura | 2048 de largura x 2732 de altura |
| iPad de terceira e quarta generação | 768 de largura x 1024 de altura | 1536 de largura x 2048 de altura |
| iPad Air 1 e 2 | 768 de largura x 1024 de altura | 1536 de largura x 2048 de altura |
| iPad Mini | 768 de largura x 1024 de altura | 768 de largura x 1024 de altura |
| iPad Mini 2 e 3 | 768 de largura x 1024 de altura | 1536 de largura x 2048 de altura |
| Nexus 6P | 411 de largura x 731 de altura | 1440 de largura x 2560 de altura |
| Nexus 5X | 411 de largura x 731 de altura | 1080 de largura x 1920 de altura |
| Google Pixel | 411 de largura x 731 de altura | 1080 de largura x 1920 de altura |
| Google Pixel XL | 411 de largura x 731 de altura | 1440 de largura x 2560 de altura |
| Google Pixel 2 | 411 de largura x 731 de altura | 1080 de largura x 1920 de altura |
| Google Pixel 2 XL | 411 de largura x 823 de altura | 1440 de largura x 2880 de altura |
| Samsung Galaxy Note 5 | 480 de largura x 853 de altura | 1440 de largura x 2560 de altura |
| LG G5 | 480 de largura x 853 de altura | 1440 de largura x 2560 de altura |
| One Plus 3 | 480 de largura x 853 de altura | 1080 de largura x 1920 de altura |
| Samsung Galaxy S9 | 360 de largura x 740 de altura | 1440 de largura x 2960 de altura |
| Samsung Galaxy S9+ | 360 de largura x 740 de altura | 1440 de largura x 2960 de altura |
| Samsung Galaxy S8 | 360 de largura x 740 de altura | 1440 de largura x 2960 de altura |
| Samsung Galaxy S8+ | 360 de largura x 740 de altura | 1440 de largura x 2960 de altura |
| Samsung Galaxy S7 | 360 de largura x 640 de altura | 1440 de largura x 2560 de altura |
| Samsung Galaxy S7 Edge | 360 de largura x 640 de altura | 1440 de largura x 2560 de altura |
| Nexus 7 (2013) | 600 de largura x 960 de altura | 1200 de largura x 1920 de altura |
| Nexus 9 | 768 de largura x 1024 de altura | 1536 de largura x 2048 de altura |
| Samsung Galaxy Tab 10 | 800 de largura x 1280 de altura | 800 de largura x 1280 de altura |
| Chromebook Pixel | 1280 de largura x 850 de altura | 2560 de largura x 1700 de altura |

Se você deseja fornecer uma atividade a pessoas em um determinado dispositivo, escolha o público-alvo apropriado para ele no diagrama de atividade. Use o Mobile Web Composer para editar a página na atividade daquele dispositivo. Se deseja executar uma atividade em toda a sua experiência digital e certificar-se de que ela funcione em todos os dispositivos, não aplique o direcionamento, e use visores móveis para visualizar a atividade em cada tela.

Se você tiver um site responsivo, normalmente ele é projetado para abrir em uma exibição diferente, quando acessado por um dispositivo com uma tela específica. Esses tamanhos de tela que acionam as novas exibições são conhecidas como pontos de interrupção de CSS. Os pontos de interrupção CSS são pontos em que o conteúdo do site responde dependendo da largura do dispositivo para exibir o layout ideal para os visitantes. Os pontos de interrupção CSS também são chamados de query [de](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)mídia.

Save your CSS breakpoints in [!DNL Target] so you can preview your experiences for each view you define. Each of these experiences is displayed in a mobile viewport in the [!DNL Target] interface. Abra a exibição em cada tamanho de tela ao clicar no visor ao longo da parte superior do visor.

Se o seu site não for responsivo, você ainda poderá usar o Mobile Web Composer para exibir um site, se sua atividade estiver direcionada para um dispositivo específico.

>[!IMPORTANT]
>
>Embora você possa editar uma experiência em visualizações móveis, essas alterações se aplicam a todos os visualizadores e dispositivos, não apenas ao visor no qual você está trabalhando. Da mesma forma, editar uma experiência na exibição de desktop normal altera a página para todos os tamanhos de tela, não somente a exibição de desktop atual. Atualmente, não suportamos alterações de página específicas do visor.

## Mobile viewport configuration {#task_B4B161499DC0470584ED922A4D20FCAB}

Configure as janelas de visualização móvel que você deseja disponibilizar ao criar suas experiências.

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Visual Experience Composer]**.
1. Para adicionar um novo visor móvel, na seção de configuração **[!UICONTROL do visualizador]** móvel, clique em **[!UICONTROL Adicionar]**.

   ![Adicionar visor](/help/c-experiences/c-visual-experience-composer/assets/viewpoert_add.png)

   To change the configuration of an existing mobile viewport, select that viewport, then click the [!UICONTROL Edit] (pencil) icon.

1. Digite um nome para a janela de visualização móvel.

   Use um nome descritivo que seja fácil de reconhecer. O nome pode ter até 36 caracteres.

1. Insira o tamanho da tela do dispositivo móvel: largura e altura.

   A largura pode estar entre 150 e 968 pixels. A altura pode estar entre 150 e 1280 pixels.

1. (Opcional) Selecione o sistema operacional do dispositivo.

   Opções:

   * Android
   * iOS
   * Windows
   * Symbian
   * BlackBerry

   Se você usa o [Enhanced Experience Composer](../../c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D) e selecionar um sistema operacional, o emula aquele dispositivo quando você visualiza a página. [!DNL Target] If, for example, there is a different look and feel for Android than iOS on your responsive site, [!DNL Target] mimics that behavior.

1. Clique em **[!UICONTROL Salvar]**.

## Create a responsive experience {#task_D6332438B5EE48CCA8AF199270F1CAEF}

Add mobile viewports to your [!DNL Target] activities to create responsive experiences for mobile screens.

1. Crie a atividade [](/help/c-activities/activities.md)desejada.
1. No Visual Experience Composer, clique no ícone de engrenagem **[!UICONTROL Configurações]** e selecione **[!UICONTROL Adicionar janelas de visualização móvel]**.

   ![Opção Adicionar visualizações móveis](/help/c-experiences/c-visual-experience-composer/assets/add-mobile-viewports.png)

1. Clique no ícone **[!UICONTROL Dispositivos]** e ative cada dispositivo com um visor móvel.

   ![Ativar visualizações móveis](/help/c-experiences/c-visual-experience-composer/assets/mobileviewports.png)

   As janelas de visualização móvel estão listadas da menor para a maior de acordo com a largura.

1. Edite as janelas de visualização móvel conforme desejado.

   Qualquer alteração feita em uma experiência (por exemplo, se você alterar o texto em um cabeçalho) será aplicada na experiência em todos dispositivos.

   Passe o mouse sobre o nome de uma janela para ver o tamanho da janela.

   ![Experiência responsiva máxima do iPhone 11 Pro](/help/c-experiences/c-visual-experience-composer/assets/iphone11.png)

1. Se desejar, alterne entre os modos retrato e paisagem clicando no ícone de orientação desejado.

   ![Opções de orientação](/help/c-experiences/c-visual-experience-composer/assets/orientation.png)

## Use Case: Target two iPhone versions {#task_CC3144BF5BA54034996E1D3DB0BC1A35}

Este caso de uso mostra como configurar experiências para duas versões do iPhone: iPhone 6 e iPhone 6 Plus.

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Visual Experience Composer]**.
1. In the **[!UICONTROL Mobile Viewport Configuration]** section, create mobile viewports for iPhone 6 and iPhone 6 plus.

   Use as seguintes configurações para cada janela:

   | Nome | Largura | Altura | Sistema operacional |
   |---|---|---|---|
   | iPhone 6 | 375 | 667 | iOS |
   | iPhone 6 Plus | 414 | 736 | iOS |

   ![](assets/iphoneviewportconfig.png)

1. Crie uma atividade com a experiência que você gostaria de público alvo.
1. Selecione a experiência que deseja exibir para visitantes que acessarem seu site com um iPhone 6 ou iPhone 6 Plus.
1. Ao selecionar sua meta, clique em **[!UICONTROL Criar público-alvo]** e configure um público como mostrado na imagem abaixo:

   ![](assets/iphoneaudiences.png)

   Como o celular pode ficar na posição paisagem, o requerimento de altura e largura serem maior que 320 simultaneamente cria uma condição que somente o 6 e o 6 Plus podem atender, quando combinado com o modelo do dispositivo iPhone.
1. Clique em **[!UICONTROL Salvar]**.
1. Continue configurando sua atividade como normalmente faria.

## Vídeos de treinamento

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste artigo.

### Visual Experience Composer (2 de 2) (7:29) ![Etiqueta de visão geral](/help/assets/overview.png)

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