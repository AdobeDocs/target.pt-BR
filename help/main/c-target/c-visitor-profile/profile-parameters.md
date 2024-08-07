---
keywords: Script de perfil;atributos do script de perfil;práticas recomendadas do script de perfil;depurar;depuração;scripts;scripts de perfil;atributos;atributo;parâmetro
description: Saiba mais sobre os atributos específicos do visitante armazenados no perfil do visitante para fornecer informações sobre o que pode ser usado em atividades do Adobe [!DNL Target] .
title: O que são atributos de perfil?
feature: Audiences
exl-id: 6c689629-bbd3-461e-9a68-5b16d4eb4250
source-git-commit: 356b04745b58670b4bf39be929e785b8490d78ff
workflow-type: tm+mt
source-wordcount: '2426'
ht-degree: 93%

---

# Atributos do perfil

Os atributos do perfil no [!DNL Adobe Target] são parâmetros específicos de um visitante. Estes atributos são armazenados no perfil do visitante para fornecer informações sobre ele que podem ser usadas em suas atividades.

Um perfil de usuário contém informações demográficas e comportamentais de um visitante da página da Web. Essas informações podem incluir idade, gênero, produtos comprados, última visita e assim por diante. O [!DNL Target] usa essas informações para personalizar o conteúdo que ele disponibiliza para esse visitante.

Conforme um visitante navega no site, ou quando ele retorna para uma outra sessão, os atributos do perfil salvos podem ser usados para segmentar o conteúdo ou registrar informações para a filtragem de segmentos.

Para configurar atributos do perfil:

1. Clique em **[!UICONTROL Audiences]** > **[!UICONTROL Profile Scripts.]**

   ![Guia Scripts de perfil](/help/main/c-target/c-visitor-profile/assets/create-script.png)

1. Clique em **[!UICONTROL Create Script]**.

   ![Caixa de diálogo Criar scripts de perfil](/help/main/c-target/c-visitor-profile/assets/profile-script.png)

   Os tipos a seguir de atributos de perfil estão disponíveis:

   | Tipo do parâmetro | Descrição |
   |--- |--- |
   | mbox | Passado diretamente pelo código de página ao criar a mbox. Consulte [Transmitir parâmetros para uma Mbox global](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/global-mbox/pass-parameters-to-global-mbox.html?lang=pt-BR){target=_blank} no *Guia do desenvolvedor do Target*.<P>**Observação**: o [!DNL Target] tem um limite de 50 atributos de perfil exclusivos por chamada de mbox. Se você precisar passar mais de 50 atributos de perfil para [!DNL Target], passe-os usando o método [!UICONTROL Profile Update API]. Para obter mais informações, consulte [Atualizar perfis](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-api-overview.html?lang=pt-BR){target=_blank} no *Guia do desenvolvedor do Target*. |
   | Perfil | Definido diretamente com um trecho de código JavaScript. Esses snippets podem armazenar totais em execução, como o dinheiro total gasto pelo consumidor, e são executados em cada solicitação mbox. Consulte *Atributos de script de perfil* abaixo. |

## Atributos de script de perfil {#concept_8C07AEAB0A144FECA8B4FEB091AED4D2}

Defina um atributo de perfil de script com o snippet do código JavaScript associado.

Você pode usar scripts de perfil para capturar os atributos do visitante em várias visitas. Os scripts de perfil são snippets de código definidos no [!DNL Target] usando um formulário de JavaScript do lado do servidor. Por exemplo, você pode usar um script de perfil para capturar com que frequência um visitante entra no seu site e quando ele visitou pela última vez.

Os scripts de perfil não são os mesmos que os parâmetros de perfil. Os parâmetros de perfil capturam as informações sobre visitantes que usam a implementação do código de mbox do [!DNL Target].

## Criar scripts de perfil {#section_CB02F8B97CAF407DA84F7591A7504810}

Os scripts de perfil estão disponíveis na guia [!UICONTROL Audiences] da interface [!DNL Target].

Para adicionar um script de perfil, clique na guia **[!UICONTROL Profile Scripts]**, **[!UICONTROL Create Script]**, em seguida, escreva o script.

Ou

Para copiar um script de perfil existente, na lista [!UICONTROL Profile Scripts], clique no ícone de reticências do script desejado e clique em **[!UICONTROL Duplicate]**.

Você pode editar o público-alvo para criar um público-alvo semelhante.

Scripts de perfil executam os &quot;coletores&quot; de atributo de perfil em cada solicitação de localização. Quando uma solicitação de local é recebida, o [!DNL Target] determina qual atividade deve ser executada e exibe o conteúdo apropriado para essa atividade e para essa experiência. O [!DNL Target] também rastreia o sucesso da atividade e executa qualquer script de perfil relevante. Esse processo rastreia as informações sobre a visita, como o local do visitante, a hora do dia, o número de vezes que o visitante acessou o site, se ele já fez alguma compra anteriormente etc. Estas informações são então adicionadas ao perfil do visitante para que você possa melhor rastrear a atividade do visitante no seu site.

Os atributos de script de perfil têm a tag de `user.` inserida antes dos nomes dos atributos. Por exemplo:

```
if (mbox.name == 'Track_Interest') { 
    if (profile.get('model') == "A5" &&; profile.get('subcat') == "KS6") { 
        return (user.get('A5KS6') || 0) + 1; 
    } 
}
```

Lembre-se da seguinte informação:

* Consulte os atributos de script do perfil (incluindo ele mesmo) no código com `user.get('parameterName')`.
* Salve variáveis que podem ser acessadas na próxima vez que o script for executado (na própria solicitação da mbox) com o `user.setLocal('variable_name', 'value')`. Faça referência à variável com `user.getLocal('variable_name')`. Esse processo é útil para situações em que você deseja fazer referência à data e hora da última solicitação.

  Esses valores persistem como um script de perfil, mas você só tem acesso a eles dentro do script em que foram definidos.

* Os parâmetros e valores diferenciam maiúsculas de minúsculas. Verifique as letras maiúsculas e minúsculas e os valores que você recebe durante a atividade ou o teste.
* Consulte a seção &quot;Referência de JavaScript para os parâmetros do perfil de script&quot; abaixo para obter mais sintaxe de JavaScript.
* O parâmetro permanece no perfil após desabilitar o script. Os usuários cujos perfis já contêm um parâmetro que é usado no público-alvo de uma atividade são qualificados nessa atividade.
* Os scripts de perfil não podem ser excluídos enquanto estiverem sendo usados em uma atividade.
* Não é recomendado criar scripts de perfil dependentes que usem o resultado de um script de perfil em outro script de perfil. A ordem de execução do script de perfil não é garantida.

## Exibição dos cartões de informações do script de perfil {#section_18EA3B919A8E49BBB09AA9215E1E3F17}

Você pode exibir os cartões pop-up com as informações do script de perfil de forma semelhante aos cartões com as informações da oferta. Esses cartões com as informações do script de perfil permitem exibir a lista de atividades que fazem referência ao script de perfil selecionado, juntamente com outros metadados úteis.

Por exemplo, o cartão de informações do script de perfil a seguir é acessado clicando no ícone [!UICONTROL Info] do script de perfil desejado na lista ([!UICONTROL Audiences] > [!UICONTROL Profile Scripts]).

A guia [!UICONTROL Script Info] contém as seguintes informações: Nome, Descrição e código de script.

![Cartão de informações do script de perfil](assets/profile_script_info_card.png)

Clique em **[!UICONTROL View full details]** para ver os públicos-alvo e as atividades que fazem referência ao script de perfil selecionado.

![Cartão de informações do script de perfil > guia Uso do script](assets/profile_script_info_card_usage_tab.png)

>[!NOTE]
>
>A guia [!UICONTROL Script Usage] não exibe atividades que referenciam o script de perfil selecionado nas seguintes situações:
>
> * A atividade está no estado [!UICONTROL Draft].
> * O conteúdo ou a oferta usada na atividade utiliza variáveis de script (seja uma oferta na linha dentro da atividade ou dentro da biblioteca Oferta).

## O Target desativa os scripts de perfil em determinadas situações {#section_C0FCB702E60D4576AD1174D39FBBE1A7}

O [!DNL Target] desativa automaticamente os scripts de perfil em determinadas situações, como em caso de demora para execução ou de excesso de instruções.

Quando um script de perfil é desativado, um ícone de alerta amarelo é exibido perto do script de perfil na interface do Target, conforme ilustrado abaixo:

![imagem profile_script_invalid](assets/profile_script_invalid.png)

Ao passar o cursor do mouse, os detalhes do erro são exibidos, conforme ilustrado abaixo:

![imagem profile_script_hover](assets/profile_script_hover.png)

Os motivos típicos para o sistema desativar os scripts de perfil incluem o seguinte:

* Uma variável indefinida a ser referenciada.
* Um valor inválido é referenciado. Esse erro geralmente é causado pela referência a valores de URL e outros dados inseridos pelo usuário sem a validação adequada.
* Muitas instruções de JavaScript usadas. O [!DNL Target] tem um limite de 2.000 instruções de JavaScript por script, mas isso não pode ser calculado somente pela leitura manual do JavaScript. Por exemplo, o Rhino trata todas as chamadas de função e as &quot;novas&quot; chamadas como 100 instruções. Qualquer chamada para qualquer função consome 100 instruções. Além disso, o tamanho dos dados de entrada, como os valores de URL, pode afetar a contagem das instruções.
* Não seguir os itens destacados na seção [Práticas recomendadas](/help/main/c-target/c-visitor-profile/profile-parameters.md#section_64AFE5D2B0C8408A912FC2A832B3AAE0) abaixo.

## Práticas recomendadas {#best}

As orientações a seguir destinam-se a ajudar a escrever scripts de perfil simplificados que são os mais livres de erros possíveis, ao escrever código com falhas leves, para que os scripts sejam processados sem forçar uma interrupção do script do sistema. Essas orientações resultam das práticas recomendadas com execução eficaz comprovada. Essas diretrizes devem ser aplicadas juntamente com os princípios e as recomendações formulados pela comunidade de desenvolvimento Rhino.

* Defina o valor do script atual para uma variável local no script do usuário, defina um failover para a sequência de caracteres em branco.
* Valide a variável local, certificando-se de que ela não seja uma sequência de caracteres em branco.
* Use funções de manipulação com base em sequências de caracteres x Expressões regulares.
* Use limitado para loops e abertos para ou enquanto nos loops.
* Não exceda 1.300 caracteres ou 50 iterações de loop.
* Não exceda 2.000 instruções do JavaScript. O [!DNL Target] tem um limite de 2.000 instruções de JavaScript por script, mas isso não pode ser calculado somente pela leitura manual do JavaScript. Por exemplo, o Rhino trata todas as chamadas de função e as &quot;novas&quot; chamadas como 100 instruções. Além disso, o tamanho dos dados de entrada, como os valores de URL, pode afetar a contagem das instruções.
* Lembre-se não apenas do desempenho do script, mas do desempenho combinado de todos os scripts. Como prática recomendada, o [!DNL Adobe] sugere menos de 5.000 instruções no total. Contar o número de instruções não é óbvio, mas o importante a ser observado é que scripts com mais de 2.000 instruções são desabilitados automaticamente. O número de scripts de perfil ativos não deve exceder 300.. Cada script é executado com cada chamada de mbox. Execute somente a quantidade de scripts necessária.
* Em um regex, ter ponto-estrela no início (por exemplo: `/.*match/`, `/a|.*b/`) quase nunca é necessário. A pesquisa de regex começa em todas as posições em uma string (a menos que vinculada a `^`), portanto, o ponto-estrela já foi considerado. A execução do script pode ser interrompida se esse regex corresponder a dados de entrada longos o suficiente (que podem ter centenas de caracteres).
* Se tudo falhar, envolva o script em um try/catch.
* As recomendações a seguir podem ajudar a limitar a complexidade do script de perfil. Os scripts de perfil podem executar um número limitado de instruções.

  Como prática recomendada:

   * Mantenha os scripts de perfil pequenos e o mais simples possível.
   * Evite expressões regulares ou use somente expressões regulares simples. Até mesmo expressões simples podem fazer com que muitas instruções sejam avaliadas.
   * Evite a recursão.
   * Os scripts de perfil devem ser testados em relação ao desempenho antes de serem adicionados ao [!DNL Target]. Todos os scripts de perfil são executados em cada solicitação de mbox. Se os scripts de perfil não forem executados corretamente, as solicitações da mbox levarão mais tempo para serem executadas, o que pode afetar o tráfego e a conversão.
   * Se os scripts de perfil se tornarem muito complexos, considere usar [tokens de resposta](/help/main/administrating-target/response-tokens.md).

* Consulte a documentação do mecanismo JS Rhino para obter mais informações.

## Depurar scripts de perfil {#section_E9F933DE47EC4B4E9AF2463B181CE2DA}

Os métodos a seguir podem ser usados para depurar scripts de perfil:

>[!NOTE]
>
>Usar o [!DNL console.log] em um script de perfil não resultará no valor do perfil, pois os scripts de perfil são executados no lado do servidor.

* **Adicionar scripts de perfil como tokens de resposta para depurar scripts de perfil:**

  Em [!DNL Target], clique em **[!UICONTROL Administration]**, clique em **[!UICONTROL Response Tokens]** e habilite o script de perfil que deseja depurar.

  Sempre que carregar uma página para o site com [!DNL Target] nela, parte da resposta do [!DNL Target] conterá o valor para o script de perfil específico, como mostrado abaixo:

  ![imagem debug_profile_script_1](assets/debug_profile_script_1.png)

* **Use a ferramenta de depuração mboxTrace para depurar scripts de perfil.**

  Este método requer um token de autorização que pode ser gerado clicando em **[!UICONTROL Target]** > **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** > **[!UICONTROL Generate Authorization Token]** na seção [!UICONTROL Debugger tools].

  Em seguida, você adiciona esses dois parâmetros ao URL da página após o “?”: `mboxTrace=window&authorization=YOURTOKEN`.

  Adicionar esses parâmetros é um pouco mais informativo do que o token de resposta porque você obtém um instantâneo antes da execução e um instantâneo posterior do seu perfil. Ele também mostra todos os perfis disponíveis.

  ![imagem debug_profile_script_2](assets/debug_profile_script_2.png)

## Perguntas frequentes do script de perfil {#section_1389497BB6D84FC38958AE43AAA6E712}

**É possível usar os scripts de perfil para capturar informações de uma página localizada em uma camada de dados?**

Os scripts de perfil não podem ler a página diretamente porque são executados no lado do servidor. Os dados devem ser enviados por uma solicitação de mBox ou por meio de outros [métodos de inserção de dados no Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=pt-BR){target=_blank}. Depois que os dados estiverem no [!DNL Target], os scripts de perfil poderão ler os dados como um parâmetro mbox ou parâmetro de perfil.

## Referência de JavaScript para os parâmetros do perfil de script

O conhecimento simples de Javascript é necessário para usar efetivamente os parâmetros de perfil de script. Esta seção serve como uma referência rápida para torná-lo produtivo com essa funcionalidade em apenas alguns minutos.

Os parâmetros do perfil de script são encontrados na guia mboxes/perfis. É possível gravar programas de JavaScript que retornam qualquer tipo de JavaScript (sequência de caracteres, inteiro, matriz, etc.).

### Exemplos de parâmetro do perfil de script {#examples}

**Nome:** *user.recency*

```
var dayInMillis = 3600 * 24 * 1000;
if (mbox.name == 'orderThankyouPage') {
    user.setLocal('lastPurchaseTime', new Date().getTime());
}
var lastPurchaseTime = user.getLocal('lastPurchaseTime');
if (lastPurchaseTime) {
    return ((new Date()).getTime() - lastPurchaseTime) / dayInMillis;
}
```

Cria uma variável para o dia, conforme medido em milissegundos. Se o nome da mbox for `orderThankyouPage`, defina um atributo do perfil de usuário local (invisível) chamado `lastPurchaseTime` para receber o valor da data e hora atuais. O valor do último horário de compra é lido e, se estiver definido, o [!DNL Target] retorna o tempo desde a última compra, divido pelo número de milissegundos em um dia (o que resulta no número de dias desde a última compra).

**Nome:** *user.frequency*

```
var frequency = user.get('frequency') || 0;
if (mbox.name == 'orderThankyouPage') {
    return frequency + 1;
}
```

Cria uma variável chamada `frequency`, inicializando-a para o valor anterior ou 0, se não houver um valor anterior. Se o nome da mbox for `orderThankyouPage`, o valor incrementado será retornado.

**Nome:** *user.monetaryValue*

```
var monetaryValue = user.get('monetaryValue') || 0;
if (mbox.name == 'orderThankyouPage') {
    return monetaryValue + parseInt(mbox.param('orderTotal'));
}
```

Cria uma variável chamada `monetaryValue`, que pesquisa o valor atual de um determinado visitante (ou define como 0 se não houver um valor anterior). Se o nome da mbox for `orderThankyouPage`, o novo valor monetário será retornado adicionando o anterior e o valor do parâmetro `orderTotal` passado para a mbox.

**Nome:** adobeQA

```
if (page.param("adobeQA"))
     return page.param("adobeQA");
else if (page.param("adobeqa"))
     return page.param("adobeqa");
else if (mbox.param("adobeQA"))
     return mbox.param("adobeQA");
```

Cria uma variável chamada `adobeQA` para rastrear um usuário para [Controle de qualidade da atividade](/help/main/c-activities/c-activity-qa/activity-qa.md).

### Objetos e métodos {#objects}

Os seguintes objetos e métodos podem ser referenciados por parâmetros de perfil de script:

| Objeto ou método | Detalhes |
| --- | --- |
| `page.url` | O URL atual. |
| `page.protocol` | O protocolo usado pela página (http ou https). |
| `page.domain` | O domínio do URL atual (tudo antes da primeira barra). Por exemplo, `www.acme.com` em `http://www.acme.com/categories/men_jeans?color=blue&size=small`. |
| `page.query` | A sequência de consulta da página atual. Tudo depois de “?”. Por exemplo, `blue&size=small` em `http://www.acme.com/categories/mens_jeans?color=blue&size=small`. |
| `page.param('<par_name>')` | O valor do parâmetro indicado por `<par_name>`. Se seu URL atual for a página de pesquisa do Google e você digitou `page.param('hl')`, “en” será obtido para o URL `http://www.google.com/search?hl=en& q=what+is+asdf&btnG=Google+Search`. |
| `page.referrer` | O mesmo conjunto de operações acima se aplica ao referenciador e à landing page (ou seja, referrer.url é o endereço url do referenciador). |
| `landing.url`, `landing.protocol`, `landing.query`, e `landing.param` | Semelhante ao da página, mas para a landing page.<P>Para que o URL da página de destino funcione conforme o esperado, defina `context` > `browser` > `host`. |
| `mbox.name` | O nome da mbox ativa. |
| `mbox.param('<par_name>')` | Um parâmetro de mbox pelo nome fornecido na mbox ativa. |
| `profile.get('<par_name>')` | O parâmetro do perfil de usuário criado pelo cliente pelo nome `<par_name>`. Por exemplo, se o usuário definir um parâmetro de perfil chamado de “gênero”, o valor poderá ser extraído usando “profile.gender”. Retorna o valor do “`profile.<par_name>`” definido para o visitante atual; retorna nulo se nenhum valor for definido. Observe que `profile.get(<par_name>)` é qualificada como uma chamada de função. |
| `user.get('<par_name>')` | Retorna o valor do “`user.<par_name>`” definido para o visitante atual; retorna nulo se nenhum valor for definido. |
| `user.categoryAffinity` | Retorna o nome da melhor categoria. |
| `user.categoryAffinities` | Retorna uma matriz com as melhores categorias. |
| `user.isFirstSession` | Retorna verdadeiro se for a primeira sessão do visitante. |
| `user.browser` | Retorna o agente do usuário no cabeçalho HTTP. Como exemplo, você pode criar um direcionamento de expressão somente para usuários do Safari: `if (user.browser != null && user.browser.indexOf('Safari') != -1) { return true; }` |

### Operadores comuns

Todos os operadores JavaScript padrão estão presentes e utilizáveis. Os operadores JavaScript podem ser usados em sequências e números (bem como em outros tipos de dados). Uma breve informação:

| Operador | Descrição |
| --- | --- |
| `==` | Indica a igualdade. Permanece verdadeiro quando os operandos em ambos os lados são iguais. |
| `!=` | Indica a desigualdade. Permanece verdadeiro quando os operandos em ambos os lados não são iguais. |
| `<` | Indica que a variável à esquerda é inferior à da direita. Será avaliado como falso se as variáveis forem iguais. |
| `>` | Indica que a variável à esquerda é superior à da direita. Será avaliado como falso se as variáveis forem iguais. |
| `<=` | Igual a `<`, exceto se as variáveis forem iguais, então, será avaliado como verdadeiro. |
| `>=` | Igual a `>`, exceto se as variáveis forem iguais, então, será avaliado como verdadeiro. |
| `&&` | Na lógica, o operador “AND” só é verdadeiro quando ambas as expressões adjacentes, à esquerda e à direita, são verdadeiras (caso contrário, ele é falso). |
| `||` | Na lógica, o operador “OR” só é verdadeiro quando uma das expressões adjacentes, à esquerda ou à direita, é verdadeira (caso contrário, ele é falso). |
| `//` | Verifica se a origem contém todos os elementos que os booleanos de destino contém (origem da matriz, destino da matriz).<br>`//` extrai a subsequência do destino (correspondente ao regexp) e decodifica-a `Array/*String*/ decode(String encoding, String regexp, String target)`.<br>O recurso também suporta o uso de valores de sequência constantes, agrupando-os (`condition1 || condition2) && condition3` e expressões regulares `/[^a-z]$/.test(landing.referring.url)`). |

## Vídeo de treinamento: Scripts de perfil ![Selo do tutorial](/help/main/assets/tutorial.png)

Esse vídeo inclui informações sobre o uso e a criação de scripts de perfil.

* Explique o que é um script de perfil
* Explique como um script de perfil é diferente de um parâmetro de perfil
* Crie um script de perfil simples
* Use o menu Token disponível para acessar as opções disponíveis
* Ative e desative os scripts de perfil

>[!VIDEO](https://video.tv.adobe.com/v/17394)
