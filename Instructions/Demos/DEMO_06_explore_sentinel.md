<!---
---
Demonstração: Título: "Microsoft Sentinel" Roteiro de aprendizagem/Módulo/Título: "Roteiro de aprendizagem: descrever as capacidades das soluções de segurança da Microsoft. Módulo 3: descrever as capacidades de segurança do Microsoft Sentine.; Unidade 3: descrever as capacidades de detecção e mitigação de ameaças no Microsoft Sentinel"
---
--->

# Demonstração: Microsoft Sentinel

Essa demonstração é mapeada para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades das soluções de segurança da Microsoft
- Módulo: descrever as funcionalidades de segurança do Microsoft Sentinel
- Unidade: descrever as capacidades de detecção e mitigação de ameaças no Microsoft Sentinel

## Cenário de demonstração

Nesta demonstração, você percorrerá algumas das opções disponíveis com o Microsoft Sentinel, incluindo o uso do hub de conteúdo para encontrar soluções empacotadas que você pode implantar.  Mas, primeiro, você percorrerá o processo de configuração de permissões de controle de acesso baseado em função para usuários que precisam acessar seus recursos do Microsoft Sentinel.

### Demonstração parte 1

Uma instância do Microsoft Sentinel já deve ter sido criada como parte da instalação de pré-demonstração. Verifique se ela foi criada.

1. Abra a guia do navegador **Página Inicial – Microsoft Azure**.  Se tiver fechado previamente a guia, abra uma página do navegador e, na barra de endereços, insira **https://portal.azure.com** . Entre com as credenciais do Azure fornecidas pelo hoster de laboratório autorizado (ALH).  Isso o levará você à página inicial dos serviços do Azure.

1. Na caixa de pesquisa, na barra azul no topo da página, perto de onde está escrito Microsoft Azure, digite **Microsoft Sentinel** e selecione **Microsoft Sentinel** nos resultados da pesquisa.  

1. Na página Microsoft Sentinel, você deve ver sua instância do Sentinel listada. Selecione-a.  Se não estiver listada, crie-a agora.
    1. Na página do Microsoft Sentinel, selecione **Criar Microsoft Sentinel**.

    1. Na página Adicionar o Microsoft Sentinel a um workspace, selecione **Criar um workspace**. Na guia Básico do workspace Criar Log Analytics, insira o seguinte:
        1. Assinatura: mantenha o padrão.
        1. Grupo de recursos: selecione **Criar novo**, insira o nome **SC900-Sentinel-RG** e selecione **OK**.
        1. Nome: **SC900-LogAnalytics-workspace**.
        1. Região: **Leste dos EUA** (uma região padrão diferente pode ser selecionada de acordo com sua localização)
        1. Selecione **Revisar + Criar** (nenhuma marca será configurada).
        1. Verifique se você inseriu as informações corretas e, em seguida, selecione **Criar**.
        1. Pode levar um ou dois minutos para que o workspace seja listado. Se você ainda não conseguir vê-lo, selecione **Atualizar** e, em seguida, selecione **Adicionar**.
        1. Depois que o novo workspace for adicionado, a página Microsoft Sentinel | Novidades e guias será exibida, indicando que a avaliação gratuita do Microsoft Sentinel está ativada.  Selecione **OK**.

1. Mantenha essa página aberta, pois você vai usá-la na tarefa seguinte.

### Demonstração parte 2

Como acontece com todos os recursos do Azure, você deseja garantir que os usuários tenham as permissões adequadas para acessar seus recursos do Microsoft Sentinel. Aqui você mostrará as etapas para atribuir uma função e as funções disponíveis para uso com o Microsoft Sentinel.  

1. Na caixa de pesquisa, na barra azul, na parte superior da página, ao lado de onde está escrito Microsoft Azure, insira **grupos de recursos** e selecione **Grupos de recursos** nos resultados da pesquisa. Atribuir a função a nível do grupo de recursos vai garantir que ela seja aplicada a todos os recursos implantados para comportar o Microsoft Sentinel.

1. Na página de Grupos de recursos, selecione o grupo de recursos que você criou com o Microsoft Sentinel, **SC900-Sentinel-RG**.

1. Na página SC900-Sentinel-RG, selecione **Controle de acesso (IAM)** no painel de navegação esquerdo.

1. Na página Controle de acesso, selecione **Exibir meu acesso**.  Você provavelmente verá uma atribuição de função personalizada já configurada para esta assinatura e ela concederá as permissões necessárias.  Essa função personalizada terá sido configurada pelo host de laboratório autorizado (ALH) que fornece o ambiente de laboratório. Para fins de demonstração, no entanto, é bom mostrar as funções específicas do Sentinel.  Selecione o **X** no canto superior direito da janela de tarefas para fechá-la.

    1. Na página Controle de acesso, selecione **+ Adicionar** e, em seguida, **Adicionar atribuição de função**.

    1. A janela Adicionar atribuição de função é aberta.  Na caixa de pesquisa, digite **Microsoft Sentinel** para visualizar as funções associadas ao Microsoft Sentinel.
    1. Em qualquer uma das funções listadas, selecione a **Exibir** para ver os detalhes dessa função.  Como prática recomendada, você deve atribuir o privilégio mínimo necessário para a função.  

    1. Feche a janela selecionando o **X** no canto superior direito.

1. Na página de controle de acesso, selecione **X** no canto superior direito da janela para fechá-la.

### Demonstração parte 3

Nesta parte da demonstração, você mostrará as etapas usadas para se conectar a uma fonte de dados. Muitos conectores de dados são implantados como parte de uma solução do Microsoft Sentinel, juntamente com conteúdos relacionados, como regras de análise, pastas de trabalho e guias estratégicos. O Hub de Conteúdo do Microsoft Sentinel é o local centralizado para descobrir e gerenciar o conteúdo pronto para uso (interno). Nesta etapa, você usará o Hub de Conteúdo para implantar a solução Microsoft Defender para Nuvem para o Microsoft Sentinel.  Essa solução permite a você ingerir os alertas de segurança relatados no Microsoft Defender para Nuvem.

1. Abra a guia do navegador do Microsoft Sentinel.

1. No painel de navegação à esquerda, selecione **Hub de Conteúdo**.

1. Reserve um momento para rolar para baixo e ver a longa lista de soluções disponíveis e as opções para filtrar a lista.  Para essa tarefa, você está procurando o **Microsoft Defender para Nuvem**.  Selecione-o na lista.  Na janela lateral que se abre, leia a descrição e selecione **Instalar**.  Quando a instalação estiver concluída, a coluna de status na janela principal será exibida como instalada.

1. No lado direito da página Microsoft Defender para Nuvem está a descrição e as notas associadas à solução do Hub de Conteúdo e o que está incluído como parte dessa solução.  A janela principal possui os componentes da solução.  Nesse caso, há dois conectores de dados e uma regra de dados. O triângulo laranja indica que alguma configuração é necessária. Selecione a caixa ao lado de onde diz **Microsoft Defender para Nuvem (Herdado) baseado em assinatura**.  Uma janela é aberta no lado direito da página.  Clique em **Abrir página do conector**.

1. Anote as instruções de configuração.  Selecione a caixa ao lado do nome da assinatura e selecione **Conectar**.  O status passará para conectado.  O conector agora está habilitado, embora possa levar algum tempo para que o conector seja mostrado na página de conectores de dados.  

1. Agora, exiba informações sobre a regra de análise.  Na parte superior da página (na trilha), selecione **Microsoft Defender para Nuvem**. Desmarque a caixa próxima ao local no qual está escrito Microsoft Defender para Nuvem, pois você já configurou o conector (pode levar algum tempo até que o ícone de aviso desapareça). Selecione a caixa ao lado do local no qual está escrito **Detectar a Atividade de Exclusão do CoreBackUp a partir dos alertas de segurança relacionados**.  Isso abre a página Regras de análise.  Selecione novamente a regra **Detectar Atividade de Exclusão de CoreBackUp de alertas de segurança relacionados**. Uma janela é aberta à direita fornecendo informações sobre a regra e o que ela faz.  Selecione **Criar regra**.  
    1. Embora os detalhes da lógica da regra estejam além do escopo dos princípios básicos, siga cada guia na criação de regra para exibir o tipo de informação que deve ser configurada
    1. Ao acessar a guia Examinar + criar, selecione **Salvar**.

1. Retorne à página do Sentinel selecionando **Microsoft Sentinel | Hub de Conteúdo** na trilha na parte superior da página, acima do local em que está escrito Regras de análise.

1. Chame a atenção para o fato que, ao usar o hub de conteúdo, uma solução pode ser implantada de forma fácil e rápida.

1. Mantenha essa página aberta, pois você vai usá-la na próxima tarefa.

### Demonstração parte 4

Nesta parte da demonstração, você mostrará algumas das opções disponíveis no Sentinel.

1. No painel de navegação esquerdo, selecione **Buscar**.  Na parte superior da página, selecione a guia **Consultas**. Leia a descrição do que é uma consulta de busca. As consultas de busca podem ser adicionadas em um Hub de Conteúdo. Todas as consultas previamente instaladas seriam listadas aqui. Selecione **Acessar o hub de conteúdo**.  O Hub de Conteúdo lista o conteúdo que inclui consultas como parte de uma solução ou como uma consulta autônoma.  Role a tela para baixo para ver as opções disponíveis.

1. No painel de navegação esquerdo, selecione **MITRE ATT&CK**.  O MITRE ATT&CK é uma base de dados de conhecimento publicamente acessível de táticas e técnicas que são comumente usadas por invasores. Com o Microsoft Sentinel você pode visualizar as detecções já ativas em seu workspace e aquelas disponíveis para você configurar, para entender a cobertura de segurança da sua organização, com base nas táticas e técnicas do framework MITRE ATT&CK®.  Selecione qualquer célula da matriz e anote as informações disponíveis no lado direito da tela.  

1. À esquerda no painel de navegação, selecione **Comunidade**. A página da comunidade inclui insights e atualizações de segurança cibernética do Microsoft Research, um link para uma lista de blogs do Microsoft Sentinel, um link para os Fóruns do Microsoft Sentinel, links para as edições mais recentes para o Hub do Microsoft Sentinel e muito mais. Explore isso à vontade.

1. No painel de navegação à esquerda, selecione **Analytics**.  Devem existir duas regras ativas, uma que está disponível por padrão e a regra que você criou na tarefa anterior. Selecione a regra padrão **Advanced Multistage Attack Detection**.  Leia as informações detalhadas.  O Microsoft Sentinel usa o Fusion, um mecanismo de correlação baseado em algoritmos de aprendizado de máquina escaláveis, para detectar automaticamente ataques de vários estágios (também conhecidos como ameaças persistentes avançadas) identificando combinações de comportamentos anômalos e atividades suspeitas que são observadas em vários estágios da cadeia de eliminação. Com base nessas descobertas, o Microsoft Sentinel gera incidentes que, de outra forma, seriam difíceis de detectar.

1. No painel de navegação à esquerda, selecione **Automação**.  Aqui você pode criar regras de automação simples, integrá-las aos guias estratégicos existentes ou criar guias estratégicos.  Selecione **+ Criar** e clique em **Regra de Automação**.  Observe a janela que é aberta no lado direito da tela e as opções de criação de condições e ações são disponibilizadas.  Selecione **Cancelar** na parte inferior da tela.

1. No painel de navegação à esquerda, selecione **Pastas de trabalho**. Leia a descrição da pasta de trabalho do Microsoft Sentinel.  As pastas de trabalho podem ser adicionadas por meio do hub Conteúdo. Todas as pastas de trabalho instaladas anteriormente seriam listadas aqui. Selecione **Acessar o hub de conteúdo**.  O Hub de Conteúdo lista o conteúdo que inclui pastas de trabalho como parte de uma solução ou como uma pasta de trabalho autônoma. Role a tela para baixo para ver as opções disponíveis.

1. Feche a janela selecionando o **X** no canto superior direito.

1. No canto superior esquerdo da janela, logo abaixo da barra azul, selecione **Página Inicial** para retornar à home page do portal do Azure.  

### Revisão

Nesta demonstração, você percorreu as etapas para conectar o Microsoft Sentinel a fontes de dados, configurou uma pasta de trabalho e percorreu várias opções disponíveis no Microsoft Sentinel.
