---
keywords: environment;troubleshooting;best practices;ubox;redirects;redirect;whitelist;blacklist;blocklist;allowlist
description: Organize seus sites e ambientes de pré-produção para fácil gerenciamento e geração de relatórios separados.
title: Ambientes
feature: hosts and environments
topic: Standard
uuid: c7682269-4ec2-4a0f-b053-7e0ec77f4604
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 68%

---


# Ambientes

Organize seus sites e ambientes de pré-produção para fácil gerenciamento e geração de relatórios separados.

Os hosts são agrupados em ambientes para facilitar o gerenciamento. Por exemplo, você pode ter dezenas de hosts agrupados em dois ou três ambientes. The preset environments include [!UICONTROL Production], [!UICONTROL Staging], and [!UICONTROL Development]. Você pode adicionar novos ambientes e renomear seus ambientes, se desejado.

One environment, the default environment, is pre-named [!UICONTROL Production]. Esse ambiente padrão não pode ser removido, mesmo que você o renomeie. O [!DNL Target] parte do princípio que este é o local onde você disponibiliza atividades finais, aprovadas e testes.

When a [!DNL Target] request is received from new websites or domains, these new domains always appear in the [!UICONTROL Production] environment. The [!UICONTROL Production] environment cannot have its settings changed, so unknown or new sites are guaranteed to see only content that is active and ready. O gerenciamento de hosts também permite garantir a qualidade de novas atividades e do conteúdo em seus ambientes de teste, armazenamento temporário e desenvolvimento, antes das atividades serem ativadas.

Para gerenciar ambientes, clique em **[!UICONTROL Administração]** > **[!UICONTROL Ambientes]**.

![Lista ambientes](/help/administrating-target/assets/environments.png)

## Adicionar um ambiente {#section_32097D0993724DF3A202D164D3F18674}

1. Na lista [!UICONTROL Ambientes] , clique em **[!UICONTROL Adicionar Ambiente]**.
1. Especifique um nome descritivo para o ambiente.
1. Especifique o modo ativo desejado para o ambiente: [!UICONTROL Atividades ativas] ou [!UICONTROL Atividades ativas e inativas].
1. Clique em **[!UICONTROL Salvar]**.

## Set the default environment for reporting {#section_4F8539B07C0C45E886E8525C344D5FB0}

Você pode selecionar o ambiente que deseja usar como padrão em todos os relatórios de atividade.

If you use [!UICONTROL Production] as your default, all unknown hosts automatically are added here and report data from there is included in the default report view. Em vez disso, criar um ambiente &quot;limpo&quot; garante somente a inclusão dos seus sites/domínios principais.

Para definir o ambiente padrão para relatório:

1. Na lista [!UICONTROL Ambientes] , clique no ícone Estrela

>[!NOTE]
>
>[!DNL Recommendations]Os usuários do devem recriar sua base de dados comportamental e a base de dados de produtos se os hosts alternarem os grupos de host.

## Change the name of an environment {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. Na lista do [!UICONTROL Ambiente] , clique no ícone **[!UICONTROL Editar]** .
1. Altere o nome do ambiente.
1. Clique em **[!UICONTROL Salvar]**.

## Delete an environment {#section_737F8869612047868D03FC755B1223D3}

Você pode excluir um ambiente quando ele não é mais necessário.

1. Na lista do [!UICONTROL Ambiente] , clique no ícone **[!UICONTROL Excluir]** .
1. Clique em **[!UICONTROL Excluir]** para confirmar a exclusão.

>[!NOTE]
>
>You cannot delete the [!UICONTROL Production] environment, but you can rename it.

## Recommendations: coleções e exclusões de filtros por ambiente (grupo de hosts)

![Selo premium](/help/assets/premium.png)

Você pode visualizar o conteúdo das coleções e exclusões do Recommendations de um ambiente selecionado (grupo de hosts).

>[!NOTE]
>
>Recommendations activities are available as part of the [!DNL Target] Premium solution. Não estão disponíveis no [!DNL Target] Standard sem uma licença do [!DNL Target] Premium.

Um ambiente pode ser usado para separar os itens disponíveis no catálogo para usos diferentes. For example, you can use host groups for [!UICONTROL Development] and [!UICONTROL Production] environments, different brands, or different geographies. Por padrão, os resultados de visualização na Pesquisa no catálogo, nas Coleções e nas Exclusões estão baseados no grupo de hosts padrão. (Também é possível selecionar um grupo de hosts diferente para visualizar os resultados, usando o filtro Ambiente.) Por padrão, os itens recém adicionados ficam disponíveis em todos os grupos de hosts, a menos que uma ID de ambiente seja especificada ao criar ou atualizar o item. As recomendações entregues dependem do grupo de hosts especificado na solicitação.

Se você não visualiza seus produtos, certifique-se de que você esteja usando o grupo correto de hosts. Por exemplo, se você configurar sua recomendação para usar um ambiente de preparo e você definir o grupo de hosts para Armazenamento temporário, você pode necessitar recriar suas coleções no ambiente de preparo para serem mostradas pelos produtos. Para ver quais produtos estão disponíveis em cada ambiente, use a Pesquisa de catálogo com cada ambiente. Você também pode visualizar o conteúdo das coleções e exclusões do Recommendations para um ambiente selecionado (grupo de hosts).

>[!NOTE]
>Depois de alterar o ambiente selecionado, clique em Pesquisar para atualizar os resultados retornados.

The [!UICONTROL Environment] filter is available from the following places in the Target UI:

* Pesquisa do catálogo ([!UICONTROL Recommendations> Pesquisa do catálogo])
* Caixa de diálogo Criar coleção ([!UICONTROL Recommendations> Coleções > Criar nova])
* Caixa de diálogo Atualizar coleção ([!UICONTROL Recommendations > Coleções > Editar])
* Caixa de diálogo Criar exclusão ([!UICONTROL Recommendations > Exclusões > Criar novo])
* Caixa de diálogo Atualizar exclusão ([!UICONTROL Recommendations > Exclusões > Editar])