---
keywords: Script de perfil, atributos de script de perfil, atividades mutuamente exclusivas
description: Saiba como usar atributos de perfil para configurar testes no Adobe [!DNL Target] que comparam várias atividades, mas não permitem que os mesmos visitantes participem em cada atividade.
title: Posso Usar Scripts De Perfil Para Testar Atividades Mutuamente Exclusivas?
feature: Públicos-alvo
exl-id: b0b23887-3339-411e-9f5c-64f9d1ba778c
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 78%

---

# Usar scripts de perfil para testar atividades mutuamente exclusivas

Você pode utilizar atributos de perfil para configurar testes que comparam duas ou mais atividades, mas não permita que os mesmos visitantes participem em cada atividades.

Testar atividades mutuamente exclusivas evita que um visitante em uma atividade afete os resultados do teste de outras atividades. Quando um visitante participa em diversas atividades, pode ser difícil determinar se um incentivo positivo ou negativo é resultado da experiência do visitante em outra atividade, ou se as interações entre diversas atividades afetaram os resultados de uma ou mais atividades.

Por exemplo, você pode testar duas áreas de sistema de comércio eletrônico. Você pode querer testar tornar o botão &quot;Adicionar ao carrinho&quot; vermelho, em vez de azul. Você também pode testar um novo processo de checkout que reduz o número de etapas, de cinco para duas. Se ambas as atividades tiverem o mesmo evento bem-sucedido (uma compra concluída), pode ser difícil determinar se o botão vermelho melhora as conversões, ou se essas mesmas conversões também aumentaram devido ao processo de finalização aprimorado. Ao separar os testes em atividades mutuamente exclusivas, você pode testar cada alteração independentemente.

Esteja ciente das informações a seguir ao usar um dos scripts de perfil abaixo:

* O script de perfil devem ser executados antes da atividade ser iniciada e ele deve permanecer inalterado em toda a duração da atividade.
* Essa técnica reduz a quantidade de tráfego na atividade, o que pode exigir que a atividade seja executada por mais tempo. Você deve considerar esse fato ao estimar a duração da atividade.

## Configuração de até duas atividades

Para classificar visitantes em grupos onde cada um visualiza uma atividade diferente, você deve criar um atributo de perfil. Um atributo de perfil pode classificar um visitante em um ou mais grupos. Para configurar um atributo de perfil chamado &quot;doisgrupos&quot;, crie o script a seguir:

```javascript
if (!user.get('twogroups')) { 
    var ran_number = Math.floor(Math.random() * 99); 
    if (ran_number <= 49) { 
        return 'GroupA'; 
    } else { 
        return 'GroupB'; 
    } 
}
```

* `if (!user.get('twogroups'))` determina se o atributo de perfil *doisgrupos* está definido para o visitante atual. Se estiver definido, não é necessária mais nenhuma alteração.

* `var ran_number=Math.floor(Math.random() *99)` declara uma nova variável chamada ran_number, define um valor decimal aleatório entre 0 e 1 e, em seguida, multiplica o valor por 99 e arredonda o resultado para baixo, criando um intervalo de 100 (0-99), útil para especificar a porcentagem de visitantes que visualizarão a atividade.

* `if (ran_number <= 49)` inicia uma rotina que determina a qual grupo o usuário pertence. Se o resultado for entre 0-49, o visitante é atribuído ao GrupoA. Se o resultado for entre 50-99, o visitante é atribuído ao GrupoB. O grupo determina qual atividade o visitante visualizará.

Após criar o atributo de perfil, configure a primeira atividade para direcionar a população desejada, exigindo que o parâmetro do perfil de usuário `user.twogroups` corresponda ao valor especificado para o GrupoA.

>[!NOTE]
>
>Selecione uma mbox logo no início da página. Esse código determina se um visitante acessou a atividade. Desde que uma mbox seja encontrada primeiro pelo navegador, ela pode ser utilizada para definir esse valor.

Defina a segunda campanha de forma que o parâmetro do perfil do usuário `user.twogroups` corresponda ao valor especificado para o GrupoB.

## Configuração de três ou mais atividades

A configuração de três ou mais atividades mutuamente exclusivas é similar à configuração de duas, mas você deve alterar o atributo de perfil JavaScript para criar um grupo separado para cada atividade e determina quem visualizará as campanhas. A geração de número aleatório é diferente, dependendo da criação de um número par ou ímpar de grupos.

Por exemplo, para criar quatro grupos, utilize o JavaScript a seguir:

```javascript
if (!user.get('fourgroups')) { 
    var ran_number = Math.floor​(Math.random() * 99); 
    if (ran_number <= 24) { 
        return 'GroupA'; 
    } else if (ran_number <= 49) { 
        return 'GroupB'; 
    } else if (ran_number <= 74) { 
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

```javascript
if (!user.get('threegroups')) { 
    var ran_number = Math.random() * 99; 
    if (ran_number <= 32.33) { 
        return 'GroupA'; 
    } else if (ran_number <= 65.66) { 
        return 'GroupB'; 
    } else { 
        return 'GroupC'; 
    } 
}
```
