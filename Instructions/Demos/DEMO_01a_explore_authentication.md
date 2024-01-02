<!---
---
Demonstração: Título: 'Explorar as configurações de Usuário do Microsoft Entra ID' Roteiro de Aprendizagem/Módulo/Unidade: 'Roteiro de Aprendizagem: descrever as capacidades do Microsoft Entra; Módulo 2: descrever as capacidades de autenticação do Microsoft Entra ID; Unidade 3: descrever os métodos de autenticação e Unidade 4: descrever a autenticação multifator'
---
--->

# Demonstração: métodos de autenticação e MFA

Essa demonstração é mapeada para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as capacidades do Microsoft Entra.
- Módulo: descrever as capacidades de autenticação do Microsoft Entra ID.
- Unidades: descrever os métodos de autenticação e a autenticação multifator.

## Cenário de demonstração

Nesta demonstração, você explorará as várias configurações disponíveis para autenticação no Microsoft Entra.

1. Retorne à guia do navegador aberta com o título "Centro de Administração Microsoft Entra."  Se tiver fechado previamente essa guia do navegador, abra o Microsoft Edge e faça logon em **[entra.microsoft.com](https://entra.microsoft.com)** com suas credenciais de administrador do Microsoft 365.

1. No painel de navegação à esquerda, expanda **Proteção** e selecione **Métodos de autenticação**.

1. Selecionar métodos de autenticação exibe a página de políticas.  Aqui você verá os métodos de autenticação disponíveis e se eles estão habilitados.  Examinaremos alguns desses métodos:.  
    1. Selecione **SMS**.  Leia a descrição na parte superior da página: "Este método de autenticação entrega um código único via SMS para o telefone do usuário, e o usuário então insere esse código para fazer a entrada. O SMS pode ser utilizado para autenticação multifator e redefinição de senha self-service; ele também pode ser configurado para ser utilizado como um primeiro fator."
        1. Um ponto a ser chamado a atenção aqui é que alguns métodos de autenticação podem ser utilizados para MFA e/ou SSPR.  Alguns podem ser utilizados apenas como uma forma primária de autenticação, enquanto outros podem ser utilizados apenas como uma forma secundária de autenticação.
        1. Para configurar um determinado método de autenticação, você precisa habilitá-lo e, em seguida, direcionar quais usuários e/ou grupos devem ser incluídos.  Você também pode selecionar os grupos a serem excluídos.
        1. Não altere todas as configurações.  Para sair da página de configurações de SMS, selecione o **X** no canto superior direito da página.  
    1. Vamos dar uma olhada nas configurações da chamadas de voz.  Selecione **Chamada de Voz** e, na descrição, você pode ver uma diferença importante.  As chamadas de voz não podem ser usadas como um método de autenticação de primeiro fator.
    1. Agora, selecione **Microsoft Authenticator**.  Esse é o principal método de autenticação.  
        1. Aqui você deve habilitar os recursos e direcionar quem deve ser incluído.  Você pode fazer isso com todos os usuários ou grupos. Uma vez identificados os usuários/grupos a serem incluídos, você pode identificar os grupos específicos a serem excluídos.  
        1. Na guia **Configurar**, você pode selecionar se um recurso específico deve ser gerenciado pela Microsoft. Essa configuração é uma maneira conveniente de uma organização permitir que a Microsoft habilite ou desabilite um recurso por padrão. Isso pode ajudar uma organização a melhorar sua postura de segurança.
        1. Não altere todas as configurações. Feche a página, selecionando o **X** no canto superior direito da página.
 
1. Agora vamos dar uma olhada na proteção por senha. Selecione **Proteção por Senha**.  Observe que diferentes parâmetros de configuração estão disponíveis.  
    1. Selecione o ícone de informações ao lado de **Limite de bloqueio** para exibir o significado desse parâmetro.  Atualmente, ele está definido como 10, o que significa que pode haver até 10 entradas que falharam antes que a conta seja bloqueada.  Parece um pouco alto, portanto, você pode definir um valor diferente.
    1. Selecione o ícone de informações para cada um dos diferentes parâmetros e fale brevemente com ele.  Você desejará chamar a atenção principalmente para a lista de senhas proibidas personalizadas.

1. Os pontos fortes da autenticação são um controle de Acesso Condicional que permite que os administradores especifiquem qual combinação de métodos de autenticação pode ser utilizada para acessar um recurso. Você verá isso em Acesso condicional.

1. No painel de navegação à esquerda dos Métodos de autenticação, selecione **Atividade**.
    1. O **Registro** é mostrado com um sublinhado azul.  Aqui você pode exibir a atividade de registro para diferentes métodos de autenticação.
    1. Selecione **Uso** para exibir os detalhes de uso e observe que você pode adicionar diferentes filtros.

1. Neste módulo, você também falou sobre autenticação multifator. Você abordará mais sobre a MFA na demonstração sobre acesso condicional, mas talvez deseje dedicar um minuto para mostrar algumas configurações básicas.  No painel de navegação do centro de Administração do Microsoft Entra, selecione **Autenticação multifator**.  Talvez seja necessário selecionar **Mostrar mais** na seção Proteção, no painel de navegação à esquerda.
    1. Na página **Introdução**, ele mostra que a melhor maneira de aplicá-lo aos usuários é por meio do acesso condicional, mas existem algumas configurações específicas que você deve configurar aqui.
    1. Selecione **Bloqueio de conta** e chame os parâmetros de bloqueio configuráveis.
    1. Selecione **Bloquear/desbloquear usuários** e chame a atenção para o fato de que é aqui que um administrador pode bloquear/desbloquear usuários manualmente.  Observe que um usuário bloqueado permanecerá bloqueado por 90 dias, a menos que seja desbloqueado manualmente.
    1. Selecione **Alerta de fraude**.  Isso permite que os administradores permitam os usuários a relatar fraudes se receberem uma solicitação de verificação em duas etapas que não foi iniciada por eles.
    1. Selecione **Notificações**.  Você deve configurar o Microsoft Entra para enviar notificações por email quando os usuários relatarem alertas de fraude. Essas notificações normalmente são enviadas aos administradores de identidades, porque é provável que as credenciais da conta do usuário estejam comprometidas.
    1. Feche a página selecionando o **X** no canto superior direito das janelas.  Em seguida, repita essa etapa para voltar ao centro de administração Microsoft Entra.

1. Mantenha a guia do navegador aberta, pois você retornará ao centro de administração Microsoft Entra para a próxima demonstração.

### Revisão

Nesta demonstração, você mostrou os métodos de autenticação disponíveis no Microsoft Entra.  Você também mostra alguns dos parâmetros configuráveis associados à autenticação multifator.
