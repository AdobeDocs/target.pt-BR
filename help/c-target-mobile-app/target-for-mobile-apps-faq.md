---
description: Perguntas frequentes sobre o Adobe Target para aplicativos móveis.
keywords: aplicativo para dispositivos móveis;perguntas frequentes;faq;aplicativo para dispositivos móveis alvo
seo-description: Perguntas frequentes sobre o Adobe Target para aplicativos móveis.
seo-title: Perguntas frequentes sobre o Adobe Target para aplicativos móveis
title: Perguntas frequentes sobre o Adobe Target para aplicativos móveis
topic: Target
uuid: 3d6422ac-7cff-4e0d-9cea-64a64cd1a098
translation-type: tm+mt
source-git-commit: 43a00c7ade1f2e10a023ffdcb2e75cf2483e6907

---


# Perguntas frequentes sobre o Target para aplicativos móveis

Lista de perguntas frequentes sobre [!DNL Target] aplicativos móveis.

## Devo usar [!DNL Adobe Experience Platform Launch] para implantar o SDK ou posso implantar o SDK sem usar [!DNL Launch]?

O SDK está disponível na git [da](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)Adobe Marketing Cloud. Se você não usar o [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html), será necessário gerenciar seu próprio arquivo de configurações e gerenciá-lo no aplicativo.

## O Visual Experience Composer (VEC) para aplicativos móveis pode ser usado com suporte React-Native para o SDK da plataforma Adobe Experience v5?

Atualmente, o [VEC para aplicativos](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md) móveis nativos não é compatível com o aplicativo nativo React. Você deve usar o Criador de experiências baseado em [forma](/help/c-experiences/form-experience-composer.md).

## A integração do Mobile SDK permite a implantação de novas funcionalidades móveis? Posso ativar e desativar o sinalizador de recurso sem novas implantações de código?

Sim, você pode usar nosso SDK móvel para implantar recursos gradualmente.

## Para uma lógica mais complexa, devo desenvolver diretamente no aplicativo em vez de usar o Mobile VEC? Em caso afirmativo, que língua de desenvolvimento devo utilizar?

Atualmente, o VEC suporta casos de uso comuns, como alteração da imagem, texto, cor etc. Para casos de uso mais avançados, como a personalização do layout do aplicativo, você deve inserir a [!DNL Target] solicitação/local (mbox) no código e usar o Criador [de experiências baseado em](/help/c-experiences/form-experience-composer.md) formulário para projetar as experiências e alocar tráfego. Nosso SDK móvel suporta Java, Objetive C e Swift. Depende da preferência e dos recursos de sua equipe para escolher o idioma.

## Quais SDKs estão disponíveis hoje?

Os SDKs móveis da plataforma Adobe Experience são compatíveis com iOS, Android e React no momento. Para obter mais informações, consulte o guia [SDKs móveis da plataforma](https://aep-sdks.gitbook.io/docs/)Adobe Experience Cloud.

## Qual é a frequência do recurso baseado na localização, em termos de verificação da latitude e longitude?

Consulte a documentação [do](https://placesdocs.com/places-services-by-adobe-documentation/) Adobe Places para obter mais informações.

## Quais classes nativas são compatíveis com "Exibições" móveis? Eles suportam qualquer classe derivada NSObject (ou qualquer objeto Android) ou apenas NSViewController e Activities?

Para obter mais informações, visite a documentação do Android para obter a maneira [manual de declarar exibições](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md#views).

## Preciso do at.js para que os SDKs móveis da Adobe Experience Platform funcionem?

Não, você não precisa do at.js para usar os SDKs móveis. at.js é a biblioteca [!DNL Target] JavaScript para sites. Os SDKs do Adobe Experience Platform Mobile são para aplicativos móveis.

## O Target Mobile é uma funcionalidade do SKU de produto do Adobe Target Premium somente?

Para clientes do Adobe Target Standard, você pode usar nossos SDKs móveis somente para atividades de teste A/B e direcionamento de experiência (XT). Se você quiser usar o Recommendations ou os recursos habilitados pelo AI no aplicativo móvel, precisará de uma licença do [Adobe Target Premium](/help/c-intro/intro.md#premium) .

## É possível aproveitar os públicos-alvo do Adobe Audience Manager (AAM) no VEC para aplicativos móveis?

Sim, os SDKs móveis da Adobe Experience Platform foram criados para o [Audience Manager](https://docs.adobe.com/content/help/en/audience-manager/user-guide/aam-home.html), o [Analytics](https://docs.adobe.com/content/help/en/analytics/landing/home.html), o [Campaign](https://docs.adobe.com/content/help/en/campaign-standard/using/campaign-standard-home.html)e o Target. Seus públicos-alvo no Audience Manager são compartilhados com [!DNL Target].

## Existe uma integração de aplicativo móvel entre as atividades móveis do Adobe Experience Manager (AEM) e do Target?

Está no nosso roteiro, mas ainda não existe um calendário. No momento, você pode compartilhar Fragmentos [de](/help/c-experiences/c-manage-content/aem-experience-fragments.md) experiência JSON do AEM para o Target e, em seguida, usá-los em uma atividade de aplicativo móvel.

## É possível adicionar mais imagens usando o VEC ou alterar apenas as imagens existentes?

No momento, é possível alterar apenas as imagens existentes.
