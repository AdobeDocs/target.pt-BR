---
description: Estas notas de versão fornecem informações sobre recursos, aprimoramentos, correções e problemas conhecidos para as versões mais recentes ou que serão lançadas em breve do Target.
keywords: notas de versão
seo-description: Estas notas de versão fornecem informações sobre recursos, aprimoramentos, correções e problemas conhecidos para as versões mais recentes ou que serão lançadas em breve do Adobe Target
seo-title: Notas de versão do Target (pré-lançamento)
solution: Target
title: Notas de versão do Target (pré-lançamento)
topic: Padrão
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 9f1cab87057a7b8803f795c852a7ffe839dd8f1c

---


# Notas de versão do Target (pré-lançamento){#target-release-notes-prerelease}

Estas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para as versões mais recentes ou que serão lançadas em breve do [!DNL Adobe Target].

**Última atualização: 28 de maio de 2019**

>[!NOTE]
>
>Essas notas de versão contêm informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança. Para exibir informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser iguais ou podem ser diferentes, dependendo da temporização das versões.

## at. js versão 2.1.0 (3 de junho de 2019)

Estamos empenhados em anunciar os seguintes recursos emocionais no at. js 2.1.0:

| Recurso/Aprimoramento | Descrição |
| --- | --- |
| Suporte a aceitação da Adobe | O Adobe Opt-In é uma maneira de simplificar as integrações das soluções da Adobe com as plataformas de gerenciamento de consentimento.<br>Para obter mais informações sobre o Adobe Opt-in, consulte [Privacidade e Regulamento Geral sobre a Proteção de Dados (GDPR)](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md). |
| Conformidade com o CSP padrão do setor | O at. js não usa mais eval () para executar javascript. |
| Registro de análises do cliente | Fornece aos clientes total controle sobre como enviar dados de análise para o Adobe Analytics, tanto no cliente como no servidor. |
| Enviar notificações | Permite aos desenvolvedores enviar notificações quando uma experiência é renderizada pelo seu código em vez de usar `applyOffer()` ou `applyOffers()`. |
| Tamanho de arquivo reduzido | O tamanho do at. js é reduzido por ~ 24%. O tamanho de arquivo menor melhora o desempenho do carregamento da página e reduz o tempo para baixar o at. js na página. |

## [!DNL Target] Standard/Premium 19.5.1 (21 de maio de 21 19) {#release-19-5-1-prerelease}

Esta versão inclui os seguintes recursos, alterações e melhorias:

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe].)

### Atualizações de recursos

| Recurso/Aprimoramento | Descrição |
| --- | --- |
| Aplicativo de página única no Visual Experience Composer (SPA VEC) | O SPA VEC inclui os seguintes aprimoramentos para agilizar seu trabalho e deixá-lo mais eficiente:<ul><li>Clicar em uma ação na SPA destaca o elemento no site onde esta ação será aplicada. Cada ação VEC criada em uma Exibição tem quatro ícones correspondentes: Informações, Editar, Mover e Excluir. A nova funcionalidade «Mover» nesta versão permite mover a ação para um Evento de carregamento de página ou qualquer outra exibição que já existe no painel de modificações. (TGT-33746)</li><li>É possível executar muitas ações antes que a página seja carregada no VEC ou até mesmo se a página não carregar completamente (por exemplo, o código personalizado não é mais operacional). Ações que não podem ser editadas antes que o site seja carregado estão desabilitadas na interface do Target. (TGT-33851 e TGT-34149)</li></ul>Para obter mais informações, consulte [Aplicativo de página única (SPA) Visual Experience Composer](/help/c-experiences/spa-visual-experience-composer.md). |

### Melhorias, correções e alterações

* Os ícones da barra de ferramentas são exibidos corretamente após cancelar o carregamento de uma página dentro do VEC. Se ações específicas não puderem ser executadas após a página estar completamente carregada, os ícones da barra de ferramentas associados são desabilitados. (TGT-33811)

## Mobile App Visual Experience Composer (May 4 de maio de 2019) {mobile-vec}

| Recurso/Aprimoramento | Descrição |
| --- | --- |
| Mobile App Visual Experience Composer (VEC) | A VEC do aplicativo móvel permite criar atividades e personalizar conteúdo em aplicativos móveis nativos de maneira autônoma sem dependências de desenvolvimento contínuas e ciclos de lançamento de aplicativos.<br>Para obter mais informações, consulte:<ul><li>[aplicativo para dispositivos móveis no Visual Experience Composer](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md)</li><li>[Android - Configuração do aplicativo móvel](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md)</li><li>[iOS - Configuração do aplicativo móvel](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-ios.md)</li><li>[Configurar um rastreamento de cliques no VEC do Mobile](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md)</li><li>[Vídeo: Mobile App Visual Experience Composer](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#video)</li></ul> |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações avançadas sobre futuras melhorias do produto no Target e em outras soluções da Adobe Experience Cloud, inscreva-se na Atualização prioritária do produto da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
