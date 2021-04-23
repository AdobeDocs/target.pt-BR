---
keywords: visual experience composer, vec, url padrão, enhanced experience composer, eec, conteúdo misto, instantâneos de experiência, janela de visualização móvel, css, seletores de css
description: Saiba como configurar o Adobe [!DNL Target] Visual Experience Composer (VEC) especificando suas configurações gerais, configuração de visor móvel e seletores de CSS.
title: Como configurar o Visual Experience Composer (VEC)?
feature: Administração e configuração
role: Administrator
exl-id: cf6c9ece-6745-477e-81ac-a3e9a9fddb09
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 50%

---

# Configurar o Visual Experience Composer

Configure o [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) especificando suas configurações gerais, configuração de visor móvel e seletores de CSS.

Para acessar a página de configuração do [!UICONTROL Visual Experience Composer], clique em **[!UICONTROL Administração]** > **[!UICONTROL Visual Experience Composer].**

>[!NOTE]
>
>Observe que as configurações nesta página se aplicam a toda a conta [!DNL Target].

![Página Configuração do Visual Experience Composer](/help/administrating-target/assets/vec.png)

## Configurações gerais

Você pode especificar configurações gerais para o Visual Experience Composer.

![Seção Configurações gerais](/help/administrating-target/assets/general-settings.png)

As seguintes configurações estão disponíveis:

### URL padrão

O URL padrão usado pelo [!UICONTROL Visual Experience Composer]. Essa é a página padrão, por exemplo sua página inicial, usada sempre que você configura uma experiência para cada atividade nova. Se você não definir um URL padrão, deverá inserir um URL para cada atividade ao criá-la.

### Ativar Enhanced Experience Composer  {#eec}

Permite a edição em sites no iFrame e sites com conteúdo misto. Alguns sites podem não ser compatíveis com a versão aprimorada. Desmarque essa opção para reverter para o [!UICONTROL Visual Experience Composer] original. A entrega de atividades nos sites não é afetada por essa escolha.

Para obter mais informações, consulte [Solução de problemas do Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

Você também pode ativar o [!UICONTROL Enhanced Experience Composer] no nível da atividade.

### Carregar conteúdo misto

Ative o conteúdo misto ao abrir um site usando o [!UICONTROL Enhanced Experience Composer] (EEC). Ativar essa opção evita a sobrecarga extra do carregamento de recursos estáticos pelos servidores proxy [!DNL Target].

Essa opção será útil se, por exemplo:

* Os cabeçalhos de Política de segurança de conteúdo (CSP) permitem carregar conteúdo misto sem o uso de servidores proxy com o EEC ativado.
* Seu site HTTP tem aumentado o tempo de carregamento no EEC, o que significa que o JavaScript, as imagens e assim por diante levam mais tempo para carregar por proxy.

### Gerar instantâneos de experiência no diagrama de fluxo de atividade

Quando os instantâneos de experiência estão ativados, miniaturas são geradas para as experiências no diagrama de fluxo de trabalho da atividade. A desativação de instantâneos pode resultar no desempenho mais rápido para alguns usuários.

## ![Selo Premium ](/help/assets/premium.png) Configuração de visor móvel

É possível adicionar dispositivos para usar ao visualizar experiências. Cada dispositivo está associado a um público-alvo.

![Seção Configuração da janela de visualização móvel](/help/administrating-target/assets/mobile-viewport-configuration.png)

Clique em **[!UICONTROL Adicionar]**, especifique um nome descritivo para a janela de visualização móvel, especifique a largura e a altura, selecione o sistema operacional desejado e clique em [!UICONTROL Salvar].

Para obter mais informações sobre como adicionar um visor móvel, consulte [Configuração de visor móvel](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md).

## Seletores de CSS {#css}

Especifique como o [!DNL Target] gera seletores de CSS.

![Seção Seletores de CSS](/help/administrating-target/assets/css-selectors.png)

Essas opções ajudam o [!DNL Target] a entender a estrutura do site a fim de gerar melhores seletores de CSS para a entrega de conteúdo. Por padrão, o [!DNL Target] gera seletores com base nas IDs de elemento na página. Se o seu site usar poucas IDs ou duplicar IDs em uma mesma página, o uso de classes pode ser uma opção melhor.

É possível escolher uma das seguintes opções:

### Usar IDs de elementos

Desmarque essa opção se uma mesma ID for usada para vários elementos ou se a ID do elemento puder ser alterada no carregamento da página.

### Usar classes de elementos

Por padrão, o [!DNL Target] usa somente IDs de elemento. No entanto, se a página tiver sido projetada para usar classes para identificar os elementos, como uma página criada com o [!DNL Adobe Experience Manager], também será necessário selecionar [!UICONTROL Usar classes de elementos].

>[!NOTE]
>
>Embora tudo tenha sido feito para garantir a precisão, esteja ciente de que o uso de classes pode resultar em erros. Se você não selecionar uma das opções, a precisão também será afetada. A ordem de precisão é IDs > classes > nenhuma opção. Sempre certifique-se de testar sua página para garantir que os seletores estão corretos.

É possível substituir essa configuração por atividade (clique no ícone de roda dentada [!UICONTROL Configurações] e selecione [!UICONTROL Seletores de CSS]). Isso é especialmente útil se você tiver vários sites configurados de forma diferente.

>[!NOTE]
>
>A substituição da configuração por atividade não está disponível nas atividades [!UICONTROL Automated Personalization] e [!UICONTROL Multivariate Testing].  Consulte [Seletores de elementos usados no Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/vec-selectors.md) para obter mais informações sobre os seletores.

## Vídeo de treinamento: Preferências da conta (7:33) ![Selo de visão geral](/help/assets/overview.png)

Este vídeo inclui informações sobre as preferências da conta.

* Descreva as configurações da conta disponíveis em [!DNL Target Standard]

>[!NOTE]
>
>A interface do usuário do menu [!DNL Target] [!UICONTROL Administration] (anteriormente [!UICONTROL Setup]) foi reprojetada para fornecer melhor desempenho, reduzir o tempo de manutenção necessário ao lançar novos recursos e melhorar a experiência do usuário no produto. As informações do vídeo a seguir são geralmente corretas; no entanto, as opções podem estar em locais um pouco diferentes. Os vídeos atualizados serão publicados em breve.

>[!VIDEO](https://video.tv.adobe.com/v/17379)
