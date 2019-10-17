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
source-git-commit: 0a9cf0e98f5f833402b96f37df5513325222ad19

---


# Notas de versão do Target (pré-lançamento){#target-release-notes-prerelease}

Estas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para as versões mais recentes ou que serão lançadas em breve do [!DNL Adobe Target].

**Última atualização em: 17 outubro de 2019**

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
| at.js versão 2.2<br><br>andat.js versão 1.8<br>(10 de outubro de 2019) | Essas versões do at.js fornecem:<ul><li>Desempenho aprimorado ao usar o Serviço da Experience Cloud ID (ECID) v4.4 e o at.js 2.2 ou o at.js 1.8 em suas páginas da Web.</li><li>Anteriormente, o ECID fazia duas chamadas de bloqueio antes que o at.js pudesse buscar experiências. Isso foi reduzido a uma única chamada, o que melhora significativamente o desempenho.</li></ul> Para aproveitar essas melhorias de desempenho, atualize para at.js 2.2 ou at.js 1.8 junto com a Biblioteca ECID v4.4.<br>at.js 2.2 fornece:<ul><li>**serverState**: Uma configuração disponível em at.js v2.2+ que pode ser usada para otimizar o desempenho da página quando uma integração híbrida do Target é implementada. A integração híbrida significa que você está usando o at.js v2.2+ no lado do cliente e a API de entrega ou um SDK do Target no lado do servidor para fornecer experiências. `serverState` oferece ao at.js v2.2+ a capacidade de aplicar experiências diretamente do conteúdo obtido no lado do servidor e retornado ao cliente como parte da página que está sendo fornecida.<br>Para obter mais informações, consulte "serverState" em [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#server-state).</li></ul> |


## Target Standard/Premium 19.10.1 (22 de outubro de 2019)

| Recurso  / Aprimoramento | Descrição |
| --- | --- |
| ![Recomendações baseadas](/help/assets/premium.png) no usuário do selo Premium | Recomenda itens com base no histórico de navegação, visualização e compra de cada visitante. Esses itens são geralmente chamados de "Recomendado para você".<br>Esse critério permite que você forneça conteúdo e experiências personalizadas para visitantes novos e recorrentes. A lista de recomendações é ponderada em relação à atividade mais recente do visitante, é atualizada na sessão e se torna mais personalizada à medida que o visitante navega em seu site. |

### Melhorias, correções e alterações

* Alterações no Adobe Unified Shell.

   A Adobe está fazendo atualizações no shell existente (a barra preta na parte superior das [!DNL Experience Cloud] soluções) para unificar e melhorar sua experiência em todas as [!DNL Adobe Experience Cloud] soluções.

   Não há mudanças nos fluxos de trabalho atuais, e essas mudanças aparentemente simples foram projetadas para tornar sua vida mais fácil de formas pequenas, mas importantes.

   Ao efetuar logon no [!DNL Adobe Experience Cloud], você será direcionado para o novo Unified Shell. É muito semelhante ao Shell anterior com a barra preta na parte superior, mas oferece as seguintes melhorias:

   * É mais fácil alternar entre organizações do sistema de gerenciamento de identidade (IMS) ou para uma solução diferente da Experience [!ECloud] .
   * Ajuda do usuário aprimorada: Os resultados da pesquisa incluem os resultados da documentação do [!DNL Target] produto, bem como fóruns da comunidade e mais conteúdo de vídeo, facilitando o acesso a mais conteúdo para ajudá-lo a obter o máximo proveito [!DNL Target]. Também adicionamos um mecanismo de feedback diretamente no menu Ajuda, facilitando o relatório de problemas ou o compartilhamento de suas ideias.
   * Funcionalidade NPS (Net Promoter Score) aprimorada. Algumas vezes, alguns clientes visualizaram [!DNL Target] pesquisas com uma frequência mais alta do que nós pretendemos. Além disso, o modal da pesquisa usado para perturbar seu fluxo de trabalho. Atualizamos essa funcionalidade completamente para que se torne uma pequena pesquisa que não seja mais intrusiva. Além disso, com o novo desenho, podemos garantir que a frequência do estudo seja mais bem controlada.
   * Fluxo de logon aprimorado. Anteriormente, todos os [!DNL Target] clientes chegavam na página inicial do Target depois de clicar no [!DNL Target] ícone no Shell. Essa página permitiu que os clientes continuassem com [!DNL Target Standard/Premium], [!DNo Recommendations Classic]ou [!DNL Search&Promote], como mostrado abaixo:

      ![Página de aterrissagem](/help/r-release-notes/assets/landing.png)

      Eliminamos esta página de aterrissagem para todos os nossos clientes. Agora, você sempre é direcionado diretamente para a página Lista [!UICONTROL de] atividades clicando no [!DNL Target] ícone.

      Se você usar [!DNL Recommendations Classic], poderá ir diretamente para a solução ou ir do link curto criado na guia [!UICONTROL Recomendações] , como mostrado abaixo:

      ![Link profundo Recs Classic](/help/r-release-notes/assets/recs-classic.png)

      Se você usar [!DNL Search&Promote], precisará ir diretamente para o link. O caminho para acessar o Search&amp;Promote de dentro de [!DNL Adobe Target] um foi completamente removido.
   * No momento, as notificações para não [!DNL Target] estão mais visíveis no menu suspenso [!UICONTROL Notificações] no Shell.
   >[!NOTE]
   >
   >Esses recursos não serão implementados de uma vez, nem serão lançados para todos os clientes juntos. Estaremos lançando esses recursos nos próximos dias, começando na versão [!DNL Target Standard/Premium] 19.10.1 (22 de outubro de 2019).
   >
   >Como parte do lançamento do novo Shell, você também notará algumas alterações no URL. Todos os links marcados anteriores continuam a funcionar, mas recomendamos que você marque novos links para uma abertura mais rápida.

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
