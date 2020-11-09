---
keywords: Implementation;Mbox;download mbox.js;download api;mbox.js api
description: Para usar o Target Standard ou Target Premium, adicione uma linha de código para chamar a mbox.js.
title: Implementação da mbox.js
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 55%

---


# Implementação da mbox.js{#mbox-js-implementation}

Para usar o Target Standard ou Target Premium, adicione uma linha de código para chamar a mbox.js.

Você pode usar qualquer uma das duas referências da biblioteca: [!DNL mbox.js] ou [!DNL at.js]. [Vantagens da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) explica as diferenças entre as duas bibliotecas.

>[!NOTE]
>
>**Fim da vida útil** do mbox.js: Em 18 de janeiro de 2021, a Adobe Target não oferecerá mais suporte à biblioteca mbox.js. Após 18 de janeiro de 2021, todas as chamadas feitas a partir do mbox.js falharão e afetarão suas páginas que possuem atividades Públicos alvos em execução, atendendo ao conteúdo padrão. Recomendamos que todos os clientes migrem para a versão mais recente da biblioteca do at.js antes dessa data para evitar possíveis problemas com seus sites. For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md).
>
>Embora a mbox.js seja atualmente compatível, não fornecemos atualizações de recursos para esta biblioteca desde julho de 2017. O mais recente at.js oferece muitas vantagens sobre o mbox.js. Entre outros benefícios, o at.js melhora o tempo de carregamento da página para implementações da Web, melhora a segurança e oferece melhores opções de implementação para aplicativos de página única.
>
>Ao mudar todos os clientes para o at.js, nossos engenheiros e funcionários de suporte poderão oferecer novas funcionalidades e oferta do suporte que você espera da Adobe.

A única referência para a [!DNL mbox.js] em cada página fornece as bibliotecas necessárias para todas suas atividades. A [!DNL mbox.js] chama o [!DNL Target] de cada página que referencia o arquivo [!DNL mbox.js]. Isso permite que o [!DNL Target] faça o seguinte:

* Entregar atividades do Target
* Rastreie cliques
* Rastreie a maioria das métricas de sucesso

>[!TIP]
>
>Para simplificar a implementação, você pode referenciar a [!DNL mbox.js] no seu cabeçalho global.

Você não precisa manter versões específicas de atividades diferentes do arquivo.

1. Referencie a [!DNL mbox.js] na seção `<head>` de cada página do seu site.

   `<script src="/ *`directory`*/ *`scripts`*/mbox.js"></script>`

   Onde ` *`directory`*/ *`scripts`*` é o diretório onde você salvou o [!DNL mbox.js] arquivo depois de baixá-lo. 
Se você já tiver mboxes na sua página de uma implementação existente, essas mboxes ainda poderão ser usadas na nova interface. O arquivo [!DNL mbox.js] atualizado ainda é necessário, mas essas mboxes podem ser selecionadas para atividades e editadas usando o [!UICONTROL Visual Experience Composer].