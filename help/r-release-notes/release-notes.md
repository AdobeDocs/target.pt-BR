---
description: Essas notas de versão oferecem informações sobre recursos, aprimoramentos, correções e problemas conhecidos para cada lançamento do Target Standard e do Target Premium.
keywords: Notas de versão, pré-lançamento
seo-description: Essas notas de versão oferecem informações sobre recursos, aprimoramentos, correções e problemas conhecidos para cada lançamento do Adobe Target Standard e do Target Premium.
seo-title: Notas de versão do Target (atual)
solution: Target
title: Notas de versão do Target (atual)
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: de5d1a5852c7c6b59521e8d89493d48959a5b377

---


# Notas de versão do Target (atual){#target-release-notes-current}

Essas notas de versão oferecem informações sobre recursos, aprimoramentos e correções para cada lançamento do Target Standard e do Target Premium.

## Anúncios

Esteja ciente dos seguintes comunicados importantes:

* Em 20 de fevereiro de 2019, a infraestrutura do Adobe Target foi atualizada nas regiões EMEA, Japão e APAC para não coletar mais os dados de usuários finais com dispositivos antigos ou navegadores da Web que não sejam compatíveis com TLS 1.1 ou posteriores. A mesma atualização está planejada para a região da América do Norte em **1º de abril de 2019**. A migração para TLS 1.2 oferece segurança aprimorada. É importante que você verifique as especificidades e planeje as alterações com a equipe de TI para fazer uma transição sem complicações. Para obter mais informações, consulte [Alterações na criptografia do TLS (Transport Layer Security)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md).
* O [!DNL Target] e o [!DNL Adobe Marketing Cloud] terminarão o suporte ao Microsoft Internet Explorer 11 a partir de março de 2019. Essa alteração afeta somente a criação do [!DNL Target]; não afeta a entrega da experiência. Utilize o Microsoft Edge ou outro navegador. Para obter mais informações, consulte [Navegadores compatíveis](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md).

## Target Standard/Premium 19.6.1 (26 de junho de 2019)

Esta versão inclui os seguintes novos recursos e melhorias:

| Recurso / Aprimoramento | Descrição |
| --- | --- |
| Visual Experience Composer (VEC) | **Novas opções de menu VEC**: Quando você clica em um elemento de página no VEC, um menu mostra as opções disponíveis para esse tipo de elemento.<ul><li>You can now use the [!UICONTROL Styles &gt; Background] option to change the background image and color for the selected element. (TGT-15001)</li></ul>See *Styles* in [Visual Experience Options](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#styles).<br>**Melhorias no rastreamento de cliques**: Melhoramos o processo para configurar o rastreamento de cliques no VEC e no VEC de aplicativos de página única (SPA).<ul><li>Ao selecionar elementos a serem usados no rastreamento de cliques, os nomes de todos os elementos disponíveis são exibidos no painel Modificações do lado direito, facilitando a seleção dos elementos desejados.</li><li>The [!UICONTROL Goals &amp; Settings] page of the three-part guided activity workflow displays a number representing the number of elements selected for click tracking. Você pode passar o mouse sobre esse número para ver os nomes de todos os elementos selecionados. (TGT-33878)</li></ul>See [Click tracking](/help/c-activities/r-success-metrics/click-tracking.md). |
| Aplicativo de página única no Visual Experience Composer (SPA VEC) | **Fluxo de trabalho guiado**: Um novo fluxo de trabalho guiado ajuda você a entender como as configurações da regra de entrega de página devem ser configuradas para executar e executar uma atividade com sucesso para seu Aplicativo de página única. (TGT-33718)<br> See [Single Page App (SPA) Visual Experience Composer](/help/c-experiences/spa-visual-experience-composer.md#page-delivery-settings).<br>**Clonar modificações**: Agora é possível definir uma modificação usando o SPA VEC e clonar a modificação para uso em outras exibições no aplicativo de página única. (TGT-33882)<br>See [Single Page App (SPA) Visual Experience Composer](/help/c-experiences/spa-visual-experience-composer.md). |
| Mobile Visual Experience Composer | **Várias versões do aplicativo**: Agora você pode criar atividades para várias versões do seu aplicativo móvel. Isso economiza tempo e esforço quando as versões são semelhantes e você não precisa alterar significativamente a interface do usuário do aplicativo. (TGT-34231)<br>See &quot;Manage multiple app versions&quot; in [Mobile App Visual Experience Composer](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#using-the-mobile-vec). |
| ![Selo](/help/assets/premium.png) Premium personalização automatizada (AP) e auto-direcionamento | **Experiência específica como controle**: Você pode selecionar uma experiência a ser usada como controle ao criar uma atividade AP ou Auto-Target. Esse recurso permite direcionar todo o tráfego de controle para uma experiência específica, com base na porcentagem de alocação de tráfego configurada na atividade. Em seguida, você pode avaliar os relatórios de desempenho do tráfego personalizado contra o controle do tráfego para aquela experiência. A opção de controle atual (experiências aleatoriamente enviadas) continuará disponível. (TGT-32801, TGT-26572, &amp; TGT-26571)<br>See [Select the control for your Automated Personalization or Auto-Target Activity](/help/c-activities/t-automated-personalization/experience-as-control.md). Note that there is a [current known issue](/help/r-release-notes/known-issues-resolved-issues.md) with this feature.<br>**Relatórios de insights de personalização**: A nomenclatura amigável para atributos quando um visitante vê um conteúdo específico em um local específico fornece informações mais relevantes. (TGT-33421 &amp; TGT-34957)<br>See [Data collection for the Target personalization algorithms](/help/c-activities/t-automated-personalization/ap-data.md). |
| ![Recommendations Premium](/help/assets/premium.png) - Recommendations | Você pode usar a opção Recomendar itens comprados anteriormente ao criar a lógica de Itens visualizados recentemente. (TGT-34030)<br>Para obter mais informações, consulte [Itens visualizados recentemente](/help/c-recommendations/c-algorithms/create-new-algorithm.md#previously-purchased) em &quot;Criar critérios&quot;. |
| Políticas de cookie do Google Chrome para samesite | O Google anunciou recentemente que a partir do Chrome 76, que é slida para a versão de July 0 de julho de 20 19, os desenvolvedores devem especificar explicitamente quais cookies podem funcionar entre sites e quais cookies podem acompanhar os usuários.<br>Conforme o setor faz strides para criar uma Web mais segura para os consumidores, o Target tem o absoluto compromisso de fornecer experiências personalizadas durante a reunião e exceder as expectativas de privacidade dos visitantes.<br>Consulte [Políticas de cookie do Google Chrome](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md). |

## at. js versão 2.1.0 (3 de junho de 2019)

Estamos empenhados em anunciar os seguintes recursos emocionais no at. js 2.1.0:

| Recurso/Aprimoramento | Descrição |
| --- | --- |
| Suporte a aceitação da Adobe | O Adobe Opt-In é uma maneira de simplificar as integrações das soluções da Adobe com as plataformas de gerenciamento de consentimento.<br>Para obter mais informações sobre o Adobe Opt-in, consulte [Privacidade e Regulamento Geral sobre a Proteção de Dados (GDPR)](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md). |
| Conformidade com o CSP padrão do setor | O at. js não usa mais eval () para executar javascript. |
| Registro de análises do cliente | Fornece aos clientes total controle sobre como enviar dados de análise para o Adobe Analytics, tanto no cliente como no servidor.<br>Para obter mais informações, consulte [Logon do lado do cliente](/help/c-integrating-target-with-mac/a4t/before-implement.md#client-side) no *antes de implementar*. |
| Enviar notificações | Allows developers to send notifications when an experience is rendered by their code instead of using `applyOffer()` or `applyOffers()`.<br>Para obter mais informações, consulte [adobe. target. sendnotifications (opções)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md). |
| Tamanho de arquivo reduzido | O tamanho do at. js é reduzido por ~ 24%. O tamanho de arquivo menor melhora o desempenho do carregamento da página e reduz o tempo para baixar o at. js na página. |
| Atualizações na documentação do at. js | For a full list of all articles updated due to the at.js 2.1.0 release, see the June 3, 2019 entries in [Documentation changes](/help/r-release-notes/doc-change.md). |

## Alterações na documentação, notas de versão anteriores e notas de versão da Experience Cloud {#section_1BC5F5208DA548E9B4344A0836E4B943}

Além das notas para cada versão, os recursos a seguir oferecem informações adicionais:

| Recurso | Detalhes |
|--- |--- |
| Alterações de documentação | Veja informações detalhadas sobre atualizações neste manual que podem não ser incluídas nas notas de versão.<br>Para obter mais informações, consulte [Alterações de documentação](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de versão para versões anteriores | Veja informações sobre os novos recursos e aprimoramentos das versões anteriores do Target Standard e do Target Premium.<br>Para obter mais informações, consulte [Notas de versões anteriores](../r-release-notes/release-notes-for-previous-releases.md). |
| Notas de versão da Adobe Experience Cloud | Veja as notas de versão mais recentes para as soluções da Adobe Experience Cloud.<br>Para obter mais informações, consulte [Notas de versão da Experience Cloud](https://marketing.adobe.com/resources/help/en_US/whatsnew/). |

## Informações de pré-lançamento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Os recursos a seguir permitem ver as novidades previstas para a próxima versão do Target.

| Recurso | Detalhes |
|--- |--- |
| Lista de atualização de produtos prioritários da Adobe | Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Notas de versão futuras | Para obter informações sobre os lançamentos do Target do mês atual, incluindo informações de pré-lançamento, consulte a página [Notas de versão do Target - Pré-lançamento](/help/r-release-notes/target-release-notes.md). |