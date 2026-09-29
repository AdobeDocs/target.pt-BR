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
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: ed3d4b67c78791454c55a2cad4908a37a4d60e26
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%
---
# ➡ URLs Incluídos na lista de permissões

As URLs resolvidas definem padrões de URL confiáveis em que sua organização pode criar e executar experiências do [!DNL Adobe Target], inclusive quando você usa ofertas remotas ou de redirecionamento. A lista funciona com o [gerenciamento de hosts](/help/main/administrating-target/hosts.md) e com os [ambientes](/help/main/administrating-target/environments.md), mas se aplica especificamente aos padrões de URL de oferta remota permitidos e validações relacionadas.

Para gerenciar URLs migrados, clique em **[!UICONTROL Administração]** > **[!UICONTROL URLs migrados]**.

![página URLs Incluídos na lista de permissões mostrando a lista de URLs, o campo de pesquisa e o controle Adicionar URL](../administrating-target/assets/allowlist-1.png)

## Gerenciar URLs ➡ {#add-url}

A tabela principal lista cada padrão classificado em uma única coluna. As entradas compatíveis podem incluir URLs exatos, caminhos curingas ou formatos de padrão aceitos por sua organização para experiências remotas.

1. Clique em **[!UICONTROL Adicionar URL]**.

   ![](../administrating-target/assets/allowlist-2.png)

1. Na caixa de diálogo, insira o URL ou padrão que sua organização deve permitir.

   ![](../administrating-target/assets/allowlist-3.png)

1. Salve as alterações.

   Depois que o padrão é criado, os usuários podem criar ou executar atividades e ofertas que dependem dessa URL, sujeitas às outras regras do [!DNL Target].

1. Use o campo **[!UICONTROL Pesquisar URLs]** para filtrar a tabela.

1. Para excluir uma URL, encontre a linha para o padrão que você não precisa mais e clique no ícone ![Excluir](../administrating-target/assets/do-not-localize/Smock_Delete_18_N.svg).

   ![](../administrating-target/assets/allowlist-4.png)


