---
keywords: incluo na lista de permissões;oferta remota;administração;padrões de URL;validação;atividades;ofertas;curinga;regex
description: Saiba como visualizar, pesquisar, adicionar e excluir URLs resolvidos para ofertas remotas na seção Administração do Adobe Target, incluindo comportamento de validação e escopo de toda a conta.
title: Gerenciar URLs de oferta remota ➡
feature: Administration & Configuration
topic: Implementation
role: Admin
level: Intermediate
solution: Target
product: Target
source-git-commit: 882c91244e5dae0977c8a6a1e5878525f497a720
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%

---

# ➡ URLs Incluídos na lista de permissões

As URLs resolvidas definem padrões de URL confiáveis em que sua organização pode criar e executar experiências do [!DNL Adobe Target], inclusive quando você usa ofertas remotas ou de redirecionamento. A lista funciona com o [gerenciamento de hosts](/help/main/administrating-target/hosts.md) e com os [ambientes](/help/main/administrating-target/environments.md), mas se aplica especificamente aos padrões de URL de oferta remota permitidos e validações relacionadas.

Para gerenciar URLs migrados, clique em **[!UICONTROL Administration]** > **[!UICONTROL Allowlisted URLs]**.

![página URLs Incluídos na lista de permissões mostrando a lista de URLs, o campo de pesquisa e o controle Adicionar URL](../administrating-target/assets/allowlist-1.png)

## Gerenciar URLs ➡ {#add-url}

A tabela principal lista cada padrão classificado em uma única coluna. As entradas compatíveis podem incluir URLs exatos, caminhos curingas ou formatos de padrão aceitos por sua organização para experiências remotas.

1. Clique em **[!UICONTROL Add URL]**.

   ![](../administrating-target/assets/allowlist-2.png)

1. Na caixa de diálogo, insira o URL ou padrão que sua organização deve permitir.

   ![](../administrating-target/assets/allowlist-3.png)

1. Salve as alterações.

   Depois que o padrão é criado, os usuários podem criar ou executar atividades e ofertas que dependem dessa URL, sujeitas às outras regras do [!DNL Target].

1. Use o campo **[!UICONTROL Search URLs]** para filtrar a tabela.

1. Para excluir uma URL, encontre a linha para o padrão que você não precisa mais e clique no ícone ![Excluir](../administrating-target/assets/do-not-localize/Smock_Delete_18_N.svg).

   ![](../administrating-target/assets/allowlist-4.png)


