---
keywords: criar critérios personalizados, algoritmos, critérios, critérios de recomendações, csv, ftp, carregar csv
description: Saiba como carregar um arquivo CSV para personalizar suas recomendações no Adobe [!DNL Target] Recommendations.
title: Como fazer upload dos critérios personalizados no Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 32%

---

# Upload dos critérios personalizados

Carregue um arquivo CSV para personalizar suas recomendações no [!DNL Adobe Target].

Há várias maneiras de acessar a tela [!UICONTROL Create New Criteria]. Algumas opções de tela variam de acordo com o modo que você chegar na tela.

* Na tela da biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**, clique em **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**. Critérios que você criar aqui ficam disponíveis automaticamente para todas atividades do [!DNL Recommendations].
* Ao criar uma atividade do [!DNL Recommendations] usando o [!UICONTROL Visual Experience Composer] (VEC), você é imediatamente levado para a tela [!UICONTROL Select Criteria] depois de selecionar um elemento na sua página e clicar em [!UICONTROL Replace w/ Recommendations], [!UICONTROL Insert Recommendations Before] ou [!UICONTROL Insert Recommendations After]. Você pode selecionar um critério disponível ou clicar em **[!UICONTROL Create Criteria]**. Se você criar um novo critério, poderá salvá-lo para uso com outras atividades do [!DNL Recommendations]. Para obter mais informações, consulte [Criar uma atividade de Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* Quando você editar uma atividade [!DNL Recommendations], clique em uma caixa [!UICONTROL Recommendations Location] na sua página e selecione **[!UICONTROL Change Criteria]**. Na tela [!UICONTROL Select Criteria], clique em **[!UICONTROL Create Criteria]**. Você pode salvar seu novo critério para uso com outras atividades do [!DNL Recommendations].

As etapas a seguir consideram que você acesse a tela [!UICONTROL Create New Criteria] usando o primeiro método: a tela de biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Clique em **[!UICONTROL Create Criteria]**.

1. Preencha as informações na seção [Informações Básicas](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info).

   1. Na lista suspensa Tipo **[!UICONTROL Select Algorithm]**, selecione **[!UICONTROL Custom Criteria]**.

   1. Na lista suspensa **[!UICONTROL Algorithm]**, selecione **[!UICONTROL Custom Algorithm]**.

      >[!NOTE]
      >
      >As etapas anteriores fazem com que a seção [!UICONTROL Upload CSV] seja exibida na parte inferior da caixa de diálogo [!UICONTROL Create New Criteria].

1. (Condicional) Preencha as informações na seção [Conteúdo de Backup](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content).

1. (Condicional) Preencha as informações na seção [Regras de inclusão](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion).

1. Na seção **[!UICONTROL Upload CSV]**, selecione o **[!UICONTROL Location]** do arquivo CSV.

   ![Carregar seção CSV](assets/upload-csv.png)

   O arquivo CSV deve estar formatado corretamente para ser carregado com sucesso. Clique em **[!UICONTROL Download the CSV template]** para obter um arquivo CSV formatado corretamente.

   Você tem duas opções de local:

   * **FTP:** Para carregar seu arquivo CSV de um servidor FTP, selecione **[!UICONTROL FTP]** e insira as informações necessárias. Você pode usar SSL, que usa o protocolo FTPS para transferir seu arquivo CSV em segurança.
   * **URL:** Para carregar seu arquivo CSV de uma URL, selecione **[!UICONTROL URL]** e insira uma URL de feed.

1. Clique em **[!UICONTROL Save]**.

## Considerações

* As entidades com critérios personalizados (linhas) podem conter até 1.000 itens recomendados (colunas).

* As atualizações de critérios personalizados são &quot;cumulativas&quot; por padrão. Os novos pares de valor-chave especificados no arquivo de upload CSV substituem os pares existentes. Os pares de valores chave existentes que não têm chaves especificadas no upload de CSV ainda estarão disponíveis para entrega e expirarão em 31 dias a partir do momento em que forem carregados pela última vez, como parte do arquivo CSV.

  Entre em contato com o Atendimento ao Cliente para habilitar a configuração para descartar os resultados existentes que não estão inclusos upload CSV. Se essa configuração estiver ativada, somente as chaves presentes no arquivo de feed CSV personalizado estarão disponíveis para entrega. Essa configuração se aplica a todos os critérios personalizados.

* Os feeds de critérios personalizados atualizam uma vez a cada 24 horas.

  Você pode ver os status de carregamento e sincronização do seu critério personalizado na parte de baixo de cada cartão de critério na página [!UICONTROL Recommendations] > [!UICONTROL Criteria]. Você também pode ver o status na caixa de diálogo [!UICONTROL Edit] ao editar os critérios personalizados.

* O fluxo para um carregamento sem erros deve ser [!UICONTROL Scheduled] > [!UICONTROL Downloading Feed File] > [!UICONTROL Importing] > [!UICONTROL Successful].

* A seguir estão possíveis mensagens de erro que você poderá receber se [!DNL Target] encontrar um problema com o carregamento:

  | Mensagem de erro | Detalhes |
  |--- |--- |
  | Erro desconhecido | Indica um erro interno técnico. |
  | Erro de análise | Provavelmente há um problema com o formato do arquivo de feed. Corrija o formato do arquivo e salve novamente o algoritmo, o que reinicia o processo de download do arquivo. |
  | Servidor não encontrado | Forneça um IP ou nome de host que seja visível na internet. |
  | Erro de credenciais | Forneça um usuário e senha válidos para uma conta ativa no servidor. |
  | Diretório não encontrado | Forneça um diretório que exista no servidor. |
  | Arquivo não encontrado | Forneça o nome de um arquivo que exista no servidor dentro do diretório indicado. |

## Vídeo de treinamento: criar critérios no Recommendations (12:33) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo contém as seguintes informações (os detalhes sobre o upload de critérios personalizados começam às 11h43):

* Criar critérios
* Criar sequências de critérios
* Upload dos critérios personalizados

>[!VIDEO](https://video.tv.adobe.com/v/35374?quality=12&captions=por_br)
