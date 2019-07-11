---
description: Essas notas de versão fornecem informações sobre recursos, melhorias e correções para as últimas ou futuras [! Versões do DNL Adobe Target.
keywords: notas de versão
seo-description: Essas notas de versão fornecem informações sobre recursos, melhorias e correções para as últimas ou futuras [! Versões do DNL Adobe Target.
seo-title: Notas de versão do Adobe Target (pré-lançamento)
solution: Target
title: Notas de versão do Target (pré-lançamento)
topic: Padrão
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 414783c4072a574d278166bedc8243047135265b

---


# Notas de versão do Target (pré-lançamento){#target-release-notes-prerelease}

Estas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para as versões mais recentes ou que serão lançadas em breve do [!DNL Adobe Target].

**Última atualização: 10 de julho de 2019**

>[!NOTE]
>
>Essas notas de versão contêm informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos a alteração sem aviso prévio. Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser iguais ou diferentes, dependendo do tempo das versões.
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## Target Standard/Premium 19.7.1 (23 de julho de 2019) {#tgt-19-7-1}

Esta versão inclui os seguintes novos recursos e melhorias:

| Recurso / Aprimoramento | Descrição |
| --- | --- |
| Visual Experience Composer (VEC) | When you click an image then click [!UICONTROL Replace With], two new options display:<ul><li>**HTML**: É possível substituir uma imagem por HTML para fornecer controle total do elemento sem precisar selecionar o elemento pai para acessar a opção HTML.</li><li>**Fragmento de experiência**: Você pode substituir uma imagem por um fragmento [de experiência do Adobe Experience Manager (AEM)](/help/c-experiences/c-manage-content/aem-experience-fragments.md) para inserir rapidamente elementos criados no AEM nas atividades do Target.</li></ul>(TGT-34097) |
| Aplicativo para dispositivos móveis do Visual Experience Composer | Um novo painel Modificações é exibido no VEC do aplicativo móvel que exibe os elementos configurados para rastreamento de cliques. (TGT-31741) |
| ![Premium badgereelogations](/help/assets/premium.png)<br>em atividades de teste A/B e direcionamento de experiência (XT) | O status da oferta do Recommendations (algoritmo) é exibido na página Visão geral das atividades de teste A/B e XT que contêm ofertas do Recommendations. Os status incluem: Resultados prontos, Resultados não prontos e Falha do feed. (TGT-33649) |
| Suporte de rastreamento entre domínios para at. js 2.0 + por meio da biblioteca da Experience Cloud ID (ECID) | Anteriormente, o rastreamento entre domínios não era compatível com o at. js 2.*x*. Com esta versão, os clientes que usam at. js 2.0 ou superior agora podem utilizar rastreamento entre domínios por meio da biblioteca ECID. A biblioteca ECID deve ser instalada na página juntamente com o at. js 2.0 ou superior para que o rastreamento entre domínios funcione. It is highly recommended to use [Experience Cloud ID library 4.3.0+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html). |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
