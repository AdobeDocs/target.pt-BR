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
source-git-commit: 3a498a99e333acc92651eb94592af87cfc34c6e1

---


# Notas de versão do Target (atual){#target-release-notes-current}

Essas notas de versão oferecem informações sobre recursos, aprimoramentos e correções para cada lançamento do Target Standard e do Target Premium.

## Anúncios

Esteja ciente dos seguintes comunicados importantes:

* Em 20 de fevereiro de 2019, a infraestrutura do Adobe Target foi atualizada nas regiões EMEA, Japão e APAC para não coletar mais os dados de usuários finais com dispositivos antigos ou navegadores da Web que não sejam compatíveis com TLS 1.1 ou posteriores. A mesma atualização está planejada para a região da América do Norte em **1º de abril de 2019**. A migração para TLS 1.2 oferece segurança aprimorada. É importante que você verifique as especificidades e planeje as alterações com a equipe de TI para fazer uma transição sem complicações. Para obter mais informações, consulte [Alterações na criptografia do TLS (Transport Layer Security)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md).
* O [!DNL Target] e o [!DNL Adobe Marketing Cloud] terminarão o suporte ao Microsoft Internet Explorer 11 a partir de março de 2019. Essa alteração afeta somente a criação do [!DNL Target]; não afeta a entrega da experiência. Utilize o Microsoft Edge ou outro navegador. Para obter mais informações, consulte [Navegadores compatíveis](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md).

## at. js versão 2.1.0 (3 de junho de 2019)

Estamos empenhados em anunciar os seguintes recursos emocionais no at. js 2.1.0:

| Recurso/Aprimoramento | Descrição |
| --- | --- |
| Suporte a aceitação da Adobe | O Adobe Opt-In é uma maneira de simplificar as integrações das soluções da Adobe com as plataformas de gerenciamento de consentimento.<br>Para obter mais informações sobre o Adobe Opt-in, consulte [Privacidade e Regulamento Geral sobre a Proteção de Dados (GDPR)](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md). |
| Conformidade com o CSP padrão do setor | O at. js não usa mais eval () para executar javascript. |
| Registro de análises do cliente | Fornece aos clientes total controle sobre como enviar dados de análise para o Adobe Analytics, tanto no cliente como no servidor.<br>Para obter mais informações, consulte [Logon do lado do cliente](/help/c-integrating-target-with-mac/a4t/before-implement.md#client-side) no *antes de implementar*. |
| Enviar notificações | Permite aos desenvolvedores enviar notificações quando uma experiência é renderizada pelo seu código em vez de usar `applyOffer()` ou `applyOffers()`.<br>Para obter mais informações, consulte [adobe. target. sendnotifications (opções)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md). |
| Tamanho de arquivo reduzido | O tamanho do at. js é reduzido por ~ 24%. O tamanho de arquivo menor melhora o desempenho do carregamento da página e reduz o tempo para baixar o at. js na página. |
| Atualizações na documentação do at. js | Para obter uma lista completa de todos os artigos atualizados devido à versão do at. js 2.1.0, consulte as entradas de June de junho de 2019 na [Documentação](/help/r-release-notes/doc-change.md). |

## [!DNL Target] Standard/Premium 19.5.1 (21 de maio de 2019) {#tgt-19-5-1}

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe].)

### Atualizações de recursos

| Recurso/Aprimoramento | Descrição |
| --- | --- |
| Aplicativo de página única no Visual Experience Composer (SPA VEC) | O SPA VEC inclui os seguintes aprimoramentos para agilizar seu trabalho e deixá-lo mais eficiente:<ul><li>Clique em uma ação na SPA para destacar o elemento no site onde esta ação será aplicada. Cada ação do VEC criada em uma Exibição tem quatro ícones correspondentes: Informações, Editar, Mover e Excluir. A nova funcionalidade &quot;Mover&quot; nesta versão permite mover a ação para um Evento de carregamento de página ou qualquer outra Exibição existente no painel Modificações. (TGT-33746)</li><li>É possível executar muitas ações antes que a página seja carregada no VEC ou até mesmo se a página não carregar completamente (por exemplo, o código personalizado não é mais operacional). Ações que não podem ser editadas antes que o site seja carregado estão desabilitadas na interface do Target. (TGT-33851 e TGT-34149)</li></ul>Para obter mais informações, consulte [Aplicativo de página única (SPA) Visual Experience Composer](/help/c-experiences/spa-visual-experience-composer.md). |

### Melhorias, correções e alterações

* Os ícones da barra de ferramentas são exibidos corretamente após cancelar o carregamento de uma página dentro do VEC. Se ações específicas não puderem ser executadas após a página estar completamente carregada, os ícones da barra de ferramentas associados são desabilitados. (TGT-33811)

## Visual Experience Composer para aplicativos móveis (14 de maio de 2019) {#mobile-vec-may14-2}

| Recurso/Aprimoramento | Descrição |
| --- | --- |
| Visual Experience Composer (VEC) para aplicativos móveis | O VEC para aplicativos móveis permite criar atividades e personalizar o conteúdo em aplicativos nativos móveis de maneira autônoma, sem dependências de desenvolvimento contínuas e ciclos de lançamento de aplicativos.<br>Para obter mais informações, consulte:<ul><li>[aplicativo para dispositivos móveis no Visual Experience Composer](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md)</li><li>[Android - Configuração do aplicativo móvel](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md)</li><li>[iOS - Configuração do aplicativo móvel](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-ios.md)</li><li>[Configurar um rastreamento de cliques no VEC do Mobile](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md)</li><li>[Vídeo: Mobile App Visual Experience Composer](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#video)</li></ul> |

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