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

[!UICONTROL Enterprise Permissions allows  customers to use a single organization, but divide it into workspaces for different teams or workflows. ][!DNL Target] The [!UICONTROL Enterprise Permissions] feature facilitates effective scaling of optimization programs across teams. Although this feature was available in the [!DNL Target] UI, the Admin APIs lacked the corresponding support until the [!DNL Target] February 2019 release. Adobe updated the Admin APIs so that you can use the integration account to access all workspaces created in your organization. So, while earlier, Admin APIs were restricted to the default workspace, the February 2019 update granted access to all workspaces with Approver access.

With the upcoming  September 2019 release, Enterprise Permissions will provide customers with the following access controls:[!DNL Target]

* You can choose the workspaces to which the integration can be applied
* You can apply a role to the Adobe I/O integration: Approver, Editor, or Observer.

**Action Required: Customers who are currently leveraging APIs for CRUD operations on resources (activities, audiences, offers, and reporting) across all workspaces need to grant their existing Adobe I/O integration access to all workspaces with the desired role.** Prior to the September release, all integrations operated using Approver access, regardless of the role selected from the Product Role drop-down list.  With the upcoming release, you can now select the desired role.

This action should be performed during the month of August 2019. **** After the  September 2019 release, the access controls will activate and you will observe access to just the default workspace if that's how you are currently set up. [!DNL Target] Não há consequências adversas para a definição antecipada das funções de integração.

For step-by-step instructions and more information, see [Grant Adobe I/O integrations access to workspaces and assign roles](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md).

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
