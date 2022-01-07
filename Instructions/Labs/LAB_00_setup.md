---
lab:
    title: 'Configuração'
---

# Laboratório: Configuração

### Cenário do laboratório

Neste laboratório, você vai resgatar seu Azure Pass usando as mesmas credenciais que seu locatário do Microsoft 365.  Isso contribui para uma experiência contínua ao alternar entre o Microsoft 365 e o Azure. Como parte da configuração, você também ativará o recurso de log de auditoria no seu locatário do Microsoft 365, já que isso pode levar um tempo para entrar em vigor. O Microsoft 365 usa logs de auditoria para insights de usuário e atividades identificadas nas políticas e nos insights analíticos.

**Tempo estimado**: 5-10 minutos

#### Configuração Parte 1 – Resgatar Azure Pass
Nesta tarefa de configuração, você vai resgatar seu Azure Pass usando as mesmas credenciais que seu locatário do Microsoft 365.  Isso contribui para uma experiência mais contínua ao alternar entre o Microsoft 365 e o Azure.

1. Caso você esteja com alguma janela do navegador aberta, é recomendável fechá-la.

1. Clique com o botão direito no ícone do Microsoft Edge e selecione **Nova janela InPrivate** para abrir uma nova sessão InPrivate no navegador. Outros 

1. Na barra de endereços, insira **www.microsoftazurepass.com**.  

1. Clique no botão **Iniciar** para começar.

    1. Na janela de logon, insira o email **admin@WWLxZZZZZZ.onmicrosoft.com** (onde ZZZZZZ é seu ID de locatário exclusivo fornecido pelo seu provedor de hospedagem do laboratório) e clique em **Avançar**.
    1. Digite a senha do administrador, que deve ser fornecida pelo seu provedor de hospedagem do laboratório. Selecione **Entrar**. Se a opção para permanecer conectado for exibida, clique em **Sim**.
    1. Selecione **Confirmar conta Microsoft** se o endereço de email correto estiver listado.
    1. Insira seu código promocional na caixa designada e clique em **Resgatar código promocional**.  
    1. Na página “Seu perfil”, deixe todas as informações conforme o padrão, clique em **Concordo com o contrato de assinatura, os detalhes da oferta e a política de privacidade.** e depois em **Entrar**.
    1. Se uma janela de pesquisa for exibida, feche-a clicando no **X** ou responda conforme o caso e clique em **Enviar**.

1. A ativação da conta pode levar alguns minutos.  Depois da ativação, você é direcionado à página inicial do Portal do Azure. A janela “Bem-vindo ao Microsoft Azure” é exibida, clique em **Talvez mais tarde**. Talvez você veja a janela pop-up “Otimizar suas cargas de trabalho na nuvem com recomendações personalizadas”, clique no **X** do canto superior direito dela.

1. Deixe a guia do navegador com a página inicial do Portal do Azure aberta, você voltará para ela na próxima demonstração.

#### Configuração Parte 2 – Habilitar o log de auditoria do Microsoft 365
Nesta tarefa de configuração, você ativará o recurso de log de auditoria no Microsoft 365.  Embora a documentação indique que o log de auditoria é ativado por padrão, a maioria dos locatários de laboratório não tem este recurso habilitado e pode levar horas para que esta alteração entre em vigor.  Ativar este recurso é benéfico porque o Microsoft 365 usa logs de auditoria para insights de usuário e atividades identificadas nas políticas e nos insights analíticos.

1. Abra o Microsoft Edge. Na barra de endereços, insira **admin.microsoft.com**.

1. Entre com suas credenciais de administrador.
    1. Na janela de logon insira **admin@WWLxZZZZZZ.onmicrosoft.com** (onde ZZZZZZ é seu ID de locatário exclusivo fornecido pelo seu provedor de hospedagem do laboratório) e clique em **Avançar**.
    1. Digite a senha do administrador, que deve ser fornecida pelo seu provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Se a opção para permanecer conectado for exibida, clique em **Sim**. Isso leva você à página do Centro de administração do Microsoft 365.

1. No painel de navegação esquerdo do Centro de administração do Microsoft 365, selecione **Mostrar tudo**.

1. Em Centros de administração, clique em **Conformidade**.  Uma nova janela do navegador é aberta na página de boas-vindas do Centro de conformidade do Microsoft 365.  

1. No painel de navegação esquerdo, na seção Soluções, selecione **Auditoria**.  Observação: a funcionalidade de auditoria também pode ser acessada pela página inicial do Microsoft 365 Defender (anteriormente chamado de Central de segurança do Microsoft 365).

1. Verifique se a guia **Pesquisar** está selecionada (sublinhada).

1. Depois que chegar à página de auditoria, aguarde 2-3 minutos.  Se a auditoria NÃO estiver habilitada, você verá uma barra azul que diz “Começar a registrar atividade de usuário e administrador” no topo da página.  Selecione **Começar a registrar atividade de usuário e administrador**.  Quando a auditoria é habilitada, a barra azul desaparece.  Se a barra azul não estiver presente, isso significa que a auditoria já está habilitada e nenhuma outra ação é necessária.  Outra forma de verificar se a auditoria está ativada é pelo PowerShell, mas ela está fora do escopo deste curso.

1. Volte para a página inicial do Centro de conformidade do Microsoft 365 clicando em **Home** no painel de navegação à esquerda.

#### Revisão

Nesta configuração, você resgatou seu Azure Pass usando as mesmas credenciais que seu locatário do Microsoft 365.  Você também ativou o recurso de log de auditoria no Microsoft 365.