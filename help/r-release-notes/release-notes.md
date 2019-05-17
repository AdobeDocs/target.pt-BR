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
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Notas de versão do Target (atual){#target-release-notes-current}

Essas notas de versão oferecem informações sobre recursos, aprimoramentos e correções para cada lançamento do Target Standard e do Target Premium.

## Anúncios

Esteja ciente dos seguintes comunicados importantes:

* Em 20 de fevereiro de 20 19, a infraestrutura do Adobe Target foi atualizada nas regiões EMEA, Japão e APAC para não coletar dados de usuários finais com dispositivos antigos ou navegadores da Web que não são compatíveis com TLS 1.1 ou posterior. A mesma atualização está planejada para a região da América do Norte em 1 **de abril de 2019**. A migração para TLS 1.2 oferece segurança aprimorada. É importante passar pelas especificações e planejar as alterações com a equipe de TI para obter uma transição suave. Para obter mais informações, consulte [Alterações de criptografia TLS (Transport Layer Security)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md).
* O [!DNL Target] e o [!DNL Adobe Marketing Cloud] terminarão o suporte ao Microsoft Internet Explorer 11 a partir de março de 2019. Essa alteração afeta somente a criação do [!DNL Target]; não afeta a entrega da experiência. Utilize o Microsoft Edge ou outro navegador. Para obter mais informações, consulte [Navegadores compatíveis](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md).

## Mobile App Visual Experience Composer (May 4 de maio de 2019) {mobile-vec}

| Recurso/Aprimoramento | Descrição |
| --- | --- |
| Mobile App Visual Experience Composer (VEC) | A VEC do aplicativo móvel permite criar atividades e personalizar conteúdo em aplicativos móveis nativos de maneira autônoma sem dependências de desenvolvimento contínuas e ciclos de lançamento de aplicativos.<br>Para obter mais informações, consulte:<ul><li>[aplicativo para dispositivos móveis no Visual Experience Composer](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md)</li><li>[Android - Configuração do aplicativo móvel](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md)</li><li>[iOS - Configuração do aplicativo móvel](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-ios.md)</li><li>[Configurar um rastreamento de cliques no VEC do Mobile](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md)</li></ul> |

## [!DNL Target] Standard/Premium 19.4.2 (30 de abril de 20 19) {#release-19-4-2}

Essa versão inclui os seguintes recursos, alterações e aprimoramentos:

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe].)

### Atualizações de recursos

| Recurso/Aprimoramento | Descrição |
| --- | --- |
| [!UICONTROL Visual Experience Composer] | O [!UICONTROL Visual Experience Composer] (VEC) inclui os seguintes aprimoramentos para tornar seu trabalho mais rápido e eficiente:<ul><li>O recurso de caminho DOM agora está disponível ao configurar o rastreamento de cliques.<br>Para obter mais informações, consulte [Rastreamento](/help/c-activities/r-success-metrics/click-tracking.md#considerations)de cliques.</li><li>Use o painel Estilos para exibir ou editar o valor dos estilos existentes para o elemento selecionado. Você também pode adicionar estilização adicional.<br>Para acessar o painel Estilos, clique em um elemento de página no VEC e, em seguida, clique [!UICONTROL em Editar] &gt; [!UICONTROL Estilos].<br>O painel Estilos é exibido no lado direito do VEC. O painel contém uma lista de estilos que permite editar ou adicionar ao elemento selecionado. Um Editor CSS em tempo real permite exibir alterações e adicionar estilos se você estiver confortável usando Folhas de estilo em cascata (CSS) ou se receber código de seu desenvolvedor.<br>Para obter mais informações, consulte [Estilos](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#styles) nas *Opções*do Visual Experience Composer.</li><li>O Editor de Rich Text agora suporta elementos HTML 5 aninhados.<br>As especificações HTML 5 permitem novas combinações de tags para aninhamento. A versão anterior do editor de rich text não suportava o novo aninhamento de tags conforme permitido pela especificação HTML 5. Como resultado, quaisquer elementos aninhados selecionados no VEC não eram manipulados corretamente, o que resultava em alterações indesejadas de HTML. (TGT -33618)<br>Para obter mais informações, consulte [Editar texto/HTML](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#edit-text-html) nas *opções do Visual Experience Composer*.</li> |

### Melhorias, correções e alterações

* Aprimoramos o fluxo de trabalho ao excluir ativos usando o VEC. Os ativos excluídos agora são removidos da biblioteca [!UICONTROL de ofertas] e de [!DNL Scene7] (se aplicável). Os ativos excluídos não são mais exibidos nos resultados de pesquisa. (TGT-31981)
* Agora, é possível excluir pastas de ativos mesmo que elas contenham imagens (pastas não vazias). (TGT-33265)

   Anteriormente, não era possível excluir uma pasta não vazia da biblioteca de ofertas de imagem do Target ([!UICONTROL Ofertas] &gt; [!UICONTROL Ofertas de imagem]). Você receberia uma «Pasta não está vazia!» ao tentar excluir a pasta da interface do usuário. Com esse recurso, estamos adicionando a capacidade de executar a exclusão da pasta para remover uma pasta inteira contendo qualquer número de ativos e subpastas dentro. Este recurso está disponível na interface do usuário do Target também na interface do usuário dos ativos da Adobe Experience Cloud.

   * Pastas não vazias na biblioteca de Oferta de imagem podem ser excluídas. Se todas as imagens dentro da pasta não forem mencionadas em qualquer atividade, a pasta inteira e seu conteúdo serão excluídos. Se algumas imagens dentro da pasta forem referenciadas em qualquer atividade, todas as imagens não referenciadas serão excluídas, mas as imagens e pastas referenciadas que contêm essas imagens serão mantidas.
   * A renderização das ofertas de imagem no seletor de Ativos de imagem é mais rápida e eficiente.
   Para obter mais informações, consulte [Trabalhar com conteúdo na biblioteca](/help/c-experiences/c-manage-content/assets-working.md). (TGT-32897)

* Melhoramos a renderização de ofertas de imagem no seletor de ativos. Exibir e selecionar ofertas de imagem agora é mais fácil e eficiente. (TGT-32897)
* Melhoramos o direcionamento para URLs ao cancelar o carregamento de uma página dentro do VEC. (TGT-33815)
* Depois de selecionar uma coleção [!UICONTROL do Recommendations] no seletor Coleções, você deve clicar no [!UICONTROL botão Salvar] . Este fluxo de trabalho está consistente aos outros fluxos de trabalho no [!DNL Target]. (TGT-33205)
* Correção de um problema que fazia com que um pequeno conjunto de relatórios do Insights retornasse 0% taxas de conversão em vez das taxas de conversão reais. (TNT-32125)

## [!DNL Target] Standard/Premium 19.4.1 (15 de abril de 25 19) {#release-19-4-1}

Esta versão é uma versão de manutenção e inclui a seguinte alteração:

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe].)

* Atualização da [!DNL Adobe Experience Cloud] interface do usuário para refletir as alterações de marca e produto. (TGT-33546, TGT-33272 e TGT-33331)

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
| Lista de atualização de produtos prioritários da Adobe | Para receber notificações avançadas sobre futuras melhorias do produto no Target e em outras soluções da Adobe Experience Cloud, inscreva-se na Atualização prioritária do produto da Adobe:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Notas de versão futuras | Para obter informações sobre os lançamentos do Target do mês atual, incluindo informações de pré-lançamento, consulte a página [Notas de versão do Target - Pré-lançamento](/help/r-release-notes/target-release-notes.md). |