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
source-git-commit: 3b21fede9df1ef61da194fac55ffb862c037258a

---


# Notas de versão do Target (pré-lançamento){#target-release-notes-prerelease}

Estas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para as versões mais recentes ou que serão lançadas em breve do [!DNL Adobe Target].

**Última atualização: 31 de julho de 2019**

>[!NOTE]
>
>Essas notas de versão contêm informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio. Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser iguais ou diferentes, dependendo do tempo das versões.
>
>Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## Anúncios

**July 1 de julho de 21 19**

[!UICONTROL As Permissões empresariais] permitem [!DNL Target] que os clientes usem uma única organização, mas dividam-a em espaços de trabalho para diferentes equipes ou fluxos de trabalho. O [!UICONTROL recurso Permissões] empresariais facilita a escala eficaz de programas de otimização em equipes. Embora esse recurso esteja disponível na [!DNL Target] interface do usuário, as apis admin. ignoravam o suporte correspondente até [!DNL Target] a versão de fevereiro de 2019. A Adobe atualizou as apis de administração para que você possa usar a conta de integração para acessar todas as áreas de trabalho criadas em sua organização. Assim, enquanto anteriormente as apis de administração eram restritas à área de trabalho padrão, a atualização de fevereiro de 2019 concedeu acesso a todas as áreas de trabalho com [!UICONTROL acesso ao aprovador] .

Com a próxima versão [!DNL Target] de setembro de 2019, [!UICONTROL as Permissões] empresariais fornecerão aos clientes os seguintes controles de acesso:

* É possível escolher as áreas de trabalho para as quais a integração pode ser aplicada
* Você pode aplicar uma função à integração da Adobe I/O: [!UICONTROL Aprovador], [!UICONTROL Editor]ou [!UICONTROL Observador].

**Ação necessária**: Os clientes que atualmente utilizam apis para operações CRUD em recursos (atividades, públicos, ofertas e relatórios) em todas as áreas de trabalho precisam conceder acesso de integração da Adobe I/O a todas as áreas de trabalho com a função desejada. Antes da versão de setembro, todas as integrações operadas usando [!UICONTROL o Aprovador] , independentemente da função selecionada na lista [!UICONTROL suspensa Função] do produto. Com a próxima versão, agora você pode selecionar a função desejada.

Essa ação deve ser executada durante o mês **de agosto de 2019**. Após a versão [!DNL Target] de setembro de 2019, os controles de acesso serão ativados e você observará o acesso somente à área de trabalho padrão se esta for a configuração atual. Não há problemas para configurar as funções de integração antecipadamente.

Para obter instruções passo a passo e mais informações, consulte [Conceder acesso a integrações de E/S da Adobe a espaços de trabalho e atribuir funções](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md).

## Target Standard/Premium 19.9.1 (24 de setembro de 2019)

Esta versão de manutenção inclui o seguinte aprimoramento:

* Várias correções de segurança, incluindo uma atualização de segurança para o Editor de Rich Text (RTE) no Visual Experience Composer (VEC). (TGT-35383)

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
