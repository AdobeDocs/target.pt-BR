---
description: Notas de versão que fornecem informações sobre recursos, melhorias e correções para as versões mais recentes ou futuras do Adobe Target.
keywords: notas de versão;versões;atualizações;versão futura;melhorias;novos recursos;correções
seo-description: Notas de versão que fornecem informações sobre recursos, melhorias e correções para as versões mais recentes ou futuras do Adobe Target DNL.
seo-title: Notas de pré-lançamento do Adobe Target
solution: Target
title: Notas de versão do Target (pré-lançamento)
topic: Padrão
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 9fa095b910b85f244b626c34cacdf9f4a13a6929

---


# Notas de versão do Target (pré-lançamento){#target-release-notes-prerelease}

Estas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para as versões mais recentes ou que serão lançadas em breve do [!DNL Adobe Target].

**Última atualização em: 2 outubro de 2019**

>[!NOTE]
>
>Essas notas de versão contêm informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio. Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser iguais ou diferentes, dependendo do tempo das versões.
>
>Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## Plataforma de destino

| Recurso  / Aprimoramento | Descrição |
| --- | --- |
| Node.js SDK versão 1.0<br>(9 de outubro de 2019) | O SDK do Target Node.js permite implantar o servidor do Target.<br>Esse SDK do Node.js ajuda a integrar facilmente o Target a outras soluções da Experience Cloud, como o Adobe Experience Cloud Identity Service, o Adobe Analytics e o Adobe Audience Manager.<br>O SDK do Node.js apresenta práticas recomendadas e remove complexidades ao integrar-se ao Adobe Target por meio de nossa API de entrega, para que suas equipes de engenharia possam se concentrar na lógica comercial. A seguir estão recursos notáveis que estamos introduzindo na versão mais recente:<ul><li>Suporte para busca prévia e notificações que permitem otimizar o desempenho por meio do cache.</li><li>Suporte para otimizar o desempenho quando você tem uma integração híbrida do Target em suas páginas da Web e no servidor. Estamos introduzindo uma configuração chamada `serverState` que será preenchida por experiências recuperadas pelo lado do servidor para que o at.js 2.2 não faça mais uma chamada de servidor adicional para recuperar as experiências. Essa abordagem otimiza o desempenho de carregamento da página.</li><li> Suporte para recuperar atividades criadas pelo VEC por meio do SDK Node.js, que é possibilitado pela nova API de entrega.</li><li>Criado de forma aberta para que seus desenvolvedores possam contribuir com o SDK Node.js.</li></ul>Para obter mais informações, consulte Notas de [versão - SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md)do Target Node.js. |
| API<br>de entrega (9 de outubro de 2019) | Um terminal de API de entrega totalmente novo (/v1/delivery) estará disponível na produção. Os principais recursos são:<ul><li>Um terminal para recuperar experiências para uma ou mais mboxes.</li><li>Recupere atividades criadas pelo VEC por meio da API.</li><li>Suporte para um objeto totalmente novo chamado Exibições, usado para aplicativos de página única (SPAs) e aplicativos móveis.</li></ul>Para obter mais informações, consulte Notas de [versão - APIs](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md)do servidor do Target. |
| at.js versão 2.2<br><br>andat.js versão 1.8<br>(datas a determinar) | Essas versões do at.js fornecem:<ul><li>Desempenho aprimorado ao usar o Serviço da Experience Cloud ID (ECID) v4.4 e o at.js 2.2 ou o at.js 1.8 em suas páginas da Web.</li><li>Anteriormente, o ECID fazia duas chamadas de bloqueio antes que o at.js pudesse buscar experiências. Isso foi reduzido a uma única chamada, o que melhora significativamente o desempenho.</li></ul> Para aproveitar essas melhorias de desempenho, atualize para at.js 2.2 ou at.js 1.8 junto com a Biblioteca ECID v4.4. |


## Target Standard/Premium 19.10.1 (22 de outubro de 2019)

| Recurso  / Aprimoramento | Descrição |
| --- | --- |
| ![Recomendações baseadas](/help/assets/premium.png) no usuário do selo Premium | Recomenda itens com base no histórico de navegação, visualização e compra de cada visitante. Esses itens são geralmente chamados de "Recomendado para você".<br>Esse critério permite que você forneça conteúdo e experiências personalizadas para visitantes novos e recorrentes. A lista de recomendações é ponderada em relação à atividade mais recente do visitante, é atualizada na sessão e se torna mais personalizada à medida que o visitante navega em seu site. |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
