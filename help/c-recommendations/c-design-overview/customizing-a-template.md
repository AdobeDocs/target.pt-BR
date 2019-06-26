---
description: Use a linguagem de design Velocity de código aberto para personalizar designs de recomendação.
keywords: design personalizado, velocity, decimal, vírgula, personalizar design
seo-description: Use a linguagem de design Velocity de código aberto para personalizar designs de recomendação.
seo-title: Personalizar um design usando a Velocity
solution: Target
title: Personalizar um design usando a Velocity
title-outputclass: premium
topic: Premium
uuid: 80701a15-c5eb-4089-a92e-117eda11faa2
badge: premium
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# ![PREMIUM](/help/assets/premium.png) Personalizar um design usando o Velocity{#customize-a-design-using-velocity}

Use a linguagem de design Velocity de código aberto para personalizar designs de recomendação.

## Velocity overview {#section_C431ACA940BC4210954C7AEFF6D03EA5}

É possível encontrar informações sobre o Velocity em [](https://velocity.apache.org)https://velocity.apache.org.

Toda a lógica, sintaxe etc. da Velocity podem ser usados para um design de recomendação. Isso quer dizer que é possível criar *para* loops, instruções *se* e outros códigos usando Velocity em vez de JavaScript.

Qualquer variável enviada para o [!DNL Recommendations] na mbox `productPage` ou o upload do CSV podem ser exibidos no design. Esses valores são referenciados com a seguinte sintaxe:

```
$entityN.variable
```

Os nomes de variáveis devem seguir a notação taquigrafada da Velocity, que consiste em um caractere inicial *$*, seguido de um identificador da Linguagem do modelo de velocidade (VTL). O identificador VTL deve começar com um caractere alfanumérico (a-z ou A-Z).

Os nomes de variáveis da Velocity estão restritos aos seguintes tipos de caracteres:

* Alfabético (a-z, A-Z)
* Numérico (0-9)
* Hífen ( - )
* Sublinhado ( _ )

As seguintes variáveis estão disponíveis como matrizes do Velocity. Como tal, eles podem ser iterados ou referenciados por meio do índice.

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

Para obter mais informações sobre as variáveis da Velocity, consulte [https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables](https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables).

Se você usar um script de perfil em seu design, o $ precedente ao nome do script deve ser evitado com um \. Por exemplo, `\${user.script_name}`.

>[!NOTE]
>
>A quantidade máxima de entidades que podem ser referenciadas em um design, seja em código fixo ou via loops, é de 99. O comprimento do script do modelo pode conter até 65.000 caracteres.

Por exemplo, se você deseja um design que exibe algo semelhante a isto:

![](assets/velocity_example.png)

é possível usar o seguinte código:

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

>[!NOTE] {class=&quot;- topic/note &quot;}
>
>Se desejar adicionar informações após o valor da variável, faça isso usando a notação formal. Por exemplo: `${entity1.thumbnailUrl}.gif`.

Também é possível usar `algorithm.name` e `algorithm.dayCount` como variáveis nos designs, assim, um design pode ser usado para testar vários critérios e o nome do critério pode ser exibido de forma dinâmica no design. Isso mostra ao visitante que ele ou ela está olhando para os &quot;mais vendidos&quot; ou &quot;pessoas que viram isso compraram aquilo.&quot; Você ainda pode usar essas variáveis para exibir o `dayCount` (número de dias dos dados usados nos critérios, como &quot;mais vendidos nos últimos dois dias&quot; etc.

## Scenario: Display key item with recommended products {#section_7F8D8C0CCCB0403FB9904B32D9E5EDDE}

Você pode modificar seu design para mostrar seu item principal ao lado de outros produtos recomendados. Por exemplo, você pode querer mostrar o item atual para referência ao lado das recomendações.

Para fazer isso, crie uma coluna em seu design que use o atributo `$key` no qual você está baseando sua recomendação, em vez do atributo `$entity`. Por exemplo, o código da sua coluna chave pode ter esta aparência:

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

![](assets/rec_key.png)

Quando você está criando sua atividade do [!DNL Recommendations], se o item chave é obtido do perfil do visitante, como &quot;último item comprado&quot;, o [!DNL Target] exibe um produto aleatório no [!UICONTROL Visual Experience Composer] (VEC). Isso ocorre porque um perfil não está disponível enquanto você projeta a atividade. Quando os visitantes visualizam a página, eles verão o item chave esperado.

## Scenario: Replace the decimal point with the comma delimiter in a sales price {#section_01F8C993C79F42978ED00E39956FA8CA}

Você pode modificar o design para substituir o delimitador de ponto decimal usado nos Estados Unidos pelo delimitador de vírgula usado na Europa e em outros países.

O código a seguir mostra uma única linha em um exemplo condicional do preço de venda:

```
<span class="price">$entity1.value.replace(".", ",") €</span><br>
```

O código a seguir é um exemplo condicional completo de um preço de venda:

```
<div class="price"> 
    #if($entity1.hasSalesprice==true) 
    <span class="old">Statt <s>$entity1.salesprice.replace(".", ",") €</s></span><br> 
    <span style="font-size: 10px; float: left;">jetzt nur</span> $entity1.value.replace(".", ",") €<br> #else 
    <span class="price">$entity1.value.replace(".", ",") €</span><br> #end 
    <span style="font-weight:normal; font-size:10px;"> 
                                        $entity1.vatclassDisplay 
                                        <br/> 
                                        $entity1.delivery 
                                        <br> 
                                    </span>
```

## Scenario: Create a 4x2 default Recommendations design with null-checking logic {#default}

Using a Velocity script to control for dynamic sizing of the entity display, the following template accommodates a 1-to-many result to avoid creating empty HTML elements when there aren&#39;t enough matching entities returned from [!DNL Recommendations]. This script is best for scenarios when back-up recommendations wouldn&#39;t make sense and [!UICONTROL Partial Template Rendering] is enabled.

O trecho HTML a seguir substitui a porção HTML existente no design padrão de 4 x 2 (o CSS não está incluído aqui, por exemplo, para fins de abreviidade):

* If a fifth entity exists, the script inserts a closing div and opens a new row with `<div class="at-table-row">`.
* With 4x2, the maximum results shown will be eight, but this could be customized for smaller or larger lists by modifying `$count <=8`.
* Esteja ciente de que a lógica não equilibre as entidades em várias linhas. Por exemplo, se houver cinco ou seis entidades a serem exibidas, elas não se tornarão dinamicamente três na parte superior e duas na parte inferior (ou três na parte superior e três na parte inferior). A linha superior exibirá quatro itens antes de iniciar uma segunda linha.

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
