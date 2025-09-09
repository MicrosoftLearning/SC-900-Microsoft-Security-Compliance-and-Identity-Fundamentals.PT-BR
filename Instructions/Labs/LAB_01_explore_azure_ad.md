---
lab:
  title: Explorar as configurações de usuário do Microsoft Entra ID
  module: Describe the function and identity types of Microsoft Entra ID
---

# Laboratório: Explorar as configurações de usuário do Microsoft Entra ID

Esse laboratório é mapeado para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descreva as funcionalidades do Microsoft Entra.
- Módulo: descreva os tipos de função e identidade do Microsoft Entra ID.
- Unidade: descreva os tipos de identidades.

## Cenário do laboratório

Neste laboratório, você acessará o Microsoft Entra ID (anteriormente conhecido como Azure Active Directory).  Além disso, você vai criar um usuário e definir configurações diferentes, incluindo a adição de licenças.  

**Tempo estimado**: 45 minutos

### Tarefa 1

Como assinante do Microsoft 365, você já está usando o Microsoft Entra ID.  Nesta tarefa, você aprenderá a criar um novo usuário no Microsoft Entra ID e conhecerá alguns dos serviços que podem ser gerenciados no nível do usuário.

1. Se você tiver a guia centro de administração do Microsoft 365 aberta do exercício anterior, em centros de administração, selecione **Identidade**
1. Se o centro de administração do Microsoft 365 já estiver aberto no navegador, do exercício anterior, pule para a próxima etapa, caso contrário, acesse o centro de administração da Microsoft da seguinte maneira:
    1. Na barra de endereços, insira **`https://admin.microsoft.com`** e entre com as credenciais do Microsoft 365 fornecidas pelo seu ALH (hoster de laboratório autorizado).
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é a sua ID de locatário exclusiva fornecida pelo ALH) e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Dependendo do host do laboratório e se esta for a primeira vez que você está fazendo logon no locatário, pode ser que seja solicitado a concluir o processo de registro de MFA. Se este for o caso, siga as instruções na tela para configurar a MFA.
    1. Depois de entrar, você será levado para a página do Centro de administração do Microsoft 365.

1. Em Centros de administração, selecione **Identidade** (talvez seja necessário selecionar **Mostrar tudo** e rolar para baixo).  Uma nova página do navegador é aberta para a página de visão geral do Centro de administração do Microsoft Entra.  Se for solicitado que você configure a MFA, siga as etapas na tela.

1. No painel de navegação esquerdo, selecione **Usuários**.  Isso irá levar você para a página de usuários. **Todos os usuários** já devem estar selecionados. Observe que o seu locatário já está configurado com usuários.

1. Na parte superior da página, selecione **+ Novo usuário** e, na caixa suspensa, escolha **Criar usuário**.

1. Agora você está na guia de **noções básicas** da página Criar novo usuário. Preencha os campos da seguinte maneira:
    1. Nome UPN: **sara**.

    1. Apelido de email: deixe o padrão, que é definido para derivar do nome UPN.

    1. Nome de exibição: **Sara Perez**.

    1. Senha: desmarque a caixa que diz gerar senha automaticamente e insira uma senha temporária que adere aos requisitos de senha e anote-a, pois você precisará dela para concluir a tarefa subsequente.

    1. Conta habilitada: deixe a marca de seleção para garantir que a conta esteja habilitada.

    1. Na parte inferior da página, selecione **Avançar: Propriedades**.

1. Aqui, você configurará alguns dos campos na guia **Propriedades**.

    1. Nome: Sara

    1. Sobrenome: Perez

    1. Tipos de usuário: deixe o padrão como **Membro**, mas observe que, na lista suspensa, você tem a opção de selecionar Convidado.

    1. Local de uso: escolha o país/região onde você está localizado.  Observe que, para acessar o campo local de uso, você precisará rolar para baixo na página, pois ele é o último campo na página.  **OBSERVAÇÃO**: se você não fizer isso, não poderá atribuir uma licença em uma etapa subsequente.

    1. Selecione **Avançar: Atribuições**.

1. Agora você está na guia **Atribuições**, em que você adiciona uma atribuição de grupo e exibe as opções disponíveis para adicionar uma função.

    1. Selecione **Adicionar grupo**.

    1. A janela que é aberta mostra todos os grupos disponíveis.  

    1. Obter a lista dos grupos disponíveis.  Na lista, selecione **Operações**.  Na parte inferior da página, use o botão **Selecionar**.  Pode levar alguns segundos, mas você deverá ver a exibição do grupo de operações na página de atribuições.

    1. Na parte superior da página, selecione **+ Adicionar função**.  Uma janela é aberta que mostra todas as funções de diretório disponíveis.  Exiba as opções disponíveis, mas não adicione novas funções.  Feche essa página selecionando o **X** no canto superior direito da página de funções do diretório.
    1. Na parte inferior da página, selecione **Examinar + criar**. Um resumo das configurações será exibido.  Na parte inferior dessa página, clique em **Criar**.

1. Você será retornado à página de usuários.  Depois de alguns segundos, Sara Perez será listada.  Talvez seja necessário selecionar o ícone de **atualização** na parte superior da página.

1. Na lista de usuários, selecione o usuário que você criou, **Sara Melo**.  A página **Visão geral** é aberta.

1. O painel de navegação esquerdo mostra as várias opções que podem ser configuradas para o usuário. Exibir as opções disponíveis.

1. No painel de navegação à esquerda, selecione **Licenças**.  Observe que não há atribuições de licença encontradas para esse usuário, observe também o ícone de aviso que diz: "Adicionar, remover e reprocessar atribuições de licenciamento só está disponível no Centro de Administração do M365".  Você vai fazer isso na próxima tarefa.  OBSERVAÇÃO: as licenças só poderão ser atribuídas se um local de uso tiver sido configurado. Se você não definiu o local de uso, volte para essa etapa agora.

### Tarefa 2

Nesta tarefa, você atribuirá uma licença ao usuário que acabou de criar, usando o Centro de administração do Microsoft 365.

1. Abra a guia do navegador **Página Inicial – Centro de administração do Microsoft 365**.

1. No painel de navegação esquerdo, selecione **Usuários ativos**.  Na lista de usuários, selecione **Sara Perez**.  Uma janela é aberta mostrando informações sobre o usuário.  

    1. Selecione a guia **Licença e aplicativos**.
    1. Para cada uma das licenças listadas, você verá o número de licenças disponíveis.  Como não há licenças disponíveis do Microsoft 365 E5 (elas já foram atribuídas a outros usuários), atribua a licença do **Desenvolvedor Microsoft Power Apps** marcando a caixa de seleção ao lado delas.
    1. Selecione **Salvar alterações**. Uma notificação no canto superior direito da tela deve mostrar que as atribuições de licença foram bem-sucedidas.
    1. Feche a página selecionando o **X** no canto superior direito da página.

1. Você atribuiu uma licença com êxito ao usuário.

1. Saia de todas as guias abertas do navegador. Saia do serviço selecionando o ícone de usuário próximo ao endereço de email no canto superior direito da tela e selecionando **Sair**. Feche todas as janelas do navegador.

### Tarefa 3

Nesta tarefa, você se conectará como Sara Melo pela primeira vez.

1. Abra o Microsoft Edge.

1. Na barra de endereços, insira **`https://login.microsoft.com`** .

1. Entre como **sara@WWLxZZZZZ.onmicrosoft.com** , (em que ZZZZZZ é a sua ID de locatário exclusiva fornecida pelo seu ALH)
1. Insira a senha temporária que você definiu na tarefa anterior.

1. Você é solicitado a atualizar sua senha. No campo Senha atual, insira a senha temporária da tarefa anterior.

1. No campo Nova senha, insira uma nova senha, confirme a senha e selecione **Entrar**.  Anote sua nova senha, pois você precisará dela para o exercício de laboratório subsequente na SSPR.

1. Como esta é a primeira vez que você está fazendo login como Sara Perez, poderá ser solicitado que configure a MFA. Siga as instruções na tela para configurar a MFA.

1. Agora você conseguirá entrar na conta Microsoft de Sara.  Note que a licença de Sara que você atribuiu na tarefa anterior era limitada apenas ao Power Apps para Desenvolvedores e não incluiu uma licença para o E5.

1. Para sair, selecione o email de Sara na parte inferior do painel de navegação esquerdo, selecione **Sair** e feche o navegador.

### Revisão

Neste laboratório, você começou sua exploração inicial do Microsoft Entra ID. Como os assinantes do Microsoft 365 estão usando o Microsoft Entra ID automaticamente, você descobriu que pode acessar os recursos e serviços do Microsoft Entra ID pelo Portal de administração do Microsoft 365 ou pelo Portal do Azure.  Seja qual for a abordagem que você preferir para chegar ao mesmo lugar.  Você também passou pelo processo de criação de um usuário, além das diferentes configurações que podem ser definidas, incluindo os grupos aos quais o usuário pode ser atribuído, a disponibilidade de funções e a atribuição de licenças de usuário.
