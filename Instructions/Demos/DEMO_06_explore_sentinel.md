<a name="---"></a><!---
---
Demonstração: Título: 'Microsoft Sentinel' Roteiro de aprendizagem/Módulo/Título: 'Roteiro de aprendizagem: descrever as funcionalidades das soluções de segurança da Microsoft; Módulo 3: descrever as funcionalidades de segurança do Microsoft Sentinel; Unidade 3: descrever como o Microsoft Sentinel fornece gerenciamento integrado de ameaças'
---
--->

# <a name="demo-microsoft-sentinel"></a>Demonstração: Microsoft Sentinel

Essa demonstração é mapeada para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades da solução de segurança da Microsoft
- Módulo: descrever as funcionalidades de segurança do Microsoft Sentinel
- Unidade: descrever como o Microsoft Sentinel fornece gerenciamento integrado de ameaças

## <a name="demo-scenario"></a>Cenário da demonstração

Nesta demonstração, você acompanhará o processo de criação de uma instância do Microsoft Sentinel.  Também vamos configurar as permissões para garantir o acesso aos recursos que serão implantados para dar suporte ao Microsoft Sentinel.  Depois que essa configuração básica for concluída, você vai seguir as etapas para conectar o Microsoft Sentinel às suas fontes de dados e selecionar uma pasta de trabalho para monitorar e visualizar seus dados.  Por fim, você mostrará algumas das outras opções disponíveis, incluindo a análise integrada para ser notificado sobre qualquer coisa suspeita, a funcionalidade de automação, entre outros.

### <a name="pre-demo-setup--create-a-microsoft-sentinel-instance"></a>Configuração pré-demonstração: Criar uma instância do Microsoft Sentinel

1. Abra a guia do navegador, **Página Inicial – Microsoft Azure**.  Se você fechou a guia anteriormente, abra uma página do navegador e, na barra de endereços, insira portal.azure.com e entre novamente.

1. Na caixa de pesquisa, na barra azul no topo da página, perto de onde está escrito Microsoft Azure, digite **Microsoft Sentinel** e selecione **Microsoft Sentinel** nos resultados da pesquisa.

1. Na página do Microsoft Sentinel, selecione **Criar Microsoft Sentinel**.

1. Na página Adicionar o Microsoft Sentinel a um workspace, selecione **Criar um workspace**.

1. Na guia Básico da página Criar espaço de trabalho do Log Analytics, insira:
    1. Assinatura: mantenha o padrão.
    1. Grupo de recursos: selecione **Criar novo**, insira o nome **SC900-Sentinel-RG** e clique em **OK**.
    1. Nome: **SC900-LogAnalytics-workspace**.
    1. Região: **Leste dos EUA** (uma região padrão diferente pode ser selecionada com base em sua localização)
    1. Selecione **Revisar + Criar** (nenhuma marca será configurada).
    1. Verifique as informações inseridas e selecione **Criar**.
    1. Pode levar um ou dois minutos até que o novo workspace seja listado; caso ele ainda não seja exibido, selecione **Atualizar** e depois **Adicionar**.

1. Depois que o novo workspace for adicionado, a página Microsoft Sentinel | Novidades e guias será exibida, indicando que a avaliação gratuita do Microsoft Sentinel está ativada.  Selecione **OK**.  Veja as três etapas listadas na página de Introdução.

1. Mantenha essa página aberta, pois você vai usá-la na próxima tarefa.

### <a name="demo-part-2"></a>Demonstração parte 2

Com a instância do Microsoft Sentinel criada, o ideal é verificar se você tem o acesso necessário aos recursos implantados para dar suporte ao Microsoft Sentinel.  

1. Na caixa de pesquisa, na barra azul no topo da página, perto de onde está escrito Microsoft Azure, digite **grupos de recursos** e selecione **Grupos de recursos** nos resultados da pesquisa. Atribuir a função a nível do grupo de recursos vai garantir que ela seja aplicada a todos os recursos implantados para comportar o Microsoft Sentinel.

1. Na página de Grupos de recursos, selecione o grupo de recursos que você criou com o Microsoft Sentinel, **SC900-Sentinel-RG**.

1. Na página do SC900-Sentinel-RG, selecione **Controle de acesso (IAM)** no painel de navegação à esquerda.

1. Na página Controle de acesso, selecione **Exibir meu acesso**.  Como Administrador MOD, a função atual é Administrador de serviços.  Isso concederá as permissões necessárias, mas para fins de demonstração, convém mostrar as funções específicas do Sentinel.  Feche a janela de atribuições do Administrador MOD selecionando o **X** no canto superior direito da tela.

    1. Na página Controle de acesso, selecione **+Adicionar** e depois **Adicionar atribuição de função**.

    1. A janela Adicionar atribuição de função vai ser aberta.  Na caixa de pesquisa, digite **Microsoft Sentinel** para visualizar as 4 funções associadas ao Microsoft Sentinel.
    1. Em qualquer uma das funções listadas, selecione a **Exibir** para ver os detalhes dessa função.  Como prática recomendada, você deve atribuir o privilégio mínimo exigido para a função.  

    1. Feche a janela selecionando o **X** no canto superior direito.

1. Na página de controle de acesso, selecione **X** no canto superior direito da janela para fechá-la.

### <a name="demo-part-3"></a>Demonstração parte 3

Nesta parte da demonstração, você mostrará as etapas usadas para se conectar a uma fonte de dados.  Especificamente, você se conectará ao conector de dados do Microsoft Defender para Nuvem.

1. Na caixa de pesquisa, na barra azul no topo da página, perto de onde está escrito Microsoft Azure, digite **Microsoft Sentinel** e selecione **Microsoft Sentinel** nos resultados da pesquisa.

1. Na página Microsoft Sentinel, selecione o espaço de trabalho criado com a instância do Microsoft Sentinel, **SC900-LogAnalytics-workspace**.

1. A primeira etapa com o Microsoft Sentinel é conseguir coletar dados. À esquerda no painel de navegação, em configuração, selecione **Conectores de dados**.

1. Na página Conectores de dados, role para baixo na janela principal para exibir a extensa lista de conectores disponíveis. Na caixa Pesquisar da página dos conectores de dados, insira **Microsoft Defender para Nuvem** e, na lista, selecione **Microsoft Defender para Nuvem**.

1. A janela do conector do Microsoft Defender para Nuvem será aberta. Leia a descrição e selecione **Abrir página do conector**.

1. Na página do conector do Microsoft Defender para Nuvem, leia a Descrição no lado esquerdo da janela.

1. A guia Instruções na janela principal fornece os requisitos.  Analise as instruções e as informações de configuração.
    A guia Instruções na janela principal fornece os requisitos.  Analise as instruções e as informações de configuração.
    1. Na seção de configuração, selecione a caixa vazia ao lado da assinatura listada, **Assinatura MOC – lodXXXXXXXXXX**, de modo que uma marca de seleção seja exibida em uma caixa azul e escolha **Conectar** (a opção Conectar é mostrada acima da caixa de pesquisa).  Uma janela Conectar será exibida. Selecione **OK**.  Na coluna Status, ao lado da assinatura, você verá o status ser atualizado para Conectado.  Não se preocupe se você não observar o status Conectado na janela no lado esquerdo da página. NÃO atualize o navegador.
    1. Role a página para baixo e selecione **Habilitar** para criar incidentes automaticamente com base em todos os alertas gerados no serviço conectado.
    1. Agora, selecione a guia **Próximas etapas** na parte superior da página para ver as pastas de trabalho recomendadas para esse conector de dados.  O Microsoft Sentinel é fornecido com modelos de pasta de trabalho internos para que você possa obter insights rapidamente dos seus dados assim que conectar uma fonte de dados.
    1. Selecione **Conformidade e Proteção da ASC** (Observação: a ASC ou a Central de Segurança do Azure passou a se chamar Microsoft Defender para Nuvem).  Isso abrirá a página de pastas de trabalho.  No lado direito da tela, leia a descrição e selecione **Salvar**, na parte inferior da tela. Em seguida, selecione **OK** para salvar a pasta de trabalho no local padrão.  Agora selecione **Exibir pasta de trabalho salva**.  
    1. No campo do workspace, selecione **SC900-LogAnalytics-workspace**.
    1. Na parte superior da página da pasta de trabalho, selecione **Atualização automática: Desativado**, selecione **5 minutos** e escolha **Aplicar**.
    1. Na parte superior da página da pasta de trabalho, selecione o **ícone Salvar**.
    1. No canto superior esquerdo da página Pastas de trabalho, acima de onde está escrito Pastas de trabalho, clique em **Microsoft Sentinel**. Isso direcionará você de volta à página Visão geral. Agora você verá o número 1 acima em Conectado, para indicar um conector ativo (talvez seja necessário selecionar Atualizar).

1. Mantenha essa página aberta, pois você vai usá-la na próxima tarefa.

### <a name="demo-part-4"></a>Demonstração parte 4

Nesta parte da demonstração, você mostrará algumas das opções disponíveis no Sentinel.

1. No painel de navegação esquerdo, selecione **Buscar**.  Na guia **Consultas** selecionada (sublinhada), clique em qualquer consulta na lista.  Depois que uma consulta for selecionada, observe as informações fornecidas sobre ela, incluindo o código, bem como a opção de execução e exibição dos resultados.  Não selecione nada.

1. No painel de navegação esquerdo, selecione **MITRE ATT&CK**.  O MITRE ATT&CK é uma base de dados de conhecimento publicamente acessível de táticas e técnicas que são comumente usadas por invasores. Com o Microsoft Sentinel você pode visualizar as detecções já ativas em seu workspace e aquelas disponíveis para você configurar, para entender a cobertura de segurança da sua organização, com base nas táticas e técnicas do framework MITRE ATT&CK®.  Selecione qualquer célula da matriz e anote as informações disponíveis no lado direito da tela.  

1. À esquerda no painel de navegação, selecione **Comunidade**. Os analistas de segurança da Microsoft criam e adicionam constantemente novas pastas de trabalho, guias estratégicos, consultas de busca e muito mais, publicando-os na comunidade para uso em seu ambiente. Você pode baixar o conteúdo de exemplo no repositório do GitHub privado da comunidade para criar pastas de trabalho personalizadas, consultas de busca, notebooks e guias estratégicos para o Microsoft Sentinel.  Selecione **Integrar conteúdo da comunidade**.  Uma nova guia para o repositório GitHub, em que você pode baixar conteúdo para habilitar seus cenários, é aberta.  Retorne à guia do Azure no navegador.

1. À esquerda no painel de navegação, selecione **Análise**.  Selecione o primeiro item da lista **Detecção avançada de ataque de várias etapas**.  Leia as informações detalhadas.  O Microsoft Sentinel usa o Fusion, um mecanismo de correlação baseado em algoritmos de aprendizado de máquina escaláveis, para detectar automaticamente ataques de vários estágios (também conhecidos como ameaças persistentes avançadas) identificando combinações de comportamentos anômalos e atividades suspeitas que são observadas em vários estágios da cadeia de eliminação. Com base nessas descobertas, o Microsoft Sentinel gera incidentes que, de outra forma, seriam difíceis de detectar.

1. À esquerda no painel de navegação, selecione **Automação**.  Aqui você pode criar regras de automação simples, integrá-las a manuais existentes ou criar novos manuais.  Selecione **+ Criar** e clique em **Regra de Automação**.  Observe a janela que é aberta no lado direito da tela e as opções de criação de condições e ações são disponibilizadas.  Selecione **Cancelar** na parte inferior da tela.

1. À esquerda no painel de navegação, selecione **Pastas de trabalho**. Na página Pastas de trabalho, selecione a guia **Minhas pastas de trabalho**, que fica acima da caixa de pesquisa.  A pasta de trabalho que você salvou anteriormente estará listada e disponível para você visualizar e monitorar seus dados.   OBSERVAÇÃO: não há nenhuma atividade real acontecendo na assinatura do Azure para refletir na pasta de trabalho, e as assinaturas do laboratório do Azure podem enfrentar atrasos maiores do que o normal na coleta de dados que podem ser visualizados na pasta de trabalho.

1. Feche a janela selecionando o **X** no canto superior direito.

1. No canto superior esquerdo da janela, logo abaixo da barra azul, selecione **Página Inicial** para retornar à home page do portal do Azure.  

### <a name="review"></a>Revisão

Nesta demonstração, você percorreu as etapas para conectar o Microsoft Sentinel a fontes de dados, configurou uma pasta de trabalho e percorreu várias opções disponíveis no Microsoft Sentinel.
