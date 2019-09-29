---
description: Notas de versão que fornecem informações sobre recursos, melhorias e correções para as versões mais recentes ou futuras do Adobe Target.
keywords: notas de versão;versões;atualizações;versão futura;melhorias;novos recursos;correções
seo-description: Notas de versão que fornecem informações sobre recursos, melhorias e correções para as versões mais recentes ou futuras do Adobe Target DNL.
seo-title: Notas de versão do Adobe Target (pré-lançamento)
solution: Target
title: Notas de versão do Target (pré-lançamento)
topic: Padrão
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 1d91c46c78c0bcb58607def4cacaff0b761162fa

---


# Notas de versão do Target (pré-lançamento){#target-release-notes-prerelease}

Estas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para as versões mais recentes ou que serão lançadas em breve do [!DNL Adobe Target].

**Última atualização em 24 de setembro de 2019**

>[!NOTE]
>
>Essas notas de versão contêm informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio. Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser iguais ou diferentes, dependendo do tempo das versões.
>
>Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## Anúncios

**31 de julho de 2019**

[!UICONTROL As Permissões] empresariais permitem que [!DNL Target] os clientes usem uma única organização, mas as dividam em espaços de trabalho para equipes ou fluxos de trabalho diferentes. O recurso Permissões  corporativas facilita o dimensionamento efetivo de programas de otimização entre equipes. Embora esse recurso estivesse disponível na [!DNL Target] interface do usuário, as APIs administrativas não tinham o suporte correspondente até a versão [!DNL Target] de fevereiro de 2019. A Adobe atualizou as APIs de administração para que você possa usar a conta de integração para acessar todos os espaços de trabalho criados em sua organização. Assim, embora anteriormente, as APIs administrativas estivessem restritas ao espaço de trabalho padrão, a atualização de fevereiro de 2019 concedia acesso a todos os espaços de trabalho com acesso ao [!UICONTROL Aprovador] .

Com a próxima versão [!DNL Target] de setembro de 2019, as Permissões  Enterprise fornecerão aos clientes os seguintes controles de acesso:

* Você pode escolher os espaços de trabalho aos quais a integração pode ser aplicada
* Você pode aplicar uma função à integração de E/S da Adobe: [!UICONTROL Aprovador], [!UICONTROL Editor]ou [!UICONTROL Observador].

**Ação necessária**: Os clientes que atualmente estão aproveitando as APIs para operações CRUD em recursos (atividades, públicos-alvo, ofertas e relatórios) em todos os espaços de trabalho precisam conceder acesso à integração de E/S existente da Adobe a todos os espaços de trabalho com a função desejada. Antes da versão de setembro, todas as integrações operavam usando o acesso do [!UICONTROL Aprovador] , independentemente da função selecionada na lista suspensa Função [!UICONTROL do] produto. Com a próxima versão, agora é possível selecionar a função desejada.

Esta ação deverá ser executada durante o mês de **agosto de 2019**. Após a versão de [!DNL Target] setembro de 2019, os controles de acesso serão ativados e você observará o acesso apenas ao espaço de trabalho padrão se for assim que você estiver configurado no momento. Não há consequências adversas para a definição antecipada das funções de integração.

Para obter instruções passo a passo e mais informações, consulte [Conceder acesso de integrações de E/S da Adobe a espaços de trabalho e atribuir funções](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md).

## Target Standard/Premium 19.9.2 (30 de setembro de 2019)

Esta versão de manutenção inclui as seguintes melhorias:

* Várias correções de segurança, incluindo uma atualização de segurança para o Editor de Rich Text (RTE) no Visual Experience Composer (VEC). (TGT-35383)

## Target Standard/Premium 19.9.1 (10 de setembro de 2019)

| Recurso / Aprimoramento | Descrição |
| --- | --- |
| ![Permissões para empresas com o selo](/help/assets/premium.png) Premium | Com a versão de setembro de 2019 do Target, as Permissões corporativas fornecem aos clientes os seguintes controles de acesso:<UL><li>Você pode escolher os espaços de trabalho aos quais a integração pode ser aplicada.</li><li>Você pode aplicar uma função à integração de E/S da Adobe: Aprovador, Editor ou Observador.</li></ul>Para obter instruções passo a passo e mais informações, consulte [Conceder acesso de integrações de E/S da Adobe a espaços de trabalho e atribuir funções](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md). |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
