---
keywords: Target Standard;at.js;implementation
description: A at.js é uma nova biblioteca de implementação do Adobe Target, projetada para implementações típicas da Web e aplicativos de página única.
title: Migração da mbox.js para at.js
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 96%

---


# Migração da mbox.js para at.js{#migrate-from-mbox-js-to-at-js}

A at.js é uma nova biblioteca de implementação do [!DNL Adobe Target], projetada para implementações típicas da Web e aplicativos de página única.

Entre outros benefícios, a [!DNL at.js] melhora os tempos de carregamento de página de implementações da Web e fornece opções de implementações melhores para aplicativos de página única.

[!DNL at.js] substitui [!DNL mbox.js] para implementações de [!DNL Target]. A biblioteca [!DNL at.js] também inclui os componentes que foram incluídos na [!DNL target.js], portanto, não há mais chamadas para a [!DNL target.js].

>[!NOTE]
>
>O Adobe Experience Manager (AEM) 6.2 com FP-11577 (ou posterior) é compatível com as implementações da at.js com a integração do Adobe Target Cloud Services. Para obter mais informações, consulte [Pacotes de recursos](https://docs.adobe.com/docs/en/aem/6-2/release-notes/feature-packs.html) e [Integração com o Adobe Target](https://docs.adobe.com/docs/en/aem/6-2/administer/integration/marketing-cloud/target.html) na documentação do *Adobe Experience Manager 6.2*.

## Benefícios da at.js {#benefits}

A tabela a seguir explica as diferenças entre as duas bibliotecas:

| Referência da biblioteca | Descrição |
|--- |--- |
| at.js | A at.js substitui a mbox.js para implementações do [!DNL Target].<br>Entre outros benefícios, a at.js melhora os tempos de carregamento de página para implementações da Web, melhora a segurança, evita avisos de document.write no Google Chrome e fornece opções de implementações melhores para aplicativos de página única.<br>Para obter mais informações, consulte [Implementação do at.js](#implement). |
| mbox.js | Antes do [!DNL Target] 16.3.1 (março de 2016), o [!DNL Target] exigia uma chamada para a mbox.js a fim de criar a mbox global necessária para o [!DNL Target] fornecer atividades, rastrear cliques e a maioria das métricas de sucesso. Esse arquivo contém as bibliotecas necessárias para todas as suas atividades. Você não precisa manter versões específicas de atividades diferentes do arquivo.<br>Se você já tiver mboxes de envolvimento nas suas páginas de um estilo antigo de implementação do [!DNL Target], elas ainda poderão ser usadas na nova interface. O arquivo mbox.js atualizado ainda é necessário, mas essas mboxes podem ser selecionadas para atividades e editadas usando o Visual Experience Composer.<br>[!DNL Target]O Standard e Premium atualizam e complementam a mbox.js com uma referência para um arquivo target.js. O arquivo target.js é hospedado pelo Adobe. O arquivo target.js possibilita a edição de conteúdo em qualquer página que usa o Visual Experience Composer, mesmo que a página não contenha mboxes predefinidas. Você deve mencionar esse arquivo em todas as páginas do site.<br>Para obter mais informações, consulte [Implementação do mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md).<br>**Importante**: a biblioteca mbox.js ainda é suportada, mas não haverá atualizações de recursos. Todos os clientes devem migrar para a at.js. Para obter mais informações, consulte [Migrar para at.js do mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md) |

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

## Vídeo de treinamento: at.js - Vantagens e práticas recomendadas de implementação ![Etiqueta de visão geral](/help/assets/overview.png)

Este vídeo é uma gravação de &quot;[No expediente](/help/cmp-resources-and-contact-information.md)&quot;, uma iniciativa da equipe de Atendimento ao cliente da Adobe.

* Como funciona a biblioteca at.js
* As vantagens da at.js em relação a mbox.js
* Como a at.js gerencia a cintilação
* Erro de manipulação em at.js
* Metodologias de depuração
* Problemas conhecidos e roteiros futuros

>[!VIDEO](https://video.tv.adobe.com/v/22223/)
