---
lab:
  title: Explorar o Microsoft Defender para Nuvem
  module: 'Module 3 Lesson 2: Describe the capabilities of Microsoft security solutions: Describe security management capabilities of Azure'
ms.openlocfilehash: 208e11a7e82497fbb900b4fa024fb6fb367d458e
ms.sourcegitcommit: a341c2fc38e9b37dafb792d82e3c948f7ba4a099
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2022
ms.locfileid: "137893745"
---
# <a name="lab-explore-microsoft-defender-for-cloud"></a>Laboratório: Explorar o Microsoft Defender para Nuvem

## <a name="lab-scenario"></a>Cenário do laboratório
Neste laboratório, vamos explorar o Microsoft Defender para Nuvem e aprender como a Classificação de Segurança do Azure pode ser usada para melhorar a postura de segurança da sua organização.

**Tempo estimado**: 30 minutos

#### <a name="task-1-in-this-task-you-will-take-a-brief-tour-of-microsoft-defender-for-cloud"></a>Tarefa 1: Nesta tarefa, você fará um breve tour do Microsoft Defender para Nuvem.
1.  Abra o Microsoft Edge. Na barra de endereços, insira **portal.azure.com**.

1. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é sua ID de locatário exclusiva fornecida pelo provedor de hospedagem de laboratório) e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem de laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**.

1. No canto superior esquerdo da tela, ao lado de onde diz Microsoft Azure, selecione o ícone de menu Mostrar portal (as três linhas horizontais também conhecidas como ícone de hambúrguer) e, no painel de navegação esquerdo, em Favoritos, selecione **Microsoft Defender para Nuvem**.  Se ele não estiver listado em favoritos, na caixa de pesquisa, insira **Microsoft Defender para Nuvem** e, na lista de resultados, selecione **Microsoft Defender para Nuvem**.

1. Observe as informações disponíveis na página de visão geral do Microsoft Defender para Nuvem.  

1. Você pode ver uma caixa de informações azul na parte superior da página indicando que você pode estar vendo informações limitadas.  Selecione **clique aqui**.
    1. Para garantir que seu locatário tenha uma visibilidade ampla, atribua as funções necessárias.  Selecione **Administrador de Segurança** e depois **Obter acesso** na parte inferior da página.
    1. É provável que apareça a mensagem O grupo de gerenciamento raiz não existe.  Pela descrição, o sistema vai criar um grupo para você.  Pode levar até 15 minutos para ser concluído (mas geralmente acontece mais rapidamente).  Depois que o acesso for concedido, selecione **Microsoft Defender para Nuvem** no canto superior esquerdo da página, acima de onde está escrito Obter permissões e, em seguida, atualize a página de visão geral do Microsoft Defender para Nuvem.

1. As informações na parte superior da página incluem o número de assinaturas do Azure, o número de Recursos avaliados, o número de recomendações ativas e outros alertas de segurança.  No corpo principal da página, há cartões que representam Secure Score, Conformidade regulatória, Insights e muito mais.  

1. Na parte superior da página, selecione **Recursos avaliados**.  (Observe que isso equivale a selecionar Inventário no painel de navegação esquerdo da página inicial da Central de Segurança).
    1. Essa ação leva você para a página **Inventário** que mostra sua assinatura do Azure Pass.  Selecione **Azure Pass – Sponsorship**.
    1. A página Resource Health fornece uma lista de recomendações.  Na lista disponível, selecione **Deve haver mais de um proprietário atribuído à sua assinatura**.
    1. Selecione a seta suspensa ao lado de Etapas de correção. Observe como as etapas de correção detalhadas são fornecidas junto com a opção de ação.  
    1. Selecione **Microsoft Defender para Nuvem** no canto superior esquerdo da tela para retornar à página de visão geral do Microsoft Defender para Nuvem.

1. Na parte superior da página, selecione **Recomendações ativas**.  (Observe que isso equivale a selecionar Recomendações no painel de navegação esquerdo da página inicial do Microsoft Defender para Nuvem).
    1. A página de recomendações mostra o painel do Secure Score.
    1. Abaixo do painel do Secure Score, há uma lista de controles. Cada controle de segurança representa um risco de segurança que deve ser mitigado e também inclui informações sobre a pontuação máxima associada a esse controle, a pontuação atual, o aumento potencial da pontuação e o status da integridade do recurso.  
    1. Selecione um dos controles, por exemplo **Habilitar MFA**.  Selecione um dos subitens, por exemplo **A MFA deve ser habilitada em contas com permissões de proprietário em sua assinatura**.  Na página que é aberta, você verá uma descrição, etapas de correção e recursos afetados. Feche a página selecionando o **X** no canto superior direito da tela.
    1. Feche a página de recomendações clicando no **X** no canto superior direito da tela para voltar à página de visão geral.

1. Na página principal, selecione **Conformidade regulatória**. A página de conformidade regulatória fornece uma lista de controles de conformidade.  Em cada controle, está um conjunto de avaliações baseadas no parâmetro de comparação de segurança do Azure, que fornece recomendações sobre como você pode proteger suas soluções de nuvem no Azure.
    1. Selecione **IM. Gerenciamento de Identidades** e selecione **IM.6 Usar controles de autenticação forte**.  A lista mostra as ações de responsabilidade do cliente que podem ser tomadas para melhorar a postura de conformidade.
    1. Selecione o **X** no canto superior direito da tela para voltar à página Visão Geral do Microsoft Defender para Nuvem. 
    1. Mantenha aberta a página de visão geral do Microsoft Defender para Nuvem, você usará na próxima tarefa.


#### <a name="task-2-in-this-task-you-will-navigate-to-azure-secure-score-and-explore-recommendations-that-can-improve-your-secure-score"></a>Tarefa 2: Nesta tarefa, vamos navegar pela Classificação de segurança do Azure e explorar recomendações que podem melhorar sua classificação de segurança. 

1. Na página de visão geral do Microsoft Defender para Nuvem, selecione o cartão **Classificação de Segurança**.
1. Selecione **Azure Pass – Sponsorship**.  Observe a sua classificação de segurança.
1. Na página de recomendações, selecione **Implementar práticas recomendadas de segurança** para expandir a lista. Observe que ela mostra seu status de integridade do recurso como vermelho.
1. Selecione o item **Deve haver mais de um proprietário atribuído à sua assinatura**, que mostra o status do resource health em vermelho. 
1. Abaixo do local em que ele diz **Recursos afetados**, verifique se os recursos não íntegros estão selecionados/sublinhados e, em seguida, selecione a assinatura listada do Azure.
1. No topo da página Controle de acesso (IAM), selecione **+Adicionar** e depois **Adicionar atribuição de função** no menu suspenso.
    1. No lado esquerdo da página, selecione **Proprietário** (deve ser o primeiro item listado) para que a linha seja realçada em cinza e selecione **Avançar** na parte inferior da página.
    1. Ao lado de onde diz Membros, selecione **+ Selecionar membros**. 
    1. Na janela Selecionar membros que é aberta no lado direito da tela, selecione **Alex Wilber** e, em seguida, pressione **Selecionar** na parte inferior da página.  
    1. Na página Adicionar atribuição de função, verifique se Alex Wilber está listado como um membro e selecione **Avançar** seguido por **Revisar + atribuir**.
    1. Pode levar até 24 horas para atualizar o status. Depois, sua classificação de segurança também vai ser atualizada, já que todos os itens do grupo Gerenciar acesso e permissões serão atendidos.
    1. No canto superior esquerdo da página, acima onde está o Azure Pass, selecione **Microsoft Defender para Nuvem** para retornar para a página de visão geral do Microsoft Defender para Nuvem.
1. Deixe essa página aberta para a próxima tarefa.


#### <a name="task-3--recall-that-microsoft-defender-for-cloud-is-offered-in-two-modes-without-enhanced-security-features-free-and-with-enhanced-security-features-which-are-available-through-the-microsoft-defender-for-cloud-plans-in-this-task-you-discover-how-to-enabledisable-the-various-microsoft-defender-for-cloud-plans"></a>Tarefa 3:  Lembre-se de que o Microsoft Defender para Nuvem é oferecido em dois modos: sem recursos de segurança aprimorados (gratuitos) e com recursos de segurança aprimorados que estão disponíveis por meio dos planos do Microsoft Defender para Nuvem. Nesta tarefa, você descobre como habilitar/desabilitar os vários planos do Microsoft Defender para Nuvem.

1.  Na página de visão geral do Microsoft Defender para Nuvem, selecione as **Configurações de ambiente** no painel de navegação esquerdo.
1. Selecione o sinal maior que **>** ao lado de onde está o Grupo Raiz do Locatário para expandi-lo (não selecione Grupo Raiz do Locatário diretamente, pois isso direcionará você para uma página diferente) e, em seguida, selecione **Azure Pass — Patrocínio**
1.  Na página Planos do Defender, observe como você pode selecionar Habilitar todos ou selecionar planos individuais do Defender. Deixe as configurações como estão com todos os planos definidos como desligados.
1.  Agora pode fechar a guia do navegador para sair do portal do Azure.


#### <a name="review"></a>Revisão
Neste laboratório, você explorou o Microsoft Defender para Nuvem e aprendeu como a Classificação de Segurança do Azure pode ser usada para melhorar a postura de segurança da sua organização.

