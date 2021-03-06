---
Pre-Demo Setup:
  title: Configuração de demonstração
ms.openlocfilehash: 32b79bd8e8beaad0db6363b04084545cc0e1591e
ms.sourcegitcommit: 25998048c2e354ea23d6f497205e8a062d34ac80
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "144557249"
---
# <a name="pre-demo-setup"></a>Configuração antes da demonstração

## <a name="setup-part-1---redeem-azure-pass"></a>Configuração Parte 1 – Resgatar Azure Pass

Nesta tarefa de configuração, você vai resgatar seu Azure Pass usando as mesmas credenciais que seu locatário do Microsoft 365.  Isso contribui para uma experiência mais contínua ao alternar entre o Microsoft 365 e o Azure.

1. Caso você esteja com alguma janela do navegador aberta, é recomendável fechá-la.

1. Clique com o botão direito no ícone do Microsoft Edge e selecione **Nova janela InPrivate** para abrir uma nova sessão InPrivate no navegador.

1. Na barra de endereços, insira **www.microsoftazurepass.com**.  

1. Clique no botão **Iniciar** para começar.

    1. Na janela Entrar, insira o email **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é sua ID de locatário exclusiva fornecida pelo provedor de hospedagem de laboratório) e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem de laboratório. Selecione **Entrar**.  Se aparecer uma mensagem perguntando se deseja permanecer conectado, selecione **Sim**.
    1. Selecione **Confirmar conta Microsoft** se o endereço de email correto estiver listado.
    1. Insira seu código promocional na caixa designada e clique em **Resgatar código promocional**.  
    1. Na página “Seu perfil”, deixe todas as informações padrão, selecione **Concordo com o contrato de assinatura, detalhes da oferta e política de privacidade.** Em seguida, selecione **Inscrever-se**.
    1. Se uma janela de pesquisa for exibida, feche-a clicando no **X** ou responda conforme o caso e clique em **Enviar**.

1. A ativação da conta pode levar alguns minutos.  Depois da ativação, você é direcionado à página inicial do Portal do Azure. A janela “Bem-vindo ao Microsoft Azure” é exibida, clique em **Talvez mais tarde**. Talvez você veja a janela pop-up “Otimizar suas cargas de trabalho na nuvem com recomendações personalizadas”, clique no **X** do canto superior direito dela.

1. Deixe a guia do navegador com a página inicial do Portal do Azure aberta, você voltará para ela na próxima demonstração.

### <a name="setup-part-2---enable-microsoft-365-audit-log"></a>Configuração Parte 2 – Habilitar o log de auditoria do Microsoft 365

Nesta tarefa de configuração, você ativará o recurso de log de auditoria no Microsoft 365.  Embora a documentação indique que o log de auditoria é ativado por padrão, a maioria dos locatários de laboratório não tem este recurso habilitado e pode levar horas para que esta alteração entre em vigor.  Ativar este recurso é benéfico porque o Microsoft 365 usa logs de auditoria para insights de usuário e atividades identificadas nas políticas e nos insights analíticos.

1. Abra o Microsoft Edge. Na barra de endereços, insira **admin.microsoft.com**.

1. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é sua ID de locatário exclusiva fornecida pelo provedor de hospedagem de laboratório) e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem de laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**. Vamos ser direcionados à página Centro de administração do Microsoft 365.

1. À esquerda no painel de navegação do Centro de administração do Microsoft 365, selecione **Mostrar todos**.

1. Em Centros de administração, selecione **Conformidade**.  A página inicial do centro de conformidade do Microsoft 365 vai ser aberta no navegador.  

1. À esquerda no painel de navegação do centro de conformidade do Microsoft 365, selecione **Mostrar todos**.

1. Do lado esquerdo do painel de navegação, em soluções, selecione **Auditoria**.  Observação: a funcionalidade de auditoria também pode ser acessada pela página inicial do Microsoft 365 Defender.

1. Verifique se a guia **Pesquisa** está selecionada (sublinhada).

1. Após abrir a página Auditoria, aguarde de 2 a 3 minutos.  Se a Auditoria NÃO estiver habilitada, você vai ver uma barra azul no topo da página dizendo começar a registrar atividade de usuário e administrador.  Selecione **Começar a registrar atividade de usuário e administrador**.  Quando a auditoria estiver habilitada, a barra azul desaparece.  Se a barra azul não aparecer, é porque a auditoria já está habilitada e não é necessário realizar nenhuma ação adicional.

1. Volte à página inicial do centro de conformidade do Microsoft 365 selecionando **Página Inicial** à esquerda no painel de navegação.

### <a name="review"></a>Revisão

Nesta configuração, você resgatou seu Azure Pass usando as mesmas credenciais que seu locatário do Microsoft 365.  Você também ativou o recurso de log de auditoria no Microsoft 365.
