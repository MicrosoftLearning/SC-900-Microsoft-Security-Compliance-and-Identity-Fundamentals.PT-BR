---
lab:
  title: Redefinição de senha de autoatendimento do Microsoft Entra
  module: Describe the authentication capabilities of Microsoft Entra ID
---

<!---
---
Laboratório: Título: 'Explorar a autenticação do Microsoft Azure AD com redefinição de senha self-service' Roteiro de Aprendizagem/Módulo/Unidade: 'Roteiro de Aprendizagem: descrever as capacidades do Azure Active Directory (Azure AD), parte do Microsoft Entra; Módulo 2: descrever as capacidades de autenticação do Microsoft Azure AD; Unidade 4: descrever a senha self-service'
---
--->

# Laboratório: redefinição de senha self-service do Microsoft Entra

Esse laboratório é mapeado para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as capacidades do Microsoft Entra
- Módulo: descrever as capacidades de autenticação do Microsoft Entra ID
- Unidade: descrever a redefinição de senha self-service

## Cenário do laboratório

Neste laboratório, você, como administrador, percorrerá o processo de adição de um usuário ao grupo de segurança SSPR, que já está configurado no seu locatário do Microsoft 365. Com a SSPR habilitada, você assumirá a função de um usuário e passará pelo processo de registro da SSPR e pela redefinição da senha.  Por fim, você, como administrador, poderá visualizar os logs de auditoria e dados de uso e insights para SSPR.

**Tempo estimado**: 15 a 20 minutos

### Tarefa 1:

Nesta tarefa, você, como administrador, percorrerá algumas das definições de configuração disponíveis para o SSPR.

1. Abra o navegador Microsoft Edge. Na barra de endereços, insira **https://entra.microsoft.com** e entre com as credenciais de administrador do Microsoft 365 fornecidas pelo seu hoster de laboratório autorizado (ALH).
    1. Na Janela de Entrada, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é a ID de Locatário exclusiva fornecida pelo ALH) e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**.

1. No painel de navegação à esquerda, expanda a opção **Proteção** e selecione **Redefinição de senha**.  

1. As propriedades para redefinição de senha self-service são exibidas. Selecione o ícone de informações no local no qual está escrito **Redefinição de senha self-service habilitada** para exibir a descrição. Certifique-se de que **Selecionado** esteja destacado em azul. Agora, coloque o cursor sobre o ícone de informações próximo ao local no qual está escrito **Selecionar grupo** e observe que ele diz: "Define o grupo de usuários que têm permissão para redefinir suas próprias senhas." Você precisa incluir usuários em um grupo, não é possível selecionar usuários individualmente. Observe que já existe um grupo listado: SSPRSecurityGroupUsers (esse grupo foi pré-configurado como parte do seu locatário do Microsoft 365). Por fim, observe a caixa de informações azul: "Essas configurações só se aplicam a usuários finais em sua organização. Os administradores estão sempre habilitados para a redefinição de senha self-service e precisam usar dois métodos de autenticação para a redefinição de senha.

1. No painel de navegação à esquerda da Redefinição de senha, selecione **Métodos de autenticação**.

1. No Número de métodos necessários para redefinir, selecione **1**. Observe a caixa de informações na tela.

1. Observe os diferentes métodos disponíveis para os usuários.  **Email** e **Celular (somente SMS)** já devem estar marcados, caso contrário, marque-os.

1. No painel de navegação esquerdo da Redefinição de senha, selecione **Registro**.  

1. Defina Exigir que os usuários se registrem ao entrar como **Sim**.  Mantenha o Número de dias antes que os usuários precisem confirmar novamente as informações de autenticação como o padrão de 180.   Preste atenção à caixa de informações na página.

1. No painel de navegação esquerdo da Redefinição de senha, selecione **Notificações**.  

1. Defina a configuração Notificar usuários sobre redefinições de senha como **Sim**.  Defina Notificar todos os administradores quando outros administradores redefinirem suas próprias senhas como Não.

1. Observe como o painel de navegação Redefinição de senha também inclui opções para exibir logs de auditoria e Uso e insights.

1. Feche a janela de redefinição de senha selecionando o **X** no canto superior direito da janela. Isso o leva de volta ao centro de administração Microsoft Entra.

1. Mantenha a janela do Microsoft Entra aberta.

### Tarefa 2

Nesta tarefa, você, como administrador, adicionará o usuário criado no exercício de laboratório anterior ao grupo de segurança SSPR.

1. Abra a guia do navegador da página inicial do Centro de Administração Microsoft Entra **[entra.microsoft.com](https://entra.microsoft.com)** . Se necessário, expanda **Identidade**.

1. No painel de navegação à esquerda, em "Identidade", expanda **Grupos** e selecione **Todos os grupos**.

1. Uma lista de grupos existentes é exibida. No campo Grupos de pesquisa, insira **SSPR** e, nos resultados da pesquisa, selecione **SSPRSecurityGroupUsers**.  Ele o levará à opção de configuração para este grupo.

1. Selecione **Membros** no painel de navegação esquerdo.

1. Na parte superior da página, selecione **+ Adicionar membros**.  

1. Na caixa Pesquisar, insira **Sara Perez**.  Uma vez que o usuário, **Sara Perez**, aparecer abaixo da caixa de pesquisa, selecione-o e pressione **Selecionar** na parte inferior da página.  Que será retornado à página de membros.  Selecione **Atualizar** na parte superior da página. Agora você deverá ver a usuária Sara Perez listada como membro do grupo de segurança SSPR.

1. Saia de todas as guias do navegador clicando no ícone do usuário ao lado do endereço de e-mail no canto superior direito da tela. Em seguida, feche todas as janelas do navegador.

### Tarefa 3

Nesta tarefa, você, como usuária Sara Perez, passará pelo processo de registro da redefinição de senha self-service.  Esta tarefa requer que você tenha acesso a um dispositivo móvel onde possa receber mensagens de texto.

1. Abra o Microsoft Edge e, na barra de endereços, insira **https://login.microsoft.com** .

1. Entre como Sara Perez.

1. Um pop-up é exibido indicando que Mais informações são necessárias.  Isso ocorre porque, como membro do grupo SSPRSecurityGroupUsers, a configuração exige que seus membros se registrem ao entrar.  Selecione o botão **Avançar**.  Nota: uma alternativa para que os próprios usuários façam o registro é que os administradores configurem diretamente os métodos de autenticação quando adicionam um usuário. Isso exige que os administradores conheçam e definam os números de telefone e endereços de email que os usuários usam para realizar a redefinição de senha de autoatendimento e para redefinir a senha de um usuário.

1. A página "Proteja sua conta" é aberta.  A janela exibida é para o método do Microsoft Authenticator que requer o aplicativo autenticador.  Para este laboratório, usaremos um método diferente, para evitar a etapa de ter que baixar o aplicativo.  Selecione **Quero usar um método diferente**.
    1. Na janela pop-up exibida, clique na seta suspensa, depois em **Telefone** e, em seguida, em **Confirmar**.
    1. Você precisará inserir um número de telefone. Confirme se a opção **Receber um código** está habilitada.   Digite o número de telefone onde você pode receber o código e clique em **Avançar**.  
    1. Uma nova janela será aberta, indicando que um código foi enviado para o telefone que você informou.  Insira o código que receber e selecione **Avançar**. Uma janela será aberta indicando que o código foi vierificado. Clique em **Avançar** e **Concluído**.  

1. Agora você pode concluir a entrada. Se você perceber que o tempo de entrada expirou, basta digitar a senha novamente.

1. Saia de todas as guias do navegador clicando no ícone do usuário ao lado do endereço de e-mail no canto superior direito da tela. Em seguida, feche todas as janelas do navegador.

### Tarefa 4 (opcional)

Nesta tarefa, você, como usuária Sara Perez, passará pelo processo de redefinição da senha

1. Abra o Microsoft Edge.

1. Na barra de endereços, insira **https://login.microsoftonline.com** .

1. Entre como Sara Perez, inserindo seu email **sara@WWLxZZZZ.onmicrosoft.com** (em que ZZZZZZ é sua ID de Locatário exclusivo fornecida pelo provedor de hospedagem de laboratório) e selecione o botão **Avançar**. Em vez disso, você vê a janela Escolha uma conta aberta; se for o caso, selecione a conta para Sara Perez.

1. Na página Digitar senha, selecione **Esqueci minha senha**.

1. A janela Voltar para sua conta é aberta.   Verifique se o email de Sara Perez, sara@WWLxZZZZ.onmicrosoft.com, é mostrado na caixa de email ou nome de usuário.  Se não, insira-o.  

1. Na caixa vazia, insira os caracteres exibidos na imagem ou as palavras do áudio. Depois de inseri-los, selecione **Avançar**.

1. A tela mostra Voltar à sua conta e mostra a etapa de Verificação 1 > escolher uma nova senha. Deixe a configuração padrão **Enviar mensagem de texto para o meu celular**.  Você precisará inserir o número do seu celular.  Depois de inseri-lo, selecione o **botão de Texto**. 

1. Insira o código de verificação e pressione **Avançar**.

1. Na próxima tela, você precisará inserir a nova senha e confirmá-la.  Insira-os agora e selecione o botão **Concluir**.

1. Você verá uma mensagem na tela informando que a sua senha foi redefinida.  Selecione **clique aqui** para entrar com sua nova senha.

1. Na caixa Escolher uma informação de conta, selecione **sara@WWLxZZZZZZ.onmicrosoft.com**, digite sua nova senha e selecione o botão **Entrar**.  Se for exibida uma mensagem perguntando se deseja permanecer conectado. selecione **Não**.

1. Agora você conseguirá entrar na conta Microsoft de Sara.

1. Saia selecionando o ícone do usuário ao lado do endereço de email no canto superior direito da tela e selecionando **Sair**. Em seguida, feche todas as janelas do navegador.

### Tarefa 5 (opcional)

Nesta tarefa, você, como administrador, verá resumidamente os registros de auditoria e os dados de Uso e Insights associados à redefinição de senha

1. Abra o Microsoft Edge.

1. Na barra de endereços, insira **https://entra.microsoft.com** e entre com as credenciais de administrador do Microsoft 365 fornecidas pelo seu hoster de laboratório autorizado (ALH).

1. Você está no centro de administração Microsoft Entra.  No painel de navegação à esquerda, expanda a opção **Proteção** e selecione **Redefinição de senha**.

1. Selecione **Logs de auditoria** no painel de navegação esquerdo.  Observe as informações e os filtros disponíveis.  Também observe que é possível baixar os logs.  

1. Selecione **Baixar**.  Observe que você pode formatar o download como CSV ou JSON.  Feche a janela selecionando o **X** no canto superior direito da tela.

1. No painel de navegação esquerdo, selecione **Uso e insights**.

1. Observe as informações disponíveis que dizem respeito ao Registro.  Observe que pode levar tempo para atualizar esses dados, mesmo depois de fazer uma atualização, portanto, eles ainda podem não refletir os dados de registro ou de uso da tarefa anterior.

1. Na parte superior da página, selecione **Uso** para exibir o número de redefinições de senha self-service e desbloqueios de conta por método.  Observe que pode levar tempo para atualizar esses dados, mesmo depois de fazer uma atualização, portanto, talvez os dados de uso da tarefa anterior ainda não sejam refletidos.

1. Feche as guias do navegador abertas.

### Revisão

Neste laboratório, você, como administrador, viu processo de habilitar a redefinição de senha self-service. Com a SSPR habilitada, você assumirá a função de um usuário para passar pelo processo de registro da SSPR e pela redefinição da senha.  Por fim, você, como administrador, saiba onde acessar os logs de auditoria e os dados de uso e insights do SSPR.
