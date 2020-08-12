---
keywords: Profile script;profile script attributes;mutually exclusive activities
description: Você pode utilizar atributos de perfil para configurar testes que comparam duas ou mais atividades, mas não permita que os mesmos visitantes participem em cada atividades.
title: Usar scripts de perfil para testar atividades mutuamente exclusivas
feature: null
topic: Advanced,Standard,Classic
uuid: a76ed523-32cb-46a2-a2a3-aba7f880248b
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 84%

---


# Usar scripts de perfil para testar atividades mutuamente exclusivas {#section_FEFE50ACA6694DE7BF1893F2EFA96C01}

Você pode utilizar atributos de perfil para configurar testes que comparam duas ou mais atividades, mas não permita que os mesmos visitantes participem em cada atividades.

Testar atividades mutuamente exclusivas evita que um visitante em uma atividade afete os resultados do teste de outras atividades. Quando um visitante participa em diversas atividades, pode ser difícil determinar se um incentivo positivo ou negativo é resultado da experiência do visitante em outra atividade, ou se as interações entre diversas atividades afetaram os resultados de uma ou mais atividades.

Por exemplo, você pode testar duas áreas de sistema de comércio eletrônico. Você pode querer testar tornar vermelho o botão &quot;Adicionar ao carrinho&quot; em vez de azul. Você também pode testar um novo processo de checkout que reduz o número de etapas, de cinco para duas. Se ambas as atividades tiverem o mesmo evento bem-sucedido (uma compra concluída), pode ser difícil determinar se o botão vermelho melhora as conversões ou se essas mesmas conversões também aumentaram devido ao processo de checkout melhorado. Ao separar os testes em atividades mutuamente exclusivas, você pode testar cada alteração independentemente.

Esteja ciente das informações a seguir ao usar um dos scripts de perfil abaixo:

* O script de perfil devem ser executados antes da atividade ser iniciada e ele deve permanecer inalterado em toda a duração da atividade.
* Essa técnica reduz a quantidade de tráfego na atividade, o que pode exigir que a atividade seja executada por mais tempo. Você deve considerar esse fato ao estimar a duração da atividade.

## Configuração de até duas atividades

Para classificar visitantes em grupos onde cada um visualiza uma atividade diferente, você deve criar um atributo de perfil. Um atributo de perfil pode classificar um visitante em um ou mais grupos. Para configurar um atributo de perfil chamado &quot;doisgrupos&quot;, crie o script a seguir:

```
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

After you create the profile attribute, set up the first activity to target the desired population by requiring that the user profile parameter `user.twogroups` matches the value specified for GroupA.

>[!NOTE]
>
>Selecione uma mbox logo no início da página. Esse código determina se um visitante experimenta a atividade. Desde que uma mbox seja encontrada primeiro pelo navegador, ela pode ser utilizada para definir esse valor.

Defina a segunda campanha de forma que o parâmetro do perfil do usuário `user.twogroups` corresponda ao valor especificado para o GrupoB.

## Configuração de três ou mais atividades

A configuração de três ou mais atividades mutuamente exclusivas é similar à configuração de duas, mas você deve alterar o atributo de perfil JavaScript para criar um grupo separado para cada atividade e determina quem visualizará as campanhas. A geração de número aleatório é diferente, dependendo da criação de um número par ou ímpar de grupos.

Por exemplo, para criar quatro grupos, utilize o JavaScript a seguir:

```
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

```
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
