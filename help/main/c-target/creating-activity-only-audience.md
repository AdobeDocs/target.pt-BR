---
keywords: público-alvo, regras de público-alvo, criar público-alvo, criação de público-alvo, somente atividade, adhoc
description: Saiba como criar públicos-alvo somente atividade no Adobe [!DNL Target] que são para uso único.
title: Posso criar um público-alvo para usá-lo apenas uma vez?
feature: Audiences
exl-id: 5fe0507a-75d1-47bc-a941-8c8eeeaf3b75
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 52%

---

# Criar um público-alvo com apenas uma atividade

Criar públicos-alvo somente de atividades no [!DNL Adobe Target] fluxo de trabalho guiado de três etapas ao criar uma atividade. Esses públicos podem ser usados em outros locais na mesma atividade, mas não são armazenados na [!UICONTROL Biblioteca de público] para uso em outras atividades.

Públicos-alvo somente atividade proporcionam os seguintes benefícios:

* Públicos somente atividade são úteis para criar um público-alvo que você deseje usar somente uma vez e não deseje armazenar na [!UICONTROL Biblioteca de públicos-alvo]. Públicos somente atividade ajudam a impedir que o [!UICONTROL Biblioteca de públicos-alvo] não estar desorganizado com públicos que você nunca deseja usar novamente.
* Públicos somente atividade não estão visíveis na [!UICONTROL Biblioteca de públicos]. Como esses públicos-alvo não estão visíveis na biblioteca, eles são protegidos contra alterações indesejadas por outras pessoas em sua organização.

1. Ao criar uma [atividade](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), no **[!UICONTROL Direcionamento]** clique nos três elipses verticais e clique em **[!UICONTROL Substituir público-alvo]**.

   ![Resultado da etapa](assets/edit_audience.png)

1. Clique em **[!UICONTROL Criar público-alvo]**.

1. Clique em **[!UICONTROL Somente esta atividade]**.

   ![](assets/activity-only-aud.png)

1. Digite um nome de público-alvo descritivo.
1. Arraste e solte os atributos desejados no construtor de público-alvo.

   As regras possibilitam limitar o público-alvo a um subconjunto de visitantes do site. Cada tipo de regra tem seus próprios parâmetros. Consulte [Categorias para públicos](/help/main/c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D) para obter mais informações sobre como configurar cada tipo de regra de público-alvo.

1. Clique em **[!UICONTROL Concluído]**.

## Considerações

Tenha em mente as informações a seguir enquanto você trabalha com públicos somente-atividades:

* Você pode criar públicos-alvo somente atividade no [!UICONTROL Visual Experience Composer] (VEC) ou no [!UICONTROL Experience Composer baseado em formulário]. Esta funcionalidade substitui regras de refinamento em versões anteriores do [!DNL Target].
* É possível criar uma atividade para armazenar na [!UICONTROL Biblioteca de público-alvo] para reutilização em outras atividades, ou criar um público somente atividade. Depois de salvar o público-alvo, não é possível mudar o tipo de público-alvo.
* Os refinamentos das atividades existentes são migrados para públicos-alvo somente atividade.
* Públicos somente atividade terão status [!UICONTROL Utilizado] ou [!UICONTROL Não utilizado]. Públicos-alvo somente atividade não utilizados são exibidos até que a atividade seja salva. Se deixados não utilizados e você tentar salvar a atividade, uma mensagem de alerta é exibida informando que públicos-alvo somente atividade não utilizados serão excluídos.
* É possível ver os detalhes da definição de público-alvo em um cartão pop-up acessado do seletor de público-alvo sem abrir o público-alvo.
* Você pode [combinar vários públicos](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) para criar públicos somente atividade.
* Públicos somente atividade não suportam regras de exclusão.

   Você pode usar as seguintes alternativas para usar as regras de exclusão:

   * [Criar e usar um público-alvo da biblioteca](/help/main/c-target/c-audiences/create-audience.md) em vez de um público-alvo com apenas uma atividade.
   * [Combinar vários](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) (até 20) biblioteca de públicos-alvo em um público-alvo somente de atividades. Ao combinar públicos, as regras de inclusão e exclusão em públicos-alvo de bibliotecas individuais podem ser usadas mesmo quando o público-alvo combinado é salvo como um público-alvo somente de atividade.
