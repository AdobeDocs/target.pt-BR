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
source-git-commit: 3a498a99e333acc92651eb94592af87cfc34c6e1

---


# Notas de versão do Target (pré-lançamento){#target-release-notes-prerelease}

Estas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para as versões mais recentes ou que serão lançadas em breve do [!DNL Adobe Target].

**Última atualização: 6 de junho de 2019**

>[!NOTE]
>
>Essas notas de versão contêm informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos a alteração sem aviso prévio. Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser iguais ou diferentes, dependendo do tempo das versões.
>
>Os números de edição entre parênteses são para [!DNL Adobe] uso interno.

## Target Standard/Premium 19.6.1 (25 de junho de 2019) {#tgt-19-6-1}

Esta versão inclui os seguintes novos recursos e melhorias:

### Visual Experience Composer (VEC)

* **Novas opções de menu VEC**: Quando você clica em um elemento de página no VEC, um menu mostra as opções disponíveis para esse tipo de elemento.

   * **Estilos &gt; Plano de fundo**: Agora é possível usar a [!UICONTROL opção Estilos &gt; Plano de fundo] para alterar a imagem de fundo e a cor do elemento selecionado. (TGT-15001)

   * **[!UICONTROL Substituir por &gt; HTML]e[!UICONTROL Substituir por &gt; Fragmento de experiência]**: Ao clicar em uma imagem em seguida, clique [!UICONTROL em Substituir com], duas novas opções são exibidas:

      * **HTML**: É possível substituir uma imagem por HTML para fornecer controle total do elemento sem precisar selecionar o elemento pai para acessar a opção HTML.
      * **Fragmento de experiência**: Você pode substituir uma imagem por um fragmento [de experiência do Adobe Experience Manager (AEM)](/help/c-experiences/c-manage-content/aem-experience-fragments.md) para inserir rapidamente elementos criados no AEM nas atividades do Target. (TGT-34097)

* **Melhorias no rastreamento de cliques**: Melhoramos o processo para configurar o rastreamento de cliques no VEC e no VEC de aplicativos de página única (SPA).

   * Ao selecionar elementos a serem usados no rastreamento de cliques, os nomes de todos os elementos disponíveis são exibidos no painel Modificações do lado direito, facilitando a seleção dos elementos desejados.
   * A página [!UICONTROL Metas e configurações] do fluxo de trabalho guiado de três partes exibe um número que representa o número de elementos selecionados para o rastreamento de cliques. Você pode passar o mouse sobre esse número para ver os nomes de todos os elementos selecionados. (TGT-33878)

### SPA VEC

* **Fluxo de trabalho guiado**: Um novo fluxo de trabalho guiado ajuda você a entender como as configurações da regra de entrega de página devem ser configuradas para executar e executar uma atividade com sucesso para seu Aplicativo de página única. (TGT-33718)

* **Clonar modificações**: Agora é possível definir uma modificação usando o SPA VEC e clonar a modificação para uso em outras exibições no aplicativo de página única. (TGT-33882)

### VEC móvel

* **Várias versões do aplicativo**: Agora você pode criar atividades para várias versões do seu aplicativo móvel. Isso economiza tempo e esforço quando as versões são semelhantes e você não precisa alterar significativamente a interface do usuário do aplicativo. (TGT-34231)

### Selo personalização automatizada (AP) &amp; Target-Target ![Premium](/help/assets/premium.png)

* **Experiência específica como controle**: Você pode selecionar uma experiência a ser usada como controle ao criar uma atividade AP ou Auto-Target. Esse recurso permite direcionar todo o tráfego de controle para uma experiência específica, com base na porcentagem de alocação de tráfego configurada na atividade. Em seguida, você pode avaliar os relatórios de desempenho do tráfego personalizado contra o controle do tráfego para aquela experiência. A opção de controle atual (experiências aleatoriamente enviadas) continuará disponível. (TGT-32801 e TGT-26572)

### Outros aprimoramentos, correções e alterações

* A `<BODY>` tag agora é exibida no caminho DOM exibido na parte inferior do VEC quando você clica em um elemento na página, permitindo que você execute ações na `<BODY>` tag. (TGT-33736)

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
