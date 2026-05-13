---
keywords: ambiente;solução de problemas;práticas recomendadas;ubox;redireciona;redirecionar;lista de permissões;lista negra;incluir na lista de permissões;environment;troubleshooting;best practices;ubox;redirects;redirect;whitelist;blacklist;file;inclui na lista de bloqueios
description: Saiba como usar ambientes no Adobe [!DNL Target] para organizar seus sites e ambientes de pré-produção para facilitar o gerenciamento e os relatórios separados.
title: O que são ambientes e como usá-los?
feature: Administration & Configuration
role: Admin
exl-id: 820a116a-15f9-4ba0-94f3-8e35aa0f90da
TQID: https://experienceleague.adobe.com/ve3zhtylLWwRv890FaptsA9shmINkioM6-Yrq-nmmm0
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
subfeature_v2: id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 658
ht-degree: 46%

---

# Ambientes

Organize seus sites e ambientes de pré-produção para fácil gerenciamento e geração de relatórios separados.

Os hosts são agrupados em ambientes para facilitar o gerenciamento. Por exemplo, você pode ter dezenas de hosts agrupados em dois ou três ambientes. Os ambientes predefinidos incluem [!UICONTROL Production], [!UICONTROL Staging] e [!UICONTROL Development]. Você pode adicionar novos ambientes e renomear seus ambientes, se desejado.

Um ambiente, o ambiente padrão, é pré-nomeado como [!UICONTROL Production]. Esse ambiente padrão não pode ser removido, mesmo que você o renomeie. O [!DNL Target] parte do princípio que este é o local onde você disponibiliza atividades finais, aprovadas e testes.

Quando uma solicitação [!DNL Target] é recebida de novos sites ou domínios, estes sempre aparecem no ambiente [!UICONTROL Production]. O ambiente [!UICONTROL Production] não pode ter suas configurações alteradas, portanto, sites novos ou desconhecidos têm garantia de ver somente o conteúdo que está ativo e pronto. O gerenciamento de hosts também permite garantir a qualidade de novas atividades e do conteúdo em seus ambientes de teste, armazenamento temporário e desenvolvimento, antes das atividades serem ativadas.

{{permissions-update}}

Para gerenciar ambientes, clique em **[!UICONTROL Administration]** > **[!UICONTROL Environments]**.

## Adicionar um ambiente {#section_32097D0993724DF3A202D164D3F18674}

1. Na lista [!UICONTROL Environments], clique em **[!UICONTROL Add Environment]**.
1. Especifique um nome descritivo para o ambiente.
1. Especifique o modo ativo desejado para o ambiente: [!UICONTROL Active Activities] ou [!UICONTROL Active and Inactive Activities].

   Se você especificar [!UICONTROL Active and Inactive Activities], os hosts desse ambiente também exibirão atividades inativas.

1. Clique em **[!UICONTROL Save]**.

## Definir o ambiente padrão para relatórios {#section_4F8539B07C0C45E886E8525C344D5FB0}

Você pode selecionar o ambiente que deseja usar como padrão em todos os relatórios de atividade.

Se você usar [!UICONTROL Production] como padrão, todos os hosts desconhecidos serão adicionados automaticamente aqui e os dados de relatório de lá serão incluídos na exibição de relatório padrão. Em vez disso, criar um ambiente &quot;limpo&quot; garante somente a inclusão dos seus sites/domínios principais.

Para definir o ambiente padrão para relatório:

1. Na lista [!UICONTROL Environments], clique no ícone Estrela

>[!NOTE]
>
>[!DNL Recommendations]Os usuários do devem recriar sua base de dados comportamental e a base de dados de produtos se os hosts alternarem os grupos de host.
>
>Se você especificar um [ambiente padrão em uma [!DNL Adobe Experience Platform] sequência de dados](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=en#target){target=_blank}, esta configuração substituirá a configuração em [!DNL Target].

## Alterar o nome de um ambiente {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. Na lista [!UICONTROL Environment], clique no ícone **[!UICONTROL Edit]**.
1. Altere o nome do ambiente.
1. Clique em **[!UICONTROL Save]**.

## Excluir um ambiente {#section_737F8869612047868D03FC755B1223D3}

Você pode excluir um ambiente quando ele não é mais necessário.

1. Na lista [!UICONTROL Environment], clique no ícone **[!UICONTROL Delete]**.
1. Clique em **[!UICONTROL Delete]** para confirmar a exclusão.

>[!NOTE]
>
>Você não pode excluir o ambiente [!UICONTROL Production], mas pode renomeá-lo.

## [!BADGE Premium]{type=Positive url="/help/main/c-intro/intro.md#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."} Recommendations: filtre coleções e exclusões por ambiente (grupo de hosts)

Você pode visualizar o conteúdo das coleções e exclusões do Recomendações de um ambiente selecionado (grupo de hosts).

{{premium-note}}

Um ambiente pode ser usado para separar os itens disponíveis no catálogo para diferentes usos. Por exemplo, você pode usar grupos de hosts para ambientes [!UICONTROL Development] e [!UICONTROL Production], marcas diferentes ou regiões diferentes. Por padrão, os resultados de visualização na Pesquisa no catálogo, nas Coleções e nas Exclusões estão baseados no grupo de hosts padrão. (Também é possível selecionar um grupo de hosts diferente para visualizar os resultados, usando o filtro Ambiente.) Por padrão, os itens recém adicionados ficam disponíveis em todos os grupos de hosts, a menos que uma ID de ambiente seja especificada ao criar ou atualizar o item.

>[!NOTE]
>
>As recomendações entregues dependem do grupo de hosts ou da ID de ambiente especificada na solicitação.


Se você não visualiza seus produtos, certifique-se de que você esteja usando o grupo correto de hosts. Por exemplo, se você configurar sua recomendação para usar um ambiente de preparo e você definir o grupo de hosts para Armazenamento temporário, você pode necessitar recriar suas coleções no ambiente de preparo para serem mostradas pelos produtos. Para ver quais produtos estão disponíveis em cada ambiente, use a Pesquisa de catálogo com cada ambiente. Você também pode visualizar o conteúdo das coleções e exclusões do Recomendações para um ambiente selecionado (grupo de hosts).

>[!NOTE]
>Depois de alterar o ambiente selecionado, clique em Pesquisar para atualizar os resultados retornados.

O filtro [!UICONTROL Environment] está disponível nos seguintes locais na interface do usuário de Destino:

* Pesquisa no catálogo ([!UICONTROL Recommendations > Catalog Search])
* Caixa de diálogo Criar Coleção ([!UICONTROL Recommendations > Collections > Create New])
* Caixa de diálogo Atualizar Coleção ([!UICONTROL Recommendations > Collections > Edit])
* Caixa de diálogo Criar Exclusão ([!UICONTROL Recommendations > Exclusions > Create New])
* Caixa de diálogo Atualizar Exclusão ([!UICONTROL Recommendations > Exclusions > Edit])
