---
lab:
  title: Configuração do laboratório
  module: Setup your Microsoft 365 lab tenant (not associated with a Learn module)
---

# Laboratório: Configuração do locatário do Microsoft 365

## Locatários do WWL – Termos de uso
Se você estiver recebendo um locatário como parte de uma entrega de treinamento com instrutor, observe que o locatário é disponibilizado com a finalidade de dar suporte aos laboratórios práticos no treinamento com instrutor.

Os locatários não devem ser compartilhados ou usados para fins fora dos laboratórios práticos. O locatário usado neste curso é um locatário de avaliação e não pode ser usado ou acessado após o fim da aula e não está qualificado para extensão.

Os locatários não podem ser convertidos em uma assinatura paga. Os locatários obtidos como parte deste curso permanecem a propriedade da Microsoft Corporation e reservamos o direito de obter acesso e a qualquer momento.

## Cenário do laboratório

Este laboratório de configuração consiste em habilitar o Log de Auditoria da Microsoft e os recursos de monitoramento de arquivos no locatário do Microsoft 365.

**Tempo estimado**: 5 a 10 minutos

### Configuração – habilitar o monitoramento de arquivos e log de auditoria do Microsoft 365

Nesta tarefa de configuração, você habilitará a funcionalidade de monitoramento de arquivos e log de auditoria do Microsoft 365.  

1. Abra o Microsoft Edge. Na barra de endereços, insira **`https://admin.microsoft.com`** .

1. Entre com as credenciais de administrador do locatário do Microsoft 365 fornecido pelo ALH (hoster de laboratório autorizado).

1. À esquerda no painel de navegação do Centro de administração do Microsoft 365, selecione **Mostrar todos**.

1. Em Centros de administração, selecione **Segurança**.  A página inicial do portal do Microsoft Defender é aberta em uma nova página do navegador.

1. No painel de navegação esquerdo, role para baixo e expanda **Sistema**.  Na lista expandida, selecione **Auditoria**.  Observação: a funcionalidade de auditoria também pode ser acessada por meio do portal Microsoft Purview.

1. Depois de acessar a página Auditoria, aguarde de 1 a 2 minutos.  Se a Auditoria NÃO estiver habilitada, você verá uma barra azul na parte superior da página indicando "Começar a registrar atividade do usuário e do administrador".  Selecione **Iniciar a atividade de gravação de usuário e administrador**.  Depois que a auditoria estiver habilitada, a barra azul desaparecerá.  Se a barra azul não estiver presente, isso indicará que a auditoria já está habilitada e não é necessário realizar nenhuma ação adicional.  Se você vir uma mensagem: "Desculpe, estamos tendo problemas para descobrir se a atividade está sendo registrada. Tente atualizar a página" e nada mudar após a atualização da página, você precisará habilitar a auditoria por meio do PowerShell.
    1. Selecione com o botão direito do mouse o ícone azul do Windows PowerShell e selecione **Executar como administrador**.
    1. Para confirmar se o módulo PowerShell do Exchange Online está instalado no computador, insira **`Get-InstalledModule ExchangeOnlineManagement | Format-List Name,Version,InstalledLocation`**.  Você verá o nome, a versão e o local instalado do Exchange OnlineManagement.
    1. Agora carregue o módulo inserindo **`Import-Module ExchangeOnlineManagement`**.
    1. Para conectar, insira **`Connect-ExchangeOnline -UserPrincipalName admin@WWLxZZZZZZ.onmicrosoft.com`**.  Para o UPN, insira o nome de usuário do administrador encontrado na guia de recursos do laboratório.
    1. Você será solicitado a entrar.  Insira o nome de usuário e a senha administrativos encontrados na guia de recursos do laboratório.
    1. Para habilitar a Auditoria, insira **`Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true`**. Uma mensagem é exibida informando que pode levar até 60 minutos para que a alteração entre em vigor.
    1. Embora possa levar até 60 minutos para entrar em vigor, você pode verificar se o comando foi recebido inserindo **`Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled`**.  Se a auditoria estiver habilitada, a propriedade UnifiedAuditLogIngestionEnabled mostrará um valor true.

1. No painel de navegação esquerdo, em Sistema, selecione **Configurações**

1. Na página de configurações, selecione **Aplicativos de nuvem**.   Role para baixo e em **Proteção de informações**, selecione **Arquivos**.

1. Se isso ainda não estiver habilitado, selecione a caixa ao lado do texto **Habilitar monitoramento de arquivos** e escolha **Salvar**.  

1. Isso conclui a configuração do laboratório no locatário do Microsoft 365.

### Revisão

Nesta configuração, você habilitou a funcionalidade de monitoramento de arquivos e log de auditoria do Microsoft 365.
