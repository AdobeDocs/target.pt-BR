---
description: O Target Standard pode ser integrado com o Adobe Dynamic Media Classic (anteriormente Adobe Scene7) para fornecer gerenciamento de ativos digitais (DAM) na biblioteca de conteúdo.
title: Integração com o Dynamic Media Classic integração de configuração
subtopic: Getting Started
topic: Standard
uuid: 4b06a3ed-0e87-4e49-874f-2e479324f81c
translation-type: tm+mt
source-git-commit: bbc1c9282007c180f30023b6f15d693a31683243
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 94%

---


# Integração com o Dynamic Media Classic{#scene-settings}

O Target pode ser integrado com o Adobe Dynamic Media Classic (anteriormente Adobe Scene7) para fornecer gerenciamento de ativos digitais (DAM) na biblioteca de conteúdo.

>[!NOTE]
>
>A integração do Target com o Dynamic Media Classic permite a entrega de ativos (como parte das atividades) carregados na pasta de ativos da Adobe Experience Cloud. Essa integração não permite o acesso a todos ativos carregados no Dynamic Media Classic para entrega em atividades do Target.

Se você já tiver uma conta do Dynamic Media, poderá fornecer suas credenciais existentes. Se não tiver uma conta, poderá solicitar uma conta do Dynamic Media Classic de uso restrito sem nenhum custo adicional do representante da Adobe. Esta conta pode ser usada para propósitos restritos para uso apenas no Target. Este serviço está disponível para cliente com fluxos de trabalho que precisam de funcionalidade de troca de imagem.

Se esta configuração não estiver definida, a opção de troca de imagem de oferta dentro do fluxo de trabalho da criação da atividade não estará disponível. Após está configuração estar definida, a opção de trocar imagens de oferta ficará disponível no  [Visual Experience Composer (VEC) e no Experience Composer baseado em formulários](../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). Você pode então alavancar imagens de ofertas com imagens que foram carregadas na Adobe Experience Cloud para uso em atividades do Target.

Se você quer referenciar um URL de imagem pública diretamente em uma oferta ou código personalizado durante a criação da atividade, você deve implantar a imagem em seu próprio servidor web e usar seu próprio URL no código. Não há como obter o URL publicado de uma imagem carregada na Experience Cloud para consumir diretamente ou por fora de fluxos de trabalho de definição usando o Adobe Target. Esta funcionalidade não é permitida, de acordo com o contrato.

Note que o URL de armazenamento e os URLs finais de imagens publicadas do Dynamic Media são diferentes e você NÃO deve criar ofertas usando o link de imagens armazenadas, pois a entrega não irá funcionar nesses casos. Você precisa usar a capacidade de ofertas de imagem conforme explicado em nossa documentação de ajuda.

Para fazer a integração com o Dynamic Media Classic (Scene7), é necessário especificar as seguintes informações.

1. Click **[!UICONTROL Administration]** > **[!UICONTROL Scene7 Settings]**.

   ![Página do Scene7](/help/administrating-target/assets/scene7.png)

1. Especifique as seguintes informações da conta do Dynamic Media Classic:

   **Região:** A região de sua conta do Dynamic Media: América do Norte, Europa ou Ásia.

   **Pasta adhoc:** O local do conteúdo que fica fora da pasta de destino e é carregado manualmente no Dynamic Media.

   **Endereço de email:** O endereço de e-mail usado para fazer logon no Dynamic Media Classic (Scene7).

   **Senha:** A senha usada para fazer logon no Dynamic Media Classic (Scene7).

1. Clique em **[!UICONTROL Enviar]**.
