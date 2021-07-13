---
keywords: implementação; mbox.js não javascript; adbox; redirecionador; mbox
description: Saiba como implementar o Adobe [!DNL Target] em cenários que não utilizam JavaScript, como uma AdBox ou Redirecionador.
title: Como implementar [!DNL Target] para Email?
feature: Implementar Email
role: Developer
exl-id: 3287cf3d-3ed4-471f-aa06-25bb12e23ead
source-git-commit: 3c79b2ce70e456275ddf6774a35ae5c36f0ae99d
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 81%

---

# Email: implementação do Target

Informações sobre a implementação do Target em cenários que não utilizam JavaScript como uma AdBox ou redirecionador.

É possível rastrear as visitas aos anúncios e a outros conteúdos externos. Também é possível identificar a entrada e saída do mesmo usuário em seu site e fornecer uma experiência web consistente. Utilizando um único URL, a AdBox permite testes sem necessidade de JavaScript ou [!DNL at.js] ou [!DNL mbox.js].

Uma AdBox é útil para sites que não têm [!DNL at.js], como afiliadas. Se sua atividade requer anúncios dinâmicos (por exemplo, você deseja exibir um produto deixado no carrinho de compras em um anúncio), não é possível utilizar uma AdBox.

Anúncios AdBox e Redirecionador podem ser usados com qualquer tipo de atividade. A tabela abaixo compara uma AdBox e um Redirector e suas utilizações:

|  | Propósito | Quando utilizar | Estrutura do URL | Tipo de oferta | Conteúdo da oferta |
|--- |--- |--- |--- |--- |--- |
| AdBox | Retorna imagens diferentes para o anúncio | Alterar o conteúdo de um anúncio | `clientcode&#x200B;.tt.&#x200B;omtrdc&#x200B;.net/&#x200B;m2&#x200B;/&#x200B;clientcode/ubox/&#x200B;image?` | oferta de redirecionamento | URL de uma imagem |
| Redirecionador | Redireciona o visitante para uma página da Web diferente | Alterar a página de aterrissagem de um anúncio | `clientcode&#x200B;.tt.omtrdc.net/&#x200B;m2/clientcode&#x200B;/ubox/page?` | oferta de redirecionamento | URL de uma página |

## Práticas recomendadas de segurança {#security}

Observe que com o Redirecionador, você pode ser exposto a um risco de Vulnerabilidade de Redirecionamento Aberto. Para evitar o uso não autorizado de links Redirecionadores por terceiros, recomendamos que você use &quot;hosts autorizados&quot; para lista de permissões os domínios padrão de URL de redirecionamento. O Target usa hosts para a lista de permissões de domínios aos quais você deseja permitir redirecionamentos. Para obter mais informações, consulte [Criar lista de permissões que especificam hosts autorizados a enviar chamadas de mbox para o Target](/help/administrating-target/hosts.md#allowlist) em *Hosts*.

## Limitações {#section_38F559DCF1324271926608BCD4AB1227}

* Não existe um tempo limite para o lado do cliente como nas mboxes padrão. Se o Target estiver completamente inacessível, os visitantes do anúncio não visualizarão qualquer conteúdo, nem mesmo o conteúdo padrão.
* Cookies de terceiros são utilizados para rastrear as visitas. Se os PCIds forem diferentes, por padrão, o perfil de terceiros do visitante será combinado com qualquer perfil próprio existente.
* Para utilizar cookies próprios na AdBox, é necessário enviar a sessão mBox no URL. Entre em contato com seu representante de contas para fazer isso.
* Para utilizar cookies próprios para rastrear cliques de anúncios, é necessário enviar a sessão mbox no URL. Entre em contato com seu representante de contas para fazer isso.
* Para utilizar mais de uma AdBox na mesma página, você deve enviar a sessão Mbox no URL. Entre em contato com seu representante de contas para fazer isso. Você pode ter mais de uma AdBox e um link Redirecionador na mesma página (porque o Redirecionador está na segunda página).
