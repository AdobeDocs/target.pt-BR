---
keywords: ambiente;solução de problemas;práticas recomendadas;ubox;redireciona;redireciona;lista de permissões;lista negra;lista de bloqueios;lista de permissões;;troubleshooting;unpractices;redirects;redirect;whitelist;blacklist;blacklist;;_solution;best practices;ubox;redirects;
description: Saiba como usar ambientes na Adobe Target para organizar seus sites e ambientes de pré-produção para facilitar o gerenciamento e o relatórios separado.
title: O que são Ambientes e como eu os uso?
feature: Administration & Configuration
role: Administrator
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 63%

---


# Ambientes

Organize seus sites e ambientes de pré-produção para fácil gerenciamento e geração de relatórios separados.

Os hosts são agrupados em ambientes para facilitar o gerenciamento. Por exemplo, você pode ter dezenas de hosts agrupados em dois ou três ambientes. Os ambientes predefinidos incluem [!UICONTROL Production], [!UICONTROL Staging] e [!UICONTROL Development]. Você pode adicionar novos ambientes e renomear seus ambientes, se desejado.

Um ambiente, o ambiente padrão, é pré-nomeado [!UICONTROL Production]. Esse ambiente padrão não pode ser removido, mesmo que você o renomeie. O [!DNL Target] parte do princípio que este é o local onde você disponibiliza atividades finais, aprovadas e testes.

Quando uma solicitação [!DNL Target] é recebida de novos sites ou domínios, esses novos domínios sempre aparecem no ambiente [!UICONTROL Production]. O ambiente [!UICONTROL Production] não pode ter suas configurações alteradas, portanto, sites desconhecidos ou novos são garantidos para ver somente o conteúdo que está ativo e pronto. O gerenciamento de hosts também permite garantir a qualidade de novas atividades e do conteúdo em seus ambientes de teste, armazenamento temporário e desenvolvimento, antes das atividades serem ativadas.

Para gerenciar ambientes, clique em **[!UICONTROL Administração]** > **[!UICONTROL Ambientes]**.

![Lista ambientes](/help/administrating-target/assets/environments.png)

## Adicionar um ambiente {#section_32097D0993724DF3A202D164D3F18674}

1. Na lista [!UICONTROL Ambientes], clique em **[!UICONTROL Adicionar Ambiente]**.
1. Especifique um nome descritivo para o ambiente.
1. Especifique o modo ativo desejado para o ambiente: [!UICONTROL Atividades ativas] ou [!UICONTROL Atividades ativas e inativas].
1. Clique em **[!UICONTROL Salvar]**.

## Defina o ambiente padrão para o relatórios {#section_4F8539B07C0C45E886E8525C344D5FB0}

Você pode selecionar o ambiente que deseja usar como padrão em todos os relatórios de atividade.

Se você usar [!UICONTROL Production] como padrão, todos os hosts desconhecidos serão adicionados automaticamente aqui e os dados de relatório de lá serão incluídos na visualização de relatório padrão. Em vez disso, criar um ambiente &quot;limpo&quot; garante somente a inclusão dos seus sites/domínios principais.

Para definir o ambiente padrão para relatório:

1. Na lista [!UICONTROL Ambientes], clique no ícone Estrela

>[!NOTE]
>
>[!DNL Recommendations]Os usuários do devem recriar sua base de dados comportamental e a base de dados de produtos se os hosts alternarem os grupos de host.

## Alterar o nome de um ambiente {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. Na lista [!UICONTROL Ambiente], clique no ícone **[!UICONTROL Editar]**.
1. Altere o nome do ambiente.
1. Clique em **[!UICONTROL Salvar]**.

## Excluir um ambiente {#section_737F8869612047868D03FC755B1223D3}

Você pode excluir um ambiente quando ele não é mais necessário.

1. Na lista [!UICONTROL Ambiente], clique no ícone **[!UICONTROL Excluir]**.
1. Clique em **[!UICONTROL Excluir]** para confirmar a exclusão.

>[!NOTE]
>
>Não é possível excluir o ambiente [!UICONTROL Production], mas é possível renomeá-lo.

## Recommendations: coleções e exclusões de filtros por ambiente (grupo de hosts)

![Selo premium](/help/assets/premium.png)

Você pode visualizar o conteúdo das coleções e exclusões do Recommendations de um ambiente selecionado (grupo de hosts).

>[!NOTE]
>
>O Recommendations atividade está disponível como parte da solução [!DNL Target] Premium. Não estão disponíveis no [!DNL Target] Standard sem uma licença do [!DNL Target] Premium.

Um ambiente pode ser usado para separar os itens disponíveis no catálogo para usos diferentes. Por exemplo, você pode usar grupos de host para ambientes [!UICONTROL Desenvolvimento] e [!UICONTROL Produção], marcas diferentes ou localidades geográficas diferentes. Por padrão, os resultados de visualização na Pesquisa no catálogo, nas Coleções e nas Exclusões estão baseados no grupo de hosts padrão. (Também é possível selecionar um grupo de hosts diferente para visualizar os resultados, usando o filtro Ambiente.) Por padrão, os itens recém adicionados ficam disponíveis em todos os grupos de hosts, a menos que uma ID de ambiente seja especificada ao criar ou atualizar o item. As recomendações entregues dependem do grupo de hosts especificado na solicitação.

Se você não visualiza seus produtos, certifique-se de que você esteja usando o grupo correto de hosts. Por exemplo, se você configurar sua recomendação para usar um ambiente de preparo e você definir o grupo de hosts para Armazenamento temporário, você pode necessitar recriar suas coleções no ambiente de preparo para serem mostradas pelos produtos. Para ver quais produtos estão disponíveis em cada ambiente, use a Pesquisa de catálogo com cada ambiente. Você também pode visualizar o conteúdo das coleções e exclusões do Recommendations para um ambiente selecionado (grupo de hosts).

>[!NOTE]
>Depois de alterar o ambiente selecionado, clique em Pesquisar para atualizar os resultados retornados.

O filtro [!UICONTROL Ambiente] está disponível nos seguintes locais na interface do usuário do Público alvo:

* Pesquisa do catálogo ([!UICONTROL Recommendations> Pesquisa do catálogo])
* Caixa de diálogo Criar coleção ([!UICONTROL Recommendations> Coleções > Criar nova])
* Caixa de diálogo Atualizar coleção ([!UICONTROL Recommendations > Coleções > Editar])
* Caixa de diálogo Criar exclusão ([!UICONTROL Recommendations > Exclusões > Criar novo])
* Caixa de diálogo Atualizar exclusão ([!UICONTROL Recommendations > Exclusões > Editar])