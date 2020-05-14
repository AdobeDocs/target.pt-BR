---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Essas notas de versão oferecem informações sobre recursos, aprimoramentos, correções e problemas conhecidos para cada lançamento do Adobe Target Standard e do Target Premium.
title: 'Notas de versão do Target (atual) '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 8139b9373dab3b699a93036752d982793fbd1158
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 32%

---


# Notas de versão do Target (atual){#target-release-notes-current}

Essas notas de versão oferecem informações sobre recursos, aprimoramentos e correções para cada lançamento do Target Standard e do Target Premium. Além disso, as notas de versão para APIs de Públicos alvos, SDKs, biblioteca JavaScript (at.js) e outras alterações de plataforma também são incluídas, quando aplicável.

>[!NOTE]
>
>* **desaprovação** da mbox.js: Em 30 de agosto de 2020, o Público alvo da Adobe não oferecerá mais suporte à biblioteca mbox.js. Após 30 de agosto de 2020, todas as chamadas feitas do mbox.js falharão e afetarão suas páginas com atividades do Público alvo em execução. Recomendamos que todos os clientes migrem para a versão mais recente da biblioteca do at.js antes dessa data para evitar possíveis problemas com seus sites. For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). Consulte Construtor de habilidades *do Público alvo da Adobe: Bate-papo no desenvolvedor, migre o mbox.js do Público alvo da Adobe para o at.js* abaixo para obter informações.
   >
   >   
   Embora a mbox.js seja atualmente compatível, não fornecemos atualizações de recursos para esta biblioteca desde julho de 2017. O mais recente at.js oferece muitas vantagens sobre o mbox.js. Entre outros benefícios, o at.js melhora o tempo de carregamento da página para implementações da Web, melhora a segurança e oferece melhores opções de implementação para aplicativos de página única.
   >
   >   
   Ao mudar todos os clientes para o at.js, nossos engenheiros e funcionários de suporte poderão fornecer novas funcionalidades e oferta do suporte que você espera da Adobe.


Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## Construtor de habilidades do Público alvo da Adobe: Bate-papo no desenvolvedor, migre o mbox.js do Público alvo da Adobe para o at.js {#skill-builder}

Com a próxima desaprovação do mbox.js em 30 de agosto de 2020, David Son, o gerente de produtos do Público alvo da Adobe lançou recentemente um bate-papo para o desenvolvedor discutir os benefícios da migração do mbox.js para o at.js. Nos próximos 30 dias, você poderá [visualização a gravação](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)do webinar.

## Alterações na API de status de lote de Perfis v2 (14 de maio de 2020)

Com a versão de 20 de maio, o status do Lote de Perfis retornará somente os dados de falha em nível de linha que seguem em frente (os dados de sucesso não serão retornados). As IDs de perfil com falha serão retornadas pela API em andamento.

As respostas anteriores e novas da API são as seguintes:

`ProfileBatchStatus Api
http://<<edge>>/m2/<<client>>/profile/batchStatus?batchId=<batchid>`

**Atualmente, vemos a resposta como:**

```
<response>
 
    <batchId>samplebatch-1585929692655-59449976</batchId>
 
    <status>complete</status>
 
    <batchSize>164</batchSize>
 
    <profile>
 
        <id>1514187733806-729395</id>
 
        <status>success</status>
 
    </profile>
 
    <profile>
 
        <id>1573612762055-214017</id>
 
        <status>success</status>
 
    </profile>
 
    <profile>
 
        <id>some profile id</id>
 
        <status>failed</status>
 
    </profile>
 
</response>
```

**Após 4 de maio, a resposta será:**

```
<response>
 
    <batchId>samplebatch-1585929692655-59449976</batchId>
 
    <status>complete</status>
 
    <batchSize>164</batchSize>
 
    <profile>
 
        <id>some profile id</id>
 
        <status>failed</status>
 
    </profile>
 
</response>
```

## Target Standard/Premium 20.4.1 (6 de maio de 2020) 

Esta versão contém os seguintes aprimoramentos, correções e alterações:

* Correção de um problema que qualificava incorretamente um dispositivo e um tipo de navegador para uma audiência. (TGT-36266)
* Correção de um problema que impedia que os dados do relatório fossem exibidos em telas com menos de 963 pixels de largura. (TGT-36549)
* Correção de um problema que fazia com que os relatórios de Personalização automática não fossem renderizados corretamente. (TGT-36619)
* Correção de um problema que permitia a seleção de métricas incompatíveis em Autoalocação e atividades de Público alvo automático que usam o Analytics para Públicos alvos (A4t). (TGT-36646)
* Correção de um problema que fazia com que certas opções no Visual Experience Composer (VEC) não fossem exibidas corretamente. (TGT-36571)
* Correção de um problema na interface do usuário do Público alvo que fazia com que outras pré-visualizações de oferta do Recommendations exibissem o conteúdo editado depois que um usuário substituísse o conteúdo em uma única experiência. (TGT-36053 e TGT-36894)
* Correção de um problema que impedia alguns usuários de excluir itens de um catálogo do Recommendations. (TGT-36455)
* Correção de um problema que impedia os usuários de salvar critérios do Recommendations em uma atividade de várias páginas. (TGT-36249)
* Correção de um problema que fazia com que os botões de opção da fonte de dados comportamental desaparecessem ao editar os critérios por uma segunda vez consecutiva. (TGT-36796)
* Correção de um problema de exibição que fazia com que um algoritmo do Recommendations exibisse &quot;resultados de busca&quot; por um período de tempo estendido. (TGT-36550 e TGT-36551)
* Foram atualizadas várias sequências de interface localizadas em vários idiomas.

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão - APIs do lado do servidor do Público alvo](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Notas de versão relacionadas às APIs do lado do servidor do Público alvo da Adobe. |
| [Notas de versão - SDK do Node.js do Público alvo](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Notas de versão relacionadas ao SDK do Nó.js do Público alvo da Adobe. |
| [Notas de versão - SDK Java do Público alvo](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Notas de versão relacionadas ao SDK Java do Público alvo da Adobe. |
| [Detalhes da versão da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Detalhes sobre as alterações em cada versão do Público alvo da Adobe na biblioteca JavaScript at.js. |
| [Detalhes da versão da mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | Esta página mostra as alterações em cada versão da mbox.js.<br>Observe que a biblioteca mbox.js não está mais sendo desenvolvida. Todos os clientes devem migrar da mbox.js para a at.js. |

## Alterações na documentação, notas de versão anteriores e notas de versão da Experience Cloud {#section_1BC5F5208DA548E9B4344A0836E4B943}

Além das notas para cada versão, os recursos a seguir oferecem informações adicionais:

| Recurso | Detalhes |
|--- |--- |
| Alterações de documentação | Veja informações detalhadas sobre atualizações neste manual que podem não ser incluídas nas notas de versão.<br>Para obter mais informações, consulte [Alterações de documentação](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de versão para versões anteriores | Veja informações sobre os novos recursos e aprimoramentos das versões anteriores do Target Standard e do Target Premium.<br>Para obter mais informações, consulte [Notas de versões anteriores](../r-release-notes/release-notes-for-previous-releases.md). |
| Notas de versão da Adobe Experience Cloud | Veja as notas de versão mais recentes para as soluções da Adobe Experience Cloud.<br>Para obter mais informações, consulte Notas [de versão da](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)Experience Cloud. |

## Informações de pré-lançamento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Os recursos a seguir permitem ver as novidades previstas para a próxima versão do Target.

| Recurso | Detalhes |
|--- |--- |
| Lista de atualização de produtos prioritários da Adobe | Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Notas de versão futuras | Para obter informações sobre os lançamentos do Target do mês atual, incluindo informações de pré-lançamento, consulte a página [Notas de versão do Target - Pré-lançamento](/help/r-release-notes/target-release-notes.md). |
