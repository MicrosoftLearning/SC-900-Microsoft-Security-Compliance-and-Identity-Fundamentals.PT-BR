<a name="---"></a><!---
---
Laboratório: Título: 'Explorar a governança de identidade no Azure AD com o Privileged Identity Management. ' Roteiro de aprendizagem/Módulo/Unidade: 'Roteiro de aprendizagem: descrever as funcionalidades do Azure AD (Active Directory), parte do Microsoft Entra; Módulo 4: descrever as funcionalidades de proteção e governança de identidade do Azure AD; Unidade 4: descrever as funcionalidades do Privileged Identity Management'
---
--->

# <a name="lab-explore-identity-governance-in-azure-ad-with-privileged-identity-management"></a>Laboratório: Explore a governança de identidade no Azure AD com o Privileged Identity Management

Esse laboratório é mapeado para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades do Azure AD (Azure Active Directory), parte do Microsoft Entra
- Módulo: descrever as funcionalidades de governança e proteção de identidade do Azure AD
- Unidade: descrever as funcionalidades do Privileged Identity Management

## <a name="lab-scenario"></a>Cenário do laboratório

Neste laboratório, você vai explorar algumas das funcionalidades básicas do PIM (Privileged Identity Management). O PIM requer o Azure AD Premium P2.  Neste laboratório, você, como administrador, configurará um de seus usuários, Diego Siciliani, com uma função de administrador de usuário do Azure AD, por meio do Privileged ID management (PIM).   Com privilégios de administrador de usuário, Diego poderá criar usuários e grupos, gerenciar licenças e muito mais.  Tanto o administrador quanto o usuário, Diego devem ser configurados para o licenciamento P2 do Azure AD Premium.

**Tempo estimado**: 45 a 60 minutos

### <a name="task-1"></a>Tarefa 1:

Nesta tarefa você, como administrador, irá redefinir a senha do usuário Diego Siciliani. Esta etapa é necessária para que você possa inicialmente fazer logon como usuário nas tarefas seguintes.

1. Abra o Microsoft Edge.  Na barra de endereços, insira **portal.azure.com**.

2. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é a sua ID de locatário exclusiva fornecida pelo provedor de hospedagem do laboratório) e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**.

3. Selecione **Azure Active Directory**.  

4. No painel de navegação esquerdo selecione **Usuários**.

5. Escolha **Diego Siciliani** da lista de usuários.

6. Selecione **Redefinir senha** na parte superior da página. Como você não fez logon anteriormente como Diogo, você não sabe a senha dele e precisará redefini-la.

7. Quando a janela de redefinição de senha abrir, selecione **Redefinir senha**.  IMPORTANTE: anote a nova senha, pois você precisará dela em uma tarefa posterior, para entrar como o usuário.

8. Selecione o **X**, no canto superior direito da página, para fechar a janela de redefinição de senha.

9. Selecione o **X**, no canto superior direito da página, para fechar a janela de perfil do Diego.

10. Selecione o **X**, no canto superior direito da página, para fechar a janela Todos os usuários. Agora você está na página Contoso – Azure Active Directory.

11. Mantenha a página do navegador aberta, pois você vai precisar dela na tarefa seguinte.

### <a name="task-2"></a>Tarefa 2:

Nesta tarefa, você, como administrador, atribuirá a Diego uma função do Azure AD no Privileged Identity Management.

1. Vá para a guia aberta do navegador, denominada Contoso - Microsoft Azure.   Se você fechou anteriormente a guia do navegador, abra o Microsoft Edge e, na barra de endereços, digite portal.azure.com, entre com suas credenciais de administrador e escolha Azure Active Directory.  

2. No painel de navegação esquerdo, selecione **Governança de Identidade**.

3. No painel de navegação esquerdo, em Privileged Identity Management, selecione **funções do Azure AD**.

4. Agora você está na janela Início rápido do Privileged Identity Management.  Selecione **Gerenciar**.

5. Agora você está na página Funções da Contoso.  Na barra de pesquisa, na parte superior da página, digite **usuário**.  Nos resultados de pesquisa, selecione **Administrador de Usuário**.

6. Na parte superior da página, selecione **+ Atribuições**.

7. Na página Adicionar atribuições, certifique-se de que **Adesão** esteja sublinhado.  Aqui você definirá as configurações de associação da função de administrador de usuários no PIM.

8. Deixe o tipo de Escopo com seu valor padrão, Diretório.  

9. Em Selecionar membros, escolha **Nenhum membro selecionado**. Isso abre a janela Selecionar um membro.

10. Na barra de pesquisa, insira **Diego**.  Nos resultados da pesquisa, escolha **Diego Siciliani** e depois pressione **Selecionar** na parte inferior da página.  

11. Em Selecionar membros, você verá um membro selecionado e o nome e o email do membro selecionado, Diogo Martins. Na parte inferior da página Adicionar atribuições, selecione **Avançar**.  

12. Agora você está na página Configuração.  Deixe o tipo de Atribuição na configuração padrão, Elegível.

13. Se a caixa Permanentemente elegível estiver marcada, escolha **Permanentemente elegível**, para remover a marca de seleção.

14. Nos campos Início da atribuição, mantenha a data e hora padrão, de hoje, e a hora atual.

15. Nos campos Término da atribuição, altere a data para a data de hoje (observe que a configuração padrão é um ano a partir de hoje, então você precisa mudar o ano). Para a hora, defina a hora em duas horas a partir da hora atual. Depois de definir o campo relativo à hora para a hora em que a Tarefa termina, pressione a tecla tab no teclado e selecione **Atribuir** na parte inferior da página.  

16. Isso vai te levar de volta à janela Atribuições.  Após alguns segundos, você verá Diego Siciliani listado na tabela Administrador de Usuário, junto com os detalhes da atribuição. Se depois de alguns segundos não houver atualização, escolha **Atualizar** no topo da página.

17. Na parte superior da página, escolha **Configurações**.

18. Nos detalhes de configuração da Função para Administrador de Usuário, observe as diferentes opções.  Observe que a configuração para “Exigir justificativa na ativação” está definida como sim e “Na ativação, exigir Azure MFA” também está definida como sim.  Você verá ambas na próxima tarefa, quando Diogo ativar a função.  Observe também que “Exigir aprovação para ativar” está definido como Não.  Deixe todas as configurações com seus valores padrão.  Selecione o **X** no canto superior direito da tela para fechar a página.

19. Saia selecionando o ícone do usuário próximo ao endereço de email no canto superior direito da tela e selecionando **Sair**. Em seguida, feche todas as janelas do navegador.

### <a name="task-3"></a>Tarefa 3

Nesta tarefa, você, como Diogo Martins, entrará no portal do Azure para acessar a funcionalidade Privileged Identity Management do Azure Active Directory para ativar sua atribuição como Administrador de usuários.  Depois de isso ser ativado, você fará algumas alterações na configuração de um usuário existente. Observação: para esta tarefa, você precisará ter acesso a um dispositivo móvel ao qual tenha acesso imediato e possa receber mensagens de texto.

1. Abra o Microsoft Edge.  Na barra de endereço do navegador, digite **portal.azure.com**

1. Entre como Diego Siciliani.
    1. Na janela Entrar, insira **DiegoS@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é a sua ID de locatário exclusiva fornecida pelo provedor de hospedagem do laboratório) e selecione **Avançar**.
    1. Insira a senha temporária que você anotou na tarefa anterior e selecione **Entrar**.  Selecione **Entrar**.
    1. Como a senha que você inseriu era apenas temporária, você precisa atualizá-la agora. Digite a senha atual.  Para a nova senha e os campos de confirmação de senha, insira **SC900-Lab**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**.

1. Você deve estar conectado ao portal do Azure.
1. Na página de boas-vindas principal, em serviços do Azure, escolha **Azure Active Directory**.
1. No painel de navegação esquerdo, selecione **Governança de Identidade**.
1. No painel de navegação esquerdo, em Privileged Identity Management, selecione **funções do Azure AD**.
1. No painel de navegação esquerdo, selecione **Minhas funções**.  Agora você está vendo informações sobre as funções do Azure AD.  Você verá que você, Diogo, recebeu a função Administrador de usuários.  
1. Na última coluna da tabela, chamada ação, selecione **Ativar**.
1. Você verá um ícone de aviso indicando que é necessário fazer uma verificação adicional.  Selecione **Clicar para continuar**.  Lembre-se de que as configurações do PIM para a função Administrador de usuários exigem a autenticação multifator.  Além disso, como as informações de contato de Diego para uso com MFA (métodos de autenticação) não foram configuradas anteriormente, ele deve registrar suas informações para poder usar o MFA.  Embora ele tenha que fazer o MFA sempre que entrar como administrador de usuário, dentro do período de atribuição, o processo de registro do MFA é necessário apenas uma vez.
1. Você é notificado de que mais informações são necessárias. Selecione **Avançar**.
1. Digite sua senha, **SC900-Lab**.
1. No canto inferior esquerdo da janela do Microsoft Authenticator, selecione **Quero configurar um método diferente**.
1. Você precisará escolher outro método.  Ao lado de onde diz Authenticator app, selecione a tecla de seta para baixo.   Selecione **Telefone** e depois **Confirmar**.
1. Você precisará inserir um número de telefone que deseja usar. Verifique se o país está correto para o código do país do seu número de telefone.  Digite o seu número de telefone, garanta que **Envie-me um código por mensagem** esteja selecionado, e depois escolha **Avançar**.
1. Digite o código de 6 dígitos que você recebeu em seu telefone e selecione **Avançar**.
1. Você verá uma notificação indicando que o seu telefone foi registrado com sucesso. Selecione **Avançar** e depois, **Concluído**.
1. Você responderá se deseja permanecer conectado.  Selecione **Sim**.
1. A janela Ativar administrador do usuário é exibida.  Você deve inserir um motivo para a ativação.  Na caixa que aparece, digite o motivo desejado (máximo de 500 caracteres) e escolha **Ativar**.
1. Você verá o status (três fases de progresso), conforme a ativação é processada.
1. Depois que a ativação for concluída, você voltará à página Minhas funções | Funções do Azure AD, em que verá uma notificação informando que uma função foi ativada.  Selecione **Clique aqui** para ver suas funções ativas.  Se você perceber que o horário de término é diferente do que foi configurado originalmente, selecione a tecla de atualização na parte superior da página (pode levar alguns minutos para atualizar).
1. Selecione o **X** no canto superior direito da tela para fechar a janela.
1. Feche o Azure Active Directory Privileged Identity Management | Inicie rapidamente a janela selecionando o **X** no canto superior direito da tela.
1. Feche a janela Identity Governance escolhendo o **X** no canto superior direito da tela.
1. Agora você está novamente na página Contoso – Azure Active Directory.  Como um administrador de usuário do Azure AD, você pode criar usuários e grupos, gerenciar licenças e muito mais.   No painel de navegação esquerdo selecione **Usuários**.
1. Na lista de usuários, selecione **Bianca Pisani**.
1. No painel de navegação esquerdo selecione **Licenças**.
1. Observe que a Bianca não tem licenças atribuídas.  Na parte superior da página, selecione **+ Atribuições**.
1. Na lista de licenças selecionadas, selecione **Office 365 E3** e **Windows 10 Enterprise E3**.
1. Na parte inferior da página, selecione **Salvar**.  Você verá uma breve notificação no canto superior direito da página indicando que as licenças foram atribuídas com sucesso.
1. Feche a página de atribuições de licença atualizada, escolhendo o **X** no canto superior direito da página.
1. Saia selecionando o ícone do usuário próximo ao endereço de email no canto superior direito da tela e selecionando **Sair**. Em seguida, feche todas as janelas do navegador.
1. A duração da função de administrador do usuário é limitada ao tempo para o qual foi configurada.

### <a name="review"></a>Revisão

Neste laboratório, você explorou o PIM.  Você, como administrador, configurou Diego com privilégios de administrador de usuário por um determinado período de tempo.  Depois, como Diego, você percorreu o processo de ativação dos privilégios de administrador do usuário e a definição das configurações do usuário.  Lembre-se de que o PIM requer licenciamento P2 do Azure AD Premium.
