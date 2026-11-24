---
keywords: criar critérios personalizados;algoritmos;critérios;critérios de recomendações;csv;ftp;sftp;carregar csv
description: Saiba como carregar um arquivo CSV para personalizar recomendações no Adobe [!DNL Target] Recommendations.
title: Upload dos critérios personalizados
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
TQID: 'https://experienceleague.adobe.com/8gSKOQxHGB5TPe6vdhjgy5sAFxN8O7dodITo7wgrR50'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 14%
---
# Upload dos critérios personalizados {#upload-custom-criteria}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba como carregar um arquivo CSV com recomendações para criar critérios personalizados em [!DNL Adobe Target Recommendations].

>[!ENDSHADEBOX]

Os critérios personalizados usam um arquivo CSV de recomendações que é carregado para [!DNL Target]. Isso permite que as recomendações computadas fora de [!DNL Target] sejam entregues em [!DNL Recommendations] atividades. Para obter mais informações sobre como os critérios personalizados funcionam, consulte [A ciência por trás dos algoritmos de recomendações do Target](/help/main/c-recommendations/c-algorithms/recommendations-algorithms.md).

Critérios personalizados são criados a partir da tela **[!UICONTROL Criar novos critérios]**. Para saber como acessar esta tela, consulte [Acessar a tela Criar Novo Critério](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#access-create-criteria). As etapas a seguir começam na tela da biblioteca **[!UICONTROL Recomendações]** > **[!UICONTROL Critérios]**.

1. Clique em **[!UICONTROL Recomendações]** > **[!UICONTROL Critérios]**.

1. Clique em **[!UICONTROL Criar Critério]** > **[!UICONTROL Criar Critério]**.

   ![Página de Critérios com o menu Criar critérios aberto, mostrando Criar critérios e Criar sequência de critérios](../assets/criteria_create_1.png)

1. Preencha as informações na seção [Informações Básicas](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. Na lista suspensa **[!UICONTROL Selecionar tipo de algoritmo]**, selecione **[!UICONTROL Critérios personalizados]**. Na lista suspensa **[!UICONTROL Algoritmo]**, selecione **[!UICONTROL Algoritmo personalizado]**.

   ![Seção de Algoritmo de Recomendações com Critérios Personalizados como o Tipo de Algoritmo e Algoritmo Personalizado como o Algoritmo](../assets/criteria_create_9.png)

1. (Condicional) Preencha as informações nas seções [Conteúdo de Backup](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content) e [Regras de Inclusão](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion).

1. Na seção **[!UICONTROL Carregar CSV]**, selecione o **[!UICONTROL Local]** do arquivo CSV.

   O arquivo CSV deve estar formatado corretamente para ser carregado com sucesso. Para obter um arquivo CSV formatado corretamente, clique em **[!UICONTROL Baixar o modelo CSV]**.

   As seguintes opções de local estão disponíveis:

   * **FTP**: para carregar o arquivo CSV de um servidor FTP, selecione **[!UICONTROL FTP]** e insira as informações necessárias. Pode-se usar o SSL, que usa o protocolo FTPS para transferir o arquivo CSV com segurança.

   * **SFTP**: para carregar o arquivo CSV de um servidor SFTP, selecione **[!UICONTROL SFTP]** e digite o nome do host ou o endereço IP, a porta (padrão 22), o nome de usuário, uma senha e/ou a chave privada, o diretório e o nome do arquivo SSH. Para obter detalhes, consulte [Configurações compatíveis do servidor SFTP](/help/main/c-recommendations/c-products/feeds.md#steps).

     O SFTP não altera o formato CSV de critérios personalizados. Use o formato `# Key,Recommendation_1,...`. Um arquivo CSV no formato de um tipo de feed diferente causa falha na importação.

   * **URL**: para carregar o arquivo CSV de uma URL, selecione **[!UICONTROL URL]** e insira uma URL de feed.

     ![Faça upload da seção CSV com as opções de Local FTP, SFTP e URL realçadas e SFTP selecionado](../assets/criteria_create_10.png)

1. Clique em **[!UICONTROL Criar]**.

## Considerações

* As entidades com critérios personalizados (linhas) podem conter até 1.000 itens recomendados (colunas).

* As atualizações de critérios personalizados são &quot;cumulativas&quot; por padrão. Os novos pares de valor-chave no arquivo de upload CSV substituem os pares existentes. Os pares de valores chave existentes cujas chaves não estão no upload de CSV permanecem disponíveis para entrega e expiram 31 dias após terem sido carregados pela última vez como parte do arquivo CSV.

  Para descartar os resultados existentes que não são incluídos no próximo upload de CSV, entre em contato com o Atendimento ao cliente para ativar a configuração correspondente. Quando essa configuração é ativada, somente as chaves presentes no arquivo de feed CSV personalizado estão disponíveis para entrega. Essa configuração se aplica a todos os critérios personalizados.

* Os feeds de critérios personalizados atualizam uma vez a cada 24 horas.

  O status de carregamento e sincronização de cada carregamento de critério personalizado é exibido na página **[!UICONTROL Recommendations]** > **[!UICONTROL Critérios]**. O status também é exibido na caixa de diálogo **[!UICONTROL Editar]** quando critérios personalizados são editados.

* O fluxo para um carregamento sem erros é **[!UICONTROL Agendado]** > **[!UICONTROL Baixando Arquivo de Feed]** > **[!UICONTROL Importando]** > **[!UICONTROL Com Êxito]**.

* Se [!DNL Target] encontrar um problema com o carregamento, as seguintes mensagens de erro serão possíveis:

  | Mensagem de erro | Detalhes |
  |--- |--- |
  | Erro desconhecido | Indica um erro interno técnico. |
  | Erro de análise | Provavelmente há um problema com o formato do arquivo de feed. Corrija o formato do arquivo e salve novamente o algoritmo, o que reinicia o processo de download do arquivo. |
  | Servidor não encontrado | Forneça um IP ou nome de host visível na Internet. |
  | Erro de credenciais | Forneça um usuário e senha válidos para uma conta ativa no servidor. |
  | Diretório não encontrado | Forneça um diretório que exista no servidor. |
  | Arquivo não encontrado | Forneça o nome de um arquivo que existe no servidor no diretório especificado. |
