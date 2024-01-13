<!---
---
Laboratório: Título: 'Configuração'
---
--->

# Laboratório: configuração

## Locatários do WWL – Termos de uso
Se você estiver recebendo um locatário como parte de uma entrega de treinamento com instrutor, observe que o locatário é disponibilizado com a finalidade de dar suporte aos laboratórios práticos no treinamento com instrutor.

Os locatários não devem ser compartilhados ou usados para fins fora dos laboratórios práticos. O locatário usado neste curso é um locatário de avaliação e não pode ser usado ou acessado após o fim da aula e não está qualificado para extensão.

Os locatários não podem ser convertidos em uma assinatura paga. Os locatários obtidos como parte deste curso permanecem a propriedade da Microsoft Corporation e reservamos o direito de obter acesso e a qualquer momento.

## Cenário do laboratório

Esse laboratório de instalação consiste em habilitar o Log de Auditoria da Microsoft.

**Tempo estimado**: 5 a 10 minutos

### Configuração – Habilitar o log de auditoria do Microsoft 365

Nesta tarefa de configuração, você habilitará a funcionalidade de log de auditoria do Microsoft 365.  Embora a documentação indique que o log de auditoria está ativado por padrão, a maioria dos locatários do laboratório não tem este recurso habilitado e pode levar horas para que isso entre em vigor.  É útil habilitar este recurso, porque o Microsoft 365 usa os logs de auditoria para os insights de usuário e as atividades identificadas nas políticas e nos insights de análise.

1. Abra o Microsoft Edge. Na barra de endereços, insira **admin.microsoft.com**.

1. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é a sua ID de locatário exclusiva fornecida pelo provedor de hospedagem do laboratório) e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**. Vamos ser direcionados à página Centro de administração do Microsoft 365.

1. À esquerda no painel de navegação do Centro de administração do Microsoft 365, selecione **Mostrar todos**.

1. Em Centros de administração, selecione **Conformidade**.  A página inicial do portal de conformidade do Microsoft Purview é aberta em uma nova página do navegador.  

1. Em Soluções, no painel de navegação esquerdo, selecione **Auditoria**.  Observação: a funcionalidade de auditoria também pode ser acessada por meio da página inicial do Microsoft 365 Defender (anteriormente chamada de central de segurança do Microsoft 365).

1. Verifique se a guia **Nova Pesquisa** está selecionada (sublinhada).

1. Depois de acessar a página Auditoria, aguarde de 2 a 3 minutos.  Se a Auditoria NÃO estiver habilitada, você verá uma barra azul na parte superior onde se lê "Iniciar a atividade de gravação de usuário e administrador".  Selecione **Iniciar a atividade de gravação de usuário e administrador**.  Se precisar confirmar se as configurações da organização precisam ser atualizadas, selecione **Sim**. Depois que a auditoria estiver habilitada, a barra azul desaparecerá.  Se a barra azul não estiver presente, isso indicará que a auditoria já está habilitada e não é necessário realizar nenhuma ação adicional.  Outra maneira de verificar se a auditoria está habilitada é por meio do PowerShell, mas isso está fora do escopo deste curso.

1. Volte à home page do portal de conformidade do Microsoft Purview selecionando **Página Inicial** no painel de navegação à esquerda para sair do Microsoft 365. Desconecte-se selecionando o ícone no canto superior direito da janela do Microsoft 365 que é mostrado como um círculo com as letras MA (ao lado do ícone de ponto de interrogação) e escolhendo **Sair**. Em seguida, feche o navegador.

### Revisão

Nesta configuração, você habilitou a funcionalidade de log de auditoria do Microsoft 365.
