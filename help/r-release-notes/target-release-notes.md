---
description: Notas de versão que fornecem informações sobre recursos, melhorias e correções para as mais recentes ou futuras [! Versões do DNL Adobe Target.
keywords: notas de versão
seo-description: Notas de versão que fornecem informações sobre recursos, melhorias e correções para as mais recentes ou futuras [! Versões do DNL Adobe Target.
seo-title: Notas de versão do Adobe Target (pré-lançamento)
solution: Target
title: Notas de versão do Target (pré-lançamento)
topic: Padrão
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 48cb808283c9b2858e1bd041feb3fe8228253d6a

---


# Notas de versão do Target (pré-lançamento){#target-release-notes-prerelease}

Estas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para as versões mais recentes ou que serão lançadas em breve do [!DNL Adobe Target].

**Última atualização: 31 de julho de 2019**

>[!NOTE]
>
>Essas notas de versão contêm informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos a alteração sem aviso prévio. Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser iguais ou diferentes, dependendo do tempo das versões.
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## Anúncios

Enterprise Permissions allows [!DNL Target] customers to use a single organization, but divide it into workspaces for their different teams or workflows. Isso facilita o dimensionamento eficaz de seu programa de otimização em equipes. Although the feature was available in the [!DNL Target] UI, the Admin APIs lacked the corresponding support until earlier this year. In the [!DNL Target] February 2019 release, Adobe updated the Admin APIs so that you can use the integration account to access all workspaces created in your organization. So, while earlier, Admin APIs were restricted to just the default workspace, the February update granted access to all workspaces with [!UICONTROL Approver] access.

With the upcoming [!DNL Target] September 2019 release, Target Enterprise Permissions will provide customers with the following access controls:

* É possível escolher as áreas de trabalho para as quais a integração pode ser aplicada
* You can apply a role to the Adobe I/O integration: [!UICONTROL Approver], [!UICONTROL Editor], or [!UICONTROL Observer].

Esta atualização oferecerá suporte para os seguintes casos de uso:

* Grant the Adobe I/O integration access to all workspaces with the [!UICONTROL Observer] role for reporting purposes with no rights to create or edit resources.
* Conceda à integração da Adobe I/O o acesso para selecionar espaços de trabalho com a função apropriada para permitir que uma equipe central faça alterações orientadas por API em apenas algumas áreas de trabalho.
* Cada equipe proprietária de sua área de trabalho decide ter sua própria integração sempre que a equipe estiver pronta para explorar apis e escolher a função de acordo.
* Misture e corresponda a qualquer cenário acima.

**Ação necessária**: Os clientes que atualmente utilizam apis para operações CRUD em recursos (atividades, públicos, ofertas e relatórios) precisam conceder acesso de integração existente à Adobe I/O a todas as áreas de trabalho com a função desejada de acordo com o caso de uso. You can do so by selecting each [!DNL Target] [!UICONTROL Product Profile] in the [!DNL Adobe Admin Console] and adding the integration(s) in the [!UICONTROL Integration] tab. Prior to the September release, all integrations operated using [!UICONTROL Approver] access, irrespective of choice made in the [!UICONTROL Product Role] drop-down list. Agora você pode escolher a função desejada.

This action *must* be performed before September 4, 2019 to not face any disruption on your end. Se esta ação não for executada, após o [! A versão do DNL Target setembro, os controles de acesso serão ativados e você observará o acesso somente à área de trabalho padrão se esta for a configuração atual. Não há nenhuma reação negativa à configuração de integrações antecipadamente, conforme as diretrizes acima. Quanto mais cedo você efetuar essa alteração, melhor. Pouco tempo é necessário para configurar isso, dependendo do número de espaços de trabalho em sua organização. Esse processo utiliza apenas alguns cliques para adicionar uma integração existente em espaços de trabalho com a função desejada.

## Target Standard/Premium 19.8.1 (20 de agosto de 2019) {#tgt-19-8-1}

Esta versão de manutenção inclui o seguinte aprimoramento:

* Várias correções de segurança, incluindo uma atualização de segurança para o Editor de Rich Text (RTE) no Visual Experience Composer (VEC). (TGT-35383)

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
