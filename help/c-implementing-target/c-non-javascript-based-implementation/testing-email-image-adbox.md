---
description: Teste dinamicamente imagens em emails, e até mesmo mude essas imagens em tempo real quando alguém abre o email.
keywords: email;adbox
seo-description: Teste dinamicamente imagens em emails, e até mesmo mude essas imagens em tempo real quando alguém abre o email.
seo-title: Testar uma Adbox de imagem de email
solution: Target
title: Testar uma Adbox de imagem de email
topic: Recommendations
uuid: d0710adb-4649-4b57-9b70-4b49d43fa591
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Testar uma Adbox de imagem de email{#test-an-email-image-adbox}

Teste dinamicamente imagens em emails, e até mesmo mude essas imagens em tempo real quando alguém abre o email.

Redirecionadores podem ser utilizados em emails para rastrear cliques e controlar dinamicamente qual página de aterrissagem é acessada.

O teste de imagens de email é feito por meio de versões modificadas das adboxes. Como os clientes de email não permitem cookies, um identificador único deve ser gerado para cada email. Esse número é anexado ao URL da adbox e em qualquer redirecionador utilizado no email para rastrear cliques do email.

>[!NOTE]
>
>Embora o Target possa oferecer tecnicamente a otimização de imagens no tempo de abertura, cada cliente de email trata o armazenamento em cache de forma diferente, sendo assim, o sucesso será variado. Independentemente do provedor de serviço de email utilizado, o cliente de email que o usuário final usa para abrir o email (aplicativo do Gmail, Outlook, Hotmail e assim por diante) determina se a imagem é realmente obtida no tempo de abertura. Por exemplo, o Gmail armazena quase tudo em cache, assim, a imagem que o usuário final vê depende de quando o Gmail escolhe chamar e armazenar em cache a imagem.

**Código de amostra de uma adbox de imagem de email:**

```
<img src=“https://{clientcode}.tt.omtrdc.net/m2/​{clientcode}/ubox/​image?
mbox={email_header}&
mboxDefault=​{http%3A%2F%2Fwww.domain.com%2Fheader.jpg}&
mboxXDomain=disabled&
mboxSession={123456}&
mboxPC={123456}” border=“0"/>
```

Onde os valores abaixo são específicos para você:

| Valor | Descrição |
|--- |--- |
| clientcode | O código de cliente de sua empresa. Encontre isso em seu at.js ou mbox.js listado como `clientCode='yourclientcode'`. Todos os caracteres em minúsculas e sem caracteres especiais. |
| image | O tipo de oferta. É sempre "image" para anúncios gráficos e "page" para redirecionadores. |
| email_header | O nome da adbox. |
| `mboxDefault=http%3A%2F%2Fwww.domain.com%2Fheader.jpg` | Obrigatório. Substitua o URL pelo conteúdo padrão apropriado para sua adbox. Esta deve ser uma referência absoluta e deve ser codificada no URL. |
| `mboxXDomain=disabled` | Faz com que o Target não tente definir um cookie. |
| `mboxSession=123456` e `mboxPC=123456` | Dois valores são exigidos pelo Target para mesclar o perfil do usuário com o perfil existente para o seu site. 123456 é o identificador único gerado por email. Insira esse valor dinamicamente em cada adbox e URL de redirecionador. Esse número deve ser único para cada email enviado. Se um email semanal é enviado para 1.000 destinatários, 1.000 IDs únicas devem ser geradas.<br>O identificador único por email deve ser atribuído ao mboxSession e mboxPC em cada adbox e URL de redirecionador. O formato recomendado para esse identificador é timestamp-NNNNN, onde NNNNN é um número aleatório de 5 dígitos, mas qualquer formato alfanumérico funcionará. Alguns serviços de envio de emails em grandes quantidades e qualquer linguagem de programação podem gerar esse identificador único. |
