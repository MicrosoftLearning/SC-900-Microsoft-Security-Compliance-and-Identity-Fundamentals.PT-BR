<!---
---
Demonstração: Título: 'Redefinição de senha self-service (SSPR) do Microsoft Entra' Roteiro de Aprendizagem/Módulo/Unidade: 'Roteiro de Aprendizagem: descrever as capacidades do Microsoft Entra; Módulo 2: descrever as capacidades de autenticação do Microsoft Entra ID; Unidade 4: descrever a redefinição de senha self-service'
---
--->

# Demonstração: redefinição de senha self-service (SSPR) do Microsoft Entra

Essa demonstração é mapeada para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as capacidades do Microsoft Entra
- Módulo: descrever as capacidades de autenticação do Microsoft Entra ID
- Unidade: descrever a redefinição de senha self-service

## Cenário de demonstração

Nesta demonstração, você verá as várias configurações associadas à habilitação da redefinição de senha por autoatendimento.

1. Volte para a guia aberta do navegador intitulada "Página Inicial-Centro de administração do Microsoft Entra".  Se tiver fechado previamente essa guia do navegador, abra o Microsoft Edge e faça logon em **[entra.microsoft.com](https://entra.microsoft.com)** com suas credenciais de administrador do Microsoft 365.

1. No painel de navegação à esquerda, expanda **Proteção** e selecione **Redefinição de senha**.

1. A guia Propriedades está realçada.  Na janela Propriedades, observe que o SSPR pode ser habilitado para Nenhum, Selecionar ou Tudo.
    1. Coloque o cursor sobre o ícone de informações ao lado de onde está escrito "Redefinição de senha self-service habilitada" e observe que você pode escolher "Selecionado" para restringir a redefinição de senha a um grupo limitado de usuários em vez de selecionar nenhum ou todos.
    1. Posicione o cursor sobre o ícone de informações ao lado de "selecionar grupo" e ressalte que aqui é onde você identifica o grupo de usuários que tem permissão para redefinir as respectivas senhas.   Você precisa incluir usuários em um grupo, não é possível selecionar usuários individualmente.  Além disso, se você alterar o grupo, o grupo selecionado substituirá o grupo listado no momento.  Portanto, é recomendável que você adicione os usuários ao grupo da SSPR.
    1. Observe a caixa de informações azul claro e ressalte para os alunos – Essas configurações só se aplicam aos usuários finais na sua organização. Os administradores estão sempre habilitados para a redefinição de senha por autoatendimento e devem usar dois métodos de autenticação para redefinir a própria senha.

1. No painel de navegação à esquerda de Redefinição de senha, selecione Métodos de autenticação.
    1. Coloque o cursor sobre o ícone de informações ao lado de onde está escrito "Número de métodos necessários para redefinir".  Ressalte que isso define o número de métodos alternativos de identificação que um usuário neste diretório precisa ter para redefinir sua senha.   Não altere a configuração.
    1. Ressalte os diferentes "métodos disponíveis para usuários", incluindo o ponto de que o SSPR aceita perguntas de segurança. Selecione Perguntas de segurança para mostrar as opções para o uso de perguntas de segurança. Depois de falar sobre as opções, volte e selecione Perguntas de segurança para remover a marca de seleção.

1. No painel de navegação esquerdo de Redefinição de senha, selecione Registro.
    1. Passe o mouse sobre o ícone de informações ao lado de onde está escrito: "Exigir que os usuários se registrem ao fazer login".   Enfatize isso para os usuários.  
    1. Posicione o mouse sobre o ícone de informações ao lado de “Número de dias antes que os usuários precisem confirmar novamente as informações de autenticação”.   Enfatize isso para os usuários.  

1. No painel de navegação esquerdo de Redefinição de senha, selecione Notificações.  Enfatize as duas configurações – passe o mouse sobre o ícone de informações para a descrição.

1. Observe como o painel de navegação Redefinição de senha também inclui opções para exibir logs de auditoria e Uso e insights.

1. Selecione X no canto superior direito da página. Isso retorna à página principal do locatário da Contoso.

1. Deixe esta página do navegador aberta para a próxima demonstração.

### Revisão

Nesta demonstração, você mostrou as várias configurações associadas à redefinição de senha self-service.
