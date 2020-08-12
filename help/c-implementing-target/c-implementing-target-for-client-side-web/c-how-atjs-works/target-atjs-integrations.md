---
keywords: at.js integration;supported integrations;unsupported integrations;third party integrations
description: Informações sobre integrações comuns com o Target e seu status de suporte com a at.js.
title: Integrações da at.js
feature: null
topic: Standard
uuid: 19036a1d-941c-4d31-8c7b-f50c86996b1c
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 90%

---


# Integrações da at.js{#at-js-integrations}

Informações sobre integrações comuns com o [!DNL Target] e seu status de suporte com a at.js.

Se você tiver muita necessidade de uma integração que não seja compatível ou mencionada aqui, entre em contato com o representante ou consultor de conta.

## Integrações suportadas {#section_3B44A970D3FB42D1973701452C868B55}

| Integração | Detalhes |
|--- |--- |
| Analytics for Target (A4T) | Consulte [Adobe Analytics como Fonte de relatórios do Adobe Target (A4T)](../../../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE). |
| Perfis e públicos (P&amp;A) | Consulte [Audiência](https://docs.adobe.com/content/help/en/core-services/interface/audiences/audience-library.html) no Guia *do usuário dos serviços* principais. |
| Serviço da Experience Cloud ID | Consulte a [documentação de Serviço de ID da Adobe Experience Cloud](https://docs.adobe.com/content/help/en/id-service/using/home.html). |
| Adobe Launch | O Launch é a plataforma de gerenciamento de tags da Adobe de próxima geração, sendo o método preferido para implementar o Adobe Target. Ele oferece aos clientes uma forma simples de implantar e gerenciar todas as tags de análise, de marketing e de anúncios necessárias para potencializar experiências de cliente relevantes. Consulte [Implementação do Target usando o Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25). |
| Dynamic Tag Management (DTM) | See the [Best Practices for Implementing Target Using Dynamic Tag Management guide](https://docs.adobe.com/content/help/en/dtm/implementing/overview.html).   Importante: [O Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) é o método preferido e atualizado para implementar o Target e a biblioteca da at.js. Para obter novas implementações do Target, use o Launch. O guia a seguir é para clientes existentes que usam uma implementação do DTM. Considere o seguinte ao usar uma integração do DTM: <ul><li>Gerenciamento de biblioteca: use a opção de hospedagem “Custom” (Personalizado) para usar a at.js. Atualmente, o gerenciamento &quot;automático&quot; não é suportado. </li></ul> |
| Serviço em nuvem do Adobe Experience Manager (AEM) | O AEM Cloud Service permite a criação de testes A/B e atividades de direcionamento de experiência no fluxo de trabalho do AEM. Compatível com a at.js com Adobe Experience Manager 6.2 e FP-11577 (ou posterior). Para obter mais informações, consulte [Integração ao Adobe Target](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html) e selecione a sua versão do AEM. |
| Fragmentos de experiência do AEM | Os fragmentos de experiência criados no AEM nas atividades do Target permitem combinar a facilidade de uso e o poder do AEM com os poderosos recursos de Inteligência automatizada (AI) e Aprendizagem de Máquina (ML) no Target para testar e personalizar experiências em escala. O AEM reúne todo o seu conteúdo e ativos em um local central para alimentar sua estratégia de personalização. O AEM permite que você crie conteúdo facilmente para desktops, tablets e dispositivos móveis em um único local sem escrever código. Não há necessidade de criar páginas para cada dispositivo. O AEM ajusta automaticamente cada experiência usando seu conteúdo. Consulte [Fragmentos de experiência do AEM](../../../c-experiences/c-manage-content/aem-experience-fragments.md#topic_1E1E4EA01F074349B2CF8785387B5FE8). |

## Integrações não suportadas {#section_8EFCAED418DC42E0B07F95924819EAC2}

| Integração | Detalhes |
|--- |--- |
| [!DNL Legacy Target to SiteCatalyst Integration] | Esta foi a integração que enviou ids de campanha e receita para [!DNL SiteCatalyst] por meio da chamada de página, para que seja possível fazer a comunicação na interface de usuário do [!DNL SiteCatalyst]. Esse recurso foi substituído por A4T. |
| [!DNL Legacy Target to SiteCatalyst Integration] | Essa era a integração que fazia chamadas de mbox denominadas `"SiteCatalyst: Event"` e `"SiteCatalyst: Purchase"`, portanto, era possível criar métricas de sucesso e perfis de usuário com base em evars e props. Esse recurso foi substituído por A4T e P&amp;A. |
| [!DNL Legacy Audience Manager (AAM) to Target Integration] | Essa foi a integração que fez uma chamada de API front-end para recuperar segmentos do AAM e, em seguida, os enviou como parâmetros mbox para todas as chamadas mbox da página. |

## Integrações de terceiros {#section_EE599839CCAD49DD97640E5EDAD9082E}

| Integração | Detalhes |
|--- |--- |
| Outros gerenciadores de tags | A at.js deve funcionar com plataformas de gerenciamento de tags que não sejam da Adobe, mas tenha cuidado ao usar recursos de integração personalizados desenvolvidos por outros fornecedores. Suas integrações podem ser dependentes de funções da mbox.js que não existem mais na at.js. |
| Provedores de dados de terceiros (por exemplo, Demandbase, Bluekai, APIs de tempo) | Muitos provedores de dados de terceiros usados para complementar o perfil do usuário da Target podem ser integrados usando o recurso [Provedores de dados](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers) da at.js. |