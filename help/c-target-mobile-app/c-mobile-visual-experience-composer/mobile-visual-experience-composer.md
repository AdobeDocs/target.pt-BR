---
description: O Visual Experience Composer (VEC) para aplicativos móveis nativos permite criar atividades e personalizar o conteúdo de maneira autônoma, sem dependências de desenvolvimento contínuas e ciclos de lançamento de aplicativos.
seo-description: O Visual Experience Composer (VEC) para aplicativos móveis nativos permite criar atividades e personalizar o conteúdo de maneira autônoma, sem dependências de desenvolvimento contínuas e ciclos de lançamento de aplicativos.
seo-title: Aplicativo para dispositivos móveis do Visual Experience Composer
solution: Target
title: Aplicativo para dispositivos móveis do Visual Experience Composer
topic: Padrão
uuid: 83702f9c-40ff-441b-b773-46b01155a6f2
translation-type: tm+mt
source-git-commit: 5f58e6dc0e91a3341d73273edf953206a95d6450

---


# aplicativo para dispositivos móveis no Visual Experience Composer{#mobile-app-visual-experience-composer}

O Visual Experience Composer (VEC) para aplicativos móveis nativos permite criar atividades e personalizar o conteúdo de maneira autônoma, sem dependências de desenvolvimento contínuas e ciclos de lançamento de aplicativos.

O [Visual Experience Composer](../../c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D) existente fornece um recurso do tipo &quot;faça você mesmo&quot; para criar atividades e personalizar experiências que podem ser entregues dinamicamente às suas propriedades da Web, por meio da mbox global do Target, sem nenhuma intervenção do desenvolvedor. Agora você pode aproveitar o VEC para fazer o mesmo para os aplicativos móveis nativos. O aplicativo Mobile App VEC, disponível em [AEP SDK v 5](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-target-vec), pode ser usado para criar [atividades de teste](/help/c-activities/t-test-ab/test-ab.md) A/B e [direcionamento de experiência (XT)](/help/c-activities/t-experience-target/experience-target.md) para aplicativos móveis. Compatibilidade com outros tipos de atividade estará disponível no futuro.

O VEC do aplicativo móvel é compatível com os navegadores listados nos [navegadores suportados](../../c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100).

## Uso do Visual Experience Composer nos aplicativos nativos para dispositivos móveis {#using-the-mobile-vec}

A ilustração a seguir representa o processo de uso do VEC do aplicativo móvel:

![](assets/mobile-vec-diagram.png)

| Processo | Detalhes |
|--- |--- |
| Pareamento | Autorize com segurança o aplicativo para dispositivos móveis e o dispositivo móvel para funcionarem com o Target. Essa etapa é necessária apenas uma vez para um dispositivo. |
| Criação | Crie uma  [Atividade do Target](/help/c-activities/activities.md), como visualização em tempo real das ações realizadas na interface do usuário do Target. |
| Entrega | O Target entrega atividades automaticamente no aplicativo nativo para dispositivos móveis. |

**Pareamento:**

A VEC do aplicativo móvel conecta-se em tempo real ao aplicativo móvel do comerciante para criar atividades do Target. Para habilitar isso, o primeiro passo é parear com segurança (autorizar) o dispositivo e o aplicativo para dispositivos móveis ao Target.

1. Ao criar uma atividade de Teste A/B, por exemplo, selecione **[!UICONTROL Aplicativo para dispositivos móveis]**, selecione **[!UICONTROL Visual (padrão)]**, depois clique em **[!UICONTROL Próximo]**.

   ![](assets/mobile-vec-create-1.png)

1. Insira o URL do aplicativo, depois clique em **[!UICONTROL Criar deep link]**.

   ![](assets/mobile-vec-create-2.png)

O processo de pareamento contém as etapas a seguir:

1. Insira o esquema do URL do aplicativo que pode ser usado para gerar um deep link. Um deep link típico se parece com:

   `mymobileapp://path?params`

1. O deep link está disponivel como um código QR ou um URL. Os usuários podem ler o código QR do telefone ou enviar por email o URL para eles mesmos. O URL do deep link tem um token de autorização usado para parear com segurança o aplicativo para dispositivos móveis e o dispositivo móvel ao Target.
1. Abrir o URL do deep link no seu dispositivo móvel. Isso inicia o aplicativo móvel. O SDK identifica que o aplicativo foi inicializado para o pareamento e a criação no VEC.

   O SDK faz uma solicitação ao servidor do Target e se registra. O servidor do Target autoriza o token e estabelece uma conexão em tempo real com o dispositivo (por meio de soquetes da Web atualmente).

   Após a conexão ser estabelecida, uma exibição em tempo real do aplicativo aparece na interface do Target. O aplicativo tem um contorno vermelho em sobreposição que é um indicador de que o aplicativo está conectado com o Target, como mostrado na ilustração abaixo.

   ![](assets/mobile-vec-create-3.png)

   Os dispositivos que já estão pareados podem ser reconectados ao inicializar o aplicativo e abrir a interface de criação.

**Criação:**

Após o aplicativo estar conectado e uma exibição em tempo real do aplicativo aparecer no VEC, é possível começar a criar a sua atividade. Nesse momento, as seguintes ações são compatíveis:

| Ação | Detalhes |
|--- |--- |
| Trocar imagem | Trocar uma imagem por outra selecionando uma oferta de imagem diferente ou definindo diretamente o URL de CDN de uma imagem. As ofertas de imagem no Target são servidas por meio [do Adobe Scene 7](/help/administrating-target/scene7-settings.md). |
| Alterar texto | Altere o conteúdo, a cor ou o tamanho da fonte do texto em um elemento de texto, botão ou rótulo. |
| Alterar plano de fundo | Altere o conteúdo ou o plano de fundo do elemento para uma área de texto ou botão. |

As ações realizadas no VEC são visíveis em tempo real no aplicativo, o que permite uma capacidade de visualização em tempo real durante a criação. As ações estão associadas a Telas ou Exibições relevantes para dispositivos móveis e estão associadas de maneira adequada.

![](assets/mobile-vec-create-4.png)

## Solução de problemas {#troubleshooting}

**A VEC do aplicativo móvel diz que meu aplicativo foi desconectado.**

Sua conexão com a Internet deve ter caído. Reinicie o aplicativo após a Internet estar disponível novamente e uma nova conexão será estabelecida. Recomendamos a criação de uma atividade de VEC do aplicativo móvel em uma conexão Wifi.

**A VEC do aplicativo móvel não está sincronizada com meu aplicativo móvel.**

Clique no botão [!UICONTROL Atualizar] no VEC para sincronizar a exibição.

## Exibições do Target e aplicativos para dispositivos móveis {#target-views}

O VEC do aplicativo móvel aproveita um novo conceito de Exibições: um grupo lógico de elementos visuais que juntas compõem uma experiência de aplicativo móvel.

**Introdução às exibições do Target**

Considere um aplicativo de compras de flores como exemplo. O aplicativo permite que os usuários realizem as tarefas a seguir:

* Listar as flores e os buquês disponíveis
* Exibir detalhes
* Pedir flores
* Controlar configurações, como opções de pagamento e endereços

Neste aplicativo, cada uma dessas tarefas pode ser realizada em uma tela diferente do aplicativo para dispositivos móveis. Enquanto os usuários navegam pelo aplicativo, uma tela é renderizada que permite a eles realizar uma das tarefas a seguir. Se você é um desenvolvedor Android, estará mais propenso a criar quatro Classes de atividade do Android diferentes com cada classe associada a uma dessas tarefas.

Nesse caso, cada uma dessas tarefas pode ser considerada como Exibições pelas quais o seu aplicativo para dispositivos móveis transita. Isso se chama Exibições do Target— cada uma delas exclusivamente caracterizada. Uma Exibição do Target, ou Exibição em síntese, é um contâiner lógico de elementos visuais que são exibidos na tela dos dispositivos móveis. Exemplos de uma Exibição são uma tela ou uma Classe de atividade do Android.

Aplicativos para dispositivos móveis raramente são tão simples. Vamos torná-lo um pouco mais realista. Na primeira tarefa, a que lista as flores e buquês disponíveis, vamos adicionar a capacidade de criar vários layouts e, portanto, telas diferentes. Por exemplo, vamos adicionar um recurso de &quot;Classificar por&quot; que tenha três opções:

* Por popularidade
* Preço - baixo para alto
* Preço - alto para baixo

Neste exemplo, sempre que um usuário selecionar uma opção &quot;Ordenar por&quot; diferente, uma nova tela é exibida, mesmo quando a Classe de atividade é a mesma. Cada uma dessas telas pode assim ser considerada uma Exibição do Target diferente.

Como profissional de marketing, você tem interesse em criar experiências diferentes e executar ofertas distintas em cada uma dessas exibições, sem pedir aos seus desenvolvedores que configurem mboxes locais ou passem por um ciclo de lançamento de aplicativos.

## Configuração do VEC do aplicativo Target Mobile {#setting-up}

Os desenvolvedores devem fazer o seguinte para ativar o VEC do aplicativo móvel para um aplicativo móvel:

* Configurar a extensão do Adobe Target VEC no Launch
   * A extensão da VEC depende da [extensão do Adobe Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md). Verifique se a extensão do Adobe Target já está configurada e habilitada.
* Adicione a extensão do Target VEC ao seu aplicativo.
   * [Android - Configuração do aplicativo móvel](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md)
   * [iOS - Configuração do aplicativo móvel](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-ios.md)

## Métodos de implementação para o VEC do Target

A extensão do Target VEC recupera as experiências relevantes do Target para seu aplicativo por meio de uma solicitação de rede. As ofertas são recuperadas por meio dessa chamada de rede e aplicadas automaticamente nas telas direcionadas. Nenhuma solicitação de rede subsequente é feita para recuperar experiências VEC à medida que o usuário navega por várias telas do aplicativo.

O comportamento padrão da extensão é fazer uma solicitação de rede síncrona (chamada de bloqueio) no momento da inicialização do aplicativo. Você pode usar o Launch para controlar o comportamento dessa solicitação de rede para atender ao comportamento do aplicativo.

### Buscar automaticamente atividades do Target

Esse é o comportamento padrão em que uma solicitação de rede é iniciada automaticamente pela extensão do Target VEC. Você pode usar uma das seguintes opções para fazer com que esta solicitação seja chamada de bloqueio ou uma solicitação assíncrona.

* Buscar uma chamada síncrona (o plano de fundo está DESATIVADO)

   Quando selecionada, a extensão do Target VEC faz uma solicitação de rede como chamada de bloqueio na inicialização do aplicativo. As ofertas são aplicadas imediatamente e não há oscilação no aplicativo. Esse é o comportamento padrão da extensão.

* Fetch em uma chamada assíncrona (o plano de fundo está ATIVADO)

   Quando selecionada, a extensão do Target VEC faz uma solicitação de rede em segundo plano sobre o lançamento do aplicativo, mas não bloqueia o carregamento do aplicativo. Se suas experiências forem criadas na tela inicial do aplicativo, as ofertas poderão não se aplicar à tela inicial se a tela for renderizada antes da conclusão da chamada. A renderização de tela do aplicativo é geralmente identificada pelos eventos de ciclo de vida `didFinishLaunchingWithOptions` e `onActivityResumed` no iOS e Android, respectivamente. As ofertas se aplicam automaticamente em todas as telas subsequentes.

### Buscar atividades do Target de forma programática

Você pode desativar a extensão do Target VEC para fazer a solicitação de rede automaticamente e decidir fazer uma chamada programática à API de extensão. Isso proporciona aos desenvolvedores controle sobre como integrar ofertas VEC do Target no aplicativo. A extensão do Target VEC tem dois métodos estáticos `prefetchOffers` e `prefetchOffersBackground` que podem ser usados para recuperar programaticamente ofertas do Target VEC.

* O `prefetchOffers` método oculta a tela atual até que ofertas do Target VEC sejam buscadas. As ofertas são aplicadas automaticamente à tela atual, se aplicável, e a tela é visível novamente.
* O `prefetchOffersBackground` método não oculta a tela atual e é feita uma chamada para recuperar as ofertas relevantes do Target. As ofertas do Target *não* são aplicadas na tela atual e não há oscilação. Conforme o usuário navega para telas subsequentes, as ofertas são aplicadas automaticamente, se aplicável.

### Lidar com restrições de área de trabalho do Target

É possível definir o `at_property` valor para sua área de trabalho usando a interface do Launch. Isso garante que apenas atividades nessa área de trabalho sejam entregues ao seu Aplicativo móvel.

## Diretrizes gerais para chamadas de API do Target {#section_C7276795F02540DCA230AEEDF882A833}

Para adicionar Exibições do Target de maneira adequada, aqui está uma tabela simples que delineia as localizações corretas de onde colocar as chamadas a `targetView`:

| Localização aceitável para TargetView | Sob as adições corretas |
|--- |--- |
| No final do `Activity::onStart`, `Activity::onResume` | Fica a cargo do desenvolvedor se ele considera `OnStart` e `OnResume` como sendo as mesmas ou diferentes `targetViews`. Se forem as mesmas, use o mesmo `viewName`. Se forem diferentes, use `viewNames` diferentes. Estes eventos são automaticamente adicionados pelo SDK. |
| Imediatamente após uma chamada a `Activity::SetContent` | Se a interface do usuário não mudar, podemos inserir uma chamada de `targetView`. |
| Dentro do `View::willAppear` | Se a exibição selecionada que aparece unicamente em uma hierarquia de exibição específica. |
| Imediatamente após uma chamada a `Activity::SetContentView` | Se a atividade não altera/corrige qualquer conteúdo no código a seguir. |

Para o Android, aqui está uma tabela com as localizações incorretas onde colocar as chamadas a `targetView`:

| Localização de targetView inaceitável | Motivo |
|--- |--- |
| Dentro de `Activity::onCreate` | A atividade foi criada, mas a exibição associada à atividade não é garantida e/ou anexada à janela. Este posicionamento pode fazer com que a tela de criação não seja amostrada ou seja amostrada de maneira incompleta e/ou as ofertas sejam aplicadas de uma maneira não determinística. |
| Dentro do `View::didAppear` | A exibição já apareceu e o aplicativo da oferta criará uma experiência ruim na interface do usuário com tremulação. |
| Dentro do `View::didLoad` | A exibição não é anexada à hierarquia de exibição principal e pode estar instanciada, mas não há garantias de que será mostrada na interface do usuário do aplicativo. |

## Entrega {#delivery}

As atividades do Target criadas por meio da VEC do aplicativo móvel são enviadas automaticamente em aplicativos móveis. Essas atividades são pré-buscadas na inicialização do aplicativo (com base na configuração de inicialização) e aplicadas à medida que o usuário navega por diferentes Visualizações do Target, geralmente mapeadas diretamente para as telas.

Ao chamar o método `TargetVEC.prefetchOffersBackground()` API, as ofertas do Target são buscadas do Target Edge e armazenadas em cache localmente. Isso permite uma experiência do usuário mais estável, já que as ofertas do Target são aplicadas imediatamente do cache com o acionamento das exibições do Target com `targetView()`, em vez de serem buscadas pela rede.

Para maior flexibilidade, você também pode chamar a `TargetVEC.prefetchOffers()` API, que oculta o layout atual até que ofertas do Target sejam pré-busca e aplicadas para visualizar a Exibição do Target (possivelmente causando oscilação).

O `TargetVEC.prefetchOffersBackground()` também pode ser chamado repetidamente enquanto o usuário navega em um aplicativo do cliente, para atualizar o cache de oferta local do Target com o conteúdo mais apropriado (seguindo as atualizações mais recentes do perfil do usuário do Target atual).

Observe que, sempre que as ofertas do Target forem previamente buscadas, se possível, também serão aplicadas as ofertas de exibição do Target acionadas com `AdobeTargetMobile.targetView()`.

## Limitações conhecidas {#limitations}

* No momento, o VEC do aplicativo móvel pode ser usado para criar [atividades de teste](/help/c-activities/t-test-ab/test-ab.md) A/B e [direcionamento de experiência (XT)](/help/c-activities/t-experience-target/experience-target.md) para aplicativos móveis. Compatibilidade com outros tipos de atividade estará disponível no futuro.
* Ainda não há suporte para o recurso de Visualização. Ela será disponibilizada em uma versão futura.
* Ao tentar reconectar o aplicativo ao VEC do aplicativo móvel, você deve sair do aplicativo completamente e reiniciá-lo.

   Se o aplicativo móvel já estiver aberto durante qualquer um dos cenários listados abaixo, feche-o e reabra-o. No entanto, você *deve* fechar o aplicativo na seção de aplicativos recentes e *não* pressionando o botão Voltar. Se o aplicativo for fechado pressionando o botão Voltar, pode haver problemas de conexão intermitente.

   Há várias situações nas quais você deve reiniciar o aplicativo para se conectar ao VEC do aplicativo móvel se o aplicativo já estiver aberto:

   * Ao criar uma nova atividade, após selecionar o aplicativo móvel, a caixa de diálogo da lista de dispositivos é exibida. Se o aplicativo já estiver aberto, feche-o e reinicie-o para que o dispositivo seja mostrado como disponível para seleção.
   * A caixa de diálogo do dispositivo é exibida ao iniciar a edição de uma atividade. Se o aplicativo já estiver aberto, feche-o e reinicie-o para que o dispositivo seja mostrado como disponível para seleção.
   * A caixa de diálogo do dispositivo é exibida ao navegar da etapa &quot;Metas e configurações&quot; de volta para a etapa &quot;Criação&quot; (Etapa 1). Se o aplicativo já estiver aberto, você deve fechar e reiniciar o aplicativo para conectar-se novamente ao VEC do aplicativo móvel.
   Certifique-se de fechar o aplicativo na seção de aplicativos recentes e não pressionando o botão [!UICONTROL Voltar.]

## Vídeo de treinamento: Adobe Target Mobile App Visual Experience Composer (3:33) {#video}

>[!VIDEO](https://video.tv.adobe.com/v/27528)