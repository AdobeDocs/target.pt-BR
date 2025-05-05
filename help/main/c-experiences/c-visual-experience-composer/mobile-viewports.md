---
keywords: responsivo;visores móveis;janela;dispositivos;dispositivos móveis;web design responsivo;rwd
description: Os visores móveis ajudam a ver como as atividades do Adobe  [!DNL Target]  aparecem em telas de vários tamanhos. Encontre uma lista de tamanhos e resoluções populares de visores de dispositivo.
title: Como usar visores móveis para experiências responsivas?
feature: Visual Experience Composer (VEC)
exl-id: 1062e7a1-10b4-4746-bce9-67017978578d
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1350'
ht-degree: 95%

---

# Visores móveis para experiências responsivas

Os visores móveis permitem visualizar como as atividades do [!DNL Adobe Target] aparecem em telas de vários tamanhos. 

O recurso de visualização de visor móvel é projetado para sites responsivos que são renderizados em vários dispositivos, janelas e tamanhos de tela. Sites responsivos ajustam-se e se adaptam automaticamente a qualquer tamanho de tela, incluindo desktops, laptops, tablets ou telefones celulares.

>[!NOTE]
>
> * Use visores móveis se o seu site for responsivo e os mesmos elementos na sua página de desktop forem usados na sua página móvel em uma configuração diferente. Se você tiver um site móvel separado com uma estrutura separada, como `m.mysite.com`, use uma [atividade multipáginas](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48).
>
>* Os visores móveis não estarão disponíveis se sobrepostos por uma oferta de redirecionamento.

Uma visor é definido pelo tamanho do retângulo preenchido por uma página da Web na sua tela. O visor é o tamanho da janela do navegador, menos as barras de rolagem e as barras de ferramentas. Os navegadores usam &quot;pixels CSS&quot;. Em vários dispositivos, como os com telas de retina, o visor é menor que a resolução de dispositivo anunciada.

Abaixo, estão visores e resoluções para dispositivos populares. Lembre-se de usar um tamanho de visor no [!DNL Target].

>[!NOTE]
>
>Vários sites listam os tamanhos da janela de visualização de dispositivos populares. Por exemplo, consulte `https://viewportsizer.com/devices/`. Consulte o site do fabricante do dispositivo para obter as informações mais precisas e atualizadas.

| Dispositivo | Tamanho da janela de visualização (largura x altura) | Resolução do dispositivo (largura × altura) |
|---|---|---|
| iPhone 12 | 390 x 844 | 1170 x 2532 |
| iPhone 12 Mini | 360 x 780 | 1080 x 2340 |
| iPhone 12 Pro | 390 x 844 | 1170 x 2532 |
| iPhone 12 Pro Max | 428 x 926 | 1248 x 2778 |
| iPhone SE | 214 x 379 | 640 x 1136 |
| iPhone 11 Pro Max | 414 x 896 | 1242 x 2688 |
| iPhone 11 Xs Max | 414 x 896 | 1242 x 2688 |
| iPhone 11 | 414 x 896 | 828 x 1792 |
| iPhone 11 Xr | 414 x 896 | 828 x 1792 |
| iPhone 11 Pro | 375 x 812 | 1125 x 2436 |
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
| iPad Pro | 1024 x 1366 | 2048 x 2732 |
| iPad de terceira e quarta geração | 768 x 1024 | 1536 x 2048 |
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
| LG G5 | 360w x 640 | 1440 x 2560 |
| LG G4 | 360w x 640 | 1440 x 2560 |
| LG G3 | 360w x 640 | 1440 x 2560 |
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

Para entregar uma atividade aos visitantes em um dispositivo específico, escolha o público apropriado para esse dispositivo no diagrama de atividades. Use o Mobile Web Composer para editar a página na atividade daquele dispositivo. Para executar uma atividade em toda a sua experiência digital para garantir que ela fique boa em todos os dispositivos, não aplique o direcionamento. Em vez disso, use visores móveis para visualizar a atividade em cada tamanho de tela.

Para sites responsivos, normalmente seu site é projetado para abrir em uma visualização diferente quando acessado por um dispositivo com um tamanho de tela específico. Esses tamanhos de tela que acionam as novas exibições são conhecidas como pontos de interrupção de CSS. Os pontos de interrupção de CSS são pontos em que o conteúdo do site responde, dependendo da largura do dispositivo, para exibir o layout ideal para os visitantes.. Os pontos de interrupção de CSS também são chamados de [consultas de mídia](https://developer.mozilla.org/pt-BR/docs/Web/CSS/Media_Queries/Using_media_queries).

Salve seus pontos de interrupção de CSS no [!DNL Target] para que você possa visualizar as suas experiências para cada exibição que definir. Cada uma dessas experiências é exibida em um visor móvel na interface do [!DNL Target]. Abra a exibição em cada tamanho de tela ao clicar no visor ao longo da parte superior do visor.

Se o seu site não for responsivo, use o Mobile Web Composer para exibir um site se sua atividade estiver direcionada para um dispositivo específico.

>[!IMPORTANT]
>
>Você pode editar uma experiência nos visores móveis. No entanto, essas alterações se aplicam a todos os visores e dispositivos, não apenas ao visor em que você está trabalhando.. Da mesma forma, editar uma experiência na exibição de desktop normal altera a página para todos os tamanhos de tela, não somente a exibição de desktop atual. Atualmente, o [!DNL Target] não aceita alterações de página específicas do visor.

## Configuração do visor móvel {#task_B4B161499DC0470584ED922A4D20FCAB}

Configure os visores móveis que você deseja disponibilizar ao criar suas experiências.

1. Clique em **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]**.
1. Na seção **[!UICONTROL Mobile viewports configuration]**, clique em **[!UICONTROL Add]**.

   ![Adicionar visor](/help/main/c-experiences/c-visual-experience-composer/assets/viewpoert_add.png)

   Ou

   Para alterar a configuração de um visor móvel existente, selecione o visor e clique no ícone [!UICONTROL Edit] (lápis).

1. Digite um nome para a janela de visualização móvel.

   Use um nome descritivo que seja fácil de reconhecer. O nome pode ter até 36 caracteres.

1. Especifique o tamanho da tela do dispositivo móvel: largura e altura.

   A largura pode ser de 150 a 968 pixels. A altura pode ser de 150 a 1280 pixels.

1. (Opcional) Selecione o sistema operacional do dispositivo.

   Opções:

   * Android
   * iOS
   * Windows
   * Symbian
   * BlackBerry

   Se você usa o [Enhanced Experience Composer](/help/main/c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D) e selecionar um sistema operacional, o emula aquele dispositivo quando você visualiza a página. [!DNL Target] Por exemplo, se houver uma aparência diferente para Android e iOS em seu site responsivo, o [!DNL Target] imita esse comportamento.

1. Clique em **[!UICONTROL Save]**.

>[!NOTE]
>
>Se você tentar excluir um visor móvel que está em uso, a seguinte mensagem será exibida: &quot;Este visor está atualmente associado a uma ou várias atividades. Você precisa remover o visor dessas atividades antes de poder exclui-lo.&quot;

## Criar uma experiência responsiva {#task_D6332438B5EE48CCA8AF199270F1CAEF}

Adicione visores móveis a atividades do [!DNL Target] para criar atividades responsivas para telas móveis.

1. Crie a [atividade desejada](/help/main/c-activities/activities.md).
1. No [!UICONTROL Visual Experience Composer] (VEC), clique no ícone de engrenagem **[!UICONTROL Settings]** e selecione **[!UICONTROL Add Mobile Viewports]**.

   ![Opção adicionar visores móveisl](/help/main/c-experiences/c-visual-experience-composer/assets/add-mobile-viewports.png)

1. Clique no ícone **[!UICONTROL Devices]** e habilite cada dispositivo com um visor móvel.

   ![Ativar visores móveis](/help/main/c-experiences/c-visual-experience-composer/assets/mobileviewports.png)

   As janelas de visualização móvel estão listadas da menor para a maior de acordo com a largura.

1. Edite as janelas de visualização móvel conforme desejado.

   Todas as alterações feitas na experiência são aplicadas à experiência em todos os dispositivos. Por exemplo, você altera o texto em um cabeçalho.

   Passe o mouse sobre o nome de uma janela para ver o tamanho da janela.

   ![Experiência responsiva do iPhone 11 Pro Max](/help/main/c-experiences/c-visual-experience-composer/assets/iphone11.png)

1. Caso desejar, altere entre os modos retrato e paisagem ao clicar no ícone de orientação.

   ![Opções de orientação](/help/main/c-experiences/c-visual-experience-composer/assets/orientation.png)

## Vídeos de treinamento

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste artigo.

### Visual Experience Composer (2 de 2) (7:29) ![Selo de visão geral](/help/main/assets/overview.png)

O vídeo de demonstração a seguir inclui informações sobre o uso do Visual Experience Composer para funcionar com visores móveis:

* Renomear e duplicar uma experiência
* Criar uma experiência de redirecionamento
* Direcionar uma atividade para um único URL ou um grupo de URLs
* Criar uma atividade multipáginas
* Visualizar e criar a experiência para sites responsivos
* Use sobreposições para destacar tipos de elementos

>[!VIDEO](https://video.tv.adobe.com/v/30981?captions=por_br)

### Preferências da conta no Adobe Target ![Selo de visão geral](/help/main/assets/overview.png)

Este vídeo inclui informações sobre como configurar visores móveis, começando às 4:40 do vídeo.

>[!VIDEO](https://video.tv.adobe.com/v/17379)
