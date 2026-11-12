---
keywords: scene7;dynamic media classic;gerenciamento de ativos digitais;ativos;dam;biblioteca de conteúdo;trocar imagem
description: Conecte o Adobe Target ao Adobe Dynamic Media Classic (Scene7) para que os autores possam usar ofertas de imagens e trocar imagens de ativos da Experience Cloud em atividades do.
landing-page-description: Configure a configuração do Scene7 em Administração para ativar ofertas de imagens, fluxos de trabalho do DAM da biblioteca de conteúdo e ações de imagem de troca no VEC e no Experience Composer baseado em formulário.
short-description: Configure a configuração do Scene7 em Administração para ativar ofertas de imagens, fluxos de trabalho do DAM da biblioteca de conteúdo e ações de imagem de troca no VEC e no Experience Composer baseado em formulário.
title: Como configurar a integração do Dynamic Media Classic (Scene7)?
feature: Administration & Configuration
role: Admin
exl-id: 315670ca-a4d1-4808-b3ec-f2ac195c281a
TQID: 'https://experienceleague.adobe.com/LKbjwlGIxrgaU-2i6Ddn1wi-VjsSmpQPAxYkFHRNOYQ'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: da3860b0-d637-47df-bef0-273751180266
    internal-label: Digital asset management
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 553aa8fb523a62f72f0e2be7d7fd1b4eb663da6b
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 5%
---
# Configurar o Dynamic Media Classic (Scene7)

Use a guia **[!UICONTROL Configuração do Scene7]** em **[!UICONTROL Administração]** para conectar [!DNL Adobe Target] a [!DNL Adobe Dynamic Media Classic] (anteriormente [!DNL Scene7]). A integração traz o Gerenciamento de ativos digitais (DAM) para a [!UICONTROL Biblioteca de conteúdo] e habilita os fluxos de trabalho de troca de imagem nas atividades.

Para saber como essa guia se encaixa com outras tarefas de administração, consulte [Como Administrar o Target?](/help/main/administrating-target/administrating-target.md). Para localizar **[!UICONTROL Administração]** na interface, consulte [Entender a [!DNL Target] IU](/help/main/c-intro/understand-the-target-ui.md).

**Visão geral**

1. [O que a integração habilita](#what-it-enables): ofertas de imagem, imagens de troca e ativos qualificados.
1. [Conta e credenciais](#account-and-credentials): contas [!DNL Dynamic Media] existentes e tipos de contas com suporte.
1. [Diretrizes de uso](#usage-guidelines): URLs, entrega e o que não é suportado.
1. [Configurar o Scene7 no Destino](#configure-scene7): configurações de entrada e região.

{{permissions-update}}

## O que a integração permite {#what-it-enables}

Quando a **[!UICONTROL Configuração do Scene7]** estiver definida, os autores poderão usar imagens carregadas na pasta de ativos do [!DNL Adobe Experience Cloud] em atividades do [!DNL Target]. A opção **[!UICONTROL Trocar oferta de imagem]** aparece no fluxo de trabalho da atividade, incluindo no [Visual Experience Composer e no Experience Composer baseado em formulário](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). Para obter o comportamento de troca no VEC, consulte [opções do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

Se esta configuração não estiver definida, a **[!UICONTROL Oferta de troca de imagem]** não estará disponível durante a criação da atividade.

A integração do fornece ativos que fazem parte das atividades da pasta de ativos da Experience Cloud. Ele **não** expõe todos os ativos em [!DNL Dynamic Media Classic] para uso em atividades [!DNL Target].

Após a configuração, gerencie as ofertas de imagem na biblioteca [!UICONTROL Ofertas]. Consulte [Gerenciar conteúdo](/help/main/c-experiences/c-manage-content/manage-content.md).

## Conta e credenciais {#account-and-credentials}

Se você já tiver uma conta [!DNL Dynamic Media], insira essas credenciais na página **[!UICONTROL Configuração do Scene7]**.

A Adobe não provisiona mais contas [!DNL Dynamic Media Classic] de uso restrito e sem encargos para novos clientes [!DNL Target] ou novos usuários. Se sua organização já tiver credenciais de entrada para essa integração, elas continuarão funcionando. Para dúvidas sobre a conta, contate o representante do [!DNL Adobe].

## Diretrizes de uso {#usage-guidelines}

Lembre-se das seguintes restrições ao usar imagens com essa integração:

* **Ofertas de imagem, não URLs de armazenamento.** [!DNL Dynamic Media] URLs de armazenamento e URLs de entrega publicadas são diferentes. Não crie ofertas a partir de links de armazenamento; falha no delivery. Em vez disso, use [ofertas de imagem](/help/main/c-experiences/c-manage-content/manage-content.md) e fluxos de trabalho de imagem de troca.
* **URLs públicas no código personalizado.** Para referenciar um URL de imagem pública diretamente em uma oferta ou código personalizado, hospede a imagem em seus próprios servidores da Web e use esse URL. Não é possível obter uma URL publicada para uma imagem carregada pela Experience Cloud para uso fora dos fluxos de trabalho de direcionamento de [!DNL Target]; esse uso não é permitido por contrato.
* **Ativos qualificados.** Somente ativos carregados para a pasta de ativos da Experience Cloud (e fluxos de trabalho compatíveis com essa integração) estão no escopo, não no catálogo [!DNL Dynamic Media Classic] completo.

## Configurar o Scene7 no Target {#configure-scene7}

Use as etapas a seguir para conectar [!DNL Dynamic Media Classic] ([!DNL Scene7]):

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Configuração do Scene7]**.
1. Digite as informações da sua conta do [!DNL Dynamic Media Classic]:

   | Campo | Descrição |
   | --- | --- |
   | **Região** | Região da sua conta do [!DNL Dynamic Media]: América do Norte, Europa ou Ásia. |
   | **Pasta adhoc** | Local do conteúdo fora da pasta de Destino que você carrega manualmente para [!DNL Dynamic Media]. |
   | **Endereço de email** | Endereço de email usado para entrar no [!DNL Dynamic Media Classic] ([!DNL Scene7]). |
   | **Senha** | Senha usada para entrar no [!DNL Dynamic Media Classic] ([!DNL Scene7]). |

   ![Campos de configuração do Scene7](/help/main/administrating-target/assets/scene7-1.png)

1. Clique em **[!UICONTROL Enviar]**.
