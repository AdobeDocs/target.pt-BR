---
keywords: design personalizado;velocity;decimal;vírgula;personalizar design
description: Saiba como usar a linguagem de design de código aberto [!DNL Velocity] para personalizar designs de recomendação no [!DNL Target] Recommendations.
title: Personalizar um design usando a Velocity
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: 035d7988-80d8-4080-bb0d-1d0e9f8856d1
TQID: 'https://experienceleague.adobe.com/cccBRfwqqn-eL2hraSDAoJHPYSCkcA9tVne3OWDXxEU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: f9c9c7b2b78ec020fcabae420686b8955e350a0e
workflow-type: tm+mt
source-wordcount: '1086'
ht-degree: 21%
---
# Personalizar um design usando o [!DNL Velocity] {#customize-design}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba como usar a linguagem de design de código aberto [!DNL Velocity] para personalizar designs de recomendação no [!DNL Adobe Target Recommendations].

>[!ENDSHADEBOX]

## Visão geral das [!DNL Velocity] {#velocity-overview}

Informações sobre [!DNL Velocity] podem ser encontradas em [https://velocity.apache.org](https://velocity.apache.org).

Toda a lógica, sintaxe etc. do [!DNL Velocity] podem ser usados para um design de recomendação. Isso significa que *para* loops, *se* instruções e outros códigos podem ser criados com [!DNL Velocity] em vez do JavaScript.

Os atributos de entidade enviados a [!DNL Recommendations] na mbox `productPage` ou no carregamento de CSV podem ser exibidos em um design, com exceção dos atributos de &quot;valores múltiplos&quot;. Qualquer tipo de atributo pode ser enviado; no entanto, [!DNL Target] não passa atributos do tipo &quot;multi-value&quot; como uma matriz sobre a qual um design pode iterar (por exemplo, `entityN.categoriesList`).

Esses valores são referenciados com a seguinte sintaxe:

```
$entityN.variable
```

Os nomes de atributos de entidade devem seguir a notação abreviada [!DNL Velocity], que consiste em um caractere *$* à esquerda, seguido por um Identificador de VTL (Linguagem de Modelo) [!DNL Velocity]. O identificador VTL deve começar com um caractere alfanumérico (a-z ou A-Z).

[!DNL Velocity] nomes de atributos de entidade são restritos aos seguintes tipos de caracteres:

* Alfabético (a-z, A-Z)
* Numérico (0-9)
* Hífen ( - )
* Sublinhado ( _ )

Os atributos a seguir estão disponíveis como [!DNL Velocity] matrizes. Dessa forma, eles podem ser iterados ou referenciados por meio de um índice.

* `entities`
* `entityN.categoriesList`

Por exemplo:

```
#foreach ($category in $entity1.categoriesList) 
<br/>$category 
#end
```

Ou

```
#if ($entities[0].categoriesList.size() >= 3 ) 
$entities[0].categoriesList[2] 
#end
```

Para obter mais informações sobre [!DNL Velocity] variáveis (atributos), consulte [Documentação do Velocity](https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables).

Se um script de perfil for usado em um design, o $ precedente ao nome do script deve ser evitado com um `\` (barra invertida). Por exemplo:

`\${user.script_name}`

>[!NOTE]
>
>A quantidade máxima de entidades que podem ser referenciadas em um design, seja em código rígido ou em loops, é de 99. O script de design pode conter até 65.000 caracteres.

Um design que exibe algo semelhante à seguinte ilustração:

![Exemplo de um design 4 x 1 intitulado &quot;Outras atividades divertidas&quot;, com quatro itens que mostram uma foto, um nome, um preço, uma classificação e uma distância](/help/main/c-recommendations/c-design-overview/assets/velocity_example.png)

O pode usar o seguinte código:

```
<table style="border:1px solid #CCCCCC;"> 
<tr> 
<td colspan="3" style="font-size: 130%; border-bottom:1px solid  
#CCCCCC;"> You May Also Like... </td> 
</tr> 
<tr> 
<td style="border-right:1px solid #CCCCCC;"> 
<div class="search_content_inner" style="border-bottom:0px;"> 
<div class="search_title"><a href="$entity1.pageUrl"  
style="color: rgb(112, 161, 0); font-weight: bold;"> 
$entity1.id</a></div> 
By $entity1.message <a href="?x14=brand;q14=$entity1.message"> 
(More)</a><br/> 
sku: $entity1.prodId<br/> Price: $$entity1.value 
<br/><br/> 
</div> 
</td> 
<td style="border-right:1px solid #CCCCCC; padding-left:10px;"> 
<div class="search_content_inner" style="border-bottom:0px;">  
<div class="search_title"><a href="$entity2.pageUrl"  
style="color: rgb(112, 161, 0); font-weight: bold;"> 
$entity2.id</a></div> 
By $entity2.message <a href="?x14=brand;q14=$entity2.message"> 
(More)</a><br/> 
sku: $entity2.prodId<br/> 
Price: $$entity2.value 
<br/><br/> 
</div> 
</td> 
<td style="padding-left:10px;"> 
<div class="search_content_inner" style="border-bottom:0px;"> 
<div class="search_title"><a href="$entity3.pageUrl"  
style="color: rgb(112, 161, 0); font-weight: bold;"> 
$entity3.id</a></div> 
By $entity3.message <a href="?x14=brand;q14=$entity3.message"> 
(More)</a><br/> 
sku: $entity3.prodId<br/> Price: $$entity3.value 
<br/><br/> 
</div> 
</td> 
</tr>  
</table>
```

>[!NOTE]
>
>Para adicionar texto após o valor de um atributo, antes de uma tag que indica que o nome do atributo foi concluído, use uma notação formal para delimitar o nome do atributo. Por exemplo: `${entity1.thumbnailUrl}.gif`.

`algorithm.name` e `algorithm.dayCount` também podem ser usados como atributos de entidade em designs, assim, um design pode ser usado para testar vários critérios e o nome do critério pode ser exibido de forma dinâmica no design. Isso mostra ao visitante que ele está olhando para os &quot;mais vendidos&quot; ou &quot;pessoas que viram isso compraram aquilo&quot;. O `dayCount` (o número de dias dos dados usados nos critérios, por exemplo, &quot;mais vendidos nos últimos dois dias&quot;) também pode ser exibido.

## Trabalhando com números em [!DNL Velocity] designs {#numbers}

Por padrão, [!DNL Velocity] designs tratam todos os atributos de entidade como valores de cadeia de caracteres. Um atributo de entidade pode precisar ser tratado como um valor numérico para executar uma operação matemática ou compará-lo a outro valor numérico. Para tratar um atributo de entidade como um valor numérico, siga estas etapas:

1. Declare uma variável fictícia e inicialize-a em um número inteiro arbitrário ou em um valor duplo.
1. Certifique-se de que o atributo de entidade a ser usado não esteja em branco (necessário para o analisador de design do [!DNL Target Recommendations] validar e salvar o design).
1. Passe o atributo de entidade para o método `parseInt` ou `parseDouble` na variável fictícia criada na etapa 1 para transformar a cadeia de caracteres em um número inteiro ou valor duplo.
1. Execute a operação matemática ou a comparação no novo valor numérico.

### Exemplo: Calcular um preço com desconto

Para reduzir o preço exibido de um item em US$ 0,99 para aplicar um desconto, a seguinte abordagem pode ser usada:

```
#set( $double = 0.1 )

#if( $entity1.get('priceBeforeDiscount') != '' )
    #set( $discountedPrice = $double.parseDouble($entity1.get('priceBeforeDiscount')) - 0.99 )
    Item price: $$discountedPrice
#else
    Item price unavailable
#end
```

### Exemplo: Escolher o número de estrelas para exibir com base na classificação de um item

Para exibir um número apropriado de estrelas com base na média numérica das classificações atribuídas por clientes para um item, pode-se utilizar a seguinte abordagem:

```
#set( $double = 0.1 )

#if( $entity1.get('rating') != '' )
    #set( $rating = $double.parseDouble($entity1.get('rating')) )
    #if( $rating >= 4.5 )
        <img src="5_stars.jpg">
    #elseif( $rating >= 3.5 )
        <img src="4_stars.jpg">
    #elseif( $rating >= 2.5 )
        <img src="3_stars.jpg">
    #elseif( $rating >= 1.5 )
        <img src="2_stars.jpg">
    #else
        <img src="1_star.jpg">
    #end
#else
    <img src="no_rating_default.jpg">
#end
```

### Exemplo: Calcular o tempo em horas e minutos com base na duração em minutos de um item

Para exibir a duração de um filme em horas e minutos quando a duração é armazenada em minutos, a seguinte abordagem pode ser usada:

```
#if( $entity1.get('length_minutes') )
#set( $Integer = 1 )
#set( $nbr = $Integer.parseInt($entity1.get('length_minutes')) )
#set( $hrs = $nbr / 60)
#set( $mins = $nbr % 60)
#end
```

## Exibir um item principal com produtos recomendados {#key-item}

Um design pode mostrar o item principal junto com outros produtos recomendados. Por exemplo, o item atual pode ser mostrado para referência ao lado das recomendações.

Para fazer isso, crie uma coluna no design que use o atributo `$key` no qual a recomendação se baseia, em vez do atributo `$entity`. Por exemplo, o código da coluna principal pode ter esta aparência:

```
<div class="at-table-column"> 
   <a href="$key.pageURL"> 
      <img src=$key.thumbnailUrl" class="at-thumbnail"/> 
      <br/><h3>$key.name</h3> 
      <br/><p class="at-light">$key.message</p> 
      <br/><p class="at-light">$key.value</p> 
   </a> 
</div>
```

O resultado é um design como o seguinte, em que uma coluna mostra o item chave.

![Design com quatro colunas, em que a primeira coluna mostra o item chave marcado como o produto atual](/help/main/c-recommendations/c-design-overview/assets/rec_key.png)

Quando uma atividade do [!DNL Recommendations] é criada, se o item chave é obtido do perfil do visitante, como &quot;último item comprado&quot;, o [!DNL Target] exibe um produto aleatório no **[!UICONTROL Visual Experience Composer]** (VEC). Isso ocorre porque um perfil do não está disponível enquanto a atividade é criada. Quando os visitantes visualizam a página, eles veem o item principal esperado.

## Executar substituições em um valor de sequência. {#replacements}

Um design pode substituir valores em uma string. Por exemplo, o ponto decimal usado nos Estados Unidos pode ser substituído pelo ponto de vírgula usado na Europa e em outros países.

O código a seguir mostra uma única linha em um exemplo condicional do preço de venda:

```
<span class="price">$entity1.value.replace(".", ",") &euro;</span><br>
```

O código a seguir é um exemplo condicional completo de um preço de venda:

```
<div class="price"> 
    #if($entity1.hasSalesprice==true) 
    <span class="old">Statt <s>$entity1.salesprice.replace(".", ",") &euro;</s></span><br> 
    <span style="font-size: 10px; float: left;">jetzt nur</span> $entity1.value.replace(".", ",") &euro;<br> #else 
    <span class="price">$entity1.value.replace(".", ",") &euro;</span><br> #end 
    <span style="font-weight:normal; font-size:10px;"> 
                                        $entity1.vatclassDisplay 
                                        <br/> 
                                        $entity1.delivery 
                                        <br> 
                                    </span>
</div>
```

## Personalização do tamanho do design e verificação de valores em branco {#default}

Um script [!DNL Velocity] pode controlar o dimensionamento dinâmico da exibição da entidade. O design a seguir acomoda um resultado de 1 para muitos para evitar a criação de elementos HTML vazios quando entidades correspondentes insuficientes forem retornadas de [!DNL Recommendations]. Este script é mais adequado para cenários nos quais as recomendações de backup não fazem sentido e nos quais a **[!UICONTROL Renderização de Design Parcial]** está habilitada.

O trecho HTML a seguir substitui a porção HTML existente no design 4 x 2 padrão (o CSS não está incluído aqui por motivos de brevidade):

* Se uma quinta entidade existir, o script insere um div de fechamento e abre uma nova linha com `<div class="at-table-row">`.
* Com 4 x 2, o número máximo de resultados exibidos é oito, mas isso pode ser personalizado para listas menores ou maiores, modificando `$count <=8`.
* A lógica não equilibra as entidades em várias linhas. Por exemplo, se houver cinco ou seis entidades a serem exibidas, elas não se tornarão dinamicamente três na parte superior e duas na parte inferior (ou três na parte superior e três na parte inferior). A linha superior exibe quatro itens antes de iniciar uma segunda linha.

```
<div class="at-table">
  <div class="at-table-row">
    #set($count=1) 
    #foreach($e in $entities)  
        #if($e.id != "" && $count < $entities.size() && $count <=8) 
            #if($count==5) 
                </div>
                <div class="at-table-row">
            #end
            <div class="at-table-column">
                <a href="$e.pageUrl"><img src="$e.thumbnailUrl" class="at-thumbnail" />
                    <br/>
                    <h3>$e.name</h3>
                    <br/>
                    <p class="at-light">$e.message</p>
                    <br/>
                    <p class="at-light">$$e.value</p>
                </a>
            </div>
            #set($count = $count + 1) 
        #end 
    #end
  </div>
</div>
```
