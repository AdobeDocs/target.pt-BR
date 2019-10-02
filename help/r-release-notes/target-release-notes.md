---
description: Release notes that provide information about features, enhancements, and fixes for the latest or upcoming Adobe Target releases.
keywords: release notes;releases;updates;future release;enhancements;new features;fixes
seo-description: Notas de versão que fornecem informações sobre recursos, melhorias e correções para as versões mais recentes ou futuras do Adobe Target DNL.
seo-title: Adobe Target prerelease notes
solution: Target
title: Notas de versão do Target (pré-lançamento)
topic: Padrão
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 285a09503ba6abaf2bfe19fc2b214c32ebd2de3a

---


# Notas de versão do Target (pré-lançamento){#target-release-notes-prerelease}

Estas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para as versões mais recentes ou que serão lançadas em breve do [!DNL Adobe Target].

**Última atualização em: 2 outubro de 2019**

>[!NOTE]
>
>Essas notas de versão contêm informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio. Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser iguais ou diferentes, dependendo do tempo das versões.
>
>Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## Plataforma de destino (datas a serem determinadas)

| Recurso  / Aprimoramento | Descrição |
| --- | --- |
| Node.js SDK versão 1.0 | O SDK do Target Node.js permite implantar o servidor do Target.<br>Esse SDK do Node.js ajuda a integrar facilmente o Target a outras soluções da Experience Cloud, como o Adobe Experience Cloud Identity Service, o Adobe Analytics e o Adobe Audience Manager.<br>O SDK do Node.js apresenta práticas recomendadas e remove complexidades ao integrar-se ao Adobe Target por meio de nossa API de entrega, para que suas equipes de engenharia possam se concentrar na lógica comercial. A seguir estão recursos notáveis que estamos introduzindo na versão mais recente:<ul><li>Suporte para busca prévia e notificações que permitem otimizar o desempenho por meio do cache.</li><li>Suporte para otimizar o desempenho quando você tem uma integração híbrida do Target em suas páginas da Web e no servidor. Estamos introduzindo uma configuração chamada `serverState` que será preenchida por experiências recuperadas pelo lado do servidor para que o at.js 2.2 não faça mais uma chamada de servidor adicional para recuperar as experiências. Essa abordagem otimiza o desempenho de carregamento da página.</li><li> Support for retrieving VEC-created activities via the Node.js SDK, which is made possible by the new Delivery API.</li><li>Criado de forma aberta para que seus desenvolvedores possam contribuir com o SDK Node.js.</li></ul> |
| Delivery API | An entirely new delivery API endpoint (/v1/delivery) will be available in production. Notable features are:<ul><li>One endpoint to retrieve experiences for one or more mboxes.</li><li>Retrieve VEC-created activities via the API.</li><li>Suporte para um objeto totalmente novo chamado Exibições, usado para aplicativos de página única (SPAs) e aplicativos móveis.</li></ul> |
| at.js version 2.2andat.js version 1.8<br><br> | Essas versões do at.js fornecem:<ul><li>Improved performance when using both Experience Cloud ID Service (ECID) v4.4 and at.js 2.2 or at.js 1.8 on your web pages.</li><li>Previously, the ECID made two blocking calls before at.js could fetch experiences. Isso foi reduzido a uma única chamada, o que melhora significativamente o desempenho.</li></ul> Para aproveitar essas melhorias de desempenho, atualize para at.js 2.2 ou at.js 1.8 junto com a Biblioteca ECID v4.4. |


## Target Standard/Premium 19.10.1 (22 de outubro de 2019)

| Recurso  / Aprimoramento | Descrição |
| --- | --- |
| ![Recomendações baseadas](/help/assets/premium.png) no usuário do selo Premium | Recomenda itens com base no histórico de navegação, visualização e compra de cada visitante. Esses itens são geralmente chamados de "Recomendado para você".<br>Esse critério permite que você forneça conteúdo e experiências personalizadas para visitantes novos e recorrentes. A lista de recomendações é ponderada em relação à atividade mais recente do visitante, é atualizada na sessão e se torna mais personalizada à medida que o visitante navega em seu site. |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
