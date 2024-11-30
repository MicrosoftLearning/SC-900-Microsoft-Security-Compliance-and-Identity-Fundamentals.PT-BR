---
lab:
  title: Explorar o Privileged Identity Management
  module: Describe the identity protection and governance capabilities of Microsoft Entra
---

# Laboratório: explorar o Privileged Identity Management

Esse laboratório é mapeado para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as capacidades do Microsoft Entra
- Módulo: descrever as capacidades da proteção de identidade e governança do Microsoft Entra
- Unidade: descrever as funcionalidades do Privileged Identity Management

## Cenário do laboratório

Neste laboratório, você vai explorar algumas das funcionalidades básicas do PIM (Privileged Identity Management). O PIM exige o licenciamento do Microsoft Entra ID P2.  Neste laboratório, você, como administrador, configurará um dos seus usuários, Diego Siciliani, com uma função de administrador de usuário do Microsoft Entra ID, por meio do Azure AD Privileged Identity Management (PIM).   Com privilégios de administrador de usuário, Diego poderá criar usuários e grupos, gerenciar licenças e muito mais.  Tanto o administrador quanto o usuário, Diego, devem ser configurados para o licenciamento do Microsoft Entra ID P2.

**Tempo estimado**: 60 minutos

### Tarefa 1

Nesta tarefa você, como administrador, irá redefinir a senha para o usuário Diego Siciliani. Esta etapa é necessária para que você possa inicialmente fazer logon como o usuário em tarefas subsequentes.

1. Abra o Microsoft Edge.  Na barra de endereços, insira **https://entra.microsoft.com** .

1. Entre com as credenciais de administrador do Microsoft 365 fornecidas por seu ALH.
    1. Na Janela de Entrada, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é a ID de Locatário exclusiva fornecida pelo ALH) e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Dependendo do host do laboratório e se esta for a primeira vez que você está fazendo logon no locatário, pode ser que seja solicitado a concluir o processo de registro de MFA. Se este for o caso, siga as instruções na tela para configurar a MFA.
    1. Depois de entrar, você será levado para a página do Centro de administração do Microsoft 365.

1. No painel de navegação à esquerda, expanda **Identidade**, expanda **Usuários** e selecione **Todos os usuários**.

1. Selecione **Diego Siciliani** na lista de usuários.

1. Selecione **Redefinir senha** na parte superior da página. Como você não fez logon anteriormente como Diogo, você não sabe a senha dele e precisará redefini-la.

1. Quando a janela de redefinição de senha abrir, selecione **Redefinir senha**.  IMPORTANTE: anote a nova senha, pois você precisará dela em uma tarefa posterior, para entrar como o usuário.

1. No painel de navegação à esquerda, selecione **Página Inicial** para retornar à página inicial do Centro de Administração Microsoft Entra.

1. Mantenha a página do navegador aberta, pois você vai precisar dela na tarefa seguinte.

### Tarefa 2

Nesta tarefa, você, como administrador, atribuirá a Diego uma função do Microsoft Entra ID no Privileged Identity Management.

1. Abra a guia do navegador para a página inicial do centro de Administração Microsoft Entra.

1. No painel de navegação à esquerda, em "Identidade", expanda **Governança de Identidade** e selecione **Privileged Identity Management**.

1. Agora você está na página de início rápido do Privileged Identity Management. Analise as informações na página Introdução. Na janela principal, onde diz Gerenciar acesso, selecione **Gerenciar**.

1. Agora você está na página Funções da Contoso.  Na parte superior da página, insira **usuário** na barra de pesquisa.  Nos resultados da pesquisa, selecione **Administrador de usuário**.

1. Na parte superior da página, selecione **+ Adicionar atribuições**.

1. Na página Adicionar atribuições, verifique se **Associação** está sublinhada.  Aqui você definirá as configurações de associação da função de administrador de usuários no PIM.

1. Deixe o tipo Escopo em seu valor padrão, Diretório.  

1. Em Selecionar membros, selecione **Nenhum membro selecionado**. Isso abre a janela Selecionar um membro.

1. Na barra de pesquisa, insira **Diego**.  Nos resultados da pesquisa, selecione **Diego Siciliani** e pressione **Selecionar** na parte inferior da página.  

1. Em Selecionar membros, você verá um membro selecionado e o nome e o email do membro selecionado, Diogo Martins. Na parte inferior da página Adicionar atribuições, selecione **Avançar**.  

1. Agora você está na página Configuração.  Deixe o tipo de Atribuição na configuração padrão, Elegível.

1. Se a caixa Permanentemente elegível estiver marcada, selecione **Permanentemente elegível** para remover a marca de seleção.

1. Nos campos Início da atribuição, mantenha a data e a hora padrão, ou seja, hoje e a hora atual.

1. Nos campos Fim da atribuição, altere a data para a data de hoje (observe que a configuração padrão é um ano a partir de hoje, portanto, você precisa alterar o ano). Para a hora, defina a hora como duas horas a partir da hora atual. Depois de definir o campo de hora para a hora em que a atribuição termina, pressione a tecla TAB no teclado e selecione **Atribuir** na parte inferior da página.  

1. Isso leva você de volta à janela Atribuições.  Depois de alguns segundos, você verá Diego Siciliani listado na tabela Administrador de usuários, juntamente com os detalhes da atribuição. Se depois de alguns segundos você ainda não vir a atualização, selecione **Atualizar** na parte superior da página.

1. Na parte superior da página, selecione **Configurações**.

1. Nos detalhes da configuração de função para Administrador de usuário, observe as diferentes opções.  Observe que as configurações "Exigir justificativa na ativação" e "Na ativação, exigir o Azure MFA" estão definidas como sim.  Você verá ambas na próxima tarefa, quando Diogo ativar a função.  Observe também que “Exigir aprovação para ativar” está definido como Não.  Deixe todas as configurações com seus valores padrão.  Feche a página selecionando o **X** no canto superior direito da tela.

1. Saia escolhendo o ícone do usuário ao lado do endereço de email no canto superior direito da tela e selecionando **Sair**. Em seguida, feche todas as janelas do navegador.

### Tarefa 3

Nesta tarefa, você, como Diego Siciliani, entrará no Centro de Administração Microsoft Entra para acessar a capacidade do Azure AD Privileged Identity Management para ativar sua atribuição como Administrador do Usuário.  Depois de isso ser ativado, você fará algumas alterações na configuração de um usuário existente. Observação: para esta tarefa, você precisará acessar um dispositivo móvel para usar com o aplicativo Microsoft Authenticator.

1. Abra o Microsoft Edge.  Na barra de endereços do navegador, insira **Entra.microsoft.com**.

1. Entre como Diego Siciliani.
    1. Na janela Entrar, insira **DiegoS@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é a sua ID de locatário exclusiva fornecida pelo provedor de hospedagem do laboratório) e selecione **Avançar**.
    1. Insira a senha temporária que você anotou na tarefa anterior e selecione **Entrar**.  Selecione **Entrar**.
    1. Como a senha que você inseriu era apenas temporária, você precisa atualizá-la agora. Insira a senha atual, insira uma nova senha e confirme a nova senha.  Observe que essa nova senha será necessária para concluir a tarefa.
    1. Como esta é a primeira vez que você está fazendo login como Diego, poderá ser solicitado que você configure a MFA. Siga as instruções na tela para configurar a MFA.
    1. Quando solicitado a permanecer conectado, selecione **Sim**.

1. Você deve estar conectado com êxito ao centro de administração Microsoft Entra.
1. No painel de navegação à esquerda, expanda **Governança de Identidade** e selecione **Privileged Identity Management**.
1. No painel de navegação esquerdo, selecione **Minhas funções**.  Agora você está vendo informações sobre suas atribuições qualificadas.  Você verá que você, Diogo, recebeu a função Administrador de usuários.  
1. Na última coluna da tabela, denominada ação, selecione **Ativar**.
1. Você verá um ícone de aviso indicando que é necessário fazer uma verificação adicional.  Selecione **Clique para continuar**.  Lembre-se de que as configurações do PIM para a função Administrador de usuários exigem a autenticação multifator.  Além disso, como as informações de contato de Diego para uso com a MFA (métodos de autenticação) não foram configuradas anteriormente, ele deve registrar suas próprias informações, para poder usar a MFA.  Embora ele tenha que fazer a MFA sempre que entrar como administrador de usuário, dentro do período de atribuição, o processo de registro MFA é necessário apenas uma vez.
1. A janela exibida e as etapas que seguem são para o método do aplicativo Microsoft Authenticator. .
    1. Se você já possui o aplicativo Microsoft Authenticator instalado em seu dispositivo móvel, selecione **Avançar**. Caso contrário, selecione **Baixar agora** e siga as etapas.
    1. Você começará a configurar sua conta.  Selecione **Avançar**.
    1. Usando o aplicativo Microsoft Authenticator em seu dispositivo móvel, clique em **+** para adicionar uma conta e escolha **Conta corporativa ou de estudante.**
    1. Selecione a opção para **Digitalizar o código QR** e, usando o seu dispositivo móvel, digitalize o código QR na tela do seu computador.
    1. Usando o aplicativo Microsoft Authenticator no seu dispositivo móvel, digitalize o código QR.
    1. Siga as etapas no computador e no dispositivo móvel e clique em **Avançar**.
    1. Depois de configurar suas informações de segurança, você verá uma janela de sucesso.  Selecione **Concluído**.

1. Depois de concluir o processo de registro de MFA, você retornará à página Administrador de Usuário Ativo do PIM.
1. A janela Ativar administrador do usuário é exibida.  Você deve inserir um motivo para a ativação.  Na caixa exibida, digite o motivo desejado (máximo de 500 caracteres) e selecione **Ativar**.
1. Você verá o status (três fases de progresso), conforme a ativação é processada.
1. Depois que a ativação for concluída, você retornará à página Minhas funções | Funções do Microsoft Entra ID, na qual verá uma notificação informando que ativou uma função.  Selecione **Clique aqui** para exibir suas funções ativas.  Se você notar que a hora de término é diferente da configurada originalmente, selecione a chave de atualização na parte superior da página (pode levar alguns minutos para atualizar).
1. Retorne à página inicial do Centro de Administração do Microsoft Entra, selecionando **Página Inicial** no painel de navegação à esquerda. 
1. Como administrador de usuários do Microsoft Entra ID, você pode criar usuários e grupos, gerenciar licenças e muito mais. No painel de navegação à esquerda, expanda **Identidade** e selecione **Usuários**.
1. Na lista de usuários, selecione **Bianca Pisani**.
1. No painel de navegação à esquerda, selecione **Grupos**.
1. Observe os grupos aos quais Bianca já está atribuída. Na parte superior da página, selecione **+ Associações**.
1. Na lista de grupos, selecione **Equipe do Projeto Mark 8**.
1. Clique em **Selecionar** na parte inferior da página.
1. Na página Grupos, observe que o grupo Equipe do Projeto Mark 8 foi adicionado à lista (se você não o vir imediatamente listado, clique no botão **Atualizar**).
1. Saia escolhendo o ícone do usuário ao lado do endereço de email no canto superior direito da tela e selecionando **Sair**. Em seguida, feche todas as janelas do navegador.
1. A duração da função de Usuário Administrador é limitada ao tempo que foi configurado.

### Revisão

Neste laboratório, você explorou o PIM.  Você, como administrador, configurou Diego com privilégios de administrador de usuário por um período de tempo especificado.  Em seguida, você, como Diego, passou pelo processo de ativação dos privilégios de administrador e um usuário para um grupo.  Lembre-se de que o PIM requer o licenciamento do Microsoft Entra ID Premium P2.
