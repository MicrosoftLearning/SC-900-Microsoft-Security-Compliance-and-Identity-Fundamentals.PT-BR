---
lab:
  title: 'Explorar aplicativos do Microsoft Defender for Cloud Apps '
  module: 'Module 3 Lesson 4: Describe the capabilities of Microsoft security solutions: Describe threat protection with Microsoft 365 Defender'
ms.openlocfilehash: cdd0953cafd267114577b53eb7470cd65a4c2bc5
ms.sourcegitcommit: 25998048c2e354ea23d6f497205e8a062d34ac80
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "144557563"
---
# <a name="lab-explore-microsoft-defender-for-cloud-apps"></a>Laboratório: Explorar aplicativos do Microsoft Defender for Cloud Apps

## <a name="lab-scenario"></a>Cenário do laboratório

Neste laboratório, vamos explorar as funcionalidades do Microsoft Defender for Cloud Apps.  Vamos acompanhar as informações que se encontram no painel do Cloud Discovery e as funcionalidades disponíveis para investigar as conclusões e controlar o impacto à sua organização por meio de políticas.  Observação:  A organização deve ter uma licença para usar o Microsoft Defender for Cloud Apps, já que este é um serviço por assinatura com base no usuário.

**Tempo estimado**: 15 a 20 minutos

### <a name="task-1"></a>Tarefa 1:

Explorar o Cloud Discovery.

1. Abra o Microsoft Edge. Na barra de endereços, insira **admin.microsoft.com**.

1. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é sua ID de locatário exclusiva fornecida pelo provedor de hospedagem de laboratório) e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem de laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**. Vamos ser direcionados à página Centro de administração do Microsoft 365.

1. À esquerda no painel de navegação do Centro de administração do Microsoft 365, selecione **Mostrar todos**.

1. Em Centros de administração, selecione **Segurança**.  A página inicial do Portal do Microsoft 365 Defender vai ser aberta no navegador.  

1. Na parte inferior esquerda do painel de navegação da página do Microsoft 365 Defender, selecione **Mais recursos**.

1. No cartão **Microsoft Defender for Cloud Apps**, selecione **Abrir**.  Uma nova página será aberta no navegador mostrando o Painel do Cloud App Security.  Observe os cartões informativos disponíveis.  Se nenhuma informação for exibida nos cartões, é porque este é um ambiente de locatário pré-configurado para o laboratório que não teve uso ativo.  

1. À esquerda no painel de navegação, selecione **Descobrir** e, no menu suspenso, selecione **Painel do Cloud Discovery**.  Esse painel inclui uma visão geral dos aplicativos descobertos, das categorias dos aplicativos, dos níveis de risco, entre outros.  
    1. No topo da página do Cloud Discovery, selecione a guia **Aplicativos descobertos**.  A janela de arquivos descobertos oferece uma visão mais detalhada dos aplicativos descobertos, incluindo pontuação de risco, tráfego, número de usuários, etc.
        1. A partir de qualquer item da lista, selecione as **reticências** na coluna de ações na tabela.  Observe as diversas opções disponíveis, incluindo a possibilidade de marcar um aplicativo como sancionado ou não sancionado.  Selecione as reticências de novo para fechar a caixa de ações.
        1. Ao selecionar algum dos itens listados nas linhas, uma página de detalhes é aberta para o aplicativo específico.  Selecione um item da lista.  Para o item selecionado, explore cada guia no topo da página de detalhes:  **Uso**, **Informações**, **Endereços IP**, **Usuários** e **Alertas**. Quando acabar, retorne aos aplicativos descobertos selecionando **Aplicativos descobertos**, à esquerda do painel de navegação.
    1. No topo da página, selecione a guia **Endereços IP** (equivale a selecionar endereços IP a partir do lado esquerdo do painel de navegação).  Aqui, encontramos dados como o número de transações e a quantidade de tráfego e carregamento por meio dos endereços IP.  Observe que também é possível filtrar por endereço IP específico ou exportar os dados para uma análise mais aprofundada.
    1. No topo da página (ou à esquerda no painel de navegação), selecione **Usuários**.  Esse é o mesmo tipo de informação de quando selecionamos endereços IP, mas aqui ela é listada por usuários individualmente.  Mais uma vez, é possível filtrar por usuário específico e exportar dados para análises mais aprofundadas.

1. As informações apresentadas nessas guias são geradas a partir de relatórios instantâneos com base em logs de tráfego carregados manualmente por firewalls ou proxies, ou de relatórios contínuos que analisam todos os logs encaminhados a partir da sua rede usando o Cloud App Security.  Para exibir onde é feita essa configuração, selecione as **reticências** verticais no canto superior direito da página.
    1. Selecione a primeira opção, **Criar relatório instantâneo do Cloud Discovery**. Aqui, você preenche os detalhes exigidos e carrega os logs de tráfego para gerar e carregar um relatório.  Selecione **Sair**.  Os dados que você encontra no locatário do laboratório são originados a partir de um Relatório instantâneo. É possível ver essa informação no canto superior direito da tela.
    1. Para exibir a opção de relatórios contínuos, selecione as **reticências** no canto superior direito da página. No menu suspenso, selecione **Configurar carregamento automático**.  Não tem fontes de dados conectadas, mas aqui é onde seria possível adicionar uma fonte de dados. Selecione **Adicionar fonte de dados** e, em seguida, na janela Adicionar fonte de dados, selecione a seta para baixo no campo Origem para ver os tipos de dispositivos que você pode conectar como uma fonte de dados.  Selecione **Cancelar** para sair.

1. Outro ponto que merece destaque é a possibilidade de conectar aplicativos diretamente ao configurar conectores de aplicativos que oferecem maior visibilidade e controle dos aplicativos de nuvem. No canto superior esquerdo da tela, selecione o **ícone de engrenagem para Configurações** e, na lista suspensa, selecione **Conectores de aplicativos**.  
    1. Na página Aplicativos conectados, você deve encontrar Office 365 na lista com status de conectado.  Se o Office 365 estiver mostrando um erro de conexão, é provável que a Auditoria não esteja ativada.
    1. Selecione **+Conectar um aplicativo**. Na lista suspensa, selecione **Microsoft Azure**.  Na janela pop-up do Microsoft Azure, selecione **Conectar Microsoft Azure**.  Vão ser exibidos o status de conectado e informações sobre usuários, dados e atividades de verificação.  Selecione botão de **Fechar**.

1. Deixe essa página aberta; vamos usá-la na próxima tarefa.

### <a name="task-2"></a>Tarefa 2:

Explorar formas de investigar as atividades registradas.

1. Do lado esquerdo do painel de navegação, em Investigar, selecione **Log de Atividades**.  Aqui é possível visualizar todas as atividades dos aplicativos conectados.   Como o conector do Office 365 já foi conectado, você deve encontrar alguns dados. Depois de conectar o Cloud App Security a um aplicativo usando o Conector de aplicativos, o Cloud App Security examinará todas as atividades que ocorreram – o período de tempo de verificação retroativo é diferente de acordo com o aplicativo – e, em seguida, ele será constantemente atualizado com novas atividades.  

1. Selecione a coluna de atividade de qualquer item para exibir informações mais detalhadas. Na extrema direita do item selecionado, selecione as **reticências** verticais.  Observe as várias opções.  Selecione a coluna de atividade para o mesmo item para recolher a exibição detalhada.

1. Observe, no topo da página, a opção de adicionar uma nova política da pesquisa ou exportar os dados para análises mais aprofundadas.  Selecione **+Nova política da pesquisa**.  Observe que é possível criar uma política com base em modelo, selecionar a severidade e a categoria da política, criar filtros para a política, criar alertas e até enviar alertas para o Power Automate.  Selecione **Cancelar** para sair da janela de criação de política.

1. No painel de navegação, selecione e explore a opção **Arquivos**. Observe as opções de filtrar dados, criar uma política de arquivo e exportar os dados.  

1. No painel de navegação esquerdo, selecione e explore a opção **usuário e contas**.  Observe as opções de filtrar e exportar dados.

1. À esquerda no painel de navegação, selecione **Configuração de segurança**. Esta página apresenta avaliações das configurações de segurança para contas Azure, Amazon Web Services (AWS) e Google Cloud Platform (GCP).

1. Deixe essa página aberta; vamos usá-la na próxima tarefa.

### <a name="task-3"></a>Tarefa 3

Nesta tarefa, vamos explorar as páginas de políticas e alertas no Microsoft Defender for Cloud Apps.

1. No painel de navegação esquerdo, selecione a tecla de seta para baixo ao lado de onde diz **Controlar** e selecione **Políticas**.  As políticas listadas fornecem informações sobre o número de alertas gerados pela política, gravidade etc. Selecionar qualquer item, por exemplo, **Entrada suspeita**, fornece a opção de editar a política. Selecione **Cancelar** na parte inferior da página.

1. À esquerda no painel de navegação, selecione **Alertas**.  Se tiver alertas listados, selecione um item da lista. Examine as informações apresentadas.  Da parte superior esquerda da janela, selecione **Fechar alerta** para exibir as opções de fechamento.  

1. Feche a janela do navegador.

### <a name="review"></a>Revisão

Neste laboratório, você explorou as funcionalidades do Microsoft Defender for Cloud Apps.  Acompanhamos as informações que se encontram no painel do Cloud Discovery e as funcionalidades disponíveis para investigar as conclusões e controlar o impacto à sua organização por meio de políticas.
