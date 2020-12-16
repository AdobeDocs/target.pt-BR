---
keywords: debug mbox;troubleshoot mbox;mbox issues;flicker;mboxDebug;mboxTrace;token;debugger;priority;activity priority;Adobe Experience Cloud Debugger;orderConfirmPage mbox;SiteCatalyst  purchase mbox;top selling;top seller
description: Se sua página não exibir o conteúdo esperado, há algumas etapas que você pode seguir para depurar o delivery de conteúdo no Adobe Target.
title: Solução de problemas de delivery de conteúdo no Adobe Target
feature: activities
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '1386'
ht-degree: 60%

---


# Soluções de problemas da entrega de conteúdo{#troubleshoot-content-delivery}

Se a página não exibir o conteúdo esperado, há algumas etapas que você pode seguir para depurar a entrega de conteúdo.

* Verifique seu código de campanha ou atividade cuidadosamente. Um erro de ortografia ou de outro tipo pode fazer com que o conteúdo esperado não seja exibido.
* Use mboxTrace ou mboxDebug para solucionar problemas da solicitação [!DNL Target].
* Use o Adobe Experience Cloud Debugger, uma ferramenta fácil de usar que fornece muitas das mesmas informações que mboxDebug, para solucionar problemas da solicitação [!DNL Target].

mboxDebug é especialmente útil quando você está configurando [!DNL Target] em sua página para garantir que a solicitação [!DNL Target] seja acionada e o cookie esteja sendo definido. No entanto, ela não entra no tipo de detalhes que são úteis durante a depuração da entrega de conteúdo. Se a sua atividade não aparecer na sua página ou se aparecer conteúdo indesejado, use mboxTrace para examinar e depurar a página atentamente.

## Recuperar o token de autorização para usar com as ferramentas de depuração {#section_BED130298E794D1FA229DB7C3358BA54}

Como mboxTrace e mboxDebug podem expor dados de campanha e dados de perfil a terceiros, um token de autorização é necessário. O token de autorização pode ser recuperado na interface de usuário do [!DNL Target]. O token é válido por seis horas.

Você deve ter uma das seguintes permissões de usuário para gerar um token de autenticação:

* Pelo menos [!UICONTROL Permissão do editor] (ou [!UICONTROL Aprovador])

   Para obter mais informações sobre clientes [!DNL Target Standard], consulte [Especificar funções e permissões](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) em *Usuários*. Para obter mais informações sobre clientes [!DNL Target Premium], consulte [Configurar permissões corporativas](/help/administrating-target/c-user-management/property-channel/properties-overview.md).

* Função de administrador no nível do espaço de trabalho/perfil do produto

   Os espaços de trabalho estão disponíveis somente para [!DNL Target Premium] clientes. Para obter mais informações, consulte [Configurar permissões corporativas](/help/administrating-target/c-user-management/property-channel/properties-overview.md).

* Direitos de administrador (permissão do Sysadmin) no nível do produto [!DNL Adobe Target]

Para recuperar o token de autorização:

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Implementação]**.
1. Na seção Ferramentas do depurador, clique em **[!UICONTROL Gerar novo token de autenticação]**.

   ![Gerar novo token de autenticação](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/debugger-auth-token.png)

1. Adicione o token gerado como um parâmetro ao seu URL para ativar uma das ferramentas de depuração avançadas.

   ![Token de autorização](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/auth-token.png)

## mboxTrace {#section_256FCF7C14BB435BA2C68049EF0BA99E}

mboxTrace permite que você receba informações de rastreamento anexadas às respostas [!DNL Target]. As informações de rastreamento refletem o resultado de uma chamada [!DNL Target] (por exemplo, uma conversão ou uma impressão) e quaisquer dados adicionais que possam ajudar a determinar por que esse resultado em particular aconteceu, como um conjunto de ramificações disponíveis entre as quais a seleção foi feita em uma campanha. Use essas informações para depurar a entrega de conteúdo.

Os seguintes parâmetros estão disponíveis:

| Opções de mboxTrace | Saída |
|--- |--- |
| `?mboxTrace=console` | Imprime no log do console como objetos.<br>Para at.js, em vez de abrir uma nova janela do navegador ou exibir uma saída no console como em mbox.js, você precisará inspecionar a solicitação de rede e procurar em Visualização (Chrome) ou Resposta (Firefox). |
| `?mboxTrace=json` | Imprime no log do console como sequência de caracteres JSON literal |
| `?mboxTrace=window` | Imprime em uma janela pop-up como uma sequência de caracteres JSON |
| `?mboxTrace=disable` | Desativa o rastreamento do modo de sessão |

**Exemplo de chamada mboxTrace**

`https://www.mysite.com/page.html?mboxTrace=window&authorization=f543abf-0111-4061-9619-d41d665c59a6`

A saída mostra informações muito detalhadas sobre seu conteúdo. mboxTrace mostra detalhes sobre sua campanha ou atividade e perfil. Também fornece um instantâneo do perfil antes da execução, e um instantâneo do que foi alterado após a execução. Ela também mostra quais campanhas ou atividades foram avaliadas para cada local.

Algumas das informações incluem segmentos correspondentes ou não e IDs de direcionamento:

* **SegmentId**: as IDs dos segmentos, da biblioteca de segmentos reutilizáveis ou anônimas criadas para a campanha em particular.
* **TargetId**: as IDs dos direcionamentos, da biblioteca de expressões de destino ou de direcionamentos anônimos para qualquer segmento da campanha.
* **Unmatched**: a solicitação não estava qualificada nessa chamada para esses segmentos ou direcionamentos.
* **Matched**: a solicitação estava qualificada para os segmentos ou direcionamentos especificado.

**Uso do mboxTrace em páginas** do Recomendações: Adicionar mboxTrace como um parâmetro de query em páginas com recomendações substitui o design do Recommendations na página por uma janela de detalhes mboxTrace, que exibe informações detalhadas sobre suas recomendações, incluindo:

* Recommendations devolvidas em relação às recomendações solicitadas
* A chave usada e se está gerando recomendações
* Recommendations geradas por critérios em relação a recomendações de backup
* Configurações de critérios
* Exclusões e inclusões aplicadas
* Regras de coleção

Não é necessário incluir  `=console`, `=json` ou `=window` no parâmetro de consulta. Quando terminar com os detalhes do mboxTrace, adicione `=disable` e pressione **[!UICONTROL Enter]** para retornar ao modo normal de exibição.

mboxTrace não altera o funcionamento e a aparência normais do site. Os visitantes verão o design normal de recomendações.

## mboxDebug {#mboxdebug}

Para usar mboxDebug, inclua um parâmetro mboxDebug no fim do seu URL. A tabela a seguir contém informações sobre [!DNL Target] parâmetros de URL relacionados à resposta.

>[!NOTE]
>
>Alguns parâmetros de mboxDebug estão disponíveis com ou sem autenticação.

| Parâmetros de URL | Propósito |
|--- |--- |
| `mboxDebug=1` | Depurador<br>Adicionar este parâmetro a qualquer URL com solicitações de Público alvo definidas abre uma janela pop-up com detalhes de depuração importantes. Informações sobre cookies, PCid e valores de ID de sessão aparecem escritos e todos os URLs de são visíveis. Clique em um URL de solicitação de Público alvo para mostrar a resposta da solicitação [!DNL Target]. Mais detalhes estão disponíveis em [mbox_debug.pdf](/help/assets/mbox_debug.pdf). |
| `mboxDebug=x-cookie` | Modificar o cookie |
| `mboxDisable=1` | Desabilitar mboxes na página |
| `mboxDebug=x-profile` | Ver perfis definidos. |
| `mboxDebug=x-time` | Mostrar tempo de resposta para cada solicitação [!DNL Target] |
| `mboxOverride.browserIp=<Insert IP address>` | Testar geolocalização<br>Teste a geolocalização com este parâmetro de URL. Insira um endereço IP como o valor para este atributo e o geolocalização do Test&amp;Target avalia o endereço IP para compará-lo com qualquer geolocalização e segmentação configurados em uma campanha. |

>[!NOTE]
>
>Certifique-se de que o fragmento do URL esteja depois dos parâmetros da string de query. Qualquer coisa depois do primeiro `#` é um identificador de fragmento e faz com que os parâmetros de depuração não funcionem corretamente.

## Adobe Experience Cloud Debugger   {#section_A2798ED3A431409690A4BE08A1BFCF17}

Com o depurador da Adobe Experience Cloud é mais rápido e fácil entender a implementação do Target. Você pode visualizar rapidamente a configuração da biblioteca, examinar as solicitações para garantir que os parâmetros personalizados estão sendo passados corretamente, ativar o logon no console e desativar todas as solicitações do Target. Autentique para o Experience Cloud e você pode usar a poderosa ferramenta MboxTrace para inspecionar suas qualificações de atividade e audiência, bem como seu perfil de visitante.

Para obter mais informações, consulte os vídeos de treinamento abaixo:

Para obter informações mais detalhadas, consulte [Depurar at.js usando o depurador do Adobe Experience Cloud](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md).

## Se o target.js não for carregado durante a entrega {#section_ABBA5EFDFFB749D8BEE172DB1F973058}

O mbox.js envia um cookie chamado &quot;em-disabled&quot; para o visitante quando o target.js não é carregado durante a entrega. Este cookie evita que as ofertas criadas com o Visual Experience Composer sejam renderizadas no site. Os visitantes com esse cookie não veem o conteúdo do teste nem são contados nesses relatórios de atividades. Todo o conteúdo restante da oferta (por exemplo, das campanhas no Target Classic) continua sendo carregado. O cookie tem duração de 30 minutos a partir do momento da falha no carregamento.

## Os melhores vendedores não aparecem no Recommendations   {#section_3920C857270A406C80BE6CBAC8221ECD}

A chamada *`SiteCatalyst: purchase`* não pode ser usada para dados de tráfego do algoritmo de compra. Em vez disso, use a chamada *`orderConfirmPage`*.

## Verificar prioridade da atividade {#section_3D0DD07240F0465BAF655D0804100AED}

Atividades baseadas em formulário criadas com [!DNL Target Standard/Premium] podem colidir com atividades criadas na interface de usuário [!DNL Target Classic] com a mesma prioridade e usar a mesma solicitação [!DNL Target].

## O código personalizado não produz os resultados esperados no Internet Explorer 8. {#section_FAC3651F19144D12A37A3E4F14C06945}

O Target não é mais compatível com o IE8.

## O conteúdo JavaScript fornecido pela solicitação global [!DNL Target] não é carregado ao usar mbox.js. {#section_03EC9B9C410B4F52A7FCD81840311709}

Atualize para [!DNL mbox.js] versão 58 ou posterior.

mbox.js versão 58 e posterior executa conteúdo não JavaScript para a solicitação global [!DNL Target] imediatamente após a tag HTML `BODY` estar presente. O conteúdo do JavaScript nas tags `<script>` para a solicitação global [!DNL Target] é executado depois que o evento `DOMContentLoaded` é acionado. Essa ordem de delivery de conteúdo garante que o conteúdo JavaScript para a solicitação global [!DNL Target] seja entregue e renderizado corretamente.

## O cookie do público alvo não é definido {#section_77AFEB541C0B495EB67E29A4475DF960}

Se o seu site tiver um subdomínio, como [!DNL us.domain.com], mas você precisar que o cookie do esteja definido em [!DNL domain.com] (em vez de [!DNL us.domain.com]), você deve substituir a configuração `cookieDomain`. Para obter mais informações, consulte [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).

## O conteúdo do Target cintila ou não é mostrado caso um elemento também faça parte da personalização do AEM. {#section_9E1DABEB75AB431FB9F09887E6DD07D3}

Se um elemento DOM fizer parte da segmentação de personalização do Adobe Experience Manager (AEM) e de uma atividade do Target, o conteúdo do Target poderá cintilar ou não ser exibido.

Para resolver isso, você pode desativar a personalização do AEM nas páginas nas quais o Target está sendo executado.

## Falha no fornecimento de ofertas remotas e de redirecionamento devido a um URL inválido.   {#section_7D09043B687F43B39DAEDF17D00375AC}

Se a oferta remota ou de redirecionamento usar um URL inválido, poderá ocorrer uma falha no fornecimento.

Para ofertas de redirecionamento, a resposta [!DNL Target] pode conter `/* invalid redirect offer URL */`

Ou

Para ofertas remotas, a resposta [!DNL Target] pode conter `/* invalid remote offer URL */`

Você pode verificar a resposta [!DNL Target] no navegador ou usando mboxTrace. Consulte [https://tools.ietf.org/html/std66](https://tools.ietf.org/html/std66) para obter mais informações sobre URLs válidos.

## As solicitações de público alvo não estão sendo acionadas no meu site.

O at.js não aciona solicitações de Público alvo se você estiver usando um documento inválido. A at.js exige o doctype HTML 5.

## Vídeos de treinamento

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste artigo.

### Adicionar a extensão  ![Crachá do tutorial](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23114t2/)

### Depuração básica de Públicos alvos ![Etiqueta do tutorial](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23115t2/)

### Rastreamento de mbox ![Etiqueta do tutorial](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23113t2/)