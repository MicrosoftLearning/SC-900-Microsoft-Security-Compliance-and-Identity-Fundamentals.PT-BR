<a name="---"></a><!---
---
Demonstração: Título: 'SSPR (redefinição de senha self-service) do Azure AD' Roteiro de aprendizagem/Módulo/Unidade: 'Roteiro de aprendizagem: descrever as funcionalidades do Azure AD (Active Directory), parte do Microsoft Entra; Módulo 2: descrever as funcionalidades de autenticação do Azure AD; Unidade 4: descrever a redefinição de senha self-service no Azure AD'
---
--->

# <a name="demo-azure-ad-self-service-password-reset-sspr"></a>Demonstração: SSPR (redefinição de senha self-service do Azure AD)

Essa demonstração é mapeada para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades do Azure AD (Azure Active Directory), parte do Microsoft Entra
- Módulo: descrever as funcionalidades de autenticação do Azure AD
- Unidade: descrever a redefinição de senha self-service no Azure AD

## <a name="demo-scenario"></a>Cenário da demonstração

Nesta demonstração, você verá as várias configurações associadas à habilitação da redefinição de senha por autoatendimento.

1. Vá para a guia Contoso – Microsoft Azure aberta no seu navegador. Se você fechou a guia anteriormente, abra uma página do navegador e, na barra de endereços, insira portal.azure.com e selecione Azure Active Directory. Você deve estar conectado como administrador no portal do Azure; caso contrário, entre novamente.

1. No painel de navegação esquerdo, selecione Redefinição de senha.

1. A guia de propriedades é realçada.  Na janela Propriedades, observe que o SSPR pode ser habilitado para Nenhum, Selecionar ou Todos.
    1. Coloque o cursor sobre o ícone de informações próximo a “Redefinição de senha self-service habilitada” e destaque que você pode escolher “Selecionado” para restringir a redefinição de senha a um grupo limitado de usuários, em vez de selecionar Nenhum ou Todos.
    1. Coloque o cursor sobre o ícone de informações próximo a “selecionar grupo” e destaque que é aqui que você identifica o grupo de usuários que têm permissão para redefinir as próprias senhas.   Você deve incluir usuários no grupo. Não é possível selecionar usuários individualmente.  Além disso, se você alterar o grupo, o grupo selecionado substituirá o grupo listado atualmente.  Portanto, é recomendável que você adicione os usuários ao grupo da SSPR.
    1. Observe a caixa de informações em azul-claro e a destaque aos alunos. Essas configurações se aplicam apenas aos usuários finais em sua organização. Os administradores estão sempre habilitados para a redefinição de senha por autoatendimento e devem usar dois métodos de autenticação para redefinir a própria senha.

1. No painel de navegação esquerdo da Redefinição de senha, selecione Métodos de autenticação.
    1. Coloque o cursor sobre o ícone de informações ao lado de “Número de métodos necessários para redefinir”.  Destaque o fato de que isso define o número de métodos alternativos de identificação que um usuário nesse diretório deve ter para redefinir a senha.   Não altere a configuração.
    1. Destaque os diferentes “métodos disponíveis para os usuários”, incluindo o ponto de que o SSPR é compatível com perguntas de segurança. Selecione Perguntas de segurança para exibir as opções de uso de perguntas de segurança. Depois de falar sobre as opções, volte e selecione Perguntas de segurança para remover a marca de seleção.

1. No painel de navegação esquerdo da Redefinição de senha, selecione Registro.
    1. Passe o mouse sobre o ícone de informações ao lado de “Exigir que os usuários se registrem ao entrar”.   Destaque isso para os usuários.  
    1. Posicione o mouse sobre o ícone de informações ao lado de “Número de dias antes que os usuários precisem confirmar novamente as informações de autenticação”.   Destaque isso para os usuários.  

1. No painel de navegação esquerdo da Redefinição de senha, selecione Notificações.  Destaque as duas configurações. Passe o mouse sobre o ícone de informações para ver a descrição.

1. Observe como o painel de navegação de redefinição de senha também inclui opções para exibir logs de auditoria e Uso e insights.

1. Selecione o X no canto superior direito da página. Isso o leva de volta à página principal do locatário da Contoso.

1. Deixe esta página do navegador aberta para a próxima demonstração.

### <a name="review"></a>Revisão

Nesta demonstração, você mostrou as configurações associadas à redefinição de senha self-service.
