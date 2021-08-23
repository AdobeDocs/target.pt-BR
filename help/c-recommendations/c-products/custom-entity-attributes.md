---
keywords: atributos de entidade com vários valores, atributos de entidade personalizados, JSON válido, valor do atributo de entidade, matriz JSON, vários valores
description: Saiba como usar atributos de entidade personalizados de valor único e múltiplo para definir informações adicionais sobre itens em seu catálogo do Adobe [!DNL Target] Recommendations.
title: Como Posso Usar Atributos De Entidade Personalizados?
feature: Recommendations
mini-toc-levels: 3
exl-id: d7d0b04a-0f50-4d30-9cbe-c0347a3d3715
source-git-commit: f509fca07305d72cfc3ffd99d0e9a21b19dc6521
workflow-type: tm+mt
source-wordcount: '1401'
ht-degree: 89%

---

# ![PREMIUM](/help/assets/premium.png) Atributos de entidade personalizados

Use atributos de entidade personalizados de valor único e múltiplo em [!DNL Adobe Target Recommendations] para definir informações adicionais sobre itens em seu catálogo.

## Limites {#limits}

Você pode incluir até 100 atributos de entidade personalizados para definir informações adicionais sobre itens em seu catálogo. Por exemplo, é possível criar um atributo personalizado chamado `entity.genre` para especificar um livro ou filme. Ou, um vendedor de bilhetes pode criar atributos para o local de evento para incluir um artista secundário, como um time visitante em um evento esportivo ou um show de abertura em um evento.

O tamanho máximo dos atributos personalizados da entidade de valor único é de 15.000 caracteres (para idiomas codificados de um e dois bytes UTF -8, como inglês e outros alfabetos de script latinos) ou 10.000 caracteres (para idiomas codificados em três bytes, como chinês, japonês e coreano).

Os atributos personalizados de entidade de vários valores não podem conter mais de 500 valores. Cada valor individual é limitado a 100 caracteres. O número total de caracteres em todos os valores deve estar em conformidade com o limite de tamanho máximo dos atributos personalizados da entidade de valor único (veja acima).

## Valores de atributo de entidade personalizada {#section_313331A9F8194A89B5EDD89363018651}

Atributos de entidade personalizados podem conter um único valor ou vários valores. Valores de atributos da entidade são exibidos na visualização do produto.

![](assets/multi-value_product.png)

Um atributo de entidade personalizado com um único valor é formado da mesma maneira que um atributo de entidade predefinido de valor único:

`entity.genre=genre1`

Um atributo de entidade personalizada de vários valores deve ser enviado como uma matriz JSON válida:

`entity.genre=[“genre1”, “genre2”]`

Exemplos de matrizes JSON válidas suportadas pelo [!DNL Recommendations]:

* `["AB","BC"]` todos os valores são cadeia de caracteres
* `[1,2]` todos os valores são numéricos

>[!NOTE]
>
>[!DNL Recommendations] não suporta tipos de valores mistos em atributos de entidades de vários valores. Por exemplo, `["AB",1,true, [1,2,3]]` é uma matriz JSON válida, mas não é compatível com o [!DNL Recommendations] porque inclui tipos de valores mistos (cadeia de caracteres, numérico, booleano, objeto).

Depois que um atributo personalizado é enviado como uma matriz JSON válida, ele é tratado como um atributo de vários valores para todos os produtos no catálogo.

>[!NOTE]
>
>Para alterar um atributo de vários valores para valor único, você deve excluir seu catálogo e fazer upload dos dados corrigidos do produto. A exclusão do seu catálogo não exclui os dados históricos associados às suas IDs de produto. Consulte [Exclusão de todos os itens do sistema](/help/assets/adobe-recommendations-classic.pdf) na documentação *Adobe Recommendations Classic* para obter mais informações.

**Restrições**:

* Não é possível usar nomes de atributos de entidade predefinidos para atributos de entidade personalizados. (Consulte [Atributos da entidade](/help/c-recommendations/c-products/entity-attributes.md#reference_3BCC1383FB3F44F4A2120BB36270387F).)
* O atributo `entity.environment` é reservado pelo sistema e não pode ser usado para atributos de entidade personalizados. Tentativas de enviar `entity.environment` usando `targetPageParams`, feeds ou APIs serão ignoradas.
* As matrizes devem conter um único tipo de valor. Matrizes de valores mistos (`["AB",1,true]`) não são compatíveis.
* Um atributo de vários valores que inclui uma matriz JSON aninhada (`[10,12,[1,2,3]]`) é tratado como um atributo de valor único.

## Implementar atributos de vários valores {#section_80FEFE49E8AF415D99B739AA3CBA2A14}

Atributos de entidade personalizados de vários valores são compatíveis quando você usa feeds (CSV), `targetPageParams`, API de entrega e ta API Salvar entidades para carregar os produtos. Novos valores substituem valores atuais; eles não são anexados. Matrizes vazias ([]) são tratadas como não tendo valores.

Aspas duplas devem ser evitadas. Por exemplo, `"[""test"", ""value""]"` é uma matriz JSON que pode ser usada no CSV.

É possível incluir até 500 valores em um atributo de vários valores.

### Uso de targetPageParams

O exemplo a seguir mostra como usar `targetPageParams`

```javascript
function targetPageParams() { 
  return { 
    'entity.id':                   '123', 
    'entity.categoryId':            '["A", "A:B", "A:B:C", "A:B:C:D"]',        
    'entity.MultiValueAttribute':   '["X", "Y", "Z"]', 
    'entity.event.detailsOnly':     'true', 
    'excludedIds":                  '[123, 3232, 2323, 4344]', 
    'orderId":                      '123456', 
    'orderTotal":                   '195.32', 
    'productPurchaseId":            '[001,002,003]' 
  }; 
}
```

### Uso de CSV

Você pode gerenciar seus arquivos CSV de forma simples usando um editor de texto ou você pode usar um software de planilhas.

O CSV simples terá esta aparência:

![](assets/multi-value_example_raw.png)

O mesmo catálogo ficará assim em uma planilha:

![](assets/multi-value_example_excel.png)

Ao converter para o formato .csv, o software de planilha adiciona aspas duplas ao redor do conteúdo da célula para impedir que as vírgulas dentro da célula atuem como separadores de coluna. Ele também adiciona aspas duplas em torno dos valores de cadeia de caracteres JSON que você inclui em atributos personalizados de vários valores. Isso pode dificultar o trabalho diretamente com o arquivo simples. Por exemplo:

* Planilha: `["1","2","3"]`
* Simples: `"[""1"",""2"",""3""]"`

Tenha cuidado ao editar diretamente um arquivo CSV de catálogo simples.

### Uso de APIs

Você pode passar atributos de vários valores usando a API de entrega em um parâmetro de mbox como um valor de sequência de caracteres contendo uma matriz JSON escaped.

```javascript
"execute": {
    "mboxes": [
      {
        "index": 0,
        "name": "first-mbox",
        "parameters": {
          "entity.id": "32323",
          "entity.categoryId": "My Category",
          "entity.MultiValueAttribute": "[\"X\", \"Y\", \"Z\"]"
        }
      }
    ]
  }
```

Consulte a [documentação da API do Adobe Recommendations](https://developers.adobetarget.com/api/recommendations) para obter informações sobre como usar as APIs de entidades de Entrega e Salvar.

## Uso de operadores com atributos de vários valores {#section_83C2288A805242D9A02EBC4F07DEE945}

Quando você aplica operadores a atributos personalizados de vários valores em regras de inclusão de algoritmo, regras de catálogo e regras de exclusão, o resultado será *true* se pelo menos um valor na lista passar na operação (booleano *ou*).

No exemplo a seguir, a regra é  `message contains abc`.

* Caso 1: `entity.genre = ["ab", "bc", "de"]`. O resultado é false porque nenhum valor contém `abc`.
* Caso 2: `entity.genre = ["abcde","de","ef"]`. O resultado é true porque contém um valor `abc`.

Para operadores negativos, todos os valores de atributo devem passar (booleano *e*). Por exemplo, se o operador for  `notEquals`, o resultado será *false* se qualquer valor for compatível.

Consulte as seções a seguir para obter o comportamento do operador em regras de inclusão de algoritmo, regras de catálogo e regras de exclusão.

### Igual

Se qualquer valor de atributo for igual ao valor de entrada, o resultado será true.

Exemplo: `genre equals abc`

* Caso 1: `entity.genre = ["ab", "bc", "de"]`. O resultado é false porque nenhum valor é igual a `abc`.
* Caso 2: `entity.genre = ["abc", "de", "ef"]`. O resultado é true porque um valor é igual a `abc`.
* Caso 3: `entity.genre = ["abcde", "de", "ef"]`. O resultado é falso porque `abc` não é igual a nenhum elemento da lista.

### Não é igual

Se nenhum valor de atributo for igual ao valor de entrada, o resultado será true.

Exemplo: `genre not equals abc`

* Caso 1: `entity.genre = ["ab", "bc", "de"]`. O resultado é true porque nenhum valor é igual a `abc`.
* Caso 2: `entity.genre = ["abc", "de", "ef"]`. O resultado é false porque um valor é igual a `abc`.
* Caso 3: `entity.genre = ["abcde", "de", "ef"]`. O resultado é verdadeiro porque `abc` não é igual a nenhum elemento da lista.

### Contém

Se qualquer valor de atributo contém o valor de entrada, o resultado será true.

Exemplo: `genre contains abc`

* Caso 1: `entity.genre = ["ab", "bc", "de"]`. O resultado é false porque nenhum valor contém `abc`.
* Caso 2: `entity.genre = ["abcde", "de", "ef"]`. O resultado é true porque contém um valor `abc`.

### Não contém

Se nenhum valor de atributo contém o valor de entrada, o resultado será true.

Exemplo: `genre does not contain abc`

* Caso 1: `entity.genre = ["ab", "bc", "de"]`. O resultado é true porque nenhum valor contém `abc`.
* Caso 2: `entity.genre = ["abcde", "de", "ef"]`. A regra resultará em false porque um valor contém`abc`.

### Começa com

Se qualquer valor de atributo inicia com o valor de entrada, o resultado será true.

Exemplo: `genre starts with abc`

* Caso 1: `entity.genre = ["ab", "bc", "de"]`. O resultado é false porque nenhum valor inicia com `abc`.
* Caso 2: `entity.genre = ["abcde", "de", "ef"]`. O resultado é true porque um valor inicia com `abc`.
* Caso 3: `entity.genre = ["ab", "de", "abc"]`. O resultado é verdadeiro porque um valor começa com `abc` (não necessariamente o primeiro elemento da lista).

### Termina com

Se qualquer valor de atributo terminar com o valor de entrada, o resultado será true.

Exemplo: `genre ends with abc`

* Caso 1: `entity.genre = ["ab", "bc", "de"]`. O resultado é false porque nenhum valor termina com `abc`.
* Caso 2: `entity.genre = ["deabc", "de", "ef"]`. O resultado é true porque um valor termina com `abc`.

### Maior que ou igual a (apenas valores numéricos)

O valor do atributo é convertido em duplo. Atributos que não podem ser convertidos são ignorados durante a execução da regra.

Após o processamento, qualquer valor de atributo maior ou igual ao valor de entrada resultará em true.

Exemplo: `price greater than or equal to 100`

* Caso 1: `entity.price = ["10", "20", "45"]`. O resultado é false porque nenhum valor é maior do que ou igual a 100. O valor `de` é ignorado porque não pode ser convertido em double.
* Caso 2: `entity.price = ["100", "101", "90", "80"]`. O resultado é true porque dois valores são maiores ou iguais a 100.

### Menor que ou igual a (apenas valores numéricos)

O valor do atributo é convertido em duplo. Atributos que não podem ser convertidos são ignorados durante a execução da regra.

Após o processamento, qualquer valor de atributo menor ou igual ao valor de entrada resultará em true.

Exemplo: `price less than or equal to 100`

* Caso 1: `entity.price = ["101", "200", "141"]`. O resultado é false porque nenhum valor é menor do que ou igual a 100. O valor `de` é ignorado porque não pode ser convertido em double.
* Caso 2: `entity.price = ["100", "101", "90", "80"]`. O resultado é true porque dois valores são menores do que ou igual a 100.

### Correspondências dinâmicas (disponíveis apenas em algoritmos baseados em itens)

Se qualquer valor de atributo corresponder ao valor de entrada, o resultado será true.

Exemplo: `genre matches abc`

* Caso 1: `entity.genre = ["ab", "bc", "de"]`. O resultado é false porque nenhum valor corresponde `abc`.
* Caso 2: `entity.genre = ["abc", "de", "ef"]`. O resultado é true porque um valor corresponde a `abc`.

### Correspondências não dinâmicas (disponíveis apenas em algoritmos baseados em itens)

Se qualquer valor de atributo corresponder ao valor de entrada, o resultado será false.

Exemplo: `genre does not match abc`

* Caso 1: `entity.genre = ["ab", "bc", "de"]`. O resultado é true porque nenhum valor corresponde a `abc`.
* Caso 2: `entity.genre = ["abc", "de", "ef"]`. A regra resultará em false porque um valor corresponde a `abc`.

### Intervalos dinâmicos (disponíveis apenas em algoritmos baseados em itens e valores numéricos)

Se qualquer valor numérico de atributo se encaixar no intervalo especificado, o resultado será true.

Exemplo: `price dynamically ranges in 80% to 120% of 100`

* Caso 1: `entity.price = ["101", "200", "125"]`. O resultado é verdadeiro porque `101` está no intervalo de 80% a 120% de 100. O valor `de` é ignorado porque não pode ser convertido em double.
* Caso 2: `entity.price = ["130", "191", "60", "75"]`. O resultado é false porque nenhum valor está no intervalo de 80% a 120% de 100.

>[!NOTE]
>
>*Double* é um tipo de dado Java. Para operadores que exigem valores numéricos, a conversão para double elimina valores não numéricos da consideração nos resultados.

## Atributos de vários valores em designs {#section_F672E4F6E1D44B3196B7ADE89334ED4A}

Os atributos de vários valores são exibidos como uma lista separada por vírgulas quando referenciados em um design.

Exemplo:

Quando `entity.genre=["genre1","genre2"]` for utilizado em um design como `$entity<N>.genre`, o resultado será `genre1, genre2`.

## Tópicos relacionados:

* [Atributos da entidade](/help/c-recommendations/c-products/entity-attributes.md#reference_3BCC1383FB3F44F4A2120BB36270387F)
