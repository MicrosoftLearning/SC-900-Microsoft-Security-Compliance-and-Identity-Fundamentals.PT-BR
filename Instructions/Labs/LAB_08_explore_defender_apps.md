<a name="---"></a><!---
---
Laboratório: Título: 'Explorar o Microsoft Defender for Cloud Apps ' Módulo: 'Roteiro de aprendizagem: descrever as funcionalidades das soluções de segurança da Microsoft; Module 4: descrever as funcionalidades de proteção contra ameaças do Microsoft 365; Unidade 5: descrever o Microsoft Defender for Cloud Apps'
---
--->

# <a name="lab-explore-microsoft-defender-for-cloud-apps"></a>Laboratório: Explorar aplicativos do Microsoft Defender for Cloud Apps

Esse laboratório é mapeado para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades da solução de segurança da Microsoft
- Módulo: descrever as funcionalidades de proteção contra ameaças do Microsoft 365
- Unidade: descrever o Microsoft Defender for Cloud Apps

## <a name="lab-scenario"></a>Cenário do laboratório

Neste laboratório, você vai explorar as funcionalidades do Microsoft Defender para Aplicativos de Nuvem.  Você verá as informações disponíveis no painel do Cloud Discovery, o catálogo de aplicativos na nuvem, as funcionalidades disponíveis para investigar as descobertas com o Log de atividades e os Arquivos e as formas de controlar o impacto na sua organização por meio de Políticas. Observação: uma organização precisa ter uma licença para usar o Microsoft Defender para Aplicativos de Nuvem, pois este é um serviço por assinatura baseado no usuário.

**Tempo estimado**: 15 a 20 minutos

### <a name="task-1---explore-cloud-discovery"></a>Tarefa 1 – Explorar o Cloud Discovery

Explorar o Cloud Discovery.

1. Abra o Microsoft Edge. Na barra de endereços, insira **admin.microsoft.com**.

1. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é a sua ID de locatário exclusiva fornecida pelo provedor de hospedagem do laboratório) e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**. Vamos ser direcionados à página Centro de administração do Microsoft 365.

1. À esquerda no painel de navegação do Centro de administração do Microsoft 365, selecione **Mostrar todos**.

1. Em Centros de administração, selecione **Segurança**.  A página inicial do Portal do Microsoft 365 Defender vai ser aberta no navegador.  

1. Se essa for a primeira vez que você visita o portal do Microsoft 365 Defender, pode ser que apareça uma janela pop-up para fazer um tour rápido.  Feche a janela.

1. No painel de navegação à esquerda, selecione **Aplicativos de nuvem** para expandir a lista e selecione **Cloud Discovery**. Isso levará você para a exibição Painel.  Observe as informações disponíveis no painel. Na exibição de painel, você poderá selecionar diferentes guias na parte superior da página.  

1. Selecione **Aplicativos descobertos**. A janela de arquivos descobertos oferece uma visão mais detalhada dos aplicativos descobertos, incluindo pontuação de risco, tráfego, número de usuários, etc.
    1. A partir de qualquer item da lista, selecione as **reticências** na coluna de ações na tabela.  Observe as diversas opções disponíveis, incluindo a possibilidade de marcar um aplicativo como sancionado ou não sancionado.  Selecione as **reticências** de novo para fechar a caixa de ações.
    1. Ao selecionar algum dos itens listados nas linhas, uma página de detalhes é aberta para o aplicativo específico.  Selecione um item na lista e revise as informações disponíveis na página de visão geral.  Para o item selecionado, selecione a guia **Uso do aplicativo na nuvem** para ver informações mais detalhadas, incluindo **Uso**, **Usuários, IP**, **Endereços** e **Alertas**. Quando terminar de explorar a página de detalhes, volte à página de aplicativos descobertos selecionando **Cloud Discovery** na navegação estrutural na parte superior da página.  Se você selecionar Cloud Discovery no painel de navegação à esquerda, isso levará você novamente ao exibição de painel.
    1. Na parte superior da página, selecione a guia **Endereços IP**. Aqui, você encontrará dados, incluindo o número de transações, a quantidade de tráfego e os valores de upload, por endereço IP.  Observe que também é possível filtrar por endereço IP específico ou exportar os dados para uma análise mais aprofundada.
    1. Na parte superior da página, selecione **Usuários**.  Esse é o mesmo tipo de informação fornecida quando você seleciona os endereços IP, mas aqui ela é listada por usuários individuais.  Mais uma vez, é possível filtrar por usuário específico e exportar dados para análises mais aprofundadas.

1. As informações apresentadas na página Cloud Discovery e nas guias relacionadas são geradas em relatórios de instantâneos dos logs de tráfego carregados manualmente dos firewalls ou dos proxies ou em relatórios contínuos que analisam todos os logs encaminhados da sua rede por meio do Cloud App Security.  Para ver o local em que é feita essa configuração, selecione **Ações** no canto superior direito da página.
    1. Selecione a primeira opção, **Criar relatório de instantâneo do Cloud Discovery** e escolha **Avançar**. Aqui, você preenche os detalhes exigidos e carrega os logs de tráfego para gerar e carregar um relatório.  Selecione **Sair** e, se o prompt Tem certeza? for exibido, escolha **Sair** novamente.  Os dados que você vê no locatário do laboratório são provenientes de um Relatório de instantâneo. É possível ver essa informação na parte superior da janela Cloud Discovery.
    1. Para ver a opção de relatórios contínuos, selecione **Ações** no canto superior direito da página e, no menu suspenso, escolha **Configurar upload automático**.  Não tem fontes de dados conectadas, mas aqui é onde seria possível adicionar uma fonte de dados. Selecione **Adicionar uma fonte de dados** e escolha a seta para baixo no campo **Selecionar dispositivo** para ver os tipos de dispositivos que você pode conectar como uma fonte de dados.  Selecione **Cancelar** para sair. 
    1. No painel de navegação à esquerda, selecione **Cloud Discovery** para voltar à página do Cloud Discovery.

1. Você pode se conectar aos aplicativos diretamente configurando conectores de aplicativos que oferecerão maior visibilidade e controle dos aplicativos de nuvem. No canto superior direito da tela, selecione **Ações** e escolha **Configurações do Cloud Discovery**.  No lado esquerdo da tela, em Aplicativos conectados, selecione **Conectores de aplicativo**.  

    1. Na página Aplicativos conectados, selecione *Office 365** na lista para ver informações detalhadas. Se o Office 365 mostrar um erro de conexão, será provável que a Auditoria não esteja ativada.  Se a auditoria estiver habilitada, acesse as reticências verticais no lado direito do item de linha e selecione **editar configurações**.  Para se reconectar, selecione **Conectar o Office 365** na parte inferior da página. A página agora mostrará que o Office 365 está conectado. Selecione **Concluído**.  O status agora será exibido com um sinal de aviso amarelo, indicando que não há nenhum status recente.  Levará algum tempo para que o status seja atualizado, pois o período de verificação retroativo varia de acordo com o aplicativo, e os locatários do laboratório podem enfrentar atrasos mais longos do que o normal.
    1. Agora você vai configurar um novo conector de aplicativo.  Selecione **+Conectar um aplicativo**. Na lista suspensa, selecione **Microsoft Azure**.  Na janela pop-up do Microsoft Azure, selecione **Conectar Microsoft Azure** e escolha **Concluído**.  Você verá um status conectado (se não o vir, atualize o navegador) e informações sobre a verificação de usuários, dados e atividades.  Volte ao painel do Cloud Discovery selecionando **Cloud Discovery** no painel de navegação mais à esquerda.

1. Mantenha essa página aberta, pois você vai usá-la na próxima tarefa.

### <a name="task-part-2---explore-the-cloud-app-catalog"></a>Tarefa – Parte 2 – Explorar o catálogo de aplicativos na nuvem

O Cloud Discovery analisa seus logs de tráfego com base no catálogo de mais de 31 mil aplicativos na nuvem do Microsoft Defender para Aplicativos de Nuvem. Os aplicativos são classificados e pontuados com base em mais de 80 fatores de risco para fornecer visibilidade contínua do uso da nuvem, do shadow IT e o risco que o shadow IT representa para sua organização.  Nesta tarefa, você vai explorar as funcionalidades do catálogo de aplicativos na nuvem.

1. No painel de navegação à esquerda, selecione **catálogo de aplicativos na nuvem**.

1. O catálogo de aplicativos de nuvem permite que você escolha quais aplicativos atendem aos requisitos de segurança da sua organização. Os administradores podem fazer a filtragem básica de aplicativos, conforme mostrado na parte superior da página, o que inclui se o aplicativo é sancionado, não sancionado ou não tem marca, pontuação de risco, fator de risco de conformidade e fator de risco de segurança.  Por exemplo, a filtragem por fator de risco de conformidade permite que você pesquise padrões específicos, certificação e conformidade com os quais o aplicativo pode estar em conformidade. Exemplos incluem HIPAA, ISO 27001, SOC 2 e PCI-DSS. Selecione **Fator de risco de conformidade** para ver as opções disponíveis.  Você pode filtrar ainda mais o conteúdo por pontuação de risco, movendo os controles deslizantes na pontuação de risco na parte superior da página. Se você moveu o controle deslizante, defina-o para que o intervalo seja definido como 0 a 10.

1. Os administradores também podem pesquisar aplicativos por categoria.  Por exemplo, no campo Pesquisar categoria, insira **Rede social** e selecione **Rede social**.  Selecione **Yammer** para obter uma exibição detalhada.  Se você posicionar o cursor sobre um tópico de determinada categoria, verá um ícone de informações que poderá selecionar para obter mais informações sobre o tópico.

1. Mantenha essa página aberta, pois você vai usá-la na próxima tarefa.

### <a name="task-3---explore-the-activity-log-and-files"></a>Tarefa 3 – Explorar o Log de atividades e os Arquivos

Explore as maneiras de investigar as atividades gravadas com o log de atividades e os arquivos.

1. No painel de navegação à esquerda, selecione e explore a opção **Arquivos** e observe as opções para filtrar os dados por aplicativo, proprietário, nível de acesso, tipo de arquivo e política correspondente. Além disso, observe a opção de criação de uma política na pesquisa e na exportação dos dados.
    1. Selecione **+ Nova política da pesquisa**.  Observe que é possível criar uma política com base em modelo, selecionar a severidade e a categoria da política, criar filtros para a política, criar alertas e até enviar alertas para o Power Automate.  Selecione **Cancelar** para sair da janela de criação de política e escolha **Sair da página**.

1. No painel de navegação à esquerda, selecione **Log de Atividades**. Aqui você obtém visibilidade de todas as atividades de seus aplicativos conectados. Talvez você não veja nenhum dado listado, pois pode levar várias horas para executar verificações retroativas depois que a auditoria estiver habilitada e os locatários do laboratório poderão enfrentar atrasos mais longos do que o normal. Observe as opções de filtro disponíveis e a opção para criar uma política por meio da pesquisa.

1. Mantenha essa página aberta, pois você vai usá-la na próxima tarefa.

### <a name="task-4---explore-policies"></a>Tarefa 4 – Explorar as políticas

Nesta tarefa, você vai explorar as políticas do Microsoft Defender para Aplicativos de Nuvem.

1. No painel de navegação à esquerda, selecione **Políticas** e **Gerenciamento de políticas**.  As políticas listadas fornecem informações sobre o número de alertas gerados pela política, gravidade etc. Selecione qualquer item de linha para ver informações mais detalhadas sobre a política. Selecione um item da lista, i.e., **Entrada suspeita**.

    1. Observe que você também pode criar uma política. Selecione **+ Criar política** para ver os tipos de políticas que você pode criar.  Selecione **Política de atividade** para ver as diferentes opções disponíveis para criar a política.  Selecione **Cancelar** para sair da janela de configuração.
    1. Observe que você também pode ter a opção de exportar as informações da política.

1. No painel de navegação à esquerda, selecione **Modelos de política**. Para criar uma política com base em um dos modelos disponíveis, selecione o **+** no lado esquerdo do item de linha do modelo.  Veja as diferentes opções de configuração da política.  Selecione **Cancelar** para sair da página.

1. Feche a janela do navegador.

### <a name="review"></a>Revisão

Neste laboratório, você explorou as funcionalidades do Microsoft Defender for Cloud Apps.  Você acompanhou as informações disponíveis no painel do Cloud Discovery, o catálogo de aplicativos na nuvem, as funcionalidades disponíveis para investigar as descobertas e as formas de controlar o impacto na sua organização por meio de políticas.
