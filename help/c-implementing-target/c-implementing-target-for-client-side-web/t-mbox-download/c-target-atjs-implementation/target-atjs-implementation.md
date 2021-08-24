---
keywords: Target Standard; at.js; implementação
description: Saiba como migrar para a at.js, a nova biblioteca de implementação do Adobe [!DNL Target] projetada para implementações típicas da Web e Aplicativos de página única (SPA).
title: Como faço para migrar da mbox.js para a at.js?
feature: at.js
role: Developer
exl-id: 1d95faeb-7caa-44d6-b637-a06db393e50e
source-git-commit: e0713ccd25da71c2655b567ff8715a22203f46fb
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 89%

---

# Migração da mbox.js para at.js

A at.js é uma nova biblioteca de implementação do [!DNL Adobe Target], projetada para implementações típicas da Web e aplicativos de página única.

Entre outros benefícios, a [!DNL at.js] melhora os tempos de carregamento de página de implementações da Web e fornece opções de implementações melhores para aplicativos de página única.

[!DNL at.js] substitui [!DNL mbox.js] para implementações de [!DNL Target]. A biblioteca [!DNL at.js] também inclui os componentes que foram incluídos na [!DNL target.js], portanto, não há mais chamadas para a [!DNL target.js].

>[!NOTE]
>
>O Adobe Experience Manager (AEM) 6.2 com FP-11577 (ou posterior) é compatível com as implementações da at.js com a integração do Adobe Target Cloud Services. Para obter mais informações, consulte [Pacotes de recursos](https://experienceleague.adobe.com/docs/) e [Integração com o Adobe Target](https://experienceleague.adobe.com/docs/) na documentação do *Adobe Experience Manager 6.2*.

## Implementar a at.js {#implement}

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

## Vídeo de treinamento: at.js - Vantagens e práticas recomendadas de implementação ![Selo de visão geral](/help/assets/overview.png)

Este vídeo é uma gravação de &quot;[No expediente](/help/cmp-resources-and-contact-information.md)&quot;, uma iniciativa da equipe de Atendimento ao cliente da Adobe.

* Como funciona a biblioteca at.js
* As vantagens da at.js em relação a mbox.js
* Como a at.js gerencia a cintilação
* Erro de manipulação em at.js
* Metodologias de depuração
* Problemas conhecidos e roteiros futuros

>[!VIDEO](https://video.tv.adobe.com/v/22223/)
