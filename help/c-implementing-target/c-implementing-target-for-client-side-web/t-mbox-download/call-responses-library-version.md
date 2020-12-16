---
description: A maneira como o Target faz e responde a chamadas de sua página dependerá da versão da biblioteca do Target em uso, se a implementação da ID de visitante de Experience Cloud estiver presente e se a ID de visitante existir.
title: Métodos de página do Target por versão da biblioteca mbox.js
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 100%

---


# Métodos de página do Target por versão da biblioteca mbox.js{#target-page-methods-by-mbox-js-library-version}

A maneira como o Target faz e responde a chamadas de sua página dependerá da versão da biblioteca do Target em uso, se a implementação da ID de visitante de Experience Cloud estiver presente e se a ID de visitante existir.

>[!NOTE]
>
>Se você utilizar [!DNL at.js], todas as chamadas serão feitas usando JSON. Esta página contém detalhes sobre as versões da biblioteca da [!DNL mbox.js]. Os comportamentos descritos nas situações abaixo não se aplicam a [!DNL at.js].

Esta seção oferece informações sobre como cada versão da biblioteca do [!DNL Target] responde à chamada do [!DNL Target] em sua página em cada uma das seguintes situações.

Há vários tipos ou endpoints, dependendo da implementação e da versão da biblioteca. Familiarize-se com cada tipo para entender como o [!DNL Target] responde às chamadas em cada situação.

| Tipo/Endpoint | Método de chamada | Conteúdo da resposta |
|--- |--- |--- |
| autocriar mbox global - síncrono | document.write para fazer chamada | JavaScript sem document.write() |
| autocriar mbox global - assíncrono | createElement() para anexar chamada ao body | JavaScript sem document.write() |
| padrão | document.write para fazer chamada | JavaScript com document.write() |
| ajax | createElement() para anexar chamada ao body | JavaScript sem document.write() |
| json | XMLHTTPrequest() para fazer chamada | retorna resposta JSON |

>[!IMPORTANT]
>
>Para qualquer tipo, exceto padrão, todos os códigos e ofertas personalizados devem ser escritos para oferecer compatibilidade com um ambiente ajax. Por exemplo, se você usar um JavaScript que inclui `document.write()`, o script não funcionará conforme o esperado.

## Sem implementação de ID de visitante {#section_C6F7213FDE4D48E8BBCB1A9A26310FEE}

Se você está usando o [!DNL Target Standard] ou [!DNL Premium] com [!DNL mbox.js], e ativou [!UICONTROL Criar mbox global] para sua conta, é feito o tipo de chamada e resposta **criar mbox global automaticamente - síncrono**, independentemente da versão da [!DNL mbox.js].

Se você escrever seu próprio código personalizado em vez de usar as ações do [!UICONTROL Visual Experience Composer], certifique-se de que seu código seja adequado para um ambiente ajax. Por exemplo, se você usar um JavaScript que inclui `document.write()`, o script não funcionará conforme o esperado.

>[!NOTE]
>
>Várias chamadas de mbox ajax com o mesmo nome de mbox, mas diferentes parâmetros, não funcionarão na mesma página. Somente a primeira chamada será feita.

Se você usar &quot;criar mbox global automaticamente&quot;, mas também tiver chamadas `mboxCreate` em sua página, por exemplo, se estiver implementando o [!DNL Target Standard] ou [!DNL Premium] em uma página que era anteriormente usada na implementação antiga, as chamadas da mbox global serão feitas usando o endpoint **criar mbox glonal automaticamente - padrão** e as chamadas `mboxCreate` são feitas usando o endpoint **padrão**. O endpoint **padrão** usa `document.write()` para fazer a chamada e responder. Isso bloqueia o carregamento da página, inclusive o conteúdo entregue na resposta ajax, até que toda a informação seja baixada.

Se você usar somente o mboxCreate, por exemplo, em páginas criadas com o [!DNL Target Classic], a página funcionará como sempre funcionou.

| Método de criação | mbox.js v57 | mbox.js v58 | mbox.js v59 | mbox.js v60 |
|---|---|---|---|---|
| autocriar mbox global | autocriar mbox global - síncrono | autocriar mbox global - síncrono | autocriar mbox global - síncrono | autocriar mbox global - síncrono |
| mboxCreate | padrão | padrão | padrão | padrão |

## Implementação de ID de visitante presente, mas sem ID de visitante definida   {#section_29888A119C7A4753AD287FC845AA63F4}

Se nenhuma ID de visitante foi configurada, não há nenhum cookie de visitante da [!DNL Experience Cloud] para o usuário. A página chama o serviço de ID de visitante para obter a ID de visitante. O aguarda a resposta com a ID que está fazendo a chamada para o [!DNL Target]Target.

>[!NOTE]
>
>[!DNL Mbox.js] A v58 é altamente recomendado para garantir que a ID de visitante retorne antes que a chamada do Target seja feita.

Se você estiver usando a versão 57 da [!DNL mbox.js] nesta situação, tudo funcionará adequadamente se não houver implementação da ID de visitante, conforme descrito na situação anterior. A partir [!DNL mbox.js] da versão 58, o [!DNL Experience Cloud Visitor ID] serviço retorna com uma ID de visitante antes de [!DNL Target] efetuar chamadas. Isso garante que os dados do público-alvo compartilhados por meio do serviço central de perfis e públicos sejam disponibilizados para a primeira chamada do [!DNL Target] na sessão do visitante. Para evitar a cintilação do conteúdo padrão antes do retorno do conteúdo do teste, [!DNL Target] oculta o `<BODY>` até o retorno do serviço de ID de visitante. Na versão 58, `display:none` é usado para ocultar a página. Isso gera alguns problemas com sites responsivos, então a partir da versão 59, `opacity:0` é usado para ocultar o conteúdo.

| Método de criação | mbox.js v57 | mbox.js v58 | mbox.js v59 | mbox.js v60 |
|---|---|---|---|---|
| autocriar mbox global | autocriar mbox global - síncrono | autocriar mbox global - assíncrono | autocriar mbox global - assíncrono | autocriar mbox global - assíncrono |
| mboxCreate | padrão | ajax | ajax | ajax |

## Implementação de ID de visitante presente, e a ID de visitante existe   {#section_9CD4AE4C8186425D886398BC3CE6C46D}

Se houver cookie de ID de visitante, o [!DNL Target] não precisará fazer uma chamada para o serviço de ID de visitante. Nesse caso, não há necessidade de aguardar o serviço de ID de visitante antes de exibir o conteúdo. Das versões 57 a 59, o tipo **criar mbox global automaticamente - síncrono** é usado, então a página aguarda a chamada para o [!DNL Target] retornar antes de continuar o carregamento. Isso impede a oscilação do conteúdo padrão. Para a versão 60, o **tipo mbox global - assíncrono** é usado para garantir que o [!DNL Target] aguarde o serviço de cancelamento da [!DNL Experience Cloud] para responder. O serviço de cancelamento é parte do lançamento do Data Co-op no quarto trimestre de 2016. Como todas as chamadas são retornadas usando o ajax, `document.write()` não deve ser usado com a [!DNL mbox.js] versão 60.

| Método de criação | mbox.js v57 | mbox.js v58 | mbox.js v59 | mbox.js v60 |
|---|---|---|---|---|
| autocriar mbox global | autocriar mbox global - síncrono | autocriar mbox global - síncrono | autocriar mbox global - síncrono | criar mbox global automaticamente - assíncrono (para auxiliar o desenvolvimento do Data Co-op, que será lançado posteriormente em 2016) |
| mboxCreate | padrão | padrão | padrão | ajax |