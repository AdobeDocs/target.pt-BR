---
description: Perguntas frequentes sobre o Adobe Target para aplicativos móveis.
keywords: aplicativo para dispositivos móveis; perguntas frequentes; perguntas frequentes; aplicativo móvel de destino
seo-description: Perguntas frequentes sobre o Adobe Target para aplicativos móveis.
seo-title: Perguntas frequentes sobre o Adobe Target para aplicativos móveis
title: Adobe Target para perguntas frequentes sobre aplicativos móveis
topic: Target
uuid: 3d6422ac-7cff-4e0d-9cea-64a64cd1a098
translation-type: tm+mt
source-git-commit: 43a00c7ade1f2e10a023ffdcb2e75cf2483e6907

---


# Target para perguntas frequentes sobre aplicativos móveis

Lista de perguntas frequentes sobre [!DNL Target] os aplicativos para dispositivos móveis.

## Devo usar [!DNL Adobe Experience Platform Launch] para implantar o SDK ou implantar o SDK sem usar [!DNL Launch]?

O SDK está disponível no git da [Adobe Marketing Cloud](https://github.com/Adobe-Marketing-Cloud/acp-sdks/). Se não usar [o Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html), você deve gerenciar seu próprio arquivo de configurações e gerenciá-lo no aplicativo.

## É possível usar o Visual Experience Composer (VEC) para aplicativos móveis com suporte nativo a Redutores para a Adobe Experience Platform SDK v 5?

O [VEC para aplicativos nativos para dispositivos móveis](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md) atualmente não suporta o aplicativo nativo Reprodutor. Você deve usar o [Criador de experiências baseado em forma](/help/c-experiences/form-experience-composer.md).

## A integração do SDK móvel permite o roll-out da nova funcionalidade móvel? É possível ativar e desativar o sinalizador de recurso sem implantações de código?

Sim, você pode usar nosso SDK móvel para implantar recursos gradualmente.

## Para lógica mais complexa, devo desenvolver diretamente no aplicativo em vez de usar o Mobile VEC? Em caso afirmativo, qual idioma de desenvolvimento devo usar?

Atualmente, o VEC suporta casos de uso comuns, como alterar a imagem, o texto, a cor etc. Para casos de uso mais avançado, como personalizar o layout do aplicativo, você deve inserir a [!DNL Target] solicitação/localização (mbox) no código e usar o [Criador de experiências baseado em forma](/help/c-experiences/form-experience-composer.md) para projetar as experiências e alocar tráfego. Nosso SDK móvel é compatível com Java, Objetive C e Swift. Depende da preferência e dos recursos da sua equipe para escolher o idioma.

## Quais sdks estão disponíveis hoje?

Atualmente, os sdks da Adobe Experience Platform Mobile são compatíveis com iOS, Android e Reagir. Para obter mais informações, consulte o [guia Sdks da plataforma Adobe Experience Cloud Platform Mobile](https://aep-sdks.gitbook.io/docs/).

## Qual é a frequência do recurso baseado em localização, em termos de verificação sobre a latitude e longitude?

Consulte a documentação do [Adobe Places](https://placesdocs.com/places-services-by-adobe-documentation/) para obter mais informações.

## Quais classes nativas são suportadas pelo Mobile «Views»? Eles suportam qualquer classe derivada nsobject (ou qualquer objeto Android) ou apenas nsviewcontroller e Atividades?

Para obter mais informações, visite a documentação do Android para obter a forma [manual de declarar exibições](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md#views).

## Preciso de at. js para que os sdks do Adobe Experience Platform Mobile funcionem?

Não, você não precisa de at. js para usar os sdks móveis. O at. js é a biblioteca [!DNL Target] javascript para sites. Os sdks da Adobe Experience Platform Mobile são para aplicativos móveis.

## O Target Mobile é uma funcionalidade somente do SKU do produto Adobe Target Premium?

Para clientes do Adobe Target Standard, você pode usar nossos sdks móveis para atividades de teste A/B e Segmentação de experiência (XT) apenas. Se quiser usar o Recommendations ou os recursos fornecidos pelo AI no aplicativo móvel, você precisa de [uma licença do Adobe Target Premium](/help/c-intro/intro.md#premium) .

## Posso aproveitar os públicos-alvo do Adobe Audience Manager (AAM) no VEC para aplicativos móveis?

Sim, os sdks da Adobe Experience Platform Mobile são criados para [o Audience Manager](https://docs.adobe.com/content/help/en/audience-manager/user-guide/aam-home.html), [Analytics](https://docs.adobe.com/content/help/en/analytics/landing/home.html), [Campaign](https://docs.adobe.com/content/help/en/campaign-standard/using/campaign-standard-home.html)e Target. Seus públicos-alvo no Audience Manager são compartilhados [!DNL Target].

## Há uma integração de aplicativos móveis entre as atividades do Adobe Experience Manager (AEM) e do Target Mobile?

Está no nosso roteiro, mas ainda não há linha do tempo. Atualmente, é possível compartilhar Fragmentos [de experiência JSON](/help/c-experiences/c-manage-content/aem-experience-fragments.md) do AEM para o Target e pode haver potencial para usá-los em uma atividade de aplicativo móvel.

## É possível adicionar mais imagens usando o VEC ou apenas alterar imagens existentes?

Atualmente, é possível alterar apenas as imagens existentes.
