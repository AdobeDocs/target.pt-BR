---
description: Os atributos do perfil são parâmetros específicos do visitante. Esses atributos são armazenados no perfil do visitante para fornecer informações sobre o visitante que pode ser usado nas atividades do Adobe Target.
keywords: Script de perfil, atributos do script de perfil, práticas recomendadas do script de perfil, depurar, depuração
seo-description: Os atributos do perfil são parâmetros específicos do visitante. Esses atributos são armazenados no perfil do visitante para fornecer informações sobre o visitante que pode ser usado nas atividades do Adobe Target.
seo-title: Atributos de perfil no Adobe Target
solution: Target
title: Atributos do perfil
topic: Advanced,Standard,Classic
uuid: a76ed523-32cb-46a2-a2a3-aba7f880248b
translation-type: tm+mt
source-git-commit: aec07af081ddc3f7e7f0dedf83c4bb3051ac9711

---


# Atributos do perfil{#profile-attributes}

Os atributos de perfil são parâmetros específicos de um visitante. Esses atributos são armazenados no perfil do visitante para fornecer informações sobre o visitante que pode ser usado em suas atividades.

Conforme um visitante procura seu site, ou quando ele retorna para outra sessão, os atributos de perfil salvos podem ser usados para direcionar conteúdo ou registrar informações para filtragem de segmentos.

Para configurar os atributos de perfil, clique em **[!UICONTROL Públicos-alvo]** &gt; **[!UICONTROL Scripts de perfil.]**

![Guia Scripts de perfil](/help/c-target/c-visitor-profile/assets/profile-scripts.png)

Os tipos a seguir de atributos de perfil estão disponíveis:

| Tipo do parâmetro | Descrição |
|--- |--- |
| Mbox | Passado diretamente pelo código de página ao criar a mbox. Consulte [Envio de parâmetros para uma mbox global](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md).<br>**** Observação: o Target tem um limite de 50 atributos de perfil exclusivos por chamada de mbox. Se você precisar passar mais de 50 atributos de perfil para o Target, é possível fazer isso usando o método de Atualização do perfil da API. Para obter mais informações, consulte [Atualização do perfil na documentação da API do Adobe Target](http://developers.adobetarget.com/api/#updating-profiles). |
| Script | Definido diretamente com um trecho de código JavaScript. Eles podem armazenar totais, como o valor total gasto por consumidor e executado em cada solicitação de mbox. Consulte Atributos de script de perfil abaixo. |

## Atributos de script de perfil {#concept_8C07AEAB0A144FECA8B4FEB091AED4D2}

Defina um atributo de perfil de script com o snippet do código JavaScript associado.

Você pode usar scripts de perfil para capturar os atributos do visitante em várias visitas. Os scripts de perfil são snippets de código definidos no Target usando um formulário de JavaScript do lado do servidor. Por exemplo, você pode usar um script de perfil para capturar a frequência na qual um visitante acessa seu site e quando ele foi visitado pela última vez.

Os scripts de perfil não são os mesmos que os parâmetros de perfil. Os parâmetros de perfil capturam as informações sobre visitantes que usam a implementação do código de mbox do Target.

>[!NOTE]
>
>O [!DNL Target] tem um limite de 1.000 scripts de perfil por conta.

## Criar scripts de perfil {#section_CB02F8B97CAF407DA84F7591A7504810}

Os scripts de perfil estão disponíveis na guia [!UICONTROL Públicos-alvo] na interface [!DNL Target].

Para adicionar um novo script de perfil, clique na guia **[!UICONTROL Scripts de perfil]**, **[!UICONTROL Criar script]**, em seguida, escreva o script.

Ou

Para copiar um script de perfil existente, na lista de [!UICONTROL Scripts de perfil], passe com o mouse sobre o script desejado e clique no ícone **[!UICONTROL Copiar]**: (assets/icon_copy.png)

Você pode editar o público-alvo para criar um público-alvo semelhante.

![Caixa de diálogo Criar script de perfil](assets/profile-script.png)

Scripts de perfil executam os &quot;coletores&quot; de atributo de perfil em cada solicitação de localização. Quando uma solicitação de localização é recebida, o Target determina qual atividade deve ser executada e exibe o conteúdo apropriado a essa atividade e experiência, monitora o sucesso da atividade e executa todos os scripts de perfil relevantes. Isto permite rastrear as informações sobre a visita, como o local do visitante, a hora do dia, o número de vezes que o visitante acessou o site, se ele já fez alguma compra anteriormente etc. Estas informações são então adicionadas ao perfil do visitante para que você possa melhor rastrear a atividade do visitante no seu site.

Os atributos de script de perfil têm a tag de `user.` inserida antes dos nomes dos atributos. Por exemplo:

```
if (mbox.name == 'Track_Interest') { 
    if (profile.get('model') == "A5" &&; profile.get('subcat') == "KS6") { 
        return (user.get('A5KS6') || 0) + 1; 
    } 
}
```

* Consulte os atributos de script do perfil (incluindo ele mesmo) no código com `user.get('parameterName')`
* Salve variáveis que podem ser acessadas na próxima vez que o script for executado (na própria solicitação da mbox) com `user.setLocal('variable_name', 'value')`. Faça referência à variável com `user.getLocal('variable_name')`. Isto é útil para situações em que você deseja fazer referência à data e hora da última solicitação.
* Os parâmetros e valores diferencia maiúsculas de minúsculas. Corresponda ao caso dos parâmetros e valores que você receberá durante a atividade ou teste.
* Consulte a seção &quot;Referência de JavaScript para os parâmetros do perfil de script&quot; abaixo para obter mais sintaxe de JavaScript.

## Exibição dos cartões de informações do script de perfil {#section_18EA3B919A8E49BBB09AA9215E1E3F17}

Você pode exibir os cartões pop-up com as informações do script de perfil de forma semelhante aos cartões com as informações da oferta. Esses cartões com as informações do script de perfil permitem exibir a lista de atividades que fazem referência ao script de perfil selecionado, juntamente com outros metadados úteis.

Por exemplo, o cartão com as informações do script de perfil é acessado ao passar o mouse sobre um script de perfil na Lista de scripts de perfil (público-alvo &gt; Scripts de perfil) e, em seguida, clicando no ícone Informações.

A guia [!UICONTROL Informações do script] contém as seguintes informações: Nome, Status, Tipo de token, ID do script, Log de alterações e Descrição.

![Cartão de informações do script de perfil](assets/profile_script_info_card.png)

A guia [!UICONTROL Uso do script] lista as atividades (e seus espaços de trabalho) que fazem referência ao script de perfil selecionado.

![Cartão de informações do script de perfil &gt; guia Uso de script](assets/profile_script_info_card_usage_tab.png)

>[!Note]
>
>A guia Uso do script não exibe atividades que referenciam o script de perfil selecionado nas seguintes situações:
> * A atividade está no estado Rascunho.
> * O conteúdo ou a oferta usada na atividade utiliza variáveis de script (seja uma oferta na linha dentro da atividade ou dentro da biblioteca Oferta).



## O Target desativa os scripts de perfil em determinadas situações {#section_C0FCB702E60D4576AD1174D39FBBE1A7}

O [!DNL Target] desativará automaticamente os scripts de perfil em determinadas situações, como em caso de demora para execução ou de excesso de instruções.

Quando um script de perfil é desativado, um ícone de alerta amarelo é exibido perto do script de perfil na interface de usuário do Target, conforme ilustrado abaixo:

![](assets/profile_script_invalid.png)

Ao passar o cursor do mouse, os detalhes do erro são exibidos, conforme ilustrado abaixo:

![](assets/profile_script_hover.png)

Os motivos típicos para o sistema desativar os scripts de perfil incluem o seguinte:

* Uma variável indefinida a ser referenciada.
* Um valor inválido é referenciado. Isso normalmente é causar pela referências a valores de URL e outros dados inseridos pelo cliente, sem a validação apropriada.
* Muitas instruções de JavaScript usadas. O Target tem um limite de 2.000 instruções de JavaScript por script, mas isso não pode ser calculado somente pela leitura manual do JavaScript. Por exemplo, o Rhino trata todas as chamadas de função e as &quot;novas&quot; chamadas como 100 instruções. Além disso, o tamanho dos dados de entrada, como os valores de URL, pode afetar a contagem das instruções.
* Não seguir os itens destacados na seção [Práticas recomendadas](../../c-target/c-visitor-profile/profile-parameters.md#section_64AFE5D2B0C8408A912FC2A832B3AAE0) abaixo.

## Práticas recomendadas {#section_64AFE5D2B0C8408A912FC2A832B3AAE0}

As orientações a seguir destinam-se a ajudar a escrever scripts de perfil simplificados que são os mais livres de erros possíveis, ao escrever código com falhas leves, para que os scripts sejam processados sem forçar uma interrupção do script do sistema. Essas orientações resultam das práticas recomendadas com execução eficaz comprovada. Essas diretrizes devem ser aplicadas juntamente com os princípios e as recomendações formulados pela comunidade de desenvolvimento Rhino.

* Defina o valor do script atual para uma variável local no script do usuário, defina um failover para a sequência de caracteres em branco.
* Valide a variável local, certificando-se de que ela não seja uma sequência de caracteres em branco.
* Use funções de manipulação com base em sequências de caracteres x Expressões Regulares.
* Use limitado para loops e abertos para ou enquanto nos loops.
* Não exceda 1.300 caracteres ou 50 iterações de loop.
* Não exceda 2.000 instruções do JavaScript. O Target tem um limite de 2.000 instruções de JavaScript por script, mas isso não pode ser calculado somente pela leitura manual do JavaScript. Por exemplo, o Rhino trata todas as chamadas de função e as &quot;novas&quot; chamadas como 100 instruções. Além disso, o tamanho dos dados de entrada, como os valores de URL, pode afetar a contagem das instruções.
* Lembre-se não apenas do desempenho do script, mas do desempenho combinado de todos os scripts. Recomenda-se menos de 5.000 instruções no total. Contar o número de instruções não é óbvio, mas o importante a ser observado é que os scripts que excedem 2 KB serão automaticamente desativados. Não há limite definido para o número de scripts que podem ser executados, mas todos são executados com uma chamada de mbox única. Execute somente a quantidade de scripts necessária.
* Se tudo falhar, envolva o script em um try/catch.
* Consulte a documentação do mecanismo JS Rhino para obter mais informações: [https://www.mozilla.org/rhino/doc.html](https://www.mozilla.org/rhino/doc.html).

## Scripts de perfil para testar atividades mutuamente exclusivas {#section_FEFE50ACA6694DE7BF1893F2EFA96C01}

Você pode utilizar atributos de perfil para configurar testes que comparam duas ou mais atividades, mas não permita que os mesmos visitantes participem em cada atividades.

Testar atividades mutuamente exclusivas evita que um visitante em uma atividade afete os resultados do teste de outras atividades. Quando um visitante participa em diversas atividades, pode ser difícil determinar se um incentivo positivo ou negativo é resultado da experiência do visitante em outra atividade, ou se as interações entre diversas atividades afetaram os resultados de uma ou mais atividades.

Por exemplo, você pode testar duas áreas de sistema de comércio eletrônico. Você pode desejar testar tornar vermelho o botão Adicionar o carrinho, em vez de azul. Você também pode testar um novo processo de checkout que reduz o número de etapas, de cinco para duas. Se ambas as atividades têm o mesmo evento de sucesso (uma compra concluída) pode ser difícil determinar se o botão vermelho melhorou as conversões, ou se as mesmas conversões também aumentaram devido ao processo melhorado de checkout. Ao separar os testes em atividades mutuamente exclusivas, você pode testar cada alteração independentemente.

Esteja ciente das informações a seguir ao usar um dos scripts de perfil abaixo:

* O script de perfil devem ser executados antes da atividade ser iniciada e ele deve permanecer inalterado em toda a duração da atividade.
* Essa técnica reduzirá a quantidade de tráfego na atividade, o que deve precisar de execução mais longa da atividade. Você deve considerar esse fato ao estimar a duração da atividade.

### Configuração de até duas atividades

Para classificar visitantes em grupos onde cada um visualiza uma atividade diferente, você deve criar um atributo de perfil. Um atributo de perfil pode classificar um visitante em um ou mais grupos. Para configurar um atributo de perfil chamado &quot;doisgrupos&quot;, crie o script a seguir:

```
if (!user.get('twogroups')) { 
    var ran_number = Math.floor(Math.random() * 99); 
    if (ran_number < = 49) { 
        return 'GroupA'; 
    } else { 
        return 'GroupB'; 
    } 
}
```

`if (!user.get('twogroups'))` determina se o atributo de perfil *doisgrupos* está definido para o visitante atual. Se estiver definido, não é necessária mais nenhuma alteração.

`var ran_number=Math.floor(Math.random() *99)` declara uma nova variável chamada ran_number, define um valor decimal aleatório entre 0 e 1 e, em seguida, multiplica o valor por 99 e arredonda o resultado para baixo, criando um intervalo de 100 (0-99), útil para especificar a porcentagem de visitantes que visualizarão a atividade.

`if (ran_number <= 49)` inicia uma rotina que determina a qual grupo o usuário pertence. Se o resultado for entre 0-49, o visitante é atribuído ao GrupoA. Se o resultado for entre 50-99, o visitante é atribuído ao GrupoB. O grupo determina qual atividade o visitante visualizará.

Após criar o atributo de perfil, defina a primeira atividade direcionada à população desejada, solicitando que o parâmetro do perfil de usuário user.twogroups corresponda ao valor do GrupoA.

>[!NOTE]
>
>Selecione uma mbox logo no início da página. Esse código determina quando o visitante visualiza a campanha. Desde que uma mbox seja encontrada primeiro pelo navegador, ela pode ser utilizada para definir esse valor.

Defina a segunda campanha de forma que o parâmetro do perfil do usuário `user.twogroups` corresponda ao valor especificado para o GrupoB.

### Configuração de três ou mais atividades

A configuração de três ou mais atividades mutuamente exclusivas é similar à configuração de duas, mas você deve alterar o atributo de perfil JavaScript para criar um grupo separado para cada atividade e determina quem visualizará as campanhas. A geração de número aleatório é diferente, dependendo da criação de um número par ou ímpar de grupos.

Por exemplo, para criar quatro grupos, utilize o JavaScript a seguir:

```
if (!user.get('fourgroups')) { 
    var ran_number = Math.floor​(Math.random() * 99); 
    if (ran_number < = 24) { 
        return 'GroupA'; 
    } else if (ran_number < = 49) { 
        return 'GroupB'; 
    } else if (ran_number < = 74) { 
        return 'GroupC'; 
    } else { 
        return 'GroupD'; 
    } 
}
```

Nesse exemplo, a matemática utilizada para gerar o número aleatório que atribui um visitante a um grupo é a mesma para somente dois grupos. Um número decimal aleatório é gerado e arredondado para baixo, criando um número inteiro.

Se você criar um número ímpar de grupos ou um número não divisível por 100, você não deve arredondar o número decimal para baixo e criar um número inteiro. Não arredondar o decimal permite especificar intervalos de números não inteiros. Altere a linha a seguir para fazer isso:

`var ran_number=Math.floor(Math.random()*99);`

para:

`var ran_number=Math.random()*99;`

Por exemplo, para atribuir visitantes em três grupos iguais, utilize o código a seguir:

```
if (!user.get('threegroups')) { 
    var ran_number = Math.random() * 99; 
    if (ran_number < = 32.33) { 
        return 'GroupA'; 
    } else if (ran_number < = 65.66) { 
        return 'GroupB'; 
    } else { 
        return 'GroupC'; 
    } 
}
```

## Depurar scripts de perfil {#section_E9F933DE47EC4B4E9AF2463B181CE2DA}

Os métodos a seguir podem ser usados para depurar scripts de perfil:

>[!NOTE]
>
>Usar [!DNL console.log] com um script de perfil não resultará no valor do perfil, pois os scripts de perfil são executados no lado do servidor.

* **Adicionar scripts de perfil como tokens de resposta para depurá-los:**

   No Target, clique em **[!UICONTROL Configurar]**, **[!UICONTROL Tokens de resposta]**, em seguida, ative o script de perfil que deseja depurar.

   Sempre que carregar uma página para o site com o Target nela, parte da resposta do Target conterá o valor para o script de perfil específico, como mostrado abaixo:

   ![](assets/debug_profile_script_1.png)

* **Use a ferramenta de depuração mboxTrace para depurar scripts de perfil.**

   Este método requer um token de autorização que pode ser gerado clicando em **[!UICONTROL Target]** &gt; **[!UICONTROL Configuração]** &gt; **[!UICONTROL Implementação]** &gt; **[!UICONTROL Gerar token de autorização]**.

   Em seguida, você adiciona esses dois parâmetros ao URL da página após o “?”: `mboxTrace=window&authorization=YOURTOKEN`.

   Isso é um pouco mais informativo do que o token de resposta, pois você obtém um instantâneo do seu perfil executado antes e um depois. Ele também mostrará todos os perfis disponíveis.

   ![](assets/debug_profile_script_2.png)

## Perguntas frequentes do script de perfil {#section_1389497BB6D84FC38958AE43AAA6E712}

**É possível usar os scripts de perfil para capturar informações de uma página localizada em uma camada de dados?**

Os scripts de perfil não podem ler a página diretamente porque são executados no lado do servidor. Os dados devem ser enviados por uma solicitação mbox ou através de outros [métodos para colocar os dados no Target](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17). Depois que os dados estiverem no destino, os scripts de perfil poderão ler os dados como um parâmetro mbox ou parâmetro de perfil.

## Referência de JavaScript para os parâmetros do perfil de script

É necessário o conhecimento básico de JavaScript para usar os parâmetros
do perfil de script de maneira eficiente. Esta seção serve como uma referência rápida para torná-lo produtivo com essa funcionalidade em apenas alguns minutos.

Os parâmetros do perfil de script são encontrados na guia mboxes/perfis. É possível gravar programas de JavaScript que retornam qualquer tipo de JavaScript (sequência de caracteres, inteiro, matriz, etc.).

### Exemplos de parâmetro do perfil de script

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

Cria uma variável para o dia, conforme medido em milissegundos. Se o nome da mbox for `orderThankyouPage`, defina um atributo do perfil de usuário local (invisível) chamado `lastPurchaseTime` para receber o valor da data e hora atuais. O valor do último horário de compra é lido e, se estiver definido, retornamos o tempo desde a última compra, divido pelo número de milissegundos em um dia (o que resulta no número de dias desde a última compra).

**Nome:** *user.frequency*

```
var frequency = user.get('frequency') || 0;
if (mbox.name == 'orderThankyouPage') {
    return frequency + 1;
}
```

Cria uma variável chamada frequência, inicializando-a para o valor anterior ou 0, se não houver um valor anterior. Se o nome da mbox for `orderThankyouPage`, o valor incrementado será retornado.

**Nome:** *user.monetaryValue*

```
var monetaryValue = user.get('monetaryValue') || 0;
if (mbox.name == 'orderThankyouPage') {
    return monetaryValue + parseInt(mbox.param('orderTotal'));
}
```

Cria uma variável chamada `monetaryValue`, que pesquisa o valor atual de um determinado visitante (ou define como 0 se não houver um valor anterior). Se o nome da mbox for `orderThankyouPage`, o novo valor monetário será retornado adicionando o anterior e o valor do parâmetro `orderTotal` passado para a mbox.

### Objetos e métodos

As seguintes propriedades e métodos podem ser referenciados pelos parâmetros do perfil de script:

| Objeto ou método | Detalhes |
| --- | --- |
| `page.url` | O URL atual. |
| `page.protocol` | O protocolo usado pela página (http ou https). |
| page.domain | O domínio do URL atual (tudo antes da primeira barra). Por exemplo, `www.acme.com` em `http://www.acme.com/categories/men_jeans?color=blu e&size=small`. |
| `page.query` | A sequência de consulta da página atual. Tudo depois de &quot;?&quot;. Por exemplo, `blue&size=small` em `http://www.acme.com/categories/mens_jeans?color=blue&size=small`. |
| `page.param(‘<par_name>’)` | O valor do parâmetro indicado por `<par_name>`. Se o URL atual for a página de pesquisa do Google e você digitou `page.param('hl')`, &quot;en&quot; seria obtido para o URL `http://www.google.com/search?hl=en& q=what+is+asdf&btnG=Google+Search`. |
| `page.referrer` | O mesmo conjunto de operações acima se aplica ao referenciador e à landing page (ou seja, referrer.url será o endereço url do referenciador). |
| `landing.url`, `landing.protocol`, `landing.query`, e `landing.param` | Semelhante ao da página, mas para a landing page. |
| `mbox.name` | O nome da mbox ativa. |
| `mbox.param(‘<par_name>’)` | Um parâmetro de mbox pelo nome fornecido na mbox ativa. |
| `profile.get(‘<par_name>’)` | O parâmetro do perfil de usuário criado pelo cliente pelo nome `<par_name>`. Por exemplo, se o usuário definir um parâmetro de perfil chamado de &quot;gênero&quot;, o valor poderá ser extraído usando &quot;profile.gender&quot;. Retorna o valor do &quot;`profile.<par_name>`&quot; definido para o visitante atual; retorna nulo se nenhum valor foi definido. |
| `user.get(‘<par_name>’)` | Retorna o valor do &quot;`user.<par_name>`&quot; definido para o visitante atual; retorna nulo se nenhum valor foi definido. |
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
| `<` | Indica que a variável à esquerda é inferior à da direita. Será avaliado como false se as variáveis forem iguais. |
| `>` | Indica que a variável à esquerda é superior à da direita. Será avaliado como false se as variáveis forem iguais. |
| `<=` | Igual a `<`, exceto se as variáveis forem iguais, então, será avaliado como verdadeiro. |
| `>=` | Igual a `>`, exceto se as variáveis forem iguais, então, será avaliado como verdadeiro. |
| `&&` | Na lógica, o &quot;AND&quot; entre as expressões, à esquerda e à direita - é verdadeiro somente quando ambos os lados são verdadeiros (caso contrário, é falso). |
| `||` | Na lógica, &quot;OR&quot; entre as expressões, à esquerda e à direita - é verdadeiro somente se um dos lados for verdadeiro (caso contrário, é falso). |
| `//` | Verifica se a origem contém todos os elementos que os booleanos de destino contém (origem da matriz, destino da matriz).<br>`//` extrai a subsequência do destino (correspondente ao regexp) e decodifica-a`Array/*String*/ decode(String encoding, String regexp, String target)`.<br>O recurso também suporta o uso de valores de sequência constantes, agrupando-os (`condition1 || condition2) && condition3` e expressões regulares (`/[^a-z]$/.test(landing.referring.url)`. |

## Vídeo de treinamento: Scripts de perfil

Esse vídeo inclui informações sobre o uso e a criação de scripts de perfil.

* Explique o que é um script de perfil
* Explique como um script de perfil é diferente de um parâmetro de perfil
* Crie um script de perfil simples
* Use o menu Token disponível para acessar as opções disponíveis
* Ative e desative os scripts de perfil

>[!VIDEO](https://video.tv.adobe.com/v/17394?captions=por_br)