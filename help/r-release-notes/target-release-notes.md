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
source-git-commit: b601e6cfa4061387352378271aa2c2e966584e40

---


# Notas de versão do Target (pré-lançamento){#target-release-notes-prerelease}

Estas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para as versões mais recentes ou que serão lançadas em breve do [!DNL Adobe Target].

**Última atualização: 28 de maio de 2019**

>[!NOTE]
>
>Essas notas de versão contêm informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança. Para exibir informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser iguais ou podem ser diferentes, dependendo da temporização das versões.

## Target Standard/Premium 19.6.1 (25 de junho de 2019) {#tgt-19-6-1}

| Recurso/Aprimoramento | Descrição |
| --- | --- |
| Visual Experience Composer (VEC) | Quando você clica em um elemento de página no VEC, um menu mostra as opções disponíveis para esse tipo de elemento. <ul><li>Agora é possível usar a [!DNL Styles > Background] opção para alterar a imagem de fundo e a cor do elemento selecionado. (TGT-15001)</li><li>Quando você clica em uma imagem em seguida, clica [!DNL Replace With]em, duas novas opções são exibidas: [!DNL HTML] e [fragmento de experiência](/help/c-experiences/c-manage-content/aem-experience-fragments.md).<br> A substituição de uma imagem com HTML fornece controle total do elemento sem precisar selecionar o elemento pai para acessar a opção HTML.<br>Fragmentos de experiência permitem inserir rapidamente elementos criados no Adobe Experience Manager (AEM) em activiites do Target. (TGT-34097)</li></ul> |
| Aplicativo de página única (SPA) Visual Experience Composer (VEC) | <ul><li>Um novo fluxo de trabalho guiado ajuda você a entender como as configurações da regra de entrega de página devem ser configuradas para executar e executar uma atividade com sucesso para seu Aplicativo de página única. (TGT-33718)</li><li>Agora é possível definir uma modificação usando o SPA VEC e clonar a modificação para uso em outras exibições no aplicativo de página única. (TGT-33882)</li><li>Melhoramos o processo para configurar o rastreamento de cliques no SPA VEC.<br>Ao selecionar elementos a serem usados no rastreamento de cliques, os nomes de todos os elementos disponíveis são exibidos no painel Modificações do lado direito, facilitando a seleção dos elementos desejados.<br>A [!DNL Goals & Settings] página do fluxo de trabalho de atividade guiada de três partes exibe um número que representa o número de elementos selecionados para o rastreamento de cliques. Você pode passar o mouse sobre esse número para ver os nomes de todos os elementos selecionados. (TGT-33878) </li></ul> |
| Mobile Visual Experience Composer (VEC) | <ul><li>Agora você pode criar atividades para várias versões do seu aplicativo móvel. Isso economiza tempo e esforço quando as versões são muito similares e você não precisa alterar significativamente a interface do usuário do aplicativo. (TGT-34231)</li></ul> |
| ![Atividades do Target](/help/assets/premium.png)<br>Badgeautomatpersonalização automatizada (AP) e do Target automático: experiência como controle | <ul><li>É possível selecionar uma experiência para ser usada como controle ao criar uma atividade de AP ou de Direcionamento automático. Esse recurso permite rotear todo o tráfego de controle para uma experiência específica, com base na porcentagem de alocação de tráfego configurada na atividade. Como consequência, você poderá avaliar o desempenho das entregas personalizadas em relação à experiência de controle. (TGT-32801 e TGT-26572)</li></ul> |

### Melhorias, correções e alterações

* A `<BODY>` tag agora é exibida no caminho DOM exibido na parte inferior do VEC quando você clica em um elemento na página, permitindo que você execute ações na `<BODY>` tag. (TGT-33736)

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações avançadas sobre futuras melhorias do produto no Target e em outras soluções da Adobe Experience Cloud, inscreva-se na Atualização prioritária do produto da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
