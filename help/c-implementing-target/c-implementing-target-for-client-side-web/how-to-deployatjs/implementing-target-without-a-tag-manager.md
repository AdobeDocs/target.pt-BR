---
keywords: implement target;implementation;implement at.js;tag manager
description: Informações sobre como implementar o Adobe Target sem usar um gerenciador de tags (Adobe Launch ou Dynamic Tag Management).
title: Implementação do Target sem um gerenciador de tags
feature: implementation general
subtopic: Getting Started
topic: Standard
uuid: 3ecc041a-42d8-40f8-90be-7856e1d3d080
translation-type: tm+mt
source-git-commit: f3877d05d583bdb4690a2638efd874bbfff6154e
workflow-type: tm+mt
source-wordcount: '1539'
ht-degree: 70%

---


# Implementação do Target sem um gerenciador de tags{#implement-target-without-a-tag-manager}

Information about implementing [!DNL Adobe Target] without using a tag manager ([!DNL Adobe Launch] or [!DNL Dynamic Tag Manager]).

>[!NOTE]
>
>[O Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) é o método preferido para a implementação do Target e da biblioteca at.js. As informações a seguir não são aplicáveis quando o Adobe Launch é usado para implementar o Target.

Para acessar a página [!UICONTROL Implementação] , clique em **[!UICONTROL Administração]** > **[!UICONTROL Implementação]**.

Você pode especificar as seguintes configurações nesta página:

* Detalhes da conta
* Métodos de implementação
* API do perfil
* Ferramentas do depurador
* Privacidade

>[!NOTE]
>
>É possível substituir as configurações na biblioteca at.js em vez de definir as configurações na interface do usuário do Target Standard/Premium ou usar APIs REST. Para obter mais informações, consulte [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).

## Detalhes da conta

Você pode visualização os seguintes detalhes de conta. Essas configurações não podem ser alteradas.

| Configuração | Descrição |
| --- | --- |
| Código do cliente | O código do cliente é uma sequência específica do cliente de caracteres frequentemente necessários ao usar as APIs do Target. |
| ID da organização IMS | Essa ID vincula sua implementação à sua conta da [!DNL Adobe Experience Cloud]. |

## Métodos de implementação

As seguintes configurações podem ser definidas no painel Métodos de implementação:

### Configurações globais

>[!NOTE]
>
>Essas configurações são aplicadas a todas as bibliotecas [!DNL Target] .js. Depois de fazer alterações na seção Métodos [!UICONTROL de] implementação, é necessário baixar a biblioteca e atualizá-la na implementação.

| Configuração | Descrição |
| --- | --- |
| Carregamento de página ativado (Criar mbox global automaticamente) | Selecione se a chamada mbox global no arquivo at.js deve ser acionada automaticamente em cada carregamento de página. |
| Mbox global | Selecione um nome para a mbox global. Como padrão, esse nome é target-global-mbox.<br>Caracteres especiais, incluindo o sinal gráfico (&amp;), podem ser usados em nomes de mbox com a at.js. |
| Tempo limite (segundos) | Se o [!DNL Target] não responder ao conteúdo no período definido, o tempo limite da chamada do servidor acaba e o conteúdo padrão é exibido. Ainda há tentativas de chamadas adicionais durante a sessão do visitante. O limite padrão é de 5 segundos.<br>A biblioteca at.js usa a configuração de tempo limite em `XMLHttpRequest`. O tempo limite começa quando a solicitação é acionada e para quando [!DNL Target] recebe uma resposta do servidor. Para obter mais informações, consulte [XMLHttpRequest.timeout](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/timeout) no site Mozilla Developer Network.<br>Se o tempo limite especificado ocorrer antes de receber uma resposta, o conteúdo padrão é mostrado e o visitante pode ser contabilizado como um participante em uma atividade, pois toda a coleta de dados acontece na borda do [!DNL Target]. Se a solicitação alcançar a borda do [!DNL Target], o visitante é contabilizado.<br>Leve em consideração o seguinte ao configurar o tempo limite:<ul><li>Se o valor for muito baixo, os usuários podem visualizar o conteúdo padrão na maioria das vezes, embora o visitante possa ser contabilizado como participante na atividade.</li><li>Se o valor for muito alto, os visitantes podem ver regiões em branco na sua página da Web, ou páginas em branco se você ocultar o corpo por períodos prolongados.</li></ul>Para obter uma compreensão melhor dos tempos de resposta do mbox, olhe a guia Rede nas Ferramentas de desenvolvedor do navegador. Você também pode usar ferramentas de monitoramento de desempenho na Web de terceiros, como Catchpoint.<br>**Observação**: A configuração [visitorApiTimeout](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) garante que o [!DNL Target] não espere a resposta da API do visitante por muito tempo. Essa configuração e a configuração de Tempo limite para at.js descrita aqui não são conflitantes. |
| Duração do perfil | Essa configuração determina a duração de armazenamento do perfil do visitante. Por padrão, os perfis são armazenados por duas semanas. Isso pode ser aumentado para até 90 dias.<br>Para alterar a configuração de Duração do perfil, entre em contato com o [Atendimento ao cliente](https://helpx.adobe.com/br/contact/enterprise-support.ec.html). |

### Método de implementação principal

>[!IMPORTANT]
>
>A equipe do Público alvo oferece suporte para o at.js 1.*x* e at.js 2.*x*. Atualize para a atualização mais recente da versão principal do at.js para garantir que você esteja executando uma versão compatível.

Para baixar a versão desejada do at.js, clique no botão **[!UICONTROL Download]** apropriado.

Para editar as configurações do at.js, clique em **[!UICONTROL Editar]** ao lado da versão desejada do at.js.

>[!IMPORTANT]
>
>Antes de alterar essas configurações padrão, consulte o [Client Care](/help/cmp-resources-and-contact-information.md) para não afetar sua implementação atual.

Além das configurações explicadas acima, as seguintes configurações específicas do at.js também estão disponíveis:

| Configuração | Descrição |
|--- |--- |
| Cabeçalho da biblioteca personalizada | Adicione qualquer JavaScript personalizado para incluir na parte superior da biblioteca. |
| Rodapé da biblioteca personalizada | Adicione qualquer JavaScript personalizado para incluir na parte inferior da biblioteca. |

### API do perfil

Ative ou desative a autenticação para atualizações em lote pela API e gere um token de autenticação de perfil.

For more information, see [Profile API settings](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/profile-api-settings.md).

### Ferramentas do depurador

Gere um token de autorização para usar ferramentas de [!DNL Target] depuração avançadas. Click **[!UICONTROL Generate New Authentication Token]**.

![Gerar novo token de autenticação](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/debugger-auth-token.png)

### Privacidade

Essas configurações permitem que você use de acordo [!DNL Target] com as leis de privacidade de dados aplicáveis.

Escolha a configuração desejada na lista suspensa Ofuscar endereço IP do Visitante:

* Última ofuscação de octeto
* Ofuscação de IP inteira
* None

Para obter mais informações, consulte [Privacidade](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md).

>[!NOTE]
>
>A opção Suporte a navegador herdado estava disponível no at.js versão 0.9.3 e anterior. Essa opção foi removida na at.js versão 0.9.4. Para obter uma lista de navegadores suportados at.js, consulte [Navegadores suportados](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md)<br>Os navegadores herdados são navegadores antigos que não suportam completamente CORS (Cross Origin Resource Sharing). Esses navegadores incluem: Internet Explorer em versão anterior a 11 e Safari versões 6 e anteriores. Se o suporte a navegador herdado estivesse desativado, o Público alvo não forneceria conteúdo ou contaria visitantes nos relatórios desses navegadores. Se essa opção estiver ativada, é recomendável fazer o controle de qualidade em navegadores mais antigos para garantir uma boa experiência do cliente.

## Baixe a at.js {#concept_1E1F958F9CCC4E35AD97581EFAF659E2}

Instructions to download the library using the [!DNL Target] interface or the Download API.

>[!NOTE]
>
>* [O Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) é o método preferido para a implementação do Target e da biblioteca at.js. As informações a seguir não são aplicáveis quando o Adobe Launch é usado para implementar o Target.
   >
   >
* A equipe do Público alvo oferece suporte para o at.js 1.*x* e at.js 2.*x*. Atualize para a atualização mais recente da versão principal do at.js para garantir que você esteja executando uma versão compatível. Para obter mais informações sobre o que há de novo em cada versão, consulte [Detalhes da versão da at.js](../../../c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A).


### Download at.js using the Target interface {#section_1F5EE401C2314338910FC57F9592894E}

Para baixar a [!DNL at.js] na interface do [!DNL Target]:

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Implementação]**.
1. Na seção Métodos [!UICONTROL de] implementação, clique no botão **[!UICONTROL Download]** ao lado da versão desejada para at.js.

### Download at.js using the Target Download API {#section_C0D9D2A9068144708D08526BA5CA10D0}

Para baixar a [!DNL at.js] usando a API.

1. Obtenha o seu código de cliente.

   Your client code is available at the top of the **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** page of the [!DNL Target] interface.

1. Obtenha o seu número de administrador.

   Carregue este URL:

   ```
   https://admin.testandtarget.omniture.com/rest/v1/endpoint/<varname>client code</varname>
   ```

   Replace `client code` with the client code from Step 1.

   O resultado do carregamento deste URL deve ser semelhante ao seguinte exemplo:

   ```
   { 
     "api": "https://admin6.testandtarget.omniture.com/admin/rest/v1" 
   }
   ```

   Neste exemplo, &quot;6&quot; é o número do administrador.

1. Baixar [!DNL at.js].

   Carregue este URL com a seguinte estrutura:

   ```
   https://admin<varname>admin number</varname>.testandtarget.omniture.com/admin/rest/v1/libraries/atjs/download?client=<varname>client code</varname>&version=<version number>
   ```

   * Replace `admin number` with your admin number.
   * Replace `client code` with the client code from Step 1.
   * Replace `version number` with the desired at.js version number (for example, 2.2).

   >[!IMPORTANT]
   >
   >A equipe do Target mantém apenas duas versões de [!DNL at.js]—a versão atual e a segunda versão mais recente. Atualize a [!DNL at.js] conforme necessário para garantir que você esteja executando uma versão suportada. Para obter mais informações sobre o que há de novo em cada versão, consulte [Detalhes da versão da at.js](../../../c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A).

   O carreamento deste URL inicia o download do arquivo da [!DNL at.js] personalizado.

## at.js implementation {#concept_03CFA86973A147839BEB48A06FEE5E5A}

A at.js deve ser implementada no elemento `<head>` de cada página do site.

Uma implementação típica do Target que não usa um gerenciador de tags como o [Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) ou [Dynamic Tag Management](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-using-dynamic-tag-management.md#concept_3A40AF6FFC0E4FD2AA81B303A79D0B96) é semelhante a:

```
<!doctype html> 
<html> 
<head> 
    <meta charset="utf-8"> 
    <title>Title of the Page</title> 
    <!--Preconnect and DNS-Prefetch to improve page load time--> 
    <link rel="preconnect" href="//<client code>.tt.omtrdc.net"> 
    <link rel="dns-prefetch" href="//<client code>.tt.omtrdc.net"> 
    <!--/Preconnect and DNS-Prefetch--> 
    <!--Data Layer to enable rich data collection and targeting--> 
    <script> 
        var digitalData = { 
            "page": { 
                "pageInfo": { 
                    "pageName": "Home" 
                } 
            } 
        }; 
    </script> 
    <!--/Data Layer--> 
    <!-- targetPageParams(), targetPageParamsAll(), Data Providers or targetGlobalSettings() functions to enrich the visitor profile or modify the library settings--> 
    <script> 
        targetPageParams = function() { 
            return { 
                "a": 1, 
                "b": 2, 
                "pageName": digitalData.page.pageInfo.pageName, 
                "profile": { 
                    "age": 26, 
                    "country": { 
                        "city": "San Francisco" 
                    } 
                } 
            }; 
        }; 
    </script> 
    <!--/targetPageParams()--> 
 
    <!--jQuery or other helper libraries should be implemented before at.js if you would like to use their methods in Target--> 
    <script src="jquery-3.3.1.min.js"></script> 
    <!--/jQuery--> 
    <!--Target's JavaScript SDK, at.js--> 
    <script src="at.js"></script> 
    <!--/at.js--> 
</head>
<body> 
    The default content of the page 
</body> 
</html>
```

Considere as informações importantes a seguir:

* O HTML5 Doctype (por exemplo, `<!doctype html>`) deve ser usado. Doctypes não compatíveis ou mais antigos poderiam imperdir o Target de fazer uma solicitação.
* Pré-conectar e Buscar previamente são opções que podem auxiliar no carregamento mais rápido das páginas da Web. If you use these configurations, ensure that you replace `<client code>` with your own client code, which you can obtain from the **[!UICONTROL Administration]** > **[!UICONTROL Implementation] page.
* Se você tiver uma camada de dados, é ideal definir o máximo dela possível em `<head>` das suas páginas, antes dos carregamentos da at.js. Esse posicionamento fornece a capacidade máxima de aproveitar essas informações no Target para personalização.
* As funções especiais do Target, como `targetPageParams()`, `targetPageParamsAll()`, Provedores de dados e `targetGlobalSettings()` devem ser definidas após a camada de dados e antes dos carregamentos da at.js. Como alternativa, é possível salvá-las na seção [!UICONTROL Cabeçalho da biblioteca] da página [!UICONTROL Editar configurações da at.js] e como parte da própria biblioteca at.js. Para obter mais informações sobre essas funções, consulte  [Funções da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md).
* Se você usar as bibliotecas auxiliares do JavaScript, como jQuery, inclua-as antes do Target, para que possa aproveitar a sintaxe e métodos delas ao criar as experiências do Target.
* Inclua a at.js no `<head>` das suas páginas.

## Track conversions {#task_E85D2F64FEB84201A594F2288FABF053}

A mbox de confirmação de pedido registra detalhes sobre pedidos no seu site e permite a geração de relatórios baseados em receita e pedidos. A mbox de confirmação de pedido também pode impulsionar algoritmos de recomendação, como &quot;Pessoas que compraram o produto x também compraram o produto y&quot;.

>[!NOTE]
>
>Se usuários fazem compras no seu site, recomendamos implementar uma mbox de confirmação de pedido mesmo se você usar Analytics for Target (A4T) como seu gerador de relatórios.

1. Na página de detalhes do pedido, insira o script da mbox seguindo o modelo abaixo.
1. Substitua as PALAVRAS EM LETRAS MAIÚSCULAS por valores dinâmicos ou estáticos do seu catálogo.

   >[!NOTE]
   >
   >Utilize delimitação por vírgulas para separar várias IDs de produto.

   **Dica:** você também pode passar informações de pedido em qualquer mbox (ela não precisa ser chamada `orderConfirmPage`). Também é possível passar informações de pedidos em várias mboxes dentro da mesma campanha.

   ```
   <script type="text/javascript"> 
   adobe.target.trackEvent({ 
       "mbox": "orderConfirmPage", 
       "params":{  
           "orderId": "ORDER ID FROM YOUR ORDER PAGE",  
           "orderTotal": "ORDER TOTAL FROM YOUR ORDER PAGE",  
           "productPurchasedId": "PRODUCT ID FROM YOUR ORDER PAGE, PRODUCT ID2, PRODUCT ID3"  
       } 
   }); 
   </script> 
   ```

A mbox de confirmação de pedido utiliza os seguintes parâmetros:

| Parâmetro | Descrição |
|--- |--- |
| orderId | Valor único para identificar um pedido de contagem de conversão.<br>O `orderId` deve ser único. Pedidos duplicados são ignorados em relatórios. |
| orderTotal | Valor monetário para a compra.<br>Não passe o símbolo de moeda. Use um ponto (não uma vírgula) para indicar valores decimais. |
| productPurchasedId (Opcional) | Lista separada por vírgula de IDs de produtos comprados no pedido.<br>Essas IDs de produtos são exibidas no relatório de auditoria para suportar análises de relatório adicionais. |