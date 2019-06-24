---
description: Estas notas de versão fornecem informações sobre recursos, aprimoramentos, correções e problemas conhecidos para as versões mais recentes ou que serão lançadas em breve do Target.
keywords: notas de versão
seo-description: Estas notas de versão fornecem informações sobre recursos, aprimoramentos, correções e problemas conhecidos para as versões mais recentes ou que serão lançadas em breve do Adobe Target
seo-title: Notas de versão do Adobe Target (pré-lançamento)
solution: Target
title: Notas de versão do Target (pré-lançamento)
topic: Padrão
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: a30f868c49bca7a0c017d272b435a6a351c6e9a6

---


# Notas de versão do Target (pré-lançamento){#target-release-notes-prerelease}

Estas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para as versões mais recentes ou que serão lançadas em breve do [!DNL Adobe Target].

**Última atualização: 7 de junho de 2019**

>[!NOTE]
>
>Essas notas de versão contêm informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos a alteração sem aviso prévio. Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser iguais ou diferentes, dependendo do tempo das versões.
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## Target Standard/Premium 19.6.1 (25 de junho de 2019) {#tgt-19-6-1}

Esta versão inclui os seguintes novos recursos e melhorias:

| Recurso / Aprimoramento | Descrição |
| --- | --- |
| Visual Experience Composer (VEC) | **Novas opções de menu VEC**: Quando você clica em um elemento de página no VEC, um menu mostra as opções disponíveis para esse tipo de elemento.<ul><li>You can now use the [!UICONTROL Styles &gt; Background] option to change the background image and color for the selected element. (TGT-15001)</li></ul>**Melhorias no rastreamento de cliques**: Melhoramos o processo para configurar o rastreamento de cliques no VEC e no VEC de aplicativos de página única (SPA).<ul><li>Ao selecionar elementos a serem usados no rastreamento de cliques, os nomes de todos os elementos disponíveis são exibidos no painel Modificações do lado direito, facilitando a seleção dos elementos desejados.</li><li>The [!UICONTROL Goals &amp; Settings] page of the three-part guided activity workflow displays a number representing the number of elements selected for click tracking. Você pode passar o mouse sobre esse número para ver os nomes de todos os elementos selecionados. (TGT-33878)</li></ul> |
| Aplicativo de página única no Visual Experience Composer (SPA VEC) | **Fluxo de trabalho guiado**: Um novo fluxo de trabalho guiado ajuda você a entender como as configurações da regra de entrega de página devem ser configuradas para executar e executar uma atividade com sucesso para seu Aplicativo de página única. (TGT-33718)<br>**Clone modifications**: You can now define a modification using the SPA VEC and then clone that modification for use in other views in your Single Page App. (TGT-33882) |
| Mobile Visual Experience Composer | **Várias versões do aplicativo**: Agora você pode criar atividades para várias versões do seu aplicativo móvel. Isso economiza tempo e esforço quando as versões são semelhantes e você não precisa alterar significativamente a interface do usuário do aplicativo. (TGT-34231) |
| ![Selo](/help/assets/premium.png) Premium personalização automatizada (AP) e auto-direcionamento | **Experiência específica como controle**: Você pode selecionar uma experiência a ser usada como controle ao criar uma atividade AP ou Auto-Target. Esse recurso permite direcionar todo o tráfego de controle para uma experiência específica, com base na porcentagem de alocação de tráfego configurada na atividade. Em seguida, você pode avaliar os relatórios de desempenho do tráfego personalizado contra o controle do tráfego para aquela experiência. A opção de controle atual (experiências aleatoriamente enviadas) continuará disponível. (TGT-32801 &amp; TGT-26572)<br>**Personalization Insights reports**: The marketer-friendly naming for attributes when a visitor sees a specific piece of content in a specific location provides more meaningful information. (TGT-33326 e TGT-34957) |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
