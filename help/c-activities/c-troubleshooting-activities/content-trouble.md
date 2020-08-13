---
keywords: debug mbox;troubleshoot mbox;mbox issues;flicker;mboxDebug;mboxTrace;token;debugger;priority;activity priority;Adobe Experience Cloud Debugger;orderConfirmPage mbox;SiteCatalyst  purchase mbox;top selling;top seller
description: Se sua página não exibir o conteúdo esperado, há algumas etapas que você pode seguir para depurar o delivery de conteúdo no Adobe Target.
title: Solução de problemas de delivery de conteúdo no Adobe Target
feature: activities
subtopic: Multivariate Test
topic: Standard
uuid: 8837d07a-f793-495e-a6c1-b9c35fbe18b1
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '1316'
ht-degree: 67%

---


# Soluções de problemas da entrega de conteúdo{#troubleshoot-content-delivery}

Se a página não exibir o conteúdo esperado, há algumas etapas que você pode seguir para depurar a entrega de conteúdo.

* Verifique seu código de campanha ou atividade cuidadosamente. Um erro de ortografia ou de outro tipo pode fazer com que o conteúdo esperado não seja exibido.
* Use mboxTrace or mboxDebug to troubleshoot the [!DNL Target] request.
* Use the Adobe Experience Cloud Debugger, an easy-to-use tool that provides much of the same information as mboxDebug, to troubleshoot the [!DNL Target] request.

mboxDebug is especially useful when you are setting up [!DNL Target] on your page to make sure the [!DNL Target] request is firing and the cookie is being set. No entanto, ela não entra no tipo de detalhes que são úteis durante a depuração da entrega de conteúdo. Se a sua atividade não aparecer na sua página ou se aparecer conteúdo indesejado, use mboxTrace para examinar e depurar a página atentamente.

## Recuperar o token de autorização para usar com as ferramentas de depuração {#section_BED130298E794D1FA229DB7C3358BA54}

Como mboxTrace e mboxDebug podem expor dados de campanha e dados de perfil a terceiros, um token de autorização é necessário. O token de autorização pode ser recuperado na interface de usuário do [!DNL Target]. O token é válido por seis horas.

Para recuperar o token de autorização:

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Implementação]**.
1. Na seção Ferramentas do depurador, clique em **[!UICONTROL Gerar novo token]** de autenticação.

   ![Gerar novo token de autenticação](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/debugger-auth-token.png)

1. Adicione o token gerado como um parâmetro ao seu URL para ativar uma das ferramentas de depuração avançadas.

   ![Token de autorização](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/auth-token.png)

## mboxTrace {#section_256FCF7C14BB435BA2C68049EF0BA99E}

mboxTrace enables you to receive trace information attached to [!DNL Target] responses. Trace information reflects the outcome of a [!DNL Target] call (for example, a conversion or an impression) and any additional data that may help in determining why this particular outcome happened, such as a set of available branches among which the selection was made in a campaign. Use essas informações para depurar a entrega de conteúdo.

Os seguintes parâmetros estão disponíveis:

| Opções de mboxTrace | Saída |
|--- |--- |
| `?mboxTrace=console` | Imprime no log do console como objetos.<br>Para at.js, em vez de abrir uma nova janela do navegador ou exibir uma saída no console como em mbox.js, você precisará inspecionar a solicitação de rede e procurar em Visualização (Chrome) ou Resposta (Firefox). |
| `?mboxTrace=json` | Imprime no log do console como sequência de caracteres JSON literal |
| `?mboxTrace=window` | Imprime em uma janela pop-up como uma sequência de caracteres JSON |
| `?mboxTrace=disable` | Desativa o rastreamento do modo de sessão |

**Exemplo de chamada de mboxTrace**

`https://www.mysite.com/page.html?mboxTrace=window&authorization=f543abf-0111-4061-9619-d41d665c59a6`

A saída mostra informações muito detalhadas sobre seu conteúdo. mboxTrace mostra detalhes sobre sua campanha ou atividade e perfil. Também fornece um instantâneo do perfil antes da execução, e um instantâneo do que foi alterado após a execução. Ela também mostra quais campanhas ou atividades foram avaliadas para cada local.

Algumas das informações incluem segmentos correspondentes ou não e IDs de direcionamento:

* **SegmentId**: as IDs dos segmentos, da biblioteca de segmentos reutilizáveis ou anônimas criadas para a campanha em particular.
* **TargetId**: as IDs dos direcionamentos, da biblioteca de expressões de destino ou de direcionamentos anônimos para qualquer segmento da campanha.
* **Unmatched**: a solicitação não estava qualificada nessa chamada para esses segmentos ou direcionamentos.
* **Matched**: a solicitação estava qualificada para os segmentos ou direcionamentos especificado.

**Usar mboxTrace nas páginas de recomendações**: a adição de mboxTrace como um parâmetro de consulta nas páginas com recomendações substitui o design de recomendações na página pela janela de detalhes de mboxTrace, que exibe informações detalhadas sobre suas recomendações, inclusive:

* Recommendations devolvidas em relação às recomendações solicitadas
* A chave usada e se está gerando recomendações
* Recommendations geradas por critérios em relação a recomendações de backup
* Configurações de critérios
* Exclusões e inclusões aplicadas
* Regras de coleção

Não é necessário incluir  `=console`, `=json` ou `=window` no parâmetro de consulta. Quando terminar com os detalhes do mboxTrace, adicione `=disable` e pressione **[!UICONTROL Enter]** para retornar ao modo normal de exibição.

mboxTrace não altera o funcionamento e a aparência normais do site. Os visitantes verão o design normal de recomendações.

## mboxDebug {#mboxdebug}

Para usar mboxDebug, inclua um parâmetro mboxDebug no fim do seu URL. The following table contains information about [!DNL Target] response-related URL parameters.

>[!NOTE]
>
>Alguns parâmetros de mboxDebug estão disponíveis com ou sem autenticação.

| Parâmetros de URL | Propósito |
|--- |--- |
| `mboxDebug=1` | <br>DepuradorA adição desse parâmetro a qualquer URL com solicitações de Público alvo definidas abre uma janela pop-up com detalhes de depuração importantes. Informações sobre cookies, PCid e valores de ID de sessão aparecem escritos e todos os URLs de são visíveis. Click on a Target request URL to show the response for that [!DNL Target] request. Mais detalhes estão disponíveis em [mbox_debug.pdf](/help/assets/mbox_debug.pdf). |
| `mboxDebug=x-cookie` | Modificar o cookie |
| `mboxDisable=1` | Desabilitar mboxes na página |
| `mboxDebug=x-profile` | Ver perfis definidos. |
| `mboxDebug=x-time` | Show response time for each [!DNL Target] request |
| `mboxOverride.browserIp=<Insert IP address>` | Testar geolocalização<br>Teste a geolocalização com este parâmetro de URL. Insira um endereço IP como o valor para este atributo e o geolocalização do Test&amp;Target avalia o endereço IP para compará-lo com qualquer geolocalização e segmentação configurados em uma campanha. |

>[!NOTE]
>
>Certifique-se de que o fragmento do URL esteja depois dos parâmetros da string de query. Qualquer coisa depois do primeiro `#` é um identificador de fragmento e faz com que os parâmetros de depuração não funcionem corretamente.

## Adobe Experience Cloud Debugger  {#section_A2798ED3A431409690A4BE08A1BFCF17}

Com o depurador da Adobe Experience Cloud é mais rápido e fácil entender a implementação do Target. Você pode visualizar rapidamente a configuração da biblioteca, examinar as solicitações para garantir que os parâmetros personalizados estão sendo passados corretamente, ativar o logon no console e desativar todas as solicitações do Target. Autentique para o Experience Cloud e você pode usar a poderosa ferramenta MboxTrace para inspecionar suas qualificações de atividade e audiência, bem como seu perfil de visitante.

Para obter mais informações, consulte os vídeos de treinamento abaixo:

Para obter informações mais detalhadas, consulte [Depurar o at.js usando o Adobe Experience Cloud Debugger](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md).

## Se o target.js não for carregado durante a entrega {#section_ABBA5EFDFFB749D8BEE172DB1F973058}

O mbox.js envia um cookie chamado &quot;em-disabled&quot; para o visitante quando o target.js não é carregado durante a entrega. Este cookie evita que as ofertas criadas com o Visual Experience Composer sejam renderizadas no site. Os visitantes com esse cookie não veem o conteúdo do teste nem são contados nesses relatórios de atividades. Todo o conteúdo restante da oferta (por exemplo, das campanhas no Target Classic) continua sendo carregado. O cookie tem duração de 30 minutos a partir do momento da falha no carregamento.

## Os melhores vendedores não aparecem no Recommendations  {#section_3920C857270A406C80BE6CBAC8221ECD}

The *`SiteCatalyst: purchase`* call can&#39;t be used for Purchase algorithm traffic data. Em vez disso, use a *`orderConfirmPage`* chamada.

## Verificar prioridade da atividade {#section_3D0DD07240F0465BAF655D0804100AED}

Form-based activities created with [!DNL Target Standard/Premium] might collide with activities created in the [!DNL Target Classic] UI that have the same priority and use the same [!DNL Target] request.

## O código personalizado não produz os resultados esperados no Internet Explorer 8. {#section_FAC3651F19144D12A37A3E4F14C06945}

O Target não é mais compatível com o IE8.

## JavaScript content delivered by the global [!DNL Target] request doesn&#39;t load when using mbox.js. {#section_03EC9B9C410B4F52A7FCD81840311709}

Atualize para [!DNL mbox.js] versão 58 ou posterior.

mbox.js version 58 and later executes non-JavaScript content for the global [!DNL Target] request immediately after the HTML `BODY` tag is present. JavaScript content inside `<script>` tags for the global [!DNL Target] request executes after the `DOMContentLoaded` event is fired. This order of content delivery ensures that JavaScript content for the global [!DNL Target] request is delivered and rendered properly.

## O cookie do Target não é definido  {#section_77AFEB541C0B495EB67E29A4475DF960}

Se o seu site tiver um subdomínio, como [!DNL us.domain.com], mas você precisar que o cookie do esteja definido em [!DNL domain.com] (em vez de [!DNL us.domain.com]), você deve substituir a configuração `cookieDomain`. Para obter mais informações, consulte [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).

## O conteúdo do Target cintila ou não é mostrado caso um elemento também faça parte da personalização do AEM. {#section_9E1DABEB75AB431FB9F09887E6DD07D3}

Se um elemento DOM fizer parte da segmentação de personalização do Adobe Experience Manager (AEM) e de uma atividade do Target, o conteúdo do Target poderá cintilar ou não ser exibido.

Para resolver isso, você pode desativar a personalização do AEM nas páginas nas quais o Target está sendo executado.

## Falha no fornecimento de ofertas remotas e de redirecionamento devido a um URL inválido.  {#section_7D09043B687F43B39DAEDF17D00375AC}

Se a oferta remota ou de redirecionamento usar um URL inválido, poderá ocorrer uma falha no fornecimento.

For redirect offers, the [!DNL Target] response can contain `/* invalid redirect offer URL */`

Ou

For remote offers, the [!DNL Target] response can contain `/* invalid remote offer URL */`

You can check the [!DNL Target] response in the browser or using mboxTrace. Consulte [https://tools.ietf.org/html/std66](https://tools.ietf.org/html/std66) para obter mais informações sobre URLs válidos.

## As solicitações de público alvo não estão sendo acionadas no meu site.

O at.js não aciona solicitações de Público alvo se você estiver usando um documento inválido. A at.js exige o doctype HTML 5.

## Vídeos de treinamento

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste artigo.

### Adicionar a extensão ![Crachá do tutorial](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23114t2/)

### Crachá do ![tutorial de depuração de Público alvo básico](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23115t2/)

### Crachá do ![tutorial de rastreamento da mbox](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23113t2/)