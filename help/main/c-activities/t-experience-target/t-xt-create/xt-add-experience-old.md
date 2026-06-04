---
keywords: criar experiência, experiência criar, prioridade, público-alvo, experiência, visual experience composer
description: Saiba como usar o [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) para criar e editar experiências em sua página da atividade de [!UICONTROL Direcionamento de experiência] (XT).
title: Como criar experiências em uma atividade de [!UICONTROL Direcionamento de experiência]?
feature: Experience Targeting
exl-id: ec3fcd93-5557-4f69-8f9c-4d00569188ad
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '962'
ht-degree: 32%

---

# Criar experiência em [!UICONTROL Direcionamento de experiência] (XT)

O [!UICONTROL Visual Experience Composer] (VEC) no [!DNL Adobe Target] fornece uma interface visual para editar as experiências em sua página da atividade de [!UICONTROL Direcionamento de experiência] (XT).

1. Selecione os elementos que deseja alterar e faça as alterações desejadas.

   Ao [criar uma atividade de [!UICONTROL Direcionamento de Experiência]](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md), a etapa um do fluxo de trabalho guiado de três etapas ([!UICONTROL Experiências]) exibe a [!UICONTROL Experiência A] padrão com um público-alvo de [!UICONTROL Todos os Visitantes].

   ![Público-alvo de todos os visitantes](/help/main/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   Todas as alterações feitas agora se aplicam à [!UICONTROL Experiência A]. Em uma etapa abaixo, você clica em **[!UICONTROL Adicionar segmentação por experiência]** para criar experiências adicionais.

   À medida que você passa o mouse sobre os elementos na página, eles são realçados. Qualquer elemento destacado pode ser alterado usando o VEC. Para ver uma lista de ações que podem ser executadas em um elemento para alterar a experiência, consulte [Opções do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   >[!NOTE]
   >
   >Por padrão, o VEC não permite alterações a elementos que contenham JavaScript, como banners giratórios. Você pode desativar o JavaScript para alterar esses elementos usando o VEC.

1. Para criar experiências adicionais, clique em **[!UICONTROL Adicionar direcionamento de experiência]**.

   ![Link Adicionar Direcionamento de experiência](/help/main/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   A caixa de diálogo [!UICONTROL Adicionar público-alvo] é exibida. Para direcionar uma experiência para um público-alvo, selecione-o antes de adicionar a experiência.

   A biblioteca de público-alvo contém públicos que foram definidos previamente, inclusive alguns comuns que são predefinidos como parte do [!DNL Target]. Você pode selecionar um público-alvo da biblioteca ou [criar um novo público-alvo](/help/main/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271).

   Além de selecionar um público-alvo existente, você pode combinar vários deles para criar públicos-alvo combinados ad hoc em vez de criar um novo. Para obter mais informações, consulte [Combinar vários públicos-alvo](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

   Ao criar um público-alvo, você pode selecionar um local e especificar parâmetros para esse local. Em [!UICONTROL Personalizado] ([!UICONTROL Criar público-alvo] > [!UICONTROL Personalizado]), selecione o local e especifique os parâmetros desejados.

   >[!NOTE]
   >
   >Os públicos-alvo são importados automaticamente em segundo plano quando você abre a lista de públicos-alvo e os públicos importados foram criados há mais de dez minutos.

1. Selecione um ou mais públicos para direcionar com a experiência e clique em **[!UICONTROL Concluído]**.

   ![Experiência B](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience-b.png)

   A Experiência B agora é exibida na ilustração anterior e essa experiência é direcionada ao público-alvo de visitantes dos EUA.

1. Selecione os elementos que deseja alterar para essa experiência e faça as alterações desejadas, conforme explicado na Etapa 1 acima.

1. Repita as etapas anteriores para criar experiências direcionadas adicionais, conforme necessário.

1. Clique em **[!UICONTROL Avançar]** quando terminar de criar as suas experiências.

   O diagrama da atividade é exibido:

   ![Diagrama de Direcionamento XT](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-new.png)

   >[!NOTE]
   >
   >Você pode fornecer uma imagem de uma fonte diferente da sua página principal (como uma imagem hospedada em `akamai.net` e entregue em `adobe.com`). As imagens hospedadas em outro lugar não são exibidas na miniatura da página mostrada no diagrama de fluxo.

1. (Condicional) Arraste e solte pares de público e experiência ao criar ou editar atividades de [!UICONTROL Direcionamento de experiência] para organizar os pares na ordem desejada.

   Os visitantes são avaliados quanto às experiências em ordem, de cima para baixo.

   ![Mover experiências](/help/main/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   [!UICONTROL O Direcionamento de experiência] presume que a ordem é importante. Se um visitante se enquadrar no primeiro par de público-alvo e experiência, a primeira experiência será entregue.

   Por exemplo, suponha que você não estivesse ciente de que a ordem é importante ao criar uma atividade de [!UICONTROL Direcionamento de experiência]. Mais tarde você percebe durante os testes que visitantes que você pensava que deveriam se qualificar para as experiências B ou C estão se qualificando para a experiência A. Isso pode ocorrer pois os públicos-alvo não são mutualmente exclusivos e não estão na ordem correta (por exemplo, experiência A = Estados Unidos, experiência B = São Francisco e experiência C = Califórnia). Nesse cenário, todos os usuários dos Estados Unidos se qualificam para a experiência A, mesmo se estiverem em São Francisco ou em outro lugar da Califórnia. É possível reordenar os pares de público-alvo e experiência do mais restritivo para o menos restritivo (São Francisco > Califórnia > Estados Unidos) sem recriar toda a atividade.

   Se você tiver um público-alvo de [!UICONTROL Todos os visitantes], certifique-se de que não seja o primeiro no diagrama. Uma experiência direcionada para &quot;[!UICONTROL Todos os visitantes]&quot; pode ser usada como a última experiência na atividade [!UICONTROL Direcionamento de experiência] para &quot;capturar&quot; todos os visitantes que não se enquadram em nenhuma outra experiência.

## Renomear ou editar uma experiência

Você pode clicar no ícone [!UICONTROL Editar] (as reticências verticais) em uma experiência de uma atividade [!UICONTROL Direcionamento de experiência] e escolher as seguintes opções, conforme necessário:

* [!UICONTROL Renomear]
* [!UICONTROL Editar]

![Opções Renomear e Editar](/help/main/c-activities/t-experience-target/t-xt-create/assets/experience_edit-new.png)

## Excluir uma experiência

Na página **[!UICONTROL Experiências]** (a primeira etapa do fluxo de trabalho guiado de três etapas), clique no ícone de reticências verticais > **[!UICONTROL Excluir]**.

![Excluir experiência](/help/main/c-activities/t-experience-target/t-xt-create/assets/delete-experience.png)

## Duplicar uma experiência

Você pode copiar uma experiência em uma atividade de [!UICONTROL Direcionamento de experiência] para fazer pequenas alterações nela sem ter que recriar toda a experiência.

Na página **[!UICONTROL Experiências]** (a primeira etapa do fluxo de trabalho guiado de três etapas), clique no ícone de reticências verticais > **[!UICONTROL Duplicar]**.

![Experiência duplicada](/help/main/c-activities/t-experience-target/t-xt-create/assets/duplicate_experience-new.png)

## Vídeos de treinamento:

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste artigo.

### De Teste A/B para [!UICONTROL Direcionamento de experiência]

Este vídeo descreve como elevar o teste A/B ao próximo nível com o [!UICONTROL Direcionamento de experiência] (XT).

* Descreva o fluxo de trabalho guiado de três etapas para configurar uma atividade de [!UICONTROL Direcionamento de experiência]
* Descreva como fornecer conteúdo específico de localização para públicos em diferentes áreas geográficas
* Descreve como reorganizar experiências para garantir que o conteúdo correto seja entregue ao público-alvo certo

>[!VIDEO](https://video.tv.adobe.com/v/22418/)

### Tipos de Atividades (9:03)

Este vídeo explica os tipos de atividade disponíveis no [!DNL Target]. [!UICONTROL Direcionamento de Experiência] discutido a partir de 5:15.

* Descreva os tipos de atividade incluídos no [!DNL Adobe Target]
* Selecione o tipo de atividade apropriado para atingir suas metas
* Descreva o fluxo de trabalho guiado em três etapas que se aplica a todos os tipos de atividade

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### Usando o [!UICONTROL Visual Experience Composer]

Este vídeo fornece informações sobre como usar as opções de [!UICONTROL Direcionamento de experiência] (VEC).

* Alterar o conteúdo de uma página
* Alterar o layout de uma página

>[!VIDEO](https://video.tv.adobe.com/v/17399)
