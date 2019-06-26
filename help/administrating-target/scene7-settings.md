---
description: O Target Standard pode ser integrado com o Adobe Scene7 para fornecer gerenciamento de ativos digitais (DAM) na Biblioteca de conteúdo.
seo-description: O Target Standard pode ser integrado com o Adobe Scene7 para fornecer gerenciamento de ativos digitais (DAM) na Biblioteca de conteúdo.
seo-title: Definições do Scene7
solution: Target
subtopic: Introdução
title: Definições do Scene7
topic: Padrão
uuid: 4b06a3ed-0e87-4e49-874f-2e479324f81c
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Definições do Scene7{#scene-settings}

O Target Standard pode ser integrado com o Adobe Scene7 para fornecer gerenciamento de ativos digitais (DAM) na Biblioteca de conteúdo.

>[!NOTE]
>
>A integração do Target com o Scene7 permite a entrega de ativos (como parte das atividades) carregados na pasta de ativos da Adobe Experience Cloud. Esta integração não permite o acesso a todos ativos carregados no Scene7 para entrega em atividades do Target.

Se você tem uma conta do Scene7, você pode fornecer suas credenciais do Scene7. Se você não tem uma conta do Scene7, entre em contato com seu representante Adobe que pode configurar esta funcionalidade com uma conta gratuita do Scene7 dedicada para sua conta Target. Esta conta pode ser usada para propósitos restritos para uso apenas no Target. Este serviço está disponível para cliente com fluxos de trabalho que precisam de funcionalidade de troca de imagem.

Se esta configuração não estiver definida, a opção de troca de imagem de oferta dentro do fluxo de trabalho da criação da atividade não estará disponível. Após está configuração estar definida, a opção de trocar imagens de oferta ficará disponível no [Visual Experience Composer (VEC) e no Experience Composer baseado em formulários](../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). Você pode então alavancar imagens de ofertas com imagens que foram carregadas na Adobe Experience Cloud para uso em atividades do Target.

Se você quer referenciar um URL de imagem pública diretamente em uma oferta ou código personalizado durante a criação da atividade, você deve implantar a imagem em seu próprio servidor web e usar seu próprio URL no código. Não há como obter o URL publicado de uma imagem carregada na Experience Cloud para consumir diretamente ou por fora de fluxos de trabalho de definição usando o Adobe Target. Esta funcionalidade não é permitida, de acordo com o contrato.

Note que o URL de armazenamento e os URLs finais de imagens publicadas do Scene7 são diferentes e você NÃO deve criar ofertas usando o link de imagens armazenadas pois a entrega não irá funcionar nesses casos. Você precisa usar a capacidade de ofertas de imagem conforme explicado em nossa documentação de ajuda.

Para integração com o Scene7, você precisa especificar algumas de suas informações do Scene7.

1. Clique em **[!UICONTROL Configuração]** &gt; **[!UICONTROL Configurações do Scene7]**.
1. Especifique as seguintes informações de conta do Scene7:

   **Região do Scene7:** a região de sua conta Scene7: América do Norte, Europa ou Ásia.

   **Pasta adhoc do Scene7:** o local do conteúdo que fica fora da pasta de destino e é carregado manualmente para o Scene7.

   **Endereço de email do Scene7:** o endereço de email usado para fazer logon no Scene7.

   **Senha do Scene7:** a senha usada para fazer logon no Scene7.
1. Clique em **[!UICONTROL Enviar]**.
