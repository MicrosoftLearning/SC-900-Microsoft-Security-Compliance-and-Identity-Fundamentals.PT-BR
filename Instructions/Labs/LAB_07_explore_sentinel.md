<a name="---"></a><!---
---
Laboratório: Título: 'Explorar o Microsoft Sentinel' Roteiro de aprendizagem/Módulo/Título: 'Roteiro de aprendizagem: descrever as funcionalidades das soluções de segurança da Microsoft; Módulo 3: descrever as funcionalidades de segurança do Microsoft Sentinel; Unidade 3: descrever como o Microsoft Sentinel fornece gerenciamento integrado de ameaças'
---
--->

# <a name="lab-explore-microsoft-sentinel"></a>Laboratório: Explorar o Microsoft Sentinel

Esse laboratório é mapeado para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades da solução de segurança da Microsoft
- Módulo: descrever as funcionalidades de segurança do Microsoft Sentinel
- Unidade: descrever como o Microsoft Sentinel fornece gerenciamento integrado de ameaças

## <a name="lab-scenario"></a>Cenário do laboratório

, você conhecerá o processo de criação de uma instância do Microsoft Sentinel.  Você também vai configurar as permissões para garantir o acesso aos recursos que serão implantados para dar suporte ao Microsoft Sentinel.  Depois que essa configuração básica for concluída, você vai seguir as etapas para conectar o Microsoft Sentinel às suas fontes de dados, configurar uma pasta de trabalho e mostrar um breve passo a passo de algumas das principais funcionalidades disponíveis no Microsoft Sentinel. 

**Tempo estimado**: 45 a 60 minutos

### <a name="task-1"></a>Tarefa 1:

Criar uma instância do Microsoft Sentinel

1. Abra o Microsoft Edge. Na barra de endereços, insira **portal.azure.com**.
1. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira o nome de usuário fornecido pelo provedor de hospedagem do laboratório e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**.

1. Na caixa de pesquisa azul na parte superior da página, insira **Microsoft Sentinel** e selecione **Microsoft Sentinel** nos resultados da pesquisa.

1. Na página do Microsoft Sentinel, selecione **Criar Microsoft Sentinel**.

1. Na página Adicionar o Microsoft Sentinel a um workspace, selecione **Criar um workspace**.

1. Na guia Básico da página Criar espaço de trabalho do Log Analytics, insira:
    1. Assinatura: mantenha o padrão. Esta é a assinatura do Azure fornecida pelo ALH (Hoster do Laboratório Autorizado).
    1. Grupo de recursos: selecione **Criar novo**, insira o nome **SC900-Sentinel-RG** e clique em **OK**.
    1. Nome: **SC900-LogAnalytics-workspace**.
    1. Região: **Leste dos EUA** (uma região padrão diferente pode ser selecionada com base em sua localização)
    1. Selecione **Revisar + Criar** (nenhuma marca será configurada).
    1. Verifique as informações inseridas e selecione **Criar**.
    1. Pode levar um ou dois minutos até que o novo workspace seja listado; caso ele ainda não seja exibido, selecione **Atualizar** e depois **Adicionar**.

1. Depois que o novo workspace for adicionado, a página Microsoft Sentinel | Novidades e guias será exibida, indicando que a avaliação gratuita do Microsoft Sentinel está ativada.  Selecione **OK**.  Veja as três etapas listadas na página de Introdução.

1. Mantenha essa página aberta, pois você vai usá-la na próxima tarefa.

### <a name="task-2"></a>Tarefa 2:

Com a instância do Microsoft Sentinel criada, é importante que os usuários que terão a responsabilidade de dar suporte ao Microsoft Sentinel tenham as permissões necessárias.  Isso é feito pela atribuição das permissões de função necessárias ao usuário designado.  Nesta tarefa, você verá as funções internas disponíveis do Microsoft Sentinel.

1. Na caixa de pesquisa azul, insira **grupos de recursos** e selecione **Grupos de recursos** nos resultados da pesquisa. 

1. Na página de Grupos de recursos, selecione o grupo de recursos que você criou com o Microsoft Sentinel, **SC900-Sentinel-RG**.  Trabalhar no grupo de recursos garantirá que qualquer função selecionada seja aplicada a todos os recursos que integram a instância do Microsoft Sentinel criada na tarefa anterior.

1. Na página do SC900-Sentinel-RG, selecione **Controle de acesso (IAM)** no painel de navegação à esquerda.

1. Na página Controle de acesso, selecione **Exibir meu acesso**.  Para a assinatura do Azure fornecida pelo Hoster de Laboratório Autorizado, uma função foi definida que dará a você acesso para gerenciar todos os recursos necessários, conforme mostrado na descrição. No entanto, é importante entender as funções específicas do Sentinel disponíveis.  Selecione o **X** no canto superior direito da janela de tarefas para fechá-la.

1. Na página Controle de acesso, selecione a guia **Funções** na parte superior da página.
    1. Na caixa de pesquisa, insira **Microsoft Sentinel** para ver as funções internas associadas ao Microsoft Sentinel.
    1. Em qualquer uma das funções listadas, selecione a **Exibir** para ver os detalhes dessa função.  Como prática recomendada, você deve atribuir o privilégio mínimo exigido para a função.  
    1. Feche a janela selecionando o **X** no canto superior direito.

1. Na página de controle de acesso, selecione **X** no canto superior direito da janela para fechá-la.

### <a name="task-3"></a>Tarefa 3

A finalidade dessa tarefa é orientar você pelas etapas envolvidas na configuração de um conector de dados para sua instância do Microsoft Sentinel e na seleção de modelos de pasta de trabalho internos para permitir que você obtenha insights rapidamente sobre seus dados assim que conectar uma fonte de dados. OBSERVAÇÃO: as assinaturas de laboratório do Azure podem enfrentar atrasos maiores do que o normal na conexão com uma fonte de dados e/ou na visualização de dados.

1. Na caixa de pesquisa, na barra azul no topo da página, perto de onde está escrito Microsoft Azure, digite **Microsoft Sentinel** e selecione **Microsoft Sentinel** nos resultados da pesquisa.

1. Na página Microsoft Sentinel, selecione o espaço de trabalho criado com a instância do Microsoft Sentinel, **SC900-LogAnalytics-workspace**.

1. A primeira etapa com o Microsoft Sentinel é conseguir coletar dados. À esquerda no painel de navegação, em configuração, selecione **Conectores de dados**.

1. Na página Conectores de dados, role para baixo na janela principal para exibir a extensa lista de conectores disponíveis. Na caixa Pesquisar da página dos conectores de dados, insira **Microsoft Defender para Nuvem** e, na lista, selecione **Microsoft Defender para Nuvem**.

1. A janela do conector do Microsoft Defender para Nuvem será aberta. Leia a descrição e selecione **Abrir página do conector**.

1. Na página do conector do Microsoft Defender para Nuvem, leia a Descrição no lado esquerdo da janela.

1. A guia Instruções na janela principal fornece os requisitos.  Analise as instruções e as informações de configuração.
    1. Na seção de configuração, selecione a caixa vazia ao lado da assinatura listada, **Assinatura MOC – lodXXXXXXXXXX**, de modo que uma marca de seleção seja exibida em uma caixa azul e escolha **Conectar** (a opção Conectar é mostrada acima da caixa de pesquisa).  Uma janela Conectar será exibida. Selecione **OK**.  Na coluna Status, ao lado da assinatura, você verá o status ser atualizado para Conectado.  Não se preocupe se você não observar o status Conectado na janela no lado esquerdo da página. NÃO atualize o navegador.
    1. Role a página para baixo e selecione **Habilitar** para criar incidentes automaticamente com base em todos os alertas gerados no serviço conectado.
    1. Agora, selecione a guia **Próximas etapas** na parte superior da página para ver as pastas de trabalho recomendadas para esse conector de dados.  O Microsoft Sentinel é fornecido com modelos de pasta de trabalho internos para que você possa obter insights rapidamente dos seus dados assim que conectar uma fonte de dados.
    1. Selecione **Conformidade e Proteção da ASC** (Observação: a ASC ou a Central de Segurança do Azure passou a se chamar Microsoft Defender para Nuvem).  Isso abrirá a página de pastas de trabalho.  No lado direito da tela, leia a descrição e selecione **Salvar**, na parte inferior da tela. Em seguida, selecione **OK** para salvar a pasta de trabalho no local padrão.  Agora selecione **Exibir pasta de trabalho salva**.
    1. No campo do workspace, selecione **SC900-LogAnalytics-workspace**.
    1. Na parte superior da página da pasta de trabalho, selecione **Atualização automática: Desativado**, selecione **5 minutos** e escolha **Aplicar**.
    1. Na parte superior da página da pasta de trabalho, selecione o **ícone Salvar**.
    1. No canto superior esquerdo da página Pastas de trabalho, acima de onde está escrito Pastas de trabalho, clique em **Microsoft Sentinel**. Isso direcionará você de volta à página Visão geral. Agora você verá o número 1 acima em Conectado, para indicar um conector ativo (talvez seja necessário selecionar Atualizar).

1. Mantenha essa página aberta, pois você vai usá-la na próxima tarefa.

### <a name="task-4"></a>Tarefa 4

Nesta tarefa, você percorrerá algumas das opções disponíveis no Sentinel.

1. No painel de navegação esquerdo, selecione **Buscar**.  Na guia **Consultas** selecionada (sublinhada), clique em qualquer consulta na lista.  Depois que uma consulta for selecionada, observe as informações fornecidas sobre ela, incluindo o código, bem como a opção de execução e exibição dos resultados.  Não selecione nada.

1. No painel de navegação esquerdo, selecione **MITRE ATT&CK**.  O MITRE ATT&CK é uma base de dados de conhecimento publicamente acessível de táticas e técnicas que são comumente usadas por invasores. Com o Microsoft Sentinel você pode visualizar as detecções já ativas em seu workspace e aquelas disponíveis para você configurar, para entender a cobertura de segurança da sua organização, com base nas táticas e técnicas do framework MITRE ATT&CK®.  Selecione qualquer célula da matriz e anote as informações disponíveis no lado direito da tela.  

1. À esquerda no painel de navegação, selecione **Comunidade**. Os analistas de segurança da Microsoft criam e adicionam constantemente novas pastas de trabalho, guias estratégicos, consultas de busca e muito mais, publicando-os na comunidade para uso em seu ambiente. No lado direito da tela, selecione **Integrar conteúdo da comunidade**.  Uma nova guia para o repositório GitHub, em que você pode baixar conteúdo para habilitar seus cenários, é aberta. Role a página para baixo até a seção README.md e leia a descrição. Retorne à guia do Azure no navegador.

1. À esquerda no painel de navegação, selecione **Análise**.  Selecione o primeiro item da lista **Detecção avançada de ataque de várias etapas**.  Leia as informações detalhadas.  O Microsoft Sentinel usa o Fusion, um mecanismo de correlação baseado em algoritmos de aprendizado de máquina escaláveis, para detectar automaticamente ataques de vários estágios (também conhecidos como ameaças persistentes avançadas) identificando combinações de comportamentos anômalos e atividades suspeitas que são observadas em vários estágios da cadeia de eliminação. Com base nessas descobertas, o Microsoft Sentinel gera incidentes que, de outra forma, seriam difíceis de detectar.

1. À esquerda no painel de navegação, selecione **Automação**.  Aqui você pode criar regras de automação simples, integrá-las aos guias estratégicos existentes ou criar guias estratégicos.  Selecione **+ Criar** e clique em **Regra de Automação**.  Observe a janela que é aberta no lado direito da tela e as opções de criação de condições e ações são disponibilizadas.  Selecione **Cancelar** na parte inferior da tela.

1. À esquerda no painel de navegação, selecione **Pastas de trabalho**. Na página Pastas de trabalho, selecione a guia **Minhas pastas de trabalho**, que fica acima da caixa de pesquisa.  A pasta de trabalho que você salvou anteriormente estará listada e disponível para você visualizar e monitorar seus dados.   OBSERVAÇÃO: não há nenhuma atividade real acontecendo na assinatura do Azure para refletir na pasta de trabalho, e as assinaturas do laboratório do Azure podem enfrentar atrasos maiores do que o normal na coleta de dados que podem ser visualizados na pasta de trabalho.

1. Feche a janela selecionando o **X** no canto superior direito.

1. No canto superior esquerdo da janela, logo abaixo da barra azul, selecione **Página Inicial** para retornar à home page do portal do Azure.

1. Feche todas as guias abertas do navegador.

### <a name="review"></a>Revisão

Nesta demonstração, você percorreu as etapas para conectar o Microsoft Sentinel a fontes de dados, configurou uma pasta de trabalho e percorreu várias opções disponíveis no Microsoft Sentinel.
