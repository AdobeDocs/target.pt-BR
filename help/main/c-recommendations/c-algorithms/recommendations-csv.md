---
keywords: criar critérios personalizados, algoritmos, critérios, critérios de recomendações, csv, ftp, carregar csv
description: Saiba como carregar um arquivo CSV para personalizar suas recomendações no Adobe [!DNL Target] Recommendations.
title: Como faço para carregar critérios personalizados no  [!DNL Recommendations]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
TQID: https://experienceleague.adobe.com/8gSKOQxHGB5TPe6vdhjgy5sAFxN8O7dodITo7wgrR50
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 16fb7a1902ea76cab56a93fa141a32a3c6bc4467
workflow-type: tm+mt
source-wordcount: 696
ht-degree: 32%

---

# Upload dos critérios personalizados

Carregue um arquivo CSV para personalizar suas recomendações no [!DNL Adobe Target].

Existem vários meios de alcançar a tela [!UICONTROL Criar novos critérios]. Algumas opções de tela variam de acordo com o modo que você chegar na tela.

* Na tela da biblioteca **[!UICONTROL Recomendações]** > **[!UICONTROL Critérios]**, clique em **[!UICONTROL Criar Critérios]** > **[!UICONTROL Criar Critérios]**. Critérios que você criar aqui ficam disponíveis automaticamente para todas atividades do [!DNL Recommendations].
* Quando você está criando uma atividade do [!DNL Recommendations] usando o [!UICONTROL Visual Experience Composer] (VEC), é imediatamente levado à tela [!UICONTROL Critérios de seleção] depois de selecionar um elemento na sua página e clicar em [!UICONTROL Substituir com o Recommendations], [!UICONTROL Inserir Recommendations antes] ou [!UICONTROL Inserir Recommendations depois de]. Você pode selecionar um critério disponível ou clicar em **[!UICONTROL Criar critério]**. Se você criar um novo critério, poderá salvá-lo para uso com outras atividades do [!DNL Recommendations]. Para obter mais informações, consulte [Criar uma atividade do Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* Quando você editar uma atividade de [!DNL Recommendations], clique em uma caixa de [!UICONTROL Localização das recomendações] na sua página e selecione **[!UICONTROL Alterar critérios]**. Na tela [!UICONTROL Selecionar critério], clique em **[!UICONTROL Criar critério]**. Você pode salvar seu novo critério para uso com outras atividades do [!DNL Recommendations].

As etapas a seguir pressupõem que você acesse a tela [!UICONTROL Criar Novo Critério] usando o primeiro método: a tela de biblioteca **[!UICONTROL Recomendações]** > **[!UICONTROL Critérios]**.

1. Clique em **[!UICONTROL Recomendações]** > **[!UICONTROL Critérios]**.

1. Clique em **[!UICONTROL Criar Critério]** > **[!UICONTROL Criar Critério]**.

1. Preencha as informações na seção [Informações Básicas](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. Na lista suspensa **[!UICONTROL Selecionar tipo de algoritmo]**, selecione **[!UICONTROL Critérios personalizados]**.

1. Na lista suspensa **[!UICONTROL Algoritmo]**, selecione **[!UICONTROL Algoritmo personalizado]**.

   >[!NOTE]
   >
   >As etapas anteriores fazem com que a seção [!UICONTROL Carregar CSV] seja exibida na parte inferior da caixa de diálogo [!UICONTROL Criar Critérios].

1. (Condicional) Preencha as informações na seção [Conteúdo de Backup](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content).

1. (Condicional) Preencha as informações na seção [Regras de inclusão](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion).

1. Na seção **[!UICONTROL Carregar CSV]**, selecione o **[!UICONTROL Local]** do arquivo CSV.

   O arquivo CSV deve estar formatado corretamente para ser carregado com sucesso. Clique em **[!UICONTROL Baixar o modelo CSV]** para obter um arquivo CSV formatado corretamente.

   Você tem duas opções de local:

   * **FTP:** Para carregar seu arquivo CSV de um servidor FTP, selecione **[!UICONTROL FTP]** e insira as informações necessárias. Você pode usar SSL, que usa o protocolo FTPS para transferir seu arquivo CSV em segurança.

   * **URL:** Para carregar seu arquivo CSV de uma URL, selecione **[!UICONTROL URL]** e insira uma URL de feed.

1. Clique em **[!UICONTROL Criar]**.

## Considerações

* As entidades com critérios personalizados (linhas) podem conter até 1.000 itens recomendados (colunas).

* As atualizações de critérios personalizados são &quot;cumulativas&quot; por padrão. Os novos pares de valor-chave especificados no arquivo de upload CSV substituem os pares existentes. Os pares de valores chave existentes que não têm chaves especificadas no upload de CSV ainda estarão disponíveis para entrega e expirarão em 31 dias a partir do momento em que forem carregados pela última vez, como parte do arquivo CSV.

  Entre em contato com o Atendimento ao Cliente para habilitar a configuração para descartar os resultados existentes que não estão inclusos upload CSV. Se essa configuração estiver ativada, somente as chaves presentes no arquivo de feed CSV personalizado estarão disponíveis para entrega. Essa configuração se aplica a todos os critérios personalizados.

* Os feeds de critérios personalizados atualizam uma vez a cada 24 horas.

  Você pode ver os status de carregamento e sincronização do seu critério personalizado na página [!UICONTROL Recomendações] > [!UICONTROL Critérios]. Você também pode ver o status na caixa de diálogo [!UICONTROL Editar] ao editar critérios personalizados.

* O fluxo para um carregamento sem erros deve ser [!UICONTROL Agendado] > [!UICONTROL Baixando Arquivo de Feed] > [!UICONTROL Importando] > [!UICONTROL Com Êxito].

* A seguir estão possíveis mensagens de erro que você poderá receber se [!DNL Target] encontrar um problema com o carregamento:

  | Mensagem de erro | Detalhes |
  |--- |--- |
  | Erro desconhecido | Indica um erro interno técnico. |
  | Erro de análise | Provavelmente há um problema com o formato do arquivo de feed. Corrija o formato do arquivo e salve novamente o algoritmo, o que reinicia o processo de download do arquivo. |
  | Servidor não encontrado | Forneça um IP ou nome de host que seja visível na internet. |
  | Erro de credenciais | Forneça um usuário e senha válidos para uma conta ativa no servidor. |
  | Diretório não encontrado | Forneça um diretório que exista no servidor. |
  | Arquivo não encontrado | Forneça o nome de um arquivo que exista no servidor dentro do diretório indicado. |
