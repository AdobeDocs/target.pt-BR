---
description: Crie públicos-alvo somente de atividades dentro do fluxo de trabalho orientado de três etapas ao criar uma atividade. Esses públicos-alvo podem ser usados em outros locais na mesma atividade, mas não são armazenados na Biblioteca de público-alvo para uso em outras atividades.
keywords: público-alvo, regras de público-alvo, criar público-alvo, criação de público-alvo, somente atividade, adhoc
seo-description: Crie públicos-alvo somente de atividades dentro do fluxo de trabalho orientado de três etapas ao criar uma atividade. Esses públicos-alvo podem ser usados em outros locais na mesma atividade, mas não são armazenados na Biblioteca de público-alvo para uso em outras atividades.
seo-title: Criar um público-alvo com apenas uma atividade
solution: Target
title: Criar um público-alvo com apenas uma atividade
topic: Advanced,Standard,Classic
uuid: 3d0898d0-96e8-4bc9-86bd-3ae39db0e74d
translation-type: tm+mt
source-git-commit: a419672c3e7acffbe5ffea224951cf54bf53e584

---


# Criar um público-alvo com apenas uma atividade{#create-an-activity-only-audience}

Crie públicos-alvo somente de atividades dentro do fluxo de trabalho orientado de três etapas ao criar uma atividade. Esses públicos-alvo podem ser usados em outros locais na mesma atividade, mas não são armazenados na Biblioteca de público-alvo para uso em outras atividades.

Públicos-alvo somente atividade proporcionam os seguintes benefícios:

* Públicos somente atividade são úteis para criar um público-alvo que você deseje usar somente uma vez e não deseje armazenar na Biblioteca de público-alvo. Isso evita que a Biblioteca de público-alvo seja desorganizada com públicos-alvo que você nunca desejará utilizará novamente.
* Públicos-alvo somente atividade não estão visíveis na Biblioteca de público-alvo. Por conta disso, elas são protegidas contra alterações indesejada por outros em sua organização.

## Criar um público-alvo com apenas uma atividade

1. Durante a criação de uma atividade, na caixa **[!UICONTROL Público-alvo]**, clique no ícone **[!UICONTROL Editar]** (três elipses verticais) e, em seguida, clique em **[!UICONTROL Substituir público-alvo]**.

   ![](assets/replace_audiience.png)

1. Na página Escolher público-alvo, clique em **[!UICONTROL Público-alvo somente atividade]**.

   ![](assets/activity-only-aud.png)

1. Clique em **[!UICONTROL Criar público-alvo]**.
1. Digite um nome de público-alvo descritivo.
1. Clique em **[!UICONTROL + Adicionar regra]**.

   As regras possibilitam a limitação do seu público-alvo a um subconjunto dos visitantes do seu site.

1. Selecione um tipo de regra.

   Cada tipo de regra tem seus próprios parâmetros. Consulte [Categorias para públicos-alvo](../c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D) para mais informações sobre a configuração de cada tipo de regra de público-alvo.

1. Defina os parâmetros da regra.
1. Clique em **[!UICONTROL Salvar]**.

## Considerações

Tenha em mente as informações a seguir enquanto você trabalha com públicos somente-atividades:

* É possível criar públicos-alvo somente atividade no Visual Experience Composer ou no Experience Composer baseado em formulário. Esta funcionalidade substitui regras de refinamento em versões anteriores do Target.
* É possível criar uma atividade para armazenar na Biblioteca de público-alvo para reutilização em outras atividades, ou criar um público-alvo somente-atividade. Depois de salvar o público-alvo, não é possível mudar o tipo de público-alvo.
* Os refinamentos das atividades existentes são migrados para públicos-alvo somente atividade.
* Públicos-alvo somente atividade terão status Utilizado ou Não utilizado. Públicos-alvo somente atividade não utilizados são exibidos até que a atividade seja salva. Se deixados não utilizados e você tentar salvar a atividade, uma mensagem de alerta é exibida informando que públicos-alvo somente atividade não utilizados serão excluídos.
* É possível ver os detalhes da definição de público-alvo em um cartão pop-up acessado do seletor de público-alvo sem abrir o público-alvo.
* Você pode [combinar vários públicos](../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) para criar públicos somente atividade.

