---
keywords: ambiente, solução de problemas, práticas recomendadas, ubox, redirecionamentos, redirecionamento, lista de permissões, lista negra, lista de bloqueios,  lista de permissões
description: Saiba como usar ambientes no Adobe [!DNL Target] para organizar seus sites e ambientes de pré-produção para fácil gerenciamento e relatórios separados.
title: O que são ambientes e como os uso?
feature: Administração e configuração
role: Administrator
exl-id: 820a116a-15f9-4ba0-94f3-8e35aa0f90da
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 63%

---

# Ambientes

Organize seus sites e ambientes de pré-produção para fácil gerenciamento e geração de relatórios separados.

Os hosts são agrupados em ambientes para facilitar o gerenciamento. Por exemplo, você pode ter dezenas de hosts agrupados em dois ou três ambientes. Os ambientes predefinidos incluem [!UICONTROL Produção], [!UICONTROL Armazenamento temporário] e [!UICONTROL Desenvolvimento]. Você pode adicionar novos ambientes e renomear seus ambientes, se desejado.

Um ambiente, o ambiente padrão, é pré-nomeado [!UICONTROL Produção]. Esse ambiente padrão não pode ser removido, mesmo que você o renomeie. O [!DNL Target] parte do princípio que este é o local onde você disponibiliza atividades finais, aprovadas e testes.

Quando uma solicitação [!DNL Target] é recebida de novos sites da Web ou domínios, esses novos domínios sempre aparecem no ambiente [!UICONTROL Production]. O ambiente [!UICONTROL Produção] não pode ter suas configurações alteradas, portanto, sites desconhecidos ou novos são garantidos para ver somente o conteúdo que está ativo e pronto. O gerenciamento de hosts também permite garantir a qualidade de novas atividades e do conteúdo em seus ambientes de teste, armazenamento temporário e desenvolvimento, antes das atividades serem ativadas.

Para gerenciar ambientes, clique em **[!UICONTROL Administration]** > **[!UICONTROL Ambientes]**.

![Lista de ambientes](/help/administrating-target/assets/environments.png)

## Adicionar um ambiente {#section_32097D0993724DF3A202D164D3F18674}

1. Na lista [!UICONTROL Ambientes], clique em **[!UICONTROL Adicionar Ambiente]**.
1. Especifique um nome descritivo para o ambiente.
1. Especifique o modo ativo desejado para o ambiente: [!UICONTROL Atividades ativas] ou [!UICONTROL Atividades ativas e inativas].
1. Clique em **[!UICONTROL Salvar]**.

## Definir o ambiente padrão para relatórios {#section_4F8539B07C0C45E886E8525C344D5FB0}

Você pode selecionar o ambiente que deseja usar como padrão em todos os relatórios de atividade.

Se você usar [!UICONTROL Produção] como padrão, todos os hosts desconhecidos serão adicionados automaticamente aqui e os dados de relatório de lá serão incluídos na exibição de relatório padrão. Em vez disso, criar um ambiente &quot;limpo&quot; garante somente a inclusão dos seus sites/domínios principais.

Para definir o ambiente padrão para relatório:

1. Na lista [!UICONTROL Ambientes], clique no ícone Estrela

>[!NOTE]
>
>[!DNL Recommendations]Os usuários do devem recriar sua base de dados comportamental e a base de dados de produtos se os hosts alternarem os grupos de host.

## Alterar o nome de um ambiente {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. Na lista [!UICONTROL Environment], clique no ícone **[!UICONTROL Edit]**.
1. Altere o nome do ambiente.
1. Clique em **[!UICONTROL Salvar]**.

## Excluir um ambiente {#section_737F8869612047868D03FC755B1223D3}

Você pode excluir um ambiente quando ele não é mais necessário.

1. Na lista [!UICONTROL Environment], clique no ícone **[!UICONTROL Delete]**.
1. Clique em **[!UICONTROL Excluir]** para confirmar a exclusão.

>[!NOTE]
>
>Não é possível excluir o ambiente [!UICONTROL Production], mas você pode renomeá-lo.

## Recommendations: coleções e exclusões de filtros por ambiente (grupo de hosts)

![Selo premium](/help/assets/premium.png)

Você pode visualizar o conteúdo das coleções e exclusões do Recommendations de um ambiente selecionado (grupo de hosts).

>[!NOTE]
>
>As atividades do Recommendations estão disponíveis como parte da solução [!DNL Target] Premium . Não estão disponíveis no [!DNL Target] Standard sem uma licença do [!DNL Target] Premium.

Um ambiente pode ser usado para separar os itens disponíveis no catálogo para diferentes usos. Por exemplo, você pode usar grupos de hosts para ambientes de [!UICONTROL Desenvolvimento] e [!UICONTROL Produção], diferentes marcas ou diferentes regiões. Por padrão, os resultados de visualização na Pesquisa no catálogo, nas Coleções e nas Exclusões estão baseados no grupo de hosts padrão. (Também é possível selecionar um grupo de hosts diferente para visualizar os resultados, usando o filtro Ambiente.) Por padrão, os itens recém adicionados ficam disponíveis em todos os grupos de hosts, a menos que uma ID de ambiente seja especificada ao criar ou atualizar o item. As recomendações entregues dependem do grupo de hosts especificado na solicitação.

Se você não visualiza seus produtos, certifique-se de que você esteja usando o grupo correto de hosts. Por exemplo, se você configurar sua recomendação para usar um ambiente de preparo e você definir o grupo de hosts para Armazenamento temporário, você pode necessitar recriar suas coleções no ambiente de preparo para serem mostradas pelos produtos. Para ver quais produtos estão disponíveis em cada ambiente, use a Pesquisa de catálogo com cada ambiente. Você também pode visualizar o conteúdo das coleções e exclusões do Recommendations para um ambiente selecionado (grupo de hosts).

>[!NOTE]
>Depois de alterar o ambiente selecionado, clique em Pesquisar para atualizar os resultados retornados.

O filtro [!UICONTROL Environment] está disponível nos seguintes locais na interface do usuário do Target:

* Pesquisa do catálogo ([!UICONTROL Recommendations> Pesquisa do catálogo])
* Caixa de diálogo Criar coleção ([!UICONTROL Recommendations> Coleções > Criar nova])
* Caixa de diálogo Atualizar coleção ([!UICONTROL Recommendations > Coleções > Editar])
* Caixa de diálogo Criar exclusão ([!UICONTROL Recommendations > Exclusões > Criar novo])
* Caixa de diálogo Atualizar exclusão ([!UICONTROL Recommendations > Exclusões > Editar])
