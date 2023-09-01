---
keywords: ambiente;solução de problemas;práticas recomendadas;ubox;redireciona;redirecionar;lista de permissões;lista negra;incluir na lista de bloqueios;incluir na lista de permissões
description: Saiba como usar ambientes no Adobe [!DNL Target] organizar seus sites e ambientes de pré-produção para facilitar o gerenciamento e gerar relatórios separados.
title: O que são ambientes e como usá-los?
feature: Administration & Configuration
role: Admin
exl-id: 820a116a-15f9-4ba0-94f3-8e35aa0f90da
source-git-commit: 516d3969c8a6ed073b9f8d53c842e4d759cee8a2
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 56%

---

# Ambientes

Organize seus sites e ambientes de pré-produção para fácil gerenciamento e geração de relatórios separados.

Os hosts são agrupados em ambientes para facilitar o gerenciamento. Por exemplo, você pode ter dezenas de hosts agrupados em dois ou três ambientes. Os ambientes predefinidos incluem [!UICONTROL Produção], [!UICONTROL Estágios], e [!UICONTROL Desenvolvimento]. Você pode adicionar novos ambientes e renomear seus ambientes, se desejado.

Um ambiente, o ambiente padrão, é pré-nomeado [!UICONTROL Produção]. Esse ambiente padrão não pode ser removido, mesmo que você o renomeie. O [!DNL Target] parte do princípio que este é o local onde você disponibiliza atividades finais, aprovadas e testes.

Quando um [!DNL Target] for recebida de novos sites ou domínios, esses novos domínios sempre aparecerão no [!UICONTROL Produção] ambiente. A variável [!UICONTROL Produção] as configurações do ambiente não podem ser alteradas, portanto, sites novos ou desconhecidos têm garantia de visualizar somente o conteúdo que está ativo e pronto. O gerenciamento de hosts também permite garantir a qualidade de novas atividades e do conteúdo em seus ambientes de teste, armazenamento temporário e desenvolvimento, antes das atividades serem ativadas.

Para gerenciar ambientes, clique em **[!UICONTROL Administração]** > **[!UICONTROL Ambientes]**.

![Lista de ambientes](/help/main/administrating-target/assets/environments.png)

## Adicionar um ambiente {#section_32097D0993724DF3A202D164D3F18674}

1. No [!UICONTROL Ambientes] clique em **[!UICONTROL Adicionar ambiente]**.
1. Especifique um nome descritivo para o ambiente.
1. Especifique o modo ativo desejado para o ambiente: [!UICONTROL Atividades ativas] ou [!UICONTROL Atividades ativas e inativas].

   Se você especificar [!UICONTROL Atividades ativas e inativas], hosts desse ambiente também exibem atividades inativas.

1. Clique em **[!UICONTROL Salvar]**.

## Definir o ambiente padrão para relatórios {#section_4F8539B07C0C45E886E8525C344D5FB0}

Você pode selecionar o ambiente que deseja usar como padrão em todos os relatórios de atividade.

Se você usar [!UICONTROL Produção] como padrão, todos os hosts desconhecidos são adicionados automaticamente aqui e os dados de relatório de lá são incluídos na visualização de relatório padrão. Em vez disso, criar um ambiente &quot;limpo&quot; garante somente a inclusão dos seus sites/domínios principais.

Para definir o ambiente padrão para relatório:

1. No [!UICONTROL Ambientes] clique no ícone Estrela

>[!NOTE]
>
>[!DNL Recommendations]Os usuários do devem recriar sua base de dados comportamental e a base de dados de produtos se os hosts alternarem os grupos de host.
>
>Se você especificar um [ambiente padrão em um [!DNL Adobe Experience Platform] sequência de dados](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=en#target){target=_blank}, esta configuração substitui a configuração em [!DNL Target].

## Alterar o nome de um ambiente {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. No [!UICONTROL Ambiente] clique na guia **[!UICONTROL Editar]** ícone.
1. Altere o nome do ambiente.
1. Clique em **[!UICONTROL Salvar]**.

## Excluir um ambiente {#section_737F8869612047868D03FC755B1223D3}

Você pode excluir um ambiente quando ele não é mais necessário.

1. No [!UICONTROL Ambiente] clique na guia **[!UICONTROL Excluir]** ícone.
1. Clique em **[!UICONTROL Excluir]** para confirmar a exclusão.

>[!NOTE]
>
>Não é possível excluir o [!UICONTROL Produção] ambiente, mas você pode renomeá-lo.

## [!BADGE Premium]{type=Positive url="/help/main/c-intro/intro.md#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."}

Você pode visualizar o conteúdo das coleções e exclusões do Recommendations de um ambiente selecionado (grupo de hosts).

{{premium-note}}

Um ambiente pode ser usado para separar os itens disponíveis no catálogo para diferentes usos. Por exemplo, você pode usar grupos de hosts para [!UICONTROL Desenvolvimento] e [!UICONTROL Produção] ambientes, marcas ou regiões diferentes. Por padrão, os resultados de visualização na Pesquisa no catálogo, nas Coleções e nas Exclusões estão baseados no grupo de hosts padrão. (Também é possível selecionar um grupo de hosts diferente para visualizar os resultados, usando o filtro Ambiente.) Por padrão, os itens recém adicionados ficam disponíveis em todos os grupos de hosts, a menos que uma ID de ambiente seja especificada ao criar ou atualizar o item.

>[!NOTE]
>
>As recomendações entregues dependem do grupo de hosts ou da ID de ambiente especificada na solicitação.


Se você não visualiza seus produtos, certifique-se de que você esteja usando o grupo correto de hosts. Por exemplo, se você configurar sua recomendação para usar um ambiente de preparo e você definir o grupo de hosts para Armazenamento temporário, você pode necessitar recriar suas coleções no ambiente de preparo para serem mostradas pelos produtos. Para ver quais produtos estão disponíveis em cada ambiente, use a Pesquisa de catálogo com cada ambiente. Você também pode visualizar o conteúdo das coleções e exclusões do Recommendations para um ambiente selecionado (grupo de hosts).

>[!NOTE]
>Depois de alterar o ambiente selecionado, clique em Pesquisar para atualizar os resultados retornados.

A variável [!UICONTROL Ambiente] O filtro está disponível nos seguintes locais na interface do usuário do Target:

* Pesquisa do catálogo ([!UICONTROL Recommendations> Pesquisa do catálogo])
* Caixa de diálogo Criar coleção ([!UICONTROL Recommendations> Coleções > Criar nova])
* Caixa de diálogo Atualizar coleção ([!UICONTROL Recommendations > Coleções > Editar])
* Caixa de diálogo Criar exclusão ([!UICONTROL Recommendations > Exclusões > Criar novo])
* Caixa de diálogo Atualizar exclusão ([!UICONTROL Recommendations > Exclusões > Editar])
