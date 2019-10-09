---
description: Essas notas de versão oferecem informações sobre recursos, aprimoramentos, correções e problemas conhecidos para cada lançamento do Target Standard e do Target Premium.
keywords: Notas de versão;novos recursos;lançamentos;atualizações;atualização;versão;aprimoramentos;correções;correções;correções de erros;notas de versão;novos recursos;lançamentos;atualizações;atualização;release;aprimoramentos;correções;correções
seo-description: Essas notas de versão oferecem informações sobre recursos, aprimoramentos, correções e problemas conhecidos para cada lançamento do Adobe Target Standard e do Target Premium.
seo-title: 'Notas de versão do Target (atual) '
solution: Target
title: Notas de versão do Target (atual)
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 71d94ef5d2351dc8410c0d418096088a0a900f03

---


# Notas de versão do Target (atual){#target-release-notes-current}

Essas notas de versão oferecem informações sobre recursos, aprimoramentos e correções para cada lançamento do Target Standard e do Target Premium. Além disso, as notas de versão para APIs do Target, SDKs, biblioteca JavaScript (at.js) e outras alterações da plataforma também são incluídas, quando aplicável.

## Plataforma Target (9 de outubro de 2019)

| Recurso  / Aprimoramento | Descrição |
| --- | --- |
| Node.js SDK versão 1.0 | O SDK do Target Node.js permite implantar o servidor do Target.<br>Esse SDK do Node.js ajuda a integrar facilmente o Target a outras soluções da Experience Cloud, como o Adobe Experience Cloud Identity Service, o Adobe Analytics e o Adobe Audience Manager.<br>O SDK do Node.js apresenta práticas recomendadas e remove complexidades ao integrar-se ao Adobe Target por meio de nossa API de entrega, para que suas equipes de engenharia possam se concentrar na lógica comercial. A seguir estão recursos notáveis que estamos introduzindo na versão mais recente:<ul><li>Suporte para busca prévia e notificações que permitem otimizar o desempenho por meio do cache.</li><li>Suporte para otimizar o desempenho quando você tem uma integração híbrida do Target em suas páginas da Web e no servidor. Estamos introduzindo uma configuração chamada `serverState` que será preenchida por experiências recuperadas pelo lado do servidor para que o at.js 2.2 não faça mais uma chamada de servidor adicional para recuperar as experiências. Essa abordagem otimiza o desempenho de carregamento da página.</li><li> Suporte para recuperar atividades criadas pelo VEC por meio do SDK Node.js, que é possibilitado pela nova API de entrega.</li><li>Criado de forma aberta para que seus desenvolvedores possam contribuir com o SDK Node.js.</li></ul><br>Para obter mais informações, consulte Notas de [versão - SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md)do Target Node.js. |
| API de entrega | Um terminal de API de entrega totalmente novo (/v1/delivery) está disponível na produção. Os principais recursos são:<ul><li>Um terminal para recuperar experiências para uma ou mais mboxes.</li><li>Recupere atividades criadas pelo VEC por meio da API.</li><li>Suporte para um objeto totalmente novo chamado Exibições, usado para aplicativos de página única (SPAs) e aplicativos móveis.</li></ul><br>Para obter mais informações, consulte Notas de [versão - APIs](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md)do servidor do Target. |

## Target Standard/Premium 19.9.2 (30 de setembro de 2019)

Esta versão de manutenção inclui o seguinte aprimoramento:

* Várias correções de segurança, incluindo uma atualização de segurança para o Rich Text Editor (RTE) no Visual Experience Composer (VEC). (TGT-35383)
* As ofertas do Recommendations agora podem ser adicionadas a outros elementos que não o DIV (p. ex. P, UL, H1), além do DIV, em atividades de teste A/B e direcionamento de experiência. (TGT-34333)
* As notificações de evento (o ícone de sinalizador na interface de usuário do Target) não estão mais disponíveis. Uma nova busca por notificações será lançada em breve.

## Target Standard/Premium 19.9.1 (10 de setembro de 2019)

| Recurso  / Aprimoramento | Descrição |
| --- | --- |
| ![Permissões para empresas com o selo](/help/assets/premium.png) Premium | Com a versão de setembro de 2019 do Target, as Permissões corporativas fornecem aos clientes os seguintes controles de acesso:<UL><li>É possível escolher os espaços de trabalho aos quais a integração pode ser aplicada.</li><li>Você pode aplicar uma função à integração do Adobe I/O: Aprovador, Editor ou Observador.</li></ul>Para obter instruções passo a passo e mais informações, consulte [Conceder acesso às integrações do Adobe I/O para espaços de trabalho e atribuir funções](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md). |

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão - APIs do servidor do Target](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Notas de versão relacionadas às APIs do servidor do Adobe Target. |
| [Notas de versão - SDK do Target Node.js](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Notas de versão relacionadas ao SDK Node.js do Adobe Target. |
| [Detalhes da versão da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Detalhes sobre as alterações em cada versão da biblioteca JavaScript do Adobe Target at.js. |
| [Detalhes da versão da mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | Esta página mostra as alterações em cada versão da mbox.js.<br>Observe que a biblioteca mbox.js não está mais sendo desenvolvida. Todos os clientes devem migrar da mbox.js para a at.js. |

## Alterações na documentação, notas de versão anteriores e notas de versão da Experience Cloud {#section_1BC5F5208DA548E9B4344A0836E4B943}

Além das notas para cada versão, os recursos a seguir oferecem informações adicionais:

| Recurso | Detalhes |
|--- |--- |
| Alterações de documentação | Veja informações detalhadas sobre atualizações neste manual que podem não ser incluídas nas notas de versão.<br>Para obter mais informações, consulte [Alterações de documentação](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de versão para versões anteriores | Veja informações sobre os novos recursos e aprimoramentos das versões anteriores do Target Standard e do Target Premium.<br>Para obter mais informações, consulte [Notas de versões anteriores](../r-release-notes/release-notes-for-previous-releases.md). |
| Notas de versão da Adobe Experience Cloud | Veja as notas de versão mais recentes para as soluções da Adobe Experience Cloud.<br>Para obter mais informações, consulte Notas [de versão da](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)Experience Cloud. |

## Informações de pré-lançamento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Os recursos a seguir permitem ver as novidades previstas para a próxima versão do Target.

| Recurso | Detalhes |
|--- |--- |
| Lista de atualização de produtos prioritários da Adobe | Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Notas de versão futuras | Para obter informações sobre os lançamentos do Target do mês atual, incluindo informações de pré-lançamento, consulte a página [Notas de versão do Target - Pré-lançamento](/help/r-release-notes/target-release-notes.md). |
