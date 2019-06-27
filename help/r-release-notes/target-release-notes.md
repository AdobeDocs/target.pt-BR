---
description: Estas notas de versão fornecem informações sobre recursos, aprimoramentos, correções e problemas conhecidos para as versões mais recentes ou que serão lançadas em breve do Adobe Target.
keywords: notas de versão
seo-description: Estas notas de versão fornecem informações sobre recursos, aprimoramentos, correções e problemas conhecidos para as versões mais recentes ou que serão lançadas em breve do Adobe Target
seo-title: Notas de versão do Adobe Target (pré-lançamento)
solution: Target
title: Notas de versão do Target (pré-lançamento)
topic: Padrão
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 51bf163881a651ce6ab92dcc6753a91f6d6cc4f8

---


# Notas de versão do Target (pré-lançamento){#target-release-notes-prerelease}

Estas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para as versões mais recentes ou que serão lançadas em breve do [!DNL Adobe Target].

**Última atualização: 25 de junho de 2019**

>[!NOTE]
>
>Essas notas de versão contêm informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos a alteração sem aviso prévio. Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser iguais ou diferentes, dependendo do tempo das versões.
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## Target Standard/Premium 19.6.1 (26 de junho de 2019) {#tgt-19-6-1}

Esta versão inclui os seguintes novos recursos e melhorias:

| Recurso / Aprimoramento | Descrição |
| --- | --- |
| Visual Experience Composer (VEC) | **Novas opções de menu VEC**: Quando você clica em um elemento de página no VEC, um menu mostra as opções disponíveis para esse tipo de elemento.<ul><li>You can now use the [!UICONTROL Styles &gt; Background] option to change the background image and color for the selected element. (TGT-15001)</li></ul>See *Styles* in [Visual Experience Options](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#styles).<br>**Melhorias no rastreamento de cliques**: Melhoramos o processo para configurar o rastreamento de cliques no VEC e no VEC de aplicativos de página única (SPA).<ul><li>Ao selecionar elementos a serem usados no rastreamento de cliques, os nomes de todos os elementos disponíveis são exibidos no painel Modificações do lado direito, facilitando a seleção dos elementos desejados.</li><li>The [!UICONTROL Goals &amp; Settings] page of the three-part guided activity workflow displays a number representing the number of elements selected for click tracking. Você pode passar o mouse sobre esse número para ver os nomes de todos os elementos selecionados. (TGT-33878)</li></ul>See [Click tracking](/help/c-activities/r-success-metrics/click-tracking.md). |
| Aplicativo de página única no Visual Experience Composer (SPA VEC) | **Fluxo de trabalho guiado**: Um novo fluxo de trabalho guiado ajuda você a entender como as configurações da regra de entrega de página devem ser configuradas para executar e executar uma atividade com sucesso para seu Aplicativo de página única. (TGT-33718)<br> See [Single Page App (SPA) Visual Experience Composer](/help/c-experiences/spa-visual-experience-composer.md#page-delivery-settings).<br>**Clonar modificações**: Agora é possível definir uma modificação usando o SPA VEC e clonar a modificação para uso em outras exibições no aplicativo de página única. (TGT-33882)<br>See [Single Page App (SPA) Visual Experience Composer](/help/c-experiences/spa-visual-experience-composer.md). |
| Mobile Visual Experience Composer | **Várias versões do aplicativo**: Agora você pode criar atividades para várias versões do seu aplicativo móvel. Isso economiza tempo e esforço quando as versões são semelhantes e você não precisa alterar significativamente a interface do usuário do aplicativo. (TGT-34231)<br>See &quot;Manage multiple app versions&quot; in [Mobile App Visual Experience Composer](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#using-the-mobile-vec). |
| ![Selo](/help/assets/premium.png) Premium personalização automatizada (AP) e auto-direcionamento | **Experiência específica como controle**: Você pode selecionar uma experiência a ser usada como controle ao criar uma atividade AP ou Auto-Target. Esse recurso permite direcionar todo o tráfego de controle para uma experiência específica, com base na porcentagem de alocação de tráfego configurada na atividade. Em seguida, você pode avaliar os relatórios de desempenho do tráfego personalizado contra o controle do tráfego para aquela experiência. A opção de controle atual (experiências aleatoriamente enviadas) continuará disponível. (TGT-32801, TGT-26572, &amp; TGT-26571)<br>See [Select the control for your Automated Personalization or Auto-Target Activity](/help/c-activities/t-automated-personalization/experience-as-control.md). Note that there is a [current known issue](/help/r-release-notes/known-issues-resolved-issues.md) with this feature.<br>**Relatórios de insights de personalização**: A nomenclatura amigável para atributos quando um visitante vê um conteúdo específico em um local específico fornece informações mais relevantes. (TGT-33421 &amp; TGT-34957)<br>See [Data collection for the Target personalization algorithms](/help/c-activities/t-automated-personalization/ap-data.md). |
| ![Recommendations Premium](/help/assets/premium.png) - Recommendations | Você pode usar a opção Recomendar itens comprados anteriormente ao criar a lógica de Itens visualizados recentemente. (TGT-34030)<br>Para obter mais informações, consulte [Itens visualizados recentemente](/help/c-recommendations/c-algorithms/create-new-algorithm.md#previously-purchased) em &quot;Criar critérios&quot;. |
| Políticas de cookie do Google Chrome para samesite | O Google anunciou recentemente que a partir do Chrome 76, que é slida para a versão de July 0 de julho de 20 19, os desenvolvedores devem especificar explicitamente quais cookies podem funcionar entre sites e quais cookies podem acompanhar os usuários.<br>Conforme o setor faz strides para criar uma Web mais segura para os consumidores, o Target tem o absoluto compromisso de fornecer experiências personalizadas durante a reunião e exceder as expectativas de privacidade dos visitantes.<br>Consulte [Políticas de cookie do Google Chrome](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md). |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
