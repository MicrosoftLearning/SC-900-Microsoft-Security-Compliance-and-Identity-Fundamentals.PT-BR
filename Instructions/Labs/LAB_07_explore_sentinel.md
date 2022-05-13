---
lab:
  title: Explorar o Microsoft Sentinel
  module: 'Module 3 Lesson 3: Describe the capabilities of Microsoft security solutions: Describe security capabilities of Microsoft Sentinel'
ms.openlocfilehash: 857d7f5ad5e0a9136d298c32cd47063a83e454e7
ms.sourcegitcommit: 25998048c2e354ea23d6f497205e8a062d34ac80
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "144557153"
---
# <a name="lab-explore-microsoft-sentinel"></a>Laboratório: Explorar o Microsoft Sentinel

## <a name="lab-scenario"></a>Cenário do laboratório

Neste laboratório, vamos passar pelo processo de criação de uma instância do Microsoft Sentinel.  Também vamos configurar as permissões para garantir o acesso aos recursos que serão implantados para dar suporte ao Microsoft Sentinel.  Depois que essa configuração básica estiver concluída, você seguirá as etapas para conectar o Microsoft Sentinel às suas fontes de dados, configurar uma pasta de trabalho e fazer uma breve explicação de alguns dos principais recursos disponíveis no Microsoft Sentinel.  

**Tempo estimado**: 45 a 60 minutos

### <a name="task-1"></a>Tarefa 1:

Criar uma instância do Microsoft Sentinel

1. Abra a guia do navegador, **Página Inicial – Microsoft Azure**.  Se você fechou a guia anteriormente, abra uma página do navegador e, na barra de endereços, insira portal.azure.com e entre novamente.

1. Na caixa de pesquisa, na barra azul no topo da página, perto de onde está escrito Microsoft Azure, digite **Microsoft Sentinel** e selecione **Microsoft Sentinel** nos resultados da pesquisa.

1. Na página do Microsoft Sentinel, selecione **Criar Microsoft Sentinel**.

1. Na página Adicionar o Microsoft Sentinel a um workspace, selecione **Criar um workspace**.

1. Na guia Básico da página Criar espaço de trabalho do Log Analytics, insira:
    1. Assinatura:  **Azure Pass – Sponsorship**
    1. Grupo de recursos: selecione **Criar novo**, insira o nome **SC900-Sentinel-RG** e clique em **OK**.
    1. Nome: **SC900-LogAnalytics-workspace**.
    1. Região: **Leste dos EUA** (uma região padrão diferente pode ser selecionada com base em sua localização)
    1. Selecione **Avançar: Marcas >**

1. Pode deixar Marcas em branco. Depois, selecione **Revisar + Criar**.

1. Verifique as informações inseridas e selecione **Criar**.

1. Pode levar um ou dois minutos até que o novo workspace seja listado; caso ele ainda não seja exibido, selecione **Atualizar** e depois **Adicionar**.

1. Uma vez que o espaço de trabalho estiver adicionado, a página Microsoft Sentinel | Notícias e Guias será exibida.  Veja as três etapas listadas na página de Introdução.

1. Deixe essa página aberta; vamos usá-la na próxima tarefa.

### <a name="task-2"></a>Tarefa 2:

Com a instância do Microsoft Sentinel criada, é prudente verificar se você tem o acesso necessário aos recursos implantados para dar suporte ao Microsoft Sentinel.

1. Na caixa de pesquisa, na barra azul no topo da página, perto de onde está escrito Microsoft Azure, digite **grupos de recursos** e selecione **Grupos de recursos** nos resultados da pesquisa. Atribuir a função a nível do grupo de recursos vai garantir que ela seja aplicada a todos os recursos implantados para comportar o Microsoft Sentinel.

1. Na página de Grupos de recursos, selecione o grupo de recursos que você criou com o Microsoft Sentinel, **SC900-Sentinel-RG**.

1. Na página do SC900-Sentinel-RG, selecione **Controle de acesso (IAM)** no painel de navegação à esquerda.

1. Na página Controle de acesso, selecione **Exibir meu acesso**.  Como Administrador MOD, a função atual é Administrador de serviços.  Isso concederá as permissões necessárias, mas é importante entender as funções específicas do Sentinel disponíveis.  Feche a janela de atribuições do Administrador MOD selecionando o **X** no canto superior direito da tela.

    1. Na página Controle de acesso, selecione **+Adicionar** e depois **Adicionar atribuição de função**.

    1. A janela Adicionar atribuição de função vai ser aberta.  Na caixa de pesquisa, digite **Microsoft Sentinel** para visualizar as 4 funções associadas ao Microsoft Sentinel.
    1. Em qualquer uma das funções listadas, selecione a **Exibir** para ver os detalhes dessa função.  Como prática recomendada, você deve atribuir o privilégio mínimo exigido para a função.  

    1. Clique no **X** no canto superior direito da janela para fechá-la.

1. Na página de controle de acesso, clique no **X** no canto superior direito da janela para fechá-la.

### <a name="task-3"></a>Tarefa 3

Nesta tarefa, vamos acompanhar o processo de conexão do Microsoft Sentinel à sua fonte de dados para começar a coletar dados.

1. Na caixa de pesquisa, na barra azul no topo da página, perto de onde está escrito Microsoft Azure, digite **Microsoft Sentinel** e selecione **Microsoft Sentinel** nos resultados da pesquisa.

1. Na página Microsoft Sentinel, selecione o espaço de trabalho criado com a instância do Microsoft Sentinel, **SC900-LogAnalytics-workspace**.

1. A primeira etapa com o Microsoft Sentinel é conseguir coletar dados. À esquerda no painel de navegação, em configuração, selecione **Conectores de dados**.

1. Na página Conectores de dados, role para baixo na janela principal para exibir a extensa lista de conectores disponíveis. Na caixa de pesquisa da página de conectores de dados, insira **Office 365** e selecione **Office 365**.

1. A janela do conector do Office 365 é aberta.  Clique em **Abrir página do conector**.

1. Na página do conector do Office 365, leia a Descrição no lado esquerdo da janela.

1. A guia de instruções na janela principal fornece os requisitos para o Microsoft Sentinel se integrar ao Office 365, todos eles devem mostrar uma marca de seleção verde.   Em configuração, selecione **Exchange** e **SharePoint** e escolha Aplicar Alterações.  Quase imediatamente você verá o status conectado no lado esquerdo da janela.

1. Clique no **X** no canto superior direito da janela para fechá-la e retornar à página de conectores de dados.

1. A parte superior da página de conectores de dados deve exibir 1 conectado, para refletir que agora você está conectado ao Office 365. Se você não vir essa conexão, selecione **Atualizar**. Pode levar alguns minutos para que a página seja atualizada.

1. Deixe essa página aberta; vamos usá-la na próxima tarefa.

### <a name="task-4"></a>Tarefa 4

Nesta tarefa, você percorrerá o processo de configuração de uma pasta de trabalho do Office 365 para visualizar e monitorar seus dados.

1. À esquerda no painel de navegação, selecione **Pastas de trabalho**.

1. Na caixa de pesquisa, insira e selecione **Office 365**.

1. Na janela que é aberta no lado direito da tela, leia a descrição e selecione **Salvar**, na parte inferior da tela, e clique em **OK** para salvar a pasta de trabalho no local padrão.  Agora selecione **Exibir pasta de trabalho salva**.

1. A página de Pastas de Trabalho do Office 365 é aberta.  Selecione a seta suspensa ao lado de **Operações: remover definição** e clique em **Todos**.  Agora, selecione a seta suspensa ao lado de **Usuários: consulta pendente** e clique em **Todos**.  Selecione o **ícone salvar (disco)** . Clique no **X** no canto superior direito da janela para fechá-la. Pode levar alguns minutos para que os dados comecem a aparecer na pasta de trabalho, então você voltará às pastas de trabalho mais tarde.

1. No canto superior esquerdo da página Pastas de trabalho, acima de onde está escrito Pastas de trabalho, clique em **Microsoft Sentinel**. Isso direcionará você de volta à página Visão geral.

### <a name="task-5"></a>Tarefa 5

Nesta tarefa, você percorrerá algumas das opções disponíveis no Sentinel.

1. No painel de navegação esquerdo, selecione **Buscar**.  Na guia **Consultas** selecionada (sublinhada), clique em qualquer consulta na lista.  Depois que uma consulta for selecionada, observe as informações fornecidas sobre ela, incluindo seu código, a opção de execução e exibir os resultados.  Não selecione nada.

1. No painel de navegação esquerdo, selecione **MITRE ATT&CK**.  O MITRE ATT&CK é uma base de dados de conhecimento publicamente acessível de táticas e técnicas que são comumente usadas por invasores. Com o Microsoft Sentinel você pode visualizar as detecções já ativas em seu workspace e aquelas disponíveis para você configurar, para entender a cobertura de segurança da sua organização, com base nas táticas e técnicas do framework MITRE ATT&CK®.  Selecione qualquer célula da matriz e anote as informações disponíveis no lado direito da tela.  

1. À esquerda no painel de navegação, selecione **Comunidade**. Os analistas de segurança da Microsoft criam e adicionam constantemente novas pastas de trabalho, guias estratégicos, consultas de busca e muito mais, publicando-os na comunidade para uso em seu ambiente. Você pode baixar o conteúdo de exemplo no repositório do GitHub privado da comunidade para criar pastas de trabalho personalizadas, consultas de busca, notebooks e guias estratégicos para o Microsoft Sentinel.  Selecione **Integrar conteúdo da comunidade**.  Uma nova guia para o repositório GitHub, em que você pode baixar conteúdo para habilitar seus cenários, é aberta.  Retorne à guia do Azure no navegador.

1. À esquerda no painel de navegação, selecione **Análise**.  Selecione o primeiro item da lista **Detecção avançada de ataque de várias etapas**.  Leia as informações detalhadas.  O Microsoft Sentinel usa o Fusion, um mecanismo de correlação baseado em algoritmos de aprendizado de máquina escaláveis, para detectar automaticamente ataques de vários estágios (também conhecidos como ameaças persistentes avançadas) identificando combinações de comportamentos anômalos e atividades suspeitas que são observadas em vários estágios da cadeia de eliminação. Com base nessas descobertas, o Microsoft Sentinel gera incidentes que, de outra forma, seriam difíceis de detectar.

1. À esquerda no painel de navegação, selecione **Automação**.  Aqui você pode criar regras de automação simples, integrá-las a manuais existentes ou criar novos manuais.  Selecione **+ Criar** e clique em **Regra de Automação**.  Observe a janela que é aberta no lado direito da tela e as opções de criação de condições e ações são disponibilizadas.  Selecione **Cancelar** na parte inferior da tela.

1. À esquerda no painel de navegação, selecione **Pastas de trabalho**. Na página Pastas de trabalho, selecione a guia **Minhas pastas de trabalho**, que fica acima da caixa de pesquisa.  A pasta de trabalho que você salvou anteriormente estará listada e disponível para você visualizar e monitorar seus dados.  Selecione **Office 365** na janela que é aberta no lado direito da tela e clique em **Exibir pasta de trabalho salva**.  Observe as visualizações relacionadas às cargas de trabalho de Office 365.  

1. Clique no **X** no canto superior direito da janela para fechá-la.

1. No canto superior esquerdo da janela, logo abaixo da barra azul, selecione **Página Inicial** para retornar à home page do portal do Azure.

### <a name="task-6"></a>Tarefa 6

O Microsoft Sentinel é cobrado de acordo com o volume da ingestão de dados para análise. Embora a quantidade de dados ingeridos durante este laboratório seja mínima, recomendamos que o grupo de recursos do Microsoft Sentinel seja excluído quando você terminar de explorar suas funcionalidades.

1. No canto superior esquerdo da página Microsoft Sentinel, em cima de Microsoft Sentinel, selecione **Todos os Serviços**.

2. Na caixa para filtrar serviços, insira grupos de recursos e selecione **Grupos de recursos** na lista gerada.

3. Na página Grupos de recursos, selecione o grupo de recursos que você criou com o Microsoft Sentinel, **SC900-ResourceGroup**.

4. Na parte superior central da página, selecione **Excluir grupo de recursos**.  Verifique o aviso de segurança.  Insira o nome do grupo de recursos, **SC900-ResourceGroup**, e selecione **Excluir** na parte inferior da página.  Vai levar alguns minutos para excluir o grupo de recursos.

5. Após verificar que o grupo de recursos foi excluído, feche a página do navegador.

### <a name="review"></a>Revisão

Nesta demonstração, você percorreu as etapas para conectar o Microsoft Sentinel a fontes de dados, configurou uma pasta de trabalho e percorreu várias opções disponíveis no Microsoft Sentinel.
