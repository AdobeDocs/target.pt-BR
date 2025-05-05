---
keywords: depurar mbox;solucionar problemas de mbox;problemas de mbox;oscilação;mboxDebug;mboxTrace;token;depurador;prioridade;prioridade de atividade;Depurador da Adobe Experience Cloud;mbox orderConfirmPage;mbox de compra do SiteCatalyst;principal venda;vendedor principal
description: Encontre sugestões para ajudar a solucionar problemas se a página não exibir o conteúdo esperado. Saiba como depurar a entrega de conteúdo no Adobe Target.
title: Como posso solucionar problemas da entrega de conteúdo?
feature: Activities
exl-id: 887b7956-1d61-439a-8339-c150deb9a378
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '1622'
ht-degree: 87%

---

# Soluções de problemas da entrega de conteúdo

Se a página não exibir o conteúdo esperado, há algumas etapas que você pode seguir para depurar a entrega de conteúdo.

* Verifique seu código de campanha ou atividade cuidadosamente. Um erro de ortografia ou de outro tipo pode fazer com que o conteúdo esperado não seja exibido.
* Use mboxTrace ou mboxDebug para solucionar problemas da solicitação do [!DNL Target].
* Use o Adobe Experience Cloud Debugger, uma ferramenta fácil de usar que fornece praticamente as mesmas informações que o mboxDebug para solucionar problemas da solicitação do [!DNL Target].

O mboxDebug é particularmente útil quando você está configurando o [!DNL Target] na sua página para garantir que a solicitação do Target seja disparada e que o cookie seja configurado. No entanto, ela não entra no tipo de detalhes que são úteis durante a depuração da entrega de conteúdo. Se a sua atividade não aparecer na sua página ou se aparecer conteúdo indesejado, use mboxTrace para examinar e depurar a página atentamente.

## Recuperar o token de autorização para usar com ferramentas de depuração {#section_BED130298E794D1FA229DB7C3358BA54}

Como mboxTrace e mboxDebug podem expor dados de campanha e dados de perfil a terceiros, um token de autorização é necessário. O token de autorização pode ser recuperado na interface de usuário do [!DNL Target]. O token é válido por seis horas.

Você deve ter uma das seguintes permissões de usuário para gerar um token de autenticação:

* Pelo menos [!UICONTROL Editor] permissão (ou [!UICONTROL Approver])

  Para obter mais informações para clientes do [!DNL Target Standard], consulte [Especificar funções e permissões](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) em *Usuários*. Para obter mais informações para clientes do [!DNL Target Premium], consulte [Configurar permissões corporativas](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md).

* Função de administrador no nível de espaço de trabalho/perfil de produto

  Os espaços de trabalho estão disponíveis somente para clientes do [!DNL Target Premium]. Para obter mais informações, consulte [Configurar permissões corporativas](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md).

* Direitos de administrador (permissão de Sysadmin) no nível do produto [!DNL Adobe Target]

Para recuperar o token de autorização:

1. Clique em **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.
1. Na seção Ferramentas de Depuração, clique em **[!UICONTROL Generate New Authentication Token]**.

   ![Gerar novo token de autenticação](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/debugger-auth-token.png)

1. Adicione o token gerado como um parâmetro ao seu URL para ativar uma das ferramentas de depuração avançadas.

   ![Token de autorização](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/auth-token.png)

## mboxTrace {#section_256FCF7C14BB435BA2C68049EF0BA99E}

A mboxTrace permite que você receba informações de rastreamento anexadas a respostas do [!DNL Target]. As informações de rastreamento refletem o resultado de uma chamada do [!DNL Target] (por exemplo, uma conversão ou uma impressão) e dados adicionais que podem ajudar a determinar por que esse resultado particular aconteceu, como um conjunto de ramificações disponíveis dentre as quais a seleção foi feita em uma campanha. Use essas informações para depurar a entrega de conteúdo.

Os seguintes parâmetros estão disponíveis:

| Opções de mboxTrace | Saída |
|--- |--- |
| `?mboxTrace=console` | Imprime no log do console como objetos.<br>Para a at.js, em vez de abrir uma nova janela no navegador ou configurar a saída para o console como na mbox.js (descontinuada), é preciso inspecionar a solicitação de rede e procurar em Visualização (Chrome) ou Resposta (Firefox). |
| `?mboxTrace=json` | Imprime no log do console como sequência de caracteres JSON literal |
| `?mboxTrace=window` | Imprime em uma janela pop-up como uma sequência de caracteres JSON |
| `?mboxTrace=disable` | Desativa o rastreamento do modo de sessão |

**Exemplo de chamada de mboxTrace**

`https://www.mysite.com/page.html?mboxTrace=window&authorization=f543abf-0111-4061-9619-d41d665c59a6`

A saída exibe informações detalhadas sobre o conteúdo. O mboxTrace mostra detalhes sobre sua campanha ou atividade e perfil. Também fornece um instantâneo do perfil antes da execução, e um instantâneo do que foi alterado após a execução. Ela também mostra quais campanhas ou atividades foram avaliadas para cada local.

Algumas das informações incluem segmentos correspondentes ou não e IDs de direcionamento:

* **SegmentId**: as IDs dos segmentos, da biblioteca de segmentos reutilizáveis ou anônimas criadas para a campanha em particular.
* **TargetId**: as IDs dos direcionamentos, da biblioteca de expressões de destino ou de direcionamentos anônimos para qualquer segmento da campanha.
* **Unmatched**: a solicitação não estava qualificada nessa chamada para esses segmentos ou direcionamentos.
* **Matched**: a solicitação estava qualificada para os segmentos ou direcionamentos especificado.

**Uso da mboxTrace nas páginas de recomendações**: a adição da mboxTrace como um parâmetro de consulta em páginas com recomendações substitui o design do Recommendations na página por uma janela de detalhes da mboxTrace, que exibe informações detalhadas sobre suas recomendações, incluindo:

* Recomendações retornadas em relação às recomendações solicitadas
* A chave usada e se está gerando recomendações
* Recomendações geradas por critérios em relação a recomendações de backup
* Configurações de critérios
* Exclusões e inclusões aplicadas
* Regras de coleção

Não é necessário incluir `=console`, `=json` ou `=window` no parâmetro de consulta. Quando terminar com os detalhes do mboxTrace, adicione `=disable` e pressione **[!UICONTROL Enter]** para retornar ao modo normal de exibição.

mboxTrace não altera o funcionamento e a aparência normais do site. Os visitantes verão o design normal do Recommendations.

## mboxDebug {#mboxdebug}

Para usar mboxDebug, inclua um parâmetro mboxDebug no fim do seu URL. A tabela a seguir contém informações sobre parâmetros de URL relacionados à resposta do [!DNL Target].

>[!NOTE]
>
>Alguns parâmetros de mboxDebug estão disponíveis com ou sem autenticação.

| Parâmetros de URL | Propósito |
|--- |--- |
| `mboxDebug=1` | Depurador<br>A adição desse parâmetro a qualquer URL com solicitações do Target definidas abre uma janela pop-up com detalhes de depuração valiosos. Informações sobre cookies, PCid e valores de ID de sessão aparecem escritos e todos os URLs de são visíveis. Clique em um URL de solicitação do Target para mostrar a resposta à solicitação do [!DNL Target]. Mais detalhes estão disponíveis em [mbox_debug.pdf](/help/main/assets/mbox_debug.pdf). |
| `mboxDisable=1` | Desabilitar mboxes na página |
| `mboxOverride.browserIp=<Insert IP address>` | Testar geolocalização<br>Teste a geolocalização com este parâmetro de URL. Insira um endereço IP como o valor para este atributo e o geolocalização do Test&amp;Target avalia o endereço IP para compará-lo com qualquer geolocalização e segmentação configurados em uma campanha. |

>[!NOTE]
>
>Verifique se o fragmento do URL está após os parâmetros da sequência de consulta. Qualquer item depois do primeiro `#` é um identificador de fragmento e faz com que os parâmetros de depuração não funcionem corretamente.

## Adobe Experience Cloud Debugger  {#section_A2798ED3A431409690A4BE08A1BFCF17}

Com o depurador da Adobe Experience Cloud é mais rápido e fácil entender a implementação do Target. Você pode visualizar rapidamente a configuração da biblioteca, examinar as solicitações para garantir que os parâmetros personalizados estão sendo passados corretamente, ativar o logon no console e desativar todas as solicitações do Target. Faça a autenticação na Experience Cloud e use a ferramenta MboxTrace avançada para inspecionar as qualificações de atividade e público-alvo, bem como o perfil do visitante.

Para obter mais informações, consulte os vídeos de treinamento abaixo:

Para obter informações mais detalhadas, consulte [Depurar at.js usando o Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/target-debugging-atjs.html?lang=pt-BR){target=_blank}.

## Os melhores vendedores não aparecem no Recommendations  {#section_3920C857270A406C80BE6CBAC8221ECD}

A chamada *`SiteCatalyst: purchase`* não pode ser usada para dados de tráfego de algoritmo de compra. Em vez disso, use a chamada *`orderConfirmPage`*.

## Verificar prioridade da atividade {#section_3D0DD07240F0465BAF655D0804100AED}

As atividades com base em formulários criadas com o [!DNL Target Standard/Premium] podem entrar em conflito com atividades criadas na interface do [!DNL Target Classic] que têm a mesma prioridade e usam a mesma solicitação do [!DNL Target].

## O código personalizado não produz os resultados esperados no Internet Explorer 8. {#section_FAC3651F19144D12A37A3E4F14C06945}

O Target não é mais compatível com o IE8.

## O cookie do Target não é definido {#section_77AFEB541C0B495EB67E29A4475DF960}

Se o seu site tiver um subdomínio, como [!DNL us.domain.com], mas você precisar que o cookie do esteja definido em [!DNL domain.com] (em vez de [!DNL us.domain.com]), você deve substituir a configuração `cookieDomain`. Para obter mais informações, consulte [targetGlobalSettings()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetglobalsettings.html?lang=pt-BR){target=_blank}.

## O conteúdo do Target cintila ou não é exibido caso um elemento também faça parte da personalização do Adobe Experience Manager. {#section_9E1DABEB75AB431FB9F09887E6DD07D3}

Se um elemento DOM fizer parte da segmentação de personalização do Adobe Experience Manager (AEM) e de uma atividade do Target, o conteúdo do Target poderá cintilar ou não ser exibido.

Para resolver isso, você pode desativar a personalização do AEM nas páginas onde o Target estiver sendo executado.

## Falha no fornecimento de ofertas remotas e de redirecionamento devido a um URL inválido.  {#section_7D09043B687F43B39DAEDF17D00375AC}

Se a oferta remota ou de redirecionamento usar um URL inválido, poderá ocorrer uma falha no fornecimento.

Para ofertas de redirecionamento, a resposta do [!DNL Target] pode conter `/* invalid redirect offer URL */`

Ou

Para ofertas remotas, a resposta do [!DNL Target] pode conter `/* invalid remote offer URL */`

Você pode verificar a resposta do [!DNL Target] no navegador ou usando a mboxTrace. Consulte [https://tools.ietf.org/html/std66](https://tools.ietf.org/html/std66) para obter mais informações sobre URLs válidos.

## [!DNL Target]As solicitações do não estão sendo disparadas em meu site.

A at.js não disparará solicitações do Target se você estiver usando um tipo de documento inválido. A at.js exige o doctype HTML 5.

## Certifique-se de que as atividades do [!DNL Target] tratam corretamente os URLs com parâmetros de sequência de consulta. {#query-strings}

O [!UICONTROL Activity URL] determina a página que qualifica os visitantes para a atividade e renderiza as experiências da atividade para os usuários. Quando solicitado durante a criação da atividade, digitar o URL completo nem sempre garante que o conteúdo será entregue na página do site, especialmente com URLs que contenham parâmetros de sequência de consulta.

Por padrão, o [!UICONTROL Visual Experience Composer] (VEC) abre a página especificada nas suas [configurações do Visual Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md). Você também pode especificar uma página diferente durante a criação da atividade.

Para exibir uma página diferente após a abertura do VEC, clique em **[!UICONTROL Configure gear icon]** > selecione **[!UICONTROL Page Delivery]** > e especifique a URL desejada no campo [!UICONTROL Activity URL].

![Definir a interface das configurações de Entrega de página](assets/configure-page-delivery.png)

Mas e se o URL contiver parâmetros de sequência de consulta? Ele funcionará e mostrará o conteúdo personalizado? Nesse cenário, independentemente do público-alvo, é possível incluir regras de modelo, além do URL básico para definir os parâmetros de consulta.

As seguintes opções podem ser usadas para incluir regras de modelo adicionais:

### Opção 1: Replique o URL e mantenha-o na regra de modelo com a opção &quot;contém&quot;.

Essa opção garante que esse URL se qualifica para a atividade. Mas saiba que há casos de exceção anexados a ela que podem influenciar seus dados de relatório com registros adicionais para URLs que contêm o URL de base.

Nesse cenário, o URL é `https://shopping.mycart.com?type=Summers%20Offers` e regras de modelo adicionais “contêm” o mesmo URL, separado por um operador OU:

![Replicar o URL nas regras de modelo](assets/option1.png)

### Opção 2: Restrinja a condição &quot;contém&quot; do URL somente com a sequência de consulta.

O caso de exceção discutido na opção anterior é aplicado nesta opção, mas aqui a configuração condicional é limitada somente à sequência de consulta.

Nesse cenário, o URL é `https://shopping.mycart.com?type=Summers%20Offers` e as regras de modelo adicionais “contêm” somente a sequência de consulta, separadas por um operador OU:

![A regra de modelo contém somente a sequência de consulta](assets/option2.png)

### Opção 3: Em vez de direcionar o URL completo, aproveite uma parte específica do URL.

Nesse cenário, a URL é `https://shopping.mycart.com?type=Summers%20Offers` e regras de modelo adicionais especificam um [!UICONTROL Query] com [!UICONTROL type] > [!UICONTROL is (case sensitive)] > type=Summers%20Offers, separadas por um operador OU:

![Regra de modelo aproveitando uma parte específica do URL](assets/option3.png)

## Evitar aspas duplas no valor do atributo de perfil [!DNL Target] não está funcionando como o esperado. {#escape}

Quando você envia valores contendo aspas duplas em um atributo de perfil [!DNL Target], você deve usar o escape duplo como mostrado abaixo.

```
adobe.target.trackEvent({
    "mbox": "data-collection",
    "params":    {
        "profile.tagLine": "Escape \\\"Double Quotes\\\" like this."
    }
});
```

## Vídeos de treinamento

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste artigo.

### Adicione a Extensão ![Selo do tutorial](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/33296?captions=por_br)

### Depuração básica do Adobe Target ![Selo do tutorial](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/33298?captions=por_br)

### Mbox Trace ![Selo do tutorial](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/33345?captions=por_br)
