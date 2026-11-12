---
keywords: visual experience composer;vec;url padrão;enhanced experience composer;eec;conteúdo misto;instantâneos da experiência;viewport móvel;css;seletores de css
description: Saiba como configurar o Visual Experience Composer (VEC) do Adobe [!DNL Target] especificando suas configurações gerais, configuração de visor móvel e seletores de CSS.
title: Como configurar o Visual Experience Composer (VEC)?
feature: Administration & Configuration
role: Admin
exl-id: cf6c9ece-6745-477e-81ac-a3e9a9fddb09
TQID: https://experienceleague.adobe.com/E1ck4-aG4txqaFLs3t3-8bN-BQIoY8stRASTRJfhZMY
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
subfeature_v2:
  - id: b1d5cd6a-4ed3-43f6-9a52-2721acea1129
    internal-label: Troubleshooting
  - id: c011fe9c-b94b-4a88-93d8-f2acece55112
    internal-label: Administration
  - id: fc9c2184-9102-403f-bd6c-0055021e4bea
    internal-label: Overview
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 553aa8fb523a62f72f0e2be7d7fd1b4eb663da6b
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 32%
---
# Configurar o Visual Experience Composer (VEC)

Use a guia **[!UICONTROL Visual Experience Composer]** em **[!UICONTROL Administração]** para definir padrões para toda a conta do [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC). Essas configurações se aplicam sempre que os autores criam ou visualizam experiências no VEC.

**Visão geral da configuração**

1. [Configurações gerais](#general-settings): URL padrão, Enhanced Experience Composer, conteúdo misto e instantâneos de experiência.
1. [Configuração de visor móvel](#mobile-viewport-configuration): visualize dispositivos para experiências responsivas (somente [Target Premium](/help/main/c-intro/intro.md#premium)).
1. [Seletores de CSS](#css): como o Target gera seletores para a entrega de conteúdo.

Para abrir a página de configuração, clique em **[!UICONTROL Administração]** > **[!UICONTROL Visual Experience Composer]**.

>[!NOTE]
>
>As configurações desta página se aplicam a toda a conta [!DNL Target].

## Configurações gerais {#general-settings}

Na seção **[!UICONTROL Configurações Gerais]**, configure os padrões usados ao abrir o VEC.

![Seção de Configurações Gerais](/help/main/administrating-target/assets/general-settings.png)

As seguintes configurações estão disponíveis:

* **URL padrão**

  O URL padrão usado pelo [!UICONTROL Visual Experience Composer]. Essa é a página padrão, por exemplo sua página inicial, usada sempre que você configura uma experiência para cada atividade nova. Se você não definir um URL padrão, deverá inserir um URL para cada atividade ao criá-la.

* **Habilitar o Enhanced Experience Composer**

  Permite a edição em sites no iFrame e sites com conteúdo misto. Alguns sites podem não ser compatíveis com a versão aprimorada. Desmarque esta opção para reverter para o [!UICONTROL Visual Experience Composer] original. A entrega de atividades nos sites não é afetada por essa escolha.

  Observe que o [!UICONTROL Enhanced Experience Composer] não é suportado no [!DNL Safari].

  Para obter mais informações, consulte [Solução de problemas do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

  Você também pode ativar o [!UICONTROL Enhanced Experience Composer] no nível da atividade. Consulte [Saiba como habilitar o Enhanced Experience Composer no nível da atividade](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md).

* **Carregar conteúdo misto**

  Habilite conteúdo misto ao abrir um site usando o [!UICONTROL Enhanced Experience Composer] (EEC). Habilitar essa opção evita a sobrecarga extra do carregamento de recursos estáticos por meio de [!DNL Target] servidores proxy.

  Essa opção é útil se, por exemplo:

  * Os cabeçalhos de Política de segurança de conteúdo (CSP) permitem carregar conteúdo misto sem usar servidores proxy com o EEC ativado.
  * Seu site HTTP enfrenta um tempo de carregamento maior no EEC, o que significa que o JavaScript, as imagens e assim por diante levam mais tempo para carregar por proxy.

* **Gerar instantâneos de experiência no diagrama de fluxo de atividades**

  Quando os instantâneos de experiência estão ativados, miniaturas são geradas para as experiências no diagrama de fluxo de trabalho da atividade. A desativação de instantâneos pode resultar no desempenho mais rápido para alguns usuários.

## Configuração do visor móvel {#mobile-viewport-configuration}

>[!NOTE]
>
>As configurações de **[!UICONTROL Configuração de Visor Móvel]** são um recurso do [Target Premium](/help/main/c-intro/intro.md#premium).

Adicionar dispositivos para usar ao visualizar experiências. Cada dispositivo está associado a um público-alvo.

![Seção de configuração de janela de visualização móvel](/help/main/administrating-target/assets/mobile-viewport-configuration.png)

Use as seguintes etapas para adicionar uma janela de visualização móvel:

1. Clique em **[!UICONTROL Adicionar]**.
1. Especifique um nome descritivo para a janela de visualização móvel, especifique a largura e a altura e selecione o sistema operacional desejado.
1. Clique em **[!UICONTROL Salvar]**.

Para obter detalhes de visualização e público-alvo, consulte [Saiba como usar visores móveis para experiências responsivas](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md).

## Seletores de CSS {#css}

Especifique como o [!DNL Target] gera seletores de CSS.

![Seção de Seletores de CSS](/help/main/administrating-target/assets/css-selectors.png)

Essas opções ajudam o [!DNL Target] a entender a estrutura do site a fim de gerar melhores seletores de CSS para a entrega de conteúdo. Por padrão, o [!DNL Target] gera seletores com base nas IDs de elemento na página. Se o seu site usar poucas IDs ou duplicar IDs em uma mesma página, o uso de classes pode ser uma opção melhor.

É possível escolher uma das seguintes opções:

* **Usar IDs de elemento**

  Desmarque essa opção se uma mesma ID for usada para vários elementos ou se a ID do elemento puder ser alterada no carregamento da página.

* **Usar classes de elementos**

  Por padrão, o [!DNL Target] usa somente IDs de elemento. No entanto, se a página tiver sido projetada para usar classes para identificar os elementos, como uma página criada com [!DNL Adobe Experience Manager], você também deverá selecionar **[!UICONTROL Usar classes de elementos]**. A precisão do seletor geralmente é mais alta ao usar IDs, mais baixa ao usar classes e mais baixa quando nenhuma opção é selecionada. Teste sua página no VEC para confirmar se os seletores estão corretos.

  É possível substituir essa configuração por atividade ao clicar no ícone de engrenagem **[!UICONTROL Configurações]** e selecionar **[!UICONTROL Seletores de CSS]**, útil quando sites na mesma conta são configurados de forma diferente. As substituições por atividade não estão disponíveis nas atividades **[!UICONTROL Automated Personalization]** ou **[!UICONTROL Multivariate Testing]**. Para comportamento do seletor e solução de problemas, consulte [Seletores de elementos usados no Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md).

## Vídeo de treinamento: Preferências da conta (7:33) ![Selo de visão geral](/help/main/assets/overview.png)

>[!BEGINSHADEBOX]

A interface do usuário do menu [!DNL Target] **[!UICONTROL Administração]** (antiga **[!UICONTROL Configuração]**) foi reprojetada para fornecer desempenho aprimorado, reduzir o tempo de manutenção necessário ao lançar novos recursos e melhorar a experiência do usuário em todo o produto. As informações do vídeo a seguir são corretas; no entanto, as opções podem estar em locais um pouco diferentes. Os vídeos atualizados serão publicados em breve.

>[!ENDSHADEBOX]

Este vídeo inclui informações sobre as preferências da conta.

* Descreva as configurações da conta disponíveis em [!DNL Target Standard]

>[!VIDEO](https://video.tv.adobe.com/v/17379)
