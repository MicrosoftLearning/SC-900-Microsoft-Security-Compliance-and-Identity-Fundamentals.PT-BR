<a name="---"></a><!---
---
Laboratório: Título: 'Configuração'
---
--->

# <a name="lab-setup"></a>Laboratório: Instalação

## <a name="lab-scenario"></a>Cenário do laboratório

Esse laboratório de instalação consiste em habilitar o Log de Auditoria da Microsoft.

**Tempo estimado**: 5-10 minutos

### <a name="setup---enable-microsoft-365-audit-log"></a>Configuração – Habilitar o log de auditoria do Microsoft 365

Nesta tarefa de configuração, você ativará o recurso de log de auditoria no Microsoft 365.  Embora a documentação indique que o log de auditoria é ativado por padrão, a maioria dos locatários de laboratório não tem este recurso habilitado e pode levar horas para que esta alteração entre em vigor.  Ativar este recurso é benéfico porque o Microsoft 365 usa logs de auditoria para insights de usuário e atividades identificadas nas políticas e nos insights analíticos.

1. Abra o Microsoft Edge. Na barra de endereços, insira **admin.microsoft.com**.

1. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é sua ID de locatário exclusiva fornecida pelo provedor de hospedagem de laboratório) e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem de laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**. Vamos ser direcionados à página Centro de administração do Microsoft 365.

1. À esquerda no painel de navegação do Centro de administração do Microsoft 365, selecione **Mostrar todos**.

1. Em Centros de administração, selecione **Conformidade**.  A página inicial do centro de conformidade do Microsoft 365 vai ser aberta no navegador.  

1. Do lado esquerdo do painel de navegação, em soluções, selecione **Auditoria**.  Observação: a funcionalidade de auditoria também pode ser acessada pela página inicial do Microsoft 365 Defender (anteriormente chamado de Central de segurança do Microsoft 365).

1. Verifique se a guia **Pesquisa** está selecionada (sublinhada).

1. Após abrir a página Auditoria, aguarde de 2 a 3 minutos.  Se a Auditoria NÃO estiver habilitada, você vai ver uma barra azul no topo da página dizendo começar a registrar atividade de usuário e administrador.  Selecione **Começar a registrar atividade de usuário e administrador**.  Se for solicitada a confirmação de que a configuração da organização precisa ser atualizada, selecione **Sim**. Quando a auditoria estiver habilitada, a barra azul desaparece.  Se a barra azul não aparecer, é porque a auditoria já está habilitada e não é necessário realizar nenhuma ação adicional.  Outra forma de verificar se a auditoria está ativada é pelo PowerShell, mas ela está fora do escopo deste curso.

1. Volte à página inicial do centro de conformidade do Microsoft 365 selecionando **Página Inicial** à esquerda no painel de navegação.

### <a name="review"></a>Revisão

Nesta configuração, você também ativou o recurso de log de auditoria no Microsoft 365.
