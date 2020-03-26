---
keywords: targeting;cookie;first-party cookie;1st-party cookie
description: Adobe Target integra-se com as páginas da Web por meio da biblioteca de JavaScript de at.js ou mbox.js.
title: Como funciona o direcionamento
uuid: 8b5a36c0-555d-42c5-8b24-c08d07440a53
translation-type: tm+mt
source-git-commit: ba4c776d93f911c122f36113a99ce4349b3c5524

---


# Como funciona o direcionamento{#how-targeting-works}

Adobe Target integra-se com as páginas da Web por meio da biblioteca de JavaScript de at.js ou mbox.js. Uma biblioteca JavaScript referenciada em cada página é tudo o que você precisa para executar suas atividades de otimização.

Cada vez que um visitante solicita uma página ativada pelo, o [!DNL Target]Target usa o seguinte processo para fornecer as ofertas:

1. Um cliente solicita uma página do seu servidor e ela é exibida no navegador.
1. Um cookie de origem é configurado no navegador do cliente para definir uma ID de visitante exclusiva.

   Uma [!DNL Experience Cloud visitor ID] também é definida se você estiver usando o Perfil mestre de marketing.

1. A página faz uma chamada para o [!DNL Target] através do arquivo [!DNL target.js] ou uma mbox na sua página.
1. O [!DNL Target] faz referência do perfil associado com o visitante.
1. O [!DNL Target] executa todos os scripts de perfis associados com esse perfil.
1. [!DNL Target]O calcula a sua resposta.
1. O conteúdo é exibido com base nas regras de sua atividade ou campanha.

A oferta exibida em um teste A/B básico é escolhida aleatoriamente. Em resultado dessa divisão aleatória de tráfego, pode ser necessário muito tráfego inicial mesmo antes de as porcentagens aparecerem. Por exemplo, se você tiver uma atividade com duas experiências, a experiência inicial será escolhida aleatoriamente. Se houver pouco tráfego, é possível que a porcentagem de visitantes venha a tender para uma experiência. Com o aumento do tráfego, as porcentagens devem se igualar cada vez mais.
