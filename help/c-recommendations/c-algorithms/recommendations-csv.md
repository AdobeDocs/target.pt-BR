---
keywords: criar critérios personalizados, algoritmos, critérios, critérios de recomendações, csv, ftp, carregar csv
description: Faça upload de um CSV para personalizar suas recomendações.
title: Carregar critérios personalizados
feature: Recommendations
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 64%

---


# ![PREMIUM](/help/assets/premium.png) Carregar critérios personalizados{#upload-custom-criteria}

Faça upload de um CSV para personalizar suas recomendações.

Existem vários meios de alcançar a tela [!UICONTROL Criar novos critérios]. Algumas opções de tela variam de acordo com o modo que você chegar na tela.

* Na tela da biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Critérios]**, clique em **[!UICONTROL Criar Critérios]** > **[!UICONTROL Criar Critérios]**. Critérios que você criar aqui ficam disponíveis automaticamente para todas atividades do [!DNL Recommendations].
* Ao criar uma atividade [!DNL Recommendations] usando o [!UICONTROL Visual Experience Composer] (VEC), você será levado imediatamente para a tela [!UICONTROL Selecionar Critérios] depois de selecionar um elemento na página e clicar em [!UICONTROL Substituir por Recommendations], [!UICONTROL Inserir Recommendations Antes], ou [!UICONTROL Inserir Recommendations After]. Você pode selecionar um critério disponível ou clicar em **[!UICONTROL Criar critérios]**. Se você criar um novo critério, terá a opção de salvar seus critérios para uso com outras [!DNL Recommendations] atividades. Para obter mais informações, consulte [Criar uma atividade Recommendations](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* Ao editar uma [!DNL Recommendations] atividade, clique em uma caixa de [!UICONTROL Localização do Recommendations] em sua página e selecione **[!UICONTROL Alterar critérios]**. Na tela [!UICONTROL Selecionar critérios], clique em **[!UICONTROL Criar critérios]**. Você terá a opção de salvar seu novo critério para uso com outras atividades do [!DNL Recommendations].

As etapas a seguir pressupõem que você acesse a tela [!UICONTROL Criar novos critérios] usando o primeiro método: a tela da biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Critérios]**.

1. Clique em **[!UICONTROL Criar critérios]** > **[!UICONTROL Carregar critérios personalizados]**.

1. Preencha as informações na seção [Informações básicas](/help/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. Preencha as informações na seção [Fonte de Dados](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source).

1. Preencha as informações na seção [Content](/help/c-recommendations/c-algorithms/create-new-algorithm.md#content).

1. (Condicional) Preencha as informações na seção [Semelhança de conteúdo](/help/c-recommendations/c-algorithms/create-new-algorithm.md#similarity).

1. (Condicional) Preencha as informações na seção [Regras de inclusão](/help/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion).

1. (Condicional) Preencha as informações na seção [Ponderação do atributo](/help/c-recommendations/c-algorithms/create-new-algorithm.md#weighting).

1. Na seção **[!UICONTROL Carregar CSV]**, selecione **[!UICONTROL Localização]** do arquivo CSV.

   ![Carregar seção CSV](/help/c-recommendations/c-algorithms/assets/upload-csv.png)

   O arquivo CSV deve estar formatado corretamente para ser carregado com sucesso. Clique em **[!UICONTROL Baixar o modelo CSV]** para obter um arquivo CSV formatado corretamente.

   Você tem duas opções de local:

   * **FTP:** para carregar seu arquivo CSV de um servidor FTP, selecione **[!UICONTROL FTP]** e insira as informações necessárias. Você tem a opção de usar SSL, que usa o protocolo FTPS para transferir seu arquivo CSV em segurança.
   * **URL:** Para carregar seu arquivo CSV de um URL, selecione o  **[!UICONTROL URL]** e insira um URL de feed.

1. Clique em **[!UICONTROL Salvar]**.

   >[!NOTE]
   >
   >As entidades com critérios personalizados (linhas) podem conter até 1.000 itens recomendados (colunas).

As atualizações de critérios personalizados são &quot;cumulativas&quot; por padrão. Os novos pares de valor-chave especificados no arquivo de upload CSV substituem os pares existentes. Os pares de valores chave existentes que não têm teclas especificadas no upload de CSV ainda estarão disponíveis para entrega e expirarão em 31 dias a partir do momento em que forem carregados pela última vez, como parte do arquivo CSV.

Entre em contato com o Atendimento ao Cliente para habilitar a configuração para descartar os resultados existentes que não estão inclusos upload CSV. Se essa configuração estiver habilitada, somente as chaves presentes no arquivo de feed CSV personalizado estarão disponíveis para entrega. Essa configuração se aplica a todos os critérios personalizados.

Os feeds de critérios personalizados atualizam uma vez a cada 24 horas.

você pode ver os status de carregamento e sincronização do seu critério personalizado na parte de baixo de cada cartão de critério na página Recommendations > Critérios. Você também pode ver o status na caixa de diálogo Editar ao editar critérios personalizados.

O fluxo para um carregamento sem erros deve ser Agendado > Baixando arquivo de feed > Importando > Sucesso.

A seguir estão possíveis mensagens de erro que você pode receber se [!DNL Target] encontrar um problema com o upload:

| Mensagem de erro | Detalhes |
|--- |--- |
| Erro desconhecido | Indica um erro interno técnico. |
| Erro de análise | Provavelmente há um problema com o formato do arquivo de feed. Corrija o formato do arquivo e salve o algoritmo novamente, o que irá reiniciar o processo de download do arquivo. |
| Servidor não encontrado | Forneça um IP ou nome de host que seja visível na internet. |
| Erro de credenciais | Forneça um usuário e senha válidos para uma conta ativa no servidor. |
| Diretório não encontrado | Forneça um diretório que exista no servidor. |
| Arquivo não encontrado | Forneça o nome de um arquivo que exista no servidor dentro do diretório indicado. |

## Vídeo de treinamento: criar critérios no Recommendations (12:33)  ![Crachá do tutorial](/help/assets/tutorial.png)

Este vídeo contém as seguintes informações (os detalhes sobre como fazer upload de critérios personalizados começam às 11:43):

* Criar critérios
* Criar sequências de critérios
* Upload dos critérios personalizados

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)