---
Demo:
  title: 'Microsoft Defender for Cloud Apps '
  module: 'Module 3 Lesson 4: Describe the capabilities of Microsoft security solutions: Describe threat protection with Microsoft 365 Defender'
ms.openlocfilehash: f653c14f8383ef3c5823d9c4626e7d6c3a693df8
ms.sourcegitcommit: a341c2fc38e9b37dafb792d82e3c948f7ba4a099
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2022
ms.locfileid: "137893770"
---
# <a name="demo-microsoft-defender-for-cloud-apps"></a>Demonstração: Microsoft Defender for Cloud Apps

### <a name="demo-scenario"></a>Cenário da demonstração
Nesta demonstração, você mostrará os recursos do Microsoft Defender for Cloud Apps.  Você apresentará ao aluno as informações disponíveis no painel do Cloud Discovery, além dos recursos disponíveis para investigar as descobertas e controlar o impacto na sua organização por meio de políticas.  Observação:  A organização deve ter uma licença para usar o Microsoft Defender for Cloud Apps, já que este é um serviço por assinatura com base no usuário.  

#### <a name="demo-part-1-explore-cloud-discovery"></a>Demonstração – Parte 1: Explorar o Cloud Discovery.

1. Abra o Microsoft Edge. Na barra de endereços, insira **admin.microsoft.com**.  Você já deve estar conectado como administrador.  Se não estiver, entre com suas credenciais de administrador.

1. À esquerda no painel de navegação do Centro de administração do Microsoft 365, selecione **Mostrar todos**.  Explique com clareza que os vários centros de administração do Microsoft 365 possam ser acessados aqui.

1. Em Centros de administração, selecione **Segurança**.  A página inicial do Portal do Microsoft 365 Defender vai ser aberta no navegador.  

1. Se essa for a primeira vez que você visita o portal do Microsoft 365 Defender, pode ser que apareça uma janela pop-up para fazer um tour rápido.  Feche a janela.

1. Na parte inferior esquerda do painel de navegação da página do Microsoft 365 Defender, selecione **Mais recursos**.

1. No cartão **Microsoft Defender for Cloud Apps**, selecione **Abrir**.  Uma nova página será aberta no navegador mostrando o Painel do Cloud App Security.  Observe os cartões informativos disponíveis.  Se nenhuma informação for exibida nos cartões, é porque este é um ambiente de locatário pré-configurado para o laboratório que não teve uso ativo.  

1. À esquerda no painel de navegação, selecione **Descobrir** e, no menu suspenso, selecione **Painel do Cloud Discovery**.  Esse painel inclui uma visão geral dos aplicativos descobertos, das categorias dos aplicativos, dos níveis de risco, entre outros.  

    1. No topo da página do Cloud Discovery, selecione a guia **Aplicativos descobertos**.  A janela de arquivos descobertos oferece uma visão mais detalhada dos aplicativos descobertos, incluindo pontuação de risco, tráfego, número de usuários, etc.

        1. A partir de qualquer item da lista, selecione as **reticências** na coluna de ações na tabela.  Observe as diversas opções disponíveis, incluindo a possibilidade de marcar um aplicativo como sancionado ou não sancionado.  Selecione as reticências de novo para fechar a caixa de ações.

        1. Ao selecionar algum dos itens listados nas linhas, uma página de detalhes é aberta para o aplicativo específico.  Selecione um item da lista.  Para o item selecionado, explore cada guia no topo da página de detalhes:  **Uso**, **Informações**, **Endereços IP**, **Usuários** e **Alertas**. Quando acabar, retorne aos aplicativos descobertos selecionando **Aplicativos descobertos**, à esquerda do painel de navegação.

    1. No topo da página, selecione a guia **Endereços IP** (equivale a selecionar endereços IP a partir do lado esquerdo do painel de navegação).  Aqui, encontramos dados como o número de transações e a quantidade de tráfego e carregamento por meio dos endereços IP.  Observe que também é possível filtrar por endereço IP específico ou exportar os dados para uma análise mais aprofundada.

    1. No topo da página (ou à esquerda no painel de navegação), selecione **Usuários**.  Esse é o mesmo tipo de informação de quando selecionamos endereços IP, mas aqui ela é listada por usuários individualmente.  Mais uma vez, é possível filtrar por usuário específico e exportar dados para análises mais aprofundadas.

1. As informações apresentadas nessas guias são geradas a partir de relatórios instantâneos com base em logs de tráfego carregados manualmente por firewalls ou proxies, ou de relatórios contínuos que analisam todos os logs encaminhados a partir da sua rede usando o Cloud App Security.  Para exibir onde é feita essa configuração, selecione as **reticências** no canto superior direito da página.

    1. Selecione a primeira opção, **Criar relatório instantâneo do Cloud Discovery**. Aqui, você preenche os detalhes exigidos e carrega os logs de tráfego para gerar e carregar um relatório.  Selecione **Cancelar**.  Os dados que você encontra no locatário do laboratório são originados a partir de um Relatório instantâneo. É possível ver essa informação no canto superior direito da tela.

    1. Para exibir a opção de relatórios contínuos, selecione as **reticências** no canto superior direito da página. No menu suspenso, selecione **Configurar carregamento automático**.  Não tem fontes de dados conectadas, mas aqui é onde seria possível adicionar uma fonte de dados. Selecione a seta para baixo em **Selecionar Dispositivo** para exibir os tipos de dispositivos que podem ser conectados como fonte de dados.  Selecione **Cancelar** para sair.

1. Outro ponto que merece destaque é a possibilidade de conectar aplicativos diretamente ao configurar conectores de aplicativos que oferecem maior visibilidade e controle dos aplicativos de nuvem. No canto superior esquerdo da tela, selecione o **ícone de engrenagem para Configurações** e, na lista suspensa, selecione **Conectores de aplicativos**.  

    1. Na página Aplicativos conectados, você deve encontrar Office 365 na lista com status de conectado.  Se o Office 365 estiver mostrando um erro de conexão, é provável que a Auditoria não esteja ativada.

    1. Selecione **+Conectar um aplicativo**. Na lista suspensa, selecione **Microsoft Azure**.  Na janela pop-up do Microsoft Azure, selecione **Conectar Microsoft Azure**.  Vão ser exibidos o status de conectado e informações sobre usuários, dados e atividades de verificação.  Selecione botão de **Fechar**.

1. Deixe essa página aberta; vamos usá-la na próxima tarefa.

#### <a name="demo-part-2-explore-ways-in-which-you-can-investigate-the-recorded-activities"></a>Demonstração — Parte 2: Explorar formas de investigar as atividades registradas.

1. No painel de navegação esquerdo, em **Investigar**, selecione **Log de atividades**.  Aqui você obtém visibilidade de todas as atividades de seus aplicativos conectados.   Como o conector do Office 365 já foi conectado, você deve encontrar alguns dados. Depois de conectar o Cloud App Security a um aplicativo usando o Conector de aplicativos, o Cloud App Security examinará todas as atividades que ocorreram – o período de tempo de verificação retroativo é diferente de acordo com o aplicativo – e, em seguida, ele será constantemente atualizado com novas atividades.  

1. Selecione um item para exibir informações mais detalhadas. Observe, no topo da página, a opção de adicionar uma nova política da pesquisa ou exportar os dados para análises mais aprofundadas.  Selecione **+Nova política da pesquisa**.  Observe que é possível criar uma política com base em modelo, selecionar a severidade e a categoria da política, criar filtros para a política, criar alertas e até enviar alertas para o Power Automate.  Selecione **Cancelar** para sair da janela de criação de política.

1. No painel de navegação, selecione e explore a opção **Arquivos**. Observe as opções de filtrar dados, criar uma política de arquivo e exportar os dados.  Selecione e explore a opção **usuário e contas**.  Observe as opções de filtrar e exportar dados.

1. À esquerda no painel de navegação, selecione Configuração de segurança. Esta página apresenta avaliações das configurações de segurança para contas Azure, Amazon Web Services (AWS) e Google Cloud Platform (GCP).

1. Deixe essa página aberta; vamos usá-la na próxima tarefa.


#### <a name="demo-part-3-in-this-task-you-will-explore-the-policies-and-alerts-pages-in-microsoft-defender-for-cloud-apps"></a>Demonstração — Parte 3: Nesta tarefa, vamos explorar as páginas de políticas e alertas no Microsoft Defender for Cloud Apps.

1. Do lado esquerdo do painel de navegação, abaixo de Controle, selecione **Políticas**.  As políticas listadas fornecem informações sobre o número de alertas gerados pela política, gravidade etc. Selecione qualquer item de linha para ver informações mais detalhadas sobre a política. Selecione um item da lista, i.e., **Entrada suspeita**.  

1. À esquerda no painel de navegação, selecione **Alertas**.  Se tiver alertas listados, selecione um item da lista. Examine as informações apresentadas.  Da parte superior esquerda da janela, selecione **Fechar alerta** para exibir as opções de fechamento.  

1. Feche a janela do navegador.

#### <a name="review"></a>Revisão
Nesta demonstração, você mostrou os recursos do Microsoft Defender for Cloud Apps.  Você mostrou as informações disponíveis no painel do Cloud Discovery, além dos recursos disponíveis para investigar as descobertas e controlar o impacto na sua organização por meio de políticas.