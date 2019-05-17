---
description: A at.js é uma nova biblioteca de implementação do Adobe Target, projetada para implementações típicas da Web e aplicativos de página única.
keywords: Target Standard; at.js; implementação
seo-description: A at.js é uma nova biblioteca de implementação do Adobe Target, projetada para implementações típicas da Web e aplicativos de página única.
seo-title: Migração da mbox.js para at.js
solution: Target
title: Migração da mbox.js para at.js
topic: Padrão
uuid: 10da01d7-d308-44e3-9c6e-ff4f713bd312
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Migração da mbox.js para at.js{#migrate-from-mbox-js-to-at-js}

A at.js é uma nova biblioteca de implementação do [!DNL Adobe Target], projetada para implementações típicas da Web e aplicativos de página única.

Entre outros benefícios, a [!DNL at.js] melhora os tempos de carregamento de página de implementações da Web e fornece opções de implementações melhores para aplicativos de página única.

[!DNL at.js] substitui [!DNL mbox.js] para implementações de [!DNL Target]. A biblioteca [!DNL at.js] também inclui os componentes que foram incluídos na [!DNL target.js], portanto, não há mais chamadas para a [!DNL target.js].

>[!NOTE]
>
>O Adobe Experience Manager (AEM) 6.2 com FP-11577 (ou posterior) é compatível com as implementações da at.js com a integração do Adobe Target Cloud Services. Para obter mais informações, consulte [Pacotes de recursos](https://docs.adobe.com/docs/en/aem/6-2/release-notes/feature-packs.html) e [Integração com o Adobe Target](https://docs.adobe.com/docs/en/aem/6-2/administer/integration/marketing-cloud/target.html) na documentação do *Adobe Experience Manager 6.2*.

Para usar a [!DNL at.js], substitua a referência da [!DNL mbox.js] nas páginas em que deseja implementá-la. Não é possível usar a [!DNL mbox.js] e a [!DNL at.js] em uma página única. No entanto, é possível usar qualquer uma em cada página do seu site.

A biblioteca [!DNL at.js] funciona para implementações existentes usando as funções `mboxCreate()`, `mboxDefine()` e `mboxUpdate()` e suporta novas funcionalidades focadas em implementações baseadas em aplicativos de página única.

Você pode utilizar a [!DNL at.js] em qualquer lugar que use atualmente a [!DNL mbox.js].

A biblioteca [!DNL at.js] oferece várias melhorias em relação à biblioteca [!DNL mbox.js], incluindo:

* Comunicação completamente assíncrona por meio do domínio cruzado AJAX

   >[!IMPORTANT]
   >
   >Embora a [!DNL at.js] se comunique com os servidores do [!DNL Target] de forma assíncrona, o arquivo [!DNL at.js] deve carregar de forma sincronizada na seção `<head>` da página. Idealmente, isso deve ser um dos primeiros scripts carregados. Após carregada, a [!DNL at.js] executa chamadas mbox de forma assíncrona por meio de `XMLHttpRequest` e não bloqueia a renderização da página.

* Não há mais chamadas de bloqueio
* Nenhum `document.write()` usado
* Nenhuma execução imediata de JavaScript nas respostas do [!DNL Target]
* Melhor tempo limite e tratamento de erros

   * Personalizável [tempo limite](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) por chamada
   * Sem recarregamentos nos tempos limites

* Funções projetadas especificamente para aplicativos de página única/estruturas de MVC

## Vídeo de treinamento: at.js - Vantagens e práticas recomendadas de implementação

Este vídeo é uma gravação de &quot;[Horas do Office](../../../../cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)&quot;, uma iniciativa liderada pela equipe de Atendimento ao cliente da Adobe.

* Como funciona a biblioteca at.js
* As vantagens da at.js em relação a mbox.js
* Como a at.js gerencia a cintilação
* Erro de manipulação em at.js
* Metodologias de depuração
* Problemas conhecidos e roteiros futuros

>[!VIDEO](https://video.tv.adobe.com/v/22223/)
