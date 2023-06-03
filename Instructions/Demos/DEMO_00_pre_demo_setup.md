<a name="---"></a><!---
---
Configuração de pré-demonstração: Título: 'Instalação de demonstração'
---
--->

## <a name="pre-demo-setup"></a>Configuração antes da demonstração

Esta configuração consiste em habilitar o Log de Auditoria da Microsoft.

### <a name="setup---enable-microsoft-365-audit-log"></a>Configuração – Habilitar o log de auditoria do Microsoft 365

Nesta tarefa de configuração, você habilitará a funcionalidade de log de auditoria do Microsoft 365.  Embora a documentação indique que o log de auditoria está ativado por padrão, a maioria dos locatários do laboratório não tem este recurso habilitado e pode levar horas para que isso entre em vigor.  É útil habilitar este recurso, porque o Microsoft 365 usa os logs de auditoria para os insights de usuário e as atividades identificadas nas políticas e nos insights de análise.

1. Abra o Microsoft Edge. Na barra de endereços, insira **admin.microsoft.com**.

1. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é a sua ID de locatário exclusiva fornecida pelo provedor de hospedagem do laboratório) e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**. Vamos ser direcionados à página Centro de administração do Microsoft 365.

1. À esquerda no painel de navegação do Centro de administração do Microsoft 365, selecione **Mostrar todos**.

1. Em Centros de administração, selecione **Conformidade**.  A página inicial do portal de conformidade do Microsoft Purview é aberta em uma nova página do navegador.  

1. À esquerda no painel de navegação do portal de conformidade do Microsoft Purview, selecione **Mostrar todos**.

1. Do lado esquerdo do painel de navegação, em soluções, selecione **Auditoria**.  Observação: a funcionalidade de auditoria também pode ser acessada pela página inicial do Microsoft 365 Defender.

1. Verifique se a guia **Pesquisa** está selecionada (sublinhada).

1. Após abrir a página Auditoria, aguarde de 2 a 3 minutos.  Se a Auditoria NÃO estiver habilitada, você verá uma barra azul na parte superior da página indicando "Começar a registrar atividade do usuário e do administrador".  Selecione **Começar a registrar atividade de usuário e administrador**.  Quando a auditoria estiver habilitada, a barra azul desaparece.  Se a barra azul não estiver presente, isso indicará que a auditoria já está habilitada e não é necessário realizar nenhuma ação adicional.

1. Volte à página inicial do portal de conformidade do Microsoft Purview selecionando **Página Inicial** no painel de navegação esquerdo.

### <a name="review"></a>Revisão

Nesta configuração, você habilitou a funcionalidade de log de auditoria do Microsoft 365.
