---
keywords: criar critérios personalizados, algoritmos, critérios, critérios de recomendações, csv, ftp, carregar csv
description: Saiba como fazer upload de um arquivo CSV para personalizar suas recomendações no Adobe [!DNL Target] Recommendations.
title: Como faço o upload de critérios personalizados no Recommendations?
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 39%

---

# ![PREMIUM](/help/main/assets/premium.png) Carregar critérios personalizados

Faça upload de um arquivo CSV para personalizar suas recomendações em [!DNL Adobe Target].

Existem vários meios de alcançar a tela [!UICONTROL Criar novos critérios]. Algumas opções de tela variam de acordo com o modo que você chegar na tela.

* No **[!UICONTROL Recommendations]** > **[!UICONTROL Critérios]** tela biblioteca, clique em **[!UICONTROL Criar critérios]** > **[!UICONTROL Criar critérios]**. Critérios que você criar aqui ficam disponíveis automaticamente para todas atividades do [!DNL Recommendations].
* Ao criar um [!DNL Recommendations] atividade usando a [!UICONTROL Visual Experience Composer] (VEC), é imediatamente levado ao [!UICONTROL Selecionar critérios] depois de selecionar um elemento na página e clicar em [!UICONTROL Substituir por Recommendations], [!UICONTROL Inserir o Recommendations antes de]ou [!UICONTROL Inserir o Recommendations depois de]. Você pode selecionar um critério disponível ou clicar em **[!UICONTROL Criar critérios]**. Se você criar um novo critério, poderá salvar seu critério para uso com outros [!DNL Recommendations] atividades. Para obter mais informações, consulte [Criar uma atividade do Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* Ao editar uma [!DNL Recommendations] atividade, clique em uma caixa de [!UICONTROL Localização do Recommendations] em sua página e selecione **[!UICONTROL Alterar critérios]**. No [!UICONTROL Selecionar critérios] , clique em **[!UICONTROL Criar critérios]**. Você pode salvar seu novo critério para uso com outros [!DNL Recommendations] atividades.

As etapas a seguir pressupõem que você acesse a variável [!UICONTROL Criar novos critérios] usando o primeiro método: o **[!UICONTROL Recommendations]** > **[!UICONTROL Critérios]** tela da biblioteca.

1. Clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Critérios]**.

1. Clique em **[!UICONTROL Criar critério]**.

1. Preencha as informações na [Informações básicas](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info) seção.

   1. No **[!UICONTROL Selecionar algoritmo]** Digite a lista suspensa, selecione **[!UICONTROL Critérios personalizados]**.

   1. No **[!UICONTROL Algoritmo]** , selecione **[!UICONTROL Algoritmo personalizado]**.

      >[!NOTE]
      >
      >As etapas anteriores causam a [!UICONTROL Fazer upload de CSV] seção a ser exibida na parte inferior da [!UICONTROL Criar novos critérios] caixa de diálogo.

1. (Condicional) Preencha as informações na [Conteúdo de backup](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content) seção.

1. (Condicional) Preencha as informações na [Regras de inclusão](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion) seção.

1. No **[!UICONTROL Fazer upload de CSV]** selecione a **[!UICONTROL Localização]** do arquivo CSV.

   ![Fazer upload da seção CSV](assets/upload-csv.png)

   O arquivo CSV deve estar formatado corretamente para ser carregado com sucesso. Clique em **[!UICONTROL Baixar o modelo CSV]** para obter um arquivo CSV formatado corretamente.

   Você tem duas opções de local:

   * **FTP:** para carregar seu arquivo CSV de um servidor FTP, selecione **[!UICONTROL FTP]** e insira as informações necessárias. Você pode usar SSL, que usa o protocolo FTPS para transferir seu arquivo CSV com segurança.
   * **URL:** Para carregar seu arquivo CSV de um URL, selecione **[!UICONTROL URL]**, em seguida, insira um URL de feed.

1. Clique em **[!UICONTROL Salvar]**.

## Considerações

* As entidades com critérios personalizados (linhas) podem conter até 1.000 itens recomendados (colunas).

* As atualizações de critérios personalizados são &quot;cumulativas&quot; por padrão. Os novos pares de valor-chave especificados no arquivo de upload CSV substituem os pares existentes. Os pares de valores chave existentes que não têm chaves especificadas no upload de CSV ainda estão disponíveis para entrega e expiram em 31 dias a partir do momento em que foram carregados pela última vez como parte do arquivo CSV.

   Entre em contato com o Atendimento ao Cliente para habilitar a configuração para descartar os resultados existentes que não estão inclusos upload CSV. Se essa configuração estiver ativada, somente as chaves presentes no arquivo de feed CSV personalizado estarão disponíveis para entrega. Essa configuração se aplica a todos os critérios personalizados.

* Os feeds de critérios personalizados atualizam uma vez a cada 24 horas.

   Você pode ver o status de carregamento e sincronização do seu critério personalizado na parte inferior de cada cartão de critério no [!UICONTROL Recommendations] > [!UICONTROL Critérios] página. Você também pode ver o status na variável [!UICONTROL Editar] ao editar critérios personalizados.

* O fluxo para um upload sem erros deve ser [!UICONTROL Programado] > [!UICONTROL Download do arquivo de feed] > [!UICONTROL Importação] > [!UICONTROL Êxito].

* A seguir estão possíveis mensagens de erro que você pode receber se [!DNL Target] encontra um problema com o upload:

   | Mensagem de erro | Detalhes |
   |--- |--- |
   | Erro desconhecido | Indica um erro interno técnico. |
   | Erro de análise | Provavelmente há um problema com o formato do arquivo de feed. Corrija o formato do arquivo e salve novamente o algoritmo, que reinicia o processo de download de arquivo. |
   | Servidor não encontrado | Forneça um IP ou nome de host que seja visível na internet. |
   | Erro de credenciais | Forneça um usuário e senha válidos para uma conta ativa no servidor. |
   | Diretório não encontrado | Forneça um diretório que exista no servidor. |
   | Arquivo não encontrado | Forneça o nome de um arquivo que exista no servidor dentro do diretório indicado. |

## Vídeo de treinamento: criar critérios no Recommendations (12:33) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo contém as seguintes informações (os detalhes sobre o upload de critérios personalizados começam às 11:43):

* Criar critérios
* Criar sequências de critérios
* Upload dos critérios personalizados

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
