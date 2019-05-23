---
description: Defina as preferências da conta para configurar o Target Standard ou o Target Premium para funcionarem corretamente com a conta.
keywords: preferências de conta; preferências; detalhes do site; nome da mbox personalizada; solução da Experience Cloud usada para relatórios; Mostrar aumento estimado na receita; seletores de css; usar classes de elemento; URL padrão do Visual Experience Composer; Habilitar Enhanced Experience Composer; Gerar instantâneos de experiência; configuração de visor móvel; Vertical do setor; Filtrar critérios incompatíveis
seo-description: Defina as preferências da conta para configurar o Adobe Target Standard ou Target Premium para funcionar corretamente com sua conta.
seo-title: Preferências
solution: Target
subtopic: Introdução
title: Preferências
topic: Padrão
uuid: ed3904c8-533b-4b9c-a3a1-079c61b1bf2a
translation-type: tm+mt
source-git-commit: ecd707927629ff8bc3882a322f0744d93abced2c

---


# Preferências{#preferences}

Defina as preferências da conta para configurar [!DNL Target Standard] ou [!DNL Target Premium] a fim de funcionar corretamente com sua conta.

Para definir suas preferências de conta, clique em **[!UICONTROL Configuração]** &gt; **[!UICONTROL Preferências]**, configure-as conforme desejado e clique em **[!UICONTROL Enviar]**.

A ilustração a seguir mostra as configurações disponíveis na página [!UICONTROL Preferências da conta].

![Página Preferências](/help/administrating-target/r-target-account-preferences/assets/target-account-preferences.png)

>[!NOTE]
>
>Algumas dessas preferências estão disponíveis somente se você tiver [o Target Premium](/help/c-intro/intro.md#premium).

## Detalhes do site {#section_04A3340FC29B46978DB77058259F4EE0}

Especifique como o site foi configurado.

### Mbox global personalizada

Selecione o nome opcional da mbox que você está usando para entregar atividades do [!DNL Target]. Essa mbox global deve ficar vazia, o que significa que não tem nenhum conteúdo padrão. Salve essa configuração somente depois que a atualização [!DNL at.js] ou [!DNL mbox.js] o arquivo for instalado no site.

>[!CAUTION]
>
>A configuração incorreta dessa configuração pode resultar em uma interrupção das atividades existentes.

## Resultados e relatórios {#section_47C887AABD704A96BCD1C00BEABF4BCE}

Defina as opções que determinam quais dados são usados para os resultados e relatórios.

| Opção | Descrição |
|--- |--- |
| Solução da Experience Cloud usada para relatórios | Selecione a fonte de relatórios das suas atividades: o [!DNL Target] ou o Adobe Analytics. Também é possível optar por selecionar sua origem de relatórios por atividade. Considere as informações a seguir ao escolher sua origem de relatórios:<ul><li>Criação, ativação e desativação de atividades de [!UICONTROL Alocação automática], [!UICONTROL Direcionamento automático] e [!UICONTROL Personalização automatizada] (AP) são permitidas independentemente da fonte de relatórios selecionada. Esses tipos de atividades não são compatíveis quando você escolhe o [Adobe Analytics como origem de relatórios para o Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md). Mesmo que você especifique o Analytics como fonte de geração de relatórios, [!DNL Target] será usado como a fonte de relatórios para esses tipos de atividades.</li><li>Se a fonte de relatórios for definida aqui como Analytics, você não poderá ativar uma atividade que usa [!DNL Target] como fonte de relatórios (a fonte de relatórios é especificada como Target por atividade). Você deve alterar a origem de relatórios para Analytics na sua atividade ou alterar o mecanismo de relatórios para Selecionar por atividade em Configurar &gt; Preferências.</li><li>Se a origem de relatório for definida aqui para [!DNL Target], você não poderá ativar uma atividade que usa o Analytics como a origem de relatório. Você deve alterar a origem de relatórios para [!DNL Target] na sua atividade ou alterar a origem de relatório para Selecionar por atividade em Configurar &gt; Preferências.</li><li>Se a origem de relatório for definida aqui para Selecionar por atividade, você pode criar, ativar e desativar atividades compatíveis com a origem de relatório selecionada. Para obter uma matriz de atividades compatíveis, consulte [Adobe Analytics como origem de relatório para o Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T).</li><li>Quando você alternar do manual A/B para [!UICONTROL Alocação automática] ou [!UICONTROL Direcionamento automático], todas as métricas e públicos-alvo serão perdidos se a origem de relatórios da atividade manual A/B não for compatível nas atividades de [!UICONTROL Alocação automática] ou [!UICONTROL Direcionamento automático].</li></ul> |
| Mostrar aumento estimado na receita | Também é possível escolher mostrar o aumento estimado na receita se inserir um valor monetário para sua meta. [!DNL Target]O pode fazer uma estimativa do aumento de receita que você obterá se todos os usuários visualizarem a experiência vencedora. O recurso de aumento estimado está desativado por padrão.<br>Apenas usuários de Administração da Experience Cloud podem habilitar ou desabilitar esse recurso. Se uma estimativa de aumento for desabilitada, os campos correspondentes não aparecerão na interface. Desabilitar o recurso não resulta em perda de dados, inclusive os dados usados para as estimativas. As estimativas são baseadas em dados coletados independentemente de o recurso estar habilitado ou não.<br>Para obter informações detalhadas, consulte [Aumento estimado na receita](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md). |
| Ativar prioridades refinadas | Permitir entradas numéricas para prioridade variam de 0-999.<br>Dependendo das configurações, a interface do usuário e as opções de Prioridade variam. É possível usar as configurações herdadas de Baixo, Médio ou Alto, ou pode ativar as prioridades otimizadas de 0 a 999.<br>A prioridade é usada se várias atividades forem atribuídas para o mesmo local com o mesmo público-alvo. Se duas ou mais atividades forem atribuídas ao local, a atividade com a maior prioridade é exibida. |

## Seletores de CSS {#section_8155EDBF449E4198863235F94D1EA872}

Especifique como o [!DNL Target] gera seletores de CSS.

Essas opções ajudam o [!DNL Target] a entender a estrutura do site a fim de gerar melhores seletores de CSS para a entrega de conteúdo. Por padrão, o [!DNL Target] gera seletores com base nas IDs de elemento na página. Se o seu site usar poucas IDs ou duplicar IDs em uma mesma página, o uso de classes pode ser uma opção melhor.

É possível escolher uma das seguintes opções:

| Opção | Descrição |
|--- |--- |
| Usar IDs de elementos | Desmarque essa opção se uma mesma ID for usada para vários elementos ou se a ID do elemento puder ser alterada no carregamento da página. |
| Usar classes de elementos | Por padrão, o [!DNL Target] usa somente IDs de elemento. No entanto, se a página tiver sido projetada para usar classes para identificar os elementos, como uma página criada com o [!DNL Adobe Experience Manager], também será necessário selecionar [!UICONTROL Usar classes de elementos].<br>**Observação**: embora tudo tenha sido feito para garantir a precisão, esteja ciente de que o uso de classes pode resultar em erros. Se você não selecionar uma das opções, a precisão também será afetada. A ordem de precisão é IDs &gt; classes &gt; nenhuma opção. Sempre certifique-se de testar sua página para garantir que os seletores estão corretos.<br>É possível substituir essa configuração por atividade (clique no ícone de roda dentada [!UICONTROL Configurações] e selecione [!UICONTROL Seletores de CSS]). Isso é especialmente útil se você tiver vários sites configurados de forma diferente.<br>**Observação**: a substituição da configuração por atividade não está disponível nas atividades de [!UICONTROL Personalização automatizada] e [!UICONROL Testes multivariados]. Consulte [Seletores de elementos usados no Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/vec-selectors.md) para obter mais informações sobre os seletores. |

## Visual Experience Composer {#section_CD9BDD372CF54E678F88E8BA95757A5A}

| Opção | Descrição |
|--- |--- |
| URL padrão do Visual Experience Composer | O URL padrão usado pelo [!UICONTROL Visual Experience Composer]. Essa é a página padrão, por exemplo sua página inicial, usada sempre que você configura uma experiência para cada atividade nova. Se você não definir um URL padrão, deverá inserir um URL para cada atividade ao criá-la. |
| Ativar Enhanced Experience Composer | Permite a edição em sites no iFrame e sites com conteúdo misto. Alguns sites podem não ser compatíveis com a versão aprimorada. Desmarque essa opção para reverter para o Experience Composer original. A entrega de atividades nos sites não é afetada por essa escolha.<br>Para obter mais informações, consulte [Solução de problemas do Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).<br>**Observação**: você também pode ativar o Enhanced Experience Composer no nível da atividade. |
| Carregar conteúdo misto | Habilite conteúdo misto ao abrir um site usando o Enhanced Experience Composer. A habilitação dessa opção evita sobrecarga extra do carregamento de recursos estáticos pelos servidores proxy do Target. |
| Gerar instantâneos de experiências | Quando os instantâneos de experiência estão ativados, miniaturas são geradas para as experiências no diagrama de fluxo de trabalho da atividade. A desativação de instantâneos pode resultar no desempenho mais rápido para alguns usuários. |

## Configuração da janela de visualização móvel {#section_42176D062BCE4A28ADBB784CC4BEF84D}

É possível adicionar dispositivos para usar ao visualizar experiências. Cada dispositivo está associado a um público-alvo.

| Opção | Descrição |
|--- |--- |
| ![Selo Premium](/help/assets/premium.png) Adicionar novo | Clique em [!UICONTROL Adicionar novo], especifique um nome descritivo para a janela de visualização móvel, especifique a largura e a altura, selecione o sistema operacional desejado e clique em [!UICONTROL Salvar]. Para obter mais informações sobre como adicionar um visor móvel, consulte [Configuração de visor móvel](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md). |

## Vídeo de treinamento: preferências da conta (7:33)

Este vídeo inclui informações sobre as preferências da conta.

* Descreva as configurações da conta disponíveis em [!DNL Target Standard]

>[!VIDEO](https://video.tv.adobe.com/v/17379)