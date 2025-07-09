---
keywords: solução de problemas, perguntas frequentes, perguntas frequentes, perguntas frequentes, metas, públicos-alvo
description: Exiba as perguntas frequentes sobre o direcionamento de experiência e os públicos-alvo usados nas atividades do Adobe [!DNL Target] .
title: Onde posso encontrar perguntas e respostas sobre direcionamentos e públicos-alvo?
feature: Audiences
exl-id: f829bd4a-852a-4eb1-85d1-89e74c14b37e
source-git-commit: cf7f18b5fd9647bbecda2e6b6419c3a927708bd6
workflow-type: tm+mt
source-wordcount: '973'
ht-degree: 53%

---

# Perguntas frequentes sobre direcionamentos e públicos

Lista de perguntas frequentes sobre o direcionamento de experiência e públicos-alvo.

## Como o [!DNL Target] avalia as URLs no direcionamento? {#url}

O Target avalia os URLs de forma diferente se você usar o direcionamento de URL de público-alvo ao criar uma atividade ou se você usar o direcionamento de URL ao criar um público-alvo.

Considere o seguinte URL:

`http://www.example.com/path1/path2/path3?queryStringParam1=test123&queryStringParam2=test7`

### Direcionamento de URL de público

Para aplicar o direcionamento de URL de público-alvo, ao criar uma atividade, na página **[!UICONTROL Experiences]** (etapa um do fluxo de trabalho guiado de três etapas), clique no ícone **[!UICONTROL Configure]** ( ![ícone Configurar](/help/main/assets/icons/Setting.svg) ), clique em **[!UICONTROL Page Delivery]** e especifique a URL desejada.

![URL de Entrega de Página](/help/main/c-target/c-troubleshooting-targets-and-audiences/assets/activity-url.png)

O direcionamento de URL de público-alvo procura uma correspondência exata de URL. Se o URL corresponder, o Target não considerará a lógica adicional. Na URL acima, se a atividade estiver definida para ser acionada em `www.example.com`, a URL corresponderá às seguintes URLs, pois o direcionamento da URL de público-alvo é agnóstico em relação à consulta:

* `www.example.com?query=something`
* `www.example.com?query=anything`
* `www.example.com?query=nothing&qa=true&stuff=random&product=shoes&height=superTall`

Além do direcionamento de público-alvo no URL, você também pode especificar valores específicos que podem estar na query.

Direcionamento de URL de público-alvo e direcionamento de URL adicionado via [!UICONTROL Template Rules] avaliado como direcionamento de URL (consulte Direcionamento de URL abaixo).

### Direcionamento de URL {#url-targeting}

Para aplicar o direcionamento de URL, ao criar um público-alvo, clique em arrastar **[!UICONTROL Site Pages]** e solte-o no painel [!UICONTROL Create Audiences], clique em **[!UICONTROL Site Pages]**, selecione uma opção na primeira lista suspensa ([!UICONTROL Current Page], [!UICONTROL Previous Page] ou [!UICONTROL Landing Page]), selecione [!UICONTROL URL] na segunda lista suspensa, especifique um avaliador e especifique a URL desejada.

![Páginas do Site > Página Atual > URL](/help/main/c-target/c-troubleshooting-targets-and-audiences/assets/site-url.png)

O direcionamento de URL transforma o URL em um conjunto de regras para avaliar:

* URL = `example.com/path1/path2/path3?queryStringParam1=test123&queryStringParam2=test7`
* Domínio = `example.com`
* Caminho = `path1/path2/path3`
* Consulta = `queryStringParam1=test123&queryStringParam2=test7`

## Ao criar cadeias de caracteres de URL complexas, [!DNL Target] avalia a URL inteira?

Se você usar o mesmo nome de parâmetro mais de uma vez em uma string de URL, o HTTP considerará o primeiro nome de parâmetro e ignorará os parâmetros subsequentes com o mesmo nome.

Por exemplo, na seguinte string de URL:

`https://www.adobe.com/SearchResults.aspx?sc=BM&fi=1&fr=1&ps=0&av=0&Category=C0010438&Category=C000047`

a primeira instância do parâmetro `Category` é avaliada e o segundo parâmetro `Category` é ignorado.

A prática recomendada é ter vários valores associados a uma única categoria, conforme mostrado abaixo:

`https://www.adobe.com/SearchResults.aspx?sc=BM&fi=1&fr=1&ps=0&av=0&Category=C0010438,C000047`

## Ao criar públicos-alvo, por que os públicos-alvo pré-criados na Biblioteca [!DNL Target] podem ser vistos em outras categorias? {#section_9EBF5B0F9DF94168A15B92B905CCF7E0}

Os públicos pré-construídos na categoria Biblioteca do Target são herdados e existem em outras categorias. Por exemplo, o público-alvo herdado da Biblioteca do Target > Novos visitantes tem uma contraparte atualizada: Perfil do visitante > Novo visitante.

A prática recomendada é usar os públicos-alvo mais recentes, pois houve melhora no desempenho. Alguns clientes podem estar usando públicos-alvo herdados e pré-contruídos, por isso, eles não foram removidos da interface do Target.

## Como sei a forma que o tráfego será dividido entre os públicos-alvo?  {#section_067EEFB956E7465CBF77EC86834470AB}

Por padrão, o tráfego é dividido igualmente entre as experiências. No entanto, é possível especificar alvos de porcentagem para cada experiência. Nesse caso, um número aleatório será gerado e usado para escolher a experiência que será exibida. As porcentagens resultantes talvez não correspondam exatamente às metas especificadas, mas um maior tráfego significa que as experiências deverão ser divididas em maior harmonia com as metas-alvo.

## Qual experiência é exibida se um usuário se qualificar para uma atividade que contém várias experiências com vários públicos-alvo qualificados?  {#section_94A60B11212D48FD8AB0803C6C7E7253}

O usuário se qualifica para a primeira experiência/público-alvo exibido na página [!UICONTROL Target] da atividade.

Por exemplo, suponha que a experiência/público-alvo liste o Windows como Experiência A, o iOS como Experiência B e a Califórnia como Experiência C. Um usuário da Califórnia que usa um dispositivo Windows se qualifica para a Experiência A (público-alvo do Windows) e a Experiência C (público-alvo da Califórnia). Para esse usuário seria mostrada a Experiência A, pois ela é exibida na lista Experiência C acima, na página de Direcionamentos.

## Por que os nomes para o mesmo público-alvo do [!DNL Target], do Adobe Audience Manager (AAM) e da Biblioteca de público-alvo nos serviços principais são diferentes? {#section_F67E61A607B6444C8DAA4F99C3E95AED}

Os nomes dos públicos-alvo no [!DNL Target] são exclusivos; no entanto, no [!DNL AAM] e no [!DNL Audience Library], você pode ter vários públicos-alvo com o mesmo nome (se estiverem em pastas diferentes). Quando o [!DNL Target] encontra um nome de público-alvo que corresponde a um público-alvo do [!DNL AAM] ou do [!DNL Audience Library], o [!DNL Target] adiciona &quot;#&lt;number>&quot; ao nome.

Por exemplo, você pode ver os seguintes públicos-alvo: &quot;usuários de PC&quot; (na [!DNL AAM]) e &quot;usuários de PC #1&quot; (no [!DNL Target]).

## Por que não posso renomear um público-alvo? {#section_54E420556F534D20836E261E253D8B97}

Alguns públicos-alvo do Target são predefinidos, como &quot;Novos visitantes&quot; e &quot;Visitantes recorrentes&quot;. Esses públicos-alvo predefinidos não podem ser renomeados pelos usuários.

## Por que todos os parâmetros de perfil não são exibidos na interface do usuário [!DNL Target]? {#section_3CD947D15C984EE9AD19550220E0E8BD}

O [!DNL Target] tem um limite de 50 atributos de perfil exclusivos por chamada de mbox. Se você precisar passar mais de 50 atributos de perfil para [!DNL Target], é possível fazer isso usando o método de API [!UICONTROL Profile Update]. Para obter mais informações, consulte [Atualização do perfil](https://developers.adobetarget.com/api/#authentication-tokens) na documentação da API do Adobe Target.

## Por que os visitantes veem experiências para uma atividade de AP que não deveriam ver? {#section_41CECEAE0881446A8D9F3B016857914B}

As atividades de Personalização automatizada são avaliadas uma vez por sessão. Se houver sessões ativas que se qualificaram para uma experiência específica e agora novas ofertas foram adicionadas a elas, os usuários verão o novo conteúdo junto com as ofertas exibidas anteriormente. Como elas se qualificaram previamente para essas experiências, eles ainda as veriam durante a sessão. Se houver um desejo de avaliar isso em todas as visitas a uma página única, você deverá mudar para o tipo de atividade de Direcionamento de experiência (XT).

## Por que as alterações feitas aos públicos-alvo criadas por meio da API não são refletidas na interface do usuário do [!DNL Target]? {#section_6BEB237CAC004A06A290F9644E5BF0FB}

Diferente de ofertas e scripts de perfil, as alterações feitas pela API para públicos criadas pelo Target Standard atualmente não são sincronizadas para a interface do usuário do Target.

## Cadeias de caracteres que representam números (números de ponto flutuante também são compatíveis) são comparadas como números.{#strings-that-represent-numbers}

Se a parte esquerda e direita das expressões “é igual a” puder ser interpretada como um número, as duas partes serão comparadas como números e não como cadeias de caracteres.

Por exemplo:

| Valor | Critérios de direcionamento | Resultado |
| --- | --- | --- |
| 1.0 | é igual a 1 | true |
| 1 | equalsIgnoreCase 1.0 | true |
| 1,230 | é igual a 1 | true |
| 1,500 | é igual a 1,5 | true |
| 1,200 | é menor que 2 | true |
| 2 | é maior que 3,0 | false |
| 045 | é igual a 45 | true |

Os números escritos em notação científica serão sempre comparados como sequências de caracteres.

Por exemplo,

&quot;4e-2&quot; somente será igual a &quot;4e-2&quot;. Ele *não* será igual a &quot;0,04&quot;.
