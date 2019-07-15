---
description: O Target Standard pode ser integrado com o Adobe Dynamic Media Classic (antigo Scene 7) para fornecer Gerenciamento de ativos digitais (DAM) na Biblioteca de conteúdo.
seo-description: O Target Standard pode ser integrado com o Adobe Dynamic Media Classic (antigo Scene 7) para fornecer Gerenciamento de ativos digitais (DAM) na Biblioteca de conteúdo.
seo-title: Integração do Dynamic Media Classic
solution: Target
subtopic: Introdução
title: Integração do Dynamic Media Classic
topic: Padrão
uuid: 4b06a3ed-0e87-4e49-874f-2e479324f81c
translation-type: tm+mt
source-git-commit: c6a59843c80017e6f072f65ffad822fe198ebb55

---


# Dynamic Media Classic integration{#scene-settings}

O Target Standard pode ser integrado com o Adobe Dynamic Media Classic (antigo Scene 7) para fornecer Gerenciamento de ativos digitais (DAM) na Biblioteca de conteúdo.

>[!NOTE]
>
>A integração do Target com o Dynamic Media Classic permite a entrega de ativos (como parte das atividades) carregados na pasta de ativos da Adobe Experience Cloud. Essa integração não habilita o acesso a todos os ativos carregados no Dynamic Media Classic para entrega nas atividades do Target.

Se você já tiver uma conta de Mídia dinâmica, poderá fornecer suas credenciais existentes. Se você não tiver uma conta, poderá solicitar uma conta do Dynamic Media Classic de uso restrito sem nenhum custo adicional do representante da Adobe. Esta conta pode ser usada para propósitos restritos para uso apenas no Target. Este serviço está disponível para cliente com fluxos de trabalho que precisam de funcionalidade de troca de imagem.

Se esta configuração não estiver definida, a opção de troca de imagem de oferta dentro do fluxo de trabalho da criação da atividade não estará disponível. Após está configuração estar definida, a opção de trocar imagens de oferta ficará disponível no [Visual Experience Composer (VEC) e no Experience Composer baseado em formulários](../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). Você pode então alavancar imagens de ofertas com imagens que foram carregadas na Adobe Experience Cloud para uso em atividades do Target.

Se você quer referenciar um URL de imagem pública diretamente em uma oferta ou código personalizado durante a criação da atividade, você deve implantar a imagem em seu próprio servidor web e usar seu próprio URL no código. Não há como obter o URL publicado de uma imagem carregada na Experience Cloud para consumir diretamente ou por fora de fluxos de trabalho de definição usando o Adobe Target. Esta funcionalidade não é permitida, de acordo com o contrato.

Observe que o URL de armazenamento e os urls de publicação finais de imagens do Dynamic Media são diferentes e um não DEVE criar ofertas usando o link de armazenamento de imagens como a entrega não funcionará em tais casos. Você precisa usar a capacidade de ofertas de imagem conforme explicado em nossa documentação de ajuda.

Para integrar com o Dynamic Media Classic (Scene 7), você precisa especificar algumas das seguintes informações.

1. Clique em **[!UICONTROL Configuração]** &gt; **[!UICONTROL Configurações do Scene7]**.
1. Especifique as seguintes informações da conta do Dynamic Media Classic:

   **Região:** A região da sua conta do Dynamic Media: América do Norte, Europa ou Ásia.

   **Pasta Adhoc:** O local do conteúdo que está fora da pasta de destino e é carregado manualmente para o Dynamic Media.

   **Endereço de email:** O endereço de email usado para fazer logon no Dynamic Media Classic (Scene 7).

   **Senha:** A senha usada para fazer logon no Dynamic Media Classic (Scene 7).
1. Clique em **[!UICONTROL Enviar]**.
