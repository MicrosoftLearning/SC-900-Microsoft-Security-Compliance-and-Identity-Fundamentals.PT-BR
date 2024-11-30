---
lab:
  title: Acesso Condicional do Microsoft Entra.
  module: Describe the access management capabilities of Microsoft Entra
---

# Laboratório: Acesso condicional do Microsoft Entra

Esse laboratório é mapeado para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as capacidades do Microsoft Entra
- Módulo: descrever as funcionalidades de gerenciamento de acesso do Microsoft Entra
- Unidade: Descrever o acesso condicional

## Cenário do laboratório

Neste laboratório, você vai explorar a MFA de acesso condicional, da perspectiva de um administrador e de um usuário.  Como administrador, você criará uma política que exigirá que usuários passem pela autenticação multifator ao acessar os portais de administração da Microsoft.  Da perspectiva de um usuário, você verá o impacto da política de acesso condicional, incluindo o processo de registro para a MFA.

**Tempo estimado**: 30 minutos

### Tarefa 1

Nesta tarefa você, como administrador, irá redefinir a senha para a usuária Debra Berger.  Esta etapa é necessária para que você possa inicialmente fazer logon como o usuário em tarefas subsequentes.

1. Abra o Microsoft Edge.  Na barra de endereços, insira **https://entra.microsoft.com** e entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é a sua ID de locatário exclusiva fornecida pelo provedor de hospedagem do laboratório) e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Dependendo do host do laboratório e se esta for a primeira vez que você está fazendo logon no locatário, pode ser que seja solicitado a concluir o processo de registro de MFA. Se este for o caso, siga as instruções na tela para configurar a MFA.
    1. Depois de entrar, você será levado para a página do Centro de administração do Microsoft 365.

1. No painel de navegação à esquerda, expanda **Identidade**, expanda **Usuários** e selecione **Todos os usuários**.

1. Selecione **Debra Berger** na lista de usuários.

1. Selecione **Redefinir senha** na parte superior da página. Como você não fez logon anteriormente como Clara Barbosa, você não sabe a senha dela e precisará redefini-la.

1. Quando a janela de redefinição de senha abrir, selecione **Redefinir senha**.  IMPORTANTE: anote a nova senha, pois você precisará dela em uma tarefa posterior, para entrar como o usuário.

1. Feche a janela de redefinição de senha selecionando o **X** no canto superior direito da página e a janela Clara Barbosa selecionando o **X** no canto superior direito da página.

1. No painel de navegação à esquerda, selecione **Página Inicial** para voltar ao centro de administração do Microsoft Entra.

1. Mantenha essa janela aberta.

### Tarefa 2

Nessa tarefa, você passará pelo processo de criação de uma política de acesso condicional no Microsoft Entra ID.

1. Abra a guia do navegador na home page do centro de administração do Microsoft Entra.   Se você fechou a guia do navegador anteriormente, abra o Microsoft Edge, insira **`https://entra.microsoft.com`** na barra de endereços e entre com as credenciais de administrador do Microsoft 365 fornecidas pelo ALH.

1. No painel de navegação à esquerda, expanda **Proteção** e selecione **Acesso Condicional**.

1. A página de visão geral do acesso condicional é exibida. Quando você acessa a página de visão geral, a guia **Introdução** é selecionada (sublinhada). Selecione a guia **Visão geral**. Aqui, você verá blocos mostrando o resumo da política e os alertas gerais.  No painel de navegação à esquerda, selecione **Políticas**.

1. No painel de navegação à esquerda, selecione **Políticas**. Todas as políticas de acesso condicional existentes são listadas aqui. Selecione **+ Nova política**.

1. No campo Nome, insira **Bloquear portais de administração**.

1. Em Usuários, selecione **0 usuários e grupos escolhidos**.

1. Agora você verá a opção Incluir ou Excluir usuários ou grupos.  Verifique se a guia **Incluir** está selecionada (sublinhada).

1. Selecione a opção **Selecionar usuários e grupos** e selecione **Usuários e grupos**.  A janela Selecionar usuários ou grupos é aberta.  

1. Na barra Pesquisa, insira **Debra**.  Selecione **Debra Berger** abaixo da barra de pesquisa e pressione o botão **Selecionar** na parte inferior da página.  Observe que uma prática comum é atribuir a política aos usuários de um grupo.  Para fins de conveniência neste laboratório, atribuiremos a política a um usuário específico.

1. Em Recursos de destino, selecione **Nenhum recurso de destino selecionado**.

1. No campo abaixo do texto **Selecionar ao que essa política se aplica**, escolha a seta para baixo e observe as opções disponíveis.  Mantenha a configuração padrão **Aplicativos de nuvem**.  Verifique se a guia **Incluir** está sublinhada.  Escolha **Selecionar aplicativos** e, abaixo de **Selecionar**, escolha **Nenhum**.  A janela para Selecionar aplicativos na nuvem é aberta.

1. Clique em **Portais de Administração da Microsoft** e pressione **Selecionar** na parte inferior da página.  Observe o aviso.  

1. Em Rede, selecione **Qualquer rede ou local**.  Revise as opções, mas não selecione nenhuma.

1. Em Condições, selecione **0 condições selecionadas**.  Observe as diferentes opções que você pode configurar.  Por meio da política, você pode controlar o acesso do usuário com base nos sinais das condições, incluindo: risco do usuário, risco de entrada, plataforma do dispositivo, localização, aplicativos cliente ou filtrar dispositivos.  Explore essas opções configuráveis, mas não defina nenhuma condição.

1. Agora você definirá os controles de acesso.  Em Concessão, selecione **0 controles selecionados**.

1. A janela Conceder é aberta.  Seleione **Bloquear acesso**. Pressione **Selecionar** na parte inferior da página.

1. Na parte inferior da página, em Habilitar política, selecione **Ativado** e **Criar**.

1. No painel de navegação à esquerda, selecione **Políticas**. A política **Bloquear portais de administração** será exibida na lista de políticas de acesso condicional (se necessário, selecione o **ícone de Atualizar** na barra de comando na parte superior da página).

1. Saia selecionando o ícone do usuário ao lado do endereço de email no canto superior direito da tela e selecionando **Sair**. Em seguida, feche todas as janelas do navegador.

### Tarefa 3

Nesta tarefa, você verá o impacto da política de acesso condicional da perspectiva do usuário, Clara Barbosa. Você começará entrando em um aplicativo que não está incluído na política de acesso condicional (o portal do Microsoft 365 em https://login.microsoftonline.com) ).  Em seguida, você vai repetir o processo para um aplicativo incluído na política de acesso condicional (o portal do Azure em https://portal.azure.com) ).  Lembre-se de que a política bloqueia o acesso de qualquer um dos Portais de administração da Microsoft, incluindo o portal do Azure.  OBSERVAÇÃO: por motivos de segurança, todas as contas de usuário que acessam qualquer portal devem a usar a MFA.  O requisito da MFA é independente deste exercício de laboratório.

1. Abra o Microsoft Edge.  Na barra de endereços, insira **https://login.microsoftonline.com** .
    1. Entre como **DebraB@WWLxZZZZZZ.onmicrosoft.com**, (em que ZZZZZZ é a sua ID de locatário exclusiva fornecida pelo provedor de hospedagem do laboratório) e selecione **Próximo**.
    1. Digite a senha que você anotou na tarefa anterior. Selecione **Entrar**.
    1. Como a senha fornecida quando você, como administrador, a redefiniu é temporária, é preciso atualizar a senha. Insira a senha atual, insira uma nova senha e confirme a nova senha.  Anote a nova senha, pois você vai precisar dela para concluir a tarefa.
    1. Como esta é a primeira vez que você está fazendo login como Débora Borges, poderá ser solicitado que você configure a MFA. Siga as instruções na tela para configurar a MFA.
    1. Quando solicitado a permanecer conectado, selecione **Sim**.  Você deve se conectar com êxito à sua conta do Microsoft 365.

1. Agora você tentará entrar em um aplicativo que atende aos critérios da Política de acesso condicional. Abra uma nova guia do navegador e insira **https://portal.azure.com**, que é o portal de administração do Azure.  Uma janela pop-up aparecerá indicando "Você não tem acesso".  Isso é resultado da política de acesso condicional que bloqueia o seu acesso a todos os portais de administração da Microsoft.

1. Desconecte-se escolhendo o ícone do usuário ao lado do endereço de email no canto superior direito da tela e selecionando Sair. Em seguida, feche todas as janelas do navegador.

### Revisão

Neste laboratório, você passou pelo processo de configuração de uma política de acesso condicional que bloqueia o acesso de todos os usuários incluídos na política aos portais de administração da Microsoft.  Em seguida, como usuário, você sofreu o impacto da política de acesso condicional ao acessar o portal do Azure.
