<!---
---
Laboratório: Título: "Explorar o Privileged Identity Management". ' Roteiro de Aprendizagem/Módulo/Unidade: 'Roteiro de Aprendizagem: descrever as capacidades do Microsoft Entra; Módulo 4: Módulo: descrever as capacidades de proteção de identidade e governança do Microsoft Entra; Unidade 4: descrever as capacidades do Privileged Identity Management'
---
--->

# Laboratório: explorar o Privileged Identity Management

Esse laboratório é mapeado para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as capacidades do Microsoft Entra
- Módulo: descrever as capacidades da proteção de identidade e governança do Microsoft Entra
- Unidade: descrever as funcionalidades do Privileged Identity Management

## Cenário do laboratório

Neste laboratório, você vai explorar algumas das funcionalidades básicas do PIM (Privileged Identity Management). O PIM exige o licenciamento do Microsoft Entra ID P2.  Neste laboratório, você, como administrador, configurará um dos seus usuários, Diego Siciliani, com uma função de administrador de usuário do Microsoft Entra ID, por meio do Azure AD Privileged Identity Management (PIM).   Com privilégios de administrador de usuário, Diego poderá criar usuários e grupos, gerenciar licenças e muito mais.  Tanto o administrador quanto o usuário, Diego, devem ser configurados para o licenciamento do Microsoft Entra ID P2.

**Tempo estimado**: 45 a 60 minutos

### Tarefa 1:

Nesta tarefa você, como administrador, irá redefinir a senha do usuário Diego Siciliani. Esta etapa é necessária para que você possa inicialmente fazer logon como usuário nas tarefas seguintes.

1. Abra o Microsoft Edge.  Na barra de endereços, insira **https://entra.microsoft.com** .

1. Entre com as credenciais de administrador do Microsoft 365 fornecidas por seu ALH.
    1. Na Janela de Entrada, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é a ID de Locatário exclusiva fornecida pelo ALH) e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**.

1. No painel de navegação à esquerda, expanda **Identidade**, expanda **Usuários** e selecione **Todos os usuários**.

1. Escolha **Diego Siciliani** da lista de usuários.

1. Selecione **Redefinir senha** na parte superior da página. Como você não fez logon anteriormente como Diogo, você não sabe a senha dele e precisará redefini-la.

1. Quando a janela de redefinição de senha abrir, selecione **Redefinir senha**.  IMPORTANTE: anote a nova senha, pois você precisará dela em uma tarefa posterior, para entrar como o usuário.

1. No painel de navegação à esquerda, selecione **Página Inicial** para retornar à página inicial do Centro de Administração Microsoft Entra.

1. Mantenha a página do navegador aberta, pois você vai precisar dela na tarefa seguinte.

### Tarefa 2:

Nesta tarefa, você, como administrador, atribuirá a Diego uma função do Azure AD no Privileged Identity Management.

1. Abra a guia do navegador para a página inicial do centro de Administração Microsoft Entra.

1. No painel de navegação à esquerda, em "Identidade", expanda **Governança de Identidade** e selecione **Privileged Identity Management**.

1. Agora você está na página de início rápido do Privileged Identity Management. Analise as informações na página Introdução. Selecione **Gerenciar**.

1. Agora você está na página Funções da Contoso.  Na barra de pesquisa, na parte superior da página, digite **usuário**.  Nos resultados de pesquisa, selecione **Administrador de Usuário**.

1. Na parte superior da página, selecione **+ Adicionar atribuições**.

1. Na página Adicionar atribuições, certifique-se de que **Adesão** esteja sublinhado.  Aqui você definirá as configurações de associação da função de administrador de usuários no PIM.

1. Deixe o tipo de Escopo com seu valor padrão, Diretório.  

1. Em Selecionar membros, selecione **Nenhum membro selecionado**. Isso abre a janela Selecionar um membro.

1. Na barra de pesquisa, insira **Diego**.  Nos resultados da pesquisa, escolha **Diego Siciliani** e depois pressione **Selecionar** na parte inferior da página.  

1. Em Selecionar membros, você verá um membro selecionado e o nome e o email do membro selecionado, Diogo Martins. Na parte inferior da página Adicionar atribuições, selecione **Avançar**.  

1. Agora você está na página Configuração.  Deixe o tipo de Atribuição na configuração padrão, Elegível.

1. Se a caixa Permanentemente elegível estiver marcada, escolha **Permanentemente elegível**, para remover a marca de seleção.

1. Nos campos Início da atribuição, mantenha a data e hora padrão, de hoje, e a hora atual.

1. Nos campos Término da atribuição, altere a data para a data de hoje (observe que a configuração padrão é um ano a partir de hoje, então você precisa mudar o ano). Para a hora, defina a hora em duas horas a partir da hora atual. Depois de definir o campo relativo à hora para a hora em que a Tarefa termina, pressione a tecla tab no teclado e selecione **Atribuir** na parte inferior da página.  

1. Isso vai te levar de volta à janela Atribuições.  Após alguns segundos, você verá Diego Siciliani listado na tabela Administrador de Usuário, junto com os detalhes da atribuição. Se depois de alguns segundos não houver atualização, escolha **Atualizar** no topo da página.

1. Na parte superior da página, escolha **Configurações**.

1. Nos detalhes de configuração da Função para Administrador de Usuário, observe as diferentes opções.  Observe que a configuração para “Exigir justificativa na ativação” está definida como sim e “Na ativação, exigir Azure MFA” também está definida como sim.  Você verá ambas na próxima tarefa, quando Diogo ativar a função.  Observe também que “Exigir aprovação para ativar” está definido como Não.  Deixe todas as configurações com seus valores padrão.  Selecione o **X** no canto superior direito da tela para fechar a página.

1. Saia selecionando o ícone do usuário próximo ao endereço de email no canto superior direito da tela e selecionando **Sair**. Em seguida, feche todas as janelas do navegador.

### Tarefa 3

Nesta tarefa, você, como Diego Siciliani, entrará no Centro de Administração Microsoft Entra para acessar a capacidade do Azure AD Privileged Identity Management para ativar sua atribuição como Administrador do Usuário.  Depois de isso ser ativado, você fará algumas alterações na configuração de um usuário existente. Observação: para esta tarefa, você precisará ter acesso a um dispositivo móvel ao qual tenha acesso imediato e possa receber mensagens de texto.

1. Abra o Microsoft Edge.  Na barra de endereços do navegador, insira **Entra.microsoft.com**.

1. Entre como Diego Siciliani.
    1. Na janela Entrar, insira **DiegoS@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é a sua ID de locatário exclusiva fornecida pelo provedor de hospedagem do laboratório) e selecione **Avançar**.
    1. Insira a senha temporária que você anotou na tarefa anterior e selecione **Entrar**.  Selecione **Entrar**.
    1. Como a senha que você inseriu era apenas temporária, você precisa atualizá-la agora. Insira a senha atual, insira uma nova senha e confirme a nova senha.  Observe que essa nova senha será necessária para concluir a tarefa.
    1. Quando solicitado a permanecer conectado, selecione **Sim**.

1. Você deve estar conectado com êxito ao centro de administração Microsoft Entra.
1. No painel de navegação à esquerda, expanda **Governança de Identidade** e selecione **Privileged Identity Management**.
1. No painel de navegação esquerdo, selecione **Minhas funções**.  Agora você está vendo informações sobre suas atribuições qualificadas.  Você verá que você, Diogo, recebeu a função Administrador de usuários.  
1. Na última coluna da tabela, chamada ação, selecione **Ativar**.
1. Você verá um ícone de aviso indicando que é necessário fazer uma verificação adicional.  Selecione **Clicar para continuar**.  Lembre-se de que as configurações do PIM para a função Administrador de usuários exigem a autenticação multifator.  Além disso, como as informações de contato de Diego para uso com MFA (métodos de autenticação) não foram configuradas anteriormente, ele deve registrar suas informações para poder usar o MFA.  Embora ele tenha que fazer o MFA sempre que entrar como administrador de usuário, dentro do período de atribuição, o processo de registro do MFA é necessário apenas uma vez.
1. Você é notificado de que mais informações são necessárias. Selecione **Avançar**.
1. Digite sua senha.
1. No canto inferior esquerdo da janela do Microsoft Authenticator, selecione **Quero configurar um método diferente**.
1. Você precisará escolher outro método.  Ao lado de onde diz Authenticator app, selecione a tecla de seta para baixo.   Selecione **Telefone** e depois **Confirmar**.
1. Você precisará inserir um número de telefone que deseja usar. Verifique se o país está correto para o código do país do seu número de telefone.  Digite o seu número de telefone, garanta que **Envie-me um código por mensagem** esteja selecionado, e depois escolha **Avançar**.
1. Digite o código de 6 dígitos que você recebeu em seu telefone e selecione **Avançar**.
1. Você verá uma notificação indicando que o seu telefone foi registrado com sucesso. Selecione **Avançar** e depois, **Concluído**.
1. Você responderá se deseja permanecer conectado.  Selecione **Sim**.
1. A janela Ativar administrador do usuário é exibida.  Você deve inserir um motivo para a ativação.  Na caixa que aparece, digite o motivo desejado (máximo de 500 caracteres) e escolha **Ativar**.
1. Você verá o status (três fases de progresso), conforme a ativação é processada.
1. Depois que a ativação for concluída, você voltará à página Minhas funções | Funções do Azure AD, em que verá uma notificação informando que uma função foi ativada.  Selecione **Clique aqui** para ver suas funções ativas.  Se você perceber que o horário de término é diferente do que foi configurado originalmente, selecione a tecla de atualização na parte superior da página (pode levar alguns minutos para atualizar).
1. Retorne à página inicial do Centro de Administração do Microsoft Entra, selecionando **Página Inicial** no painel de navegação à esquerda. 
1. Como um administrador de usuário do Azure AD, você pode criar usuários e grupos, gerenciar licenças e muito mais. No painel de navegação à esquerda, expanda **Identidade**, selecione **Usuários** e, em seguida, **Todos os usuários**.
1. Na lista de usuários, selecione **Bianca Pisani**.
1. No painel de navegação esquerdo selecione **Licenças**.
1. Observe que a Bianca não tem licenças atribuídas.  Na parte superior da página, selecione **+ Atribuições**.
1. Na lista de licenças selecionadas, selecione **Office 365 E3** e **Windows 10 Enterprise E3**.
1. Na parte inferior da página, selecione **Salvar**.  Você verá uma breve notificação no canto superior direito da página indicando que as licenças foram atribuídas com sucesso.
1. Feche a página de atribuições de licença atualizada, escolhendo o **X** no canto superior direito da página.
1. Saia selecionando o ícone do usuário próximo ao endereço de email no canto superior direito da tela e selecionando **Sair**. Em seguida, feche todas as janelas do navegador.
1. A duração da função de Usuário Administrador é limitada ao tempo que foi configurado.

### Revisão

Neste laboratório, você explorou o PIM.  Você, como administrador, configurou Diego com privilégios de administrador de usuário por um determinado período de tempo.  Depois, como Diego, você percorreu o processo de ativação dos privilégios de administrador do usuário e a definição das configurações do usuário.  Lembre-se de que o PIM requer licenciamento P2 do Azure AD Premium.
