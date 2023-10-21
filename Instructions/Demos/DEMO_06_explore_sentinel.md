<!---
---
Demonstração: Título: "Microsoft Sentinel" Roteiro de aprendizagem/Módulo/Título: "Roteiro de aprendizagem: descrever as funcionalidades das soluções de segurança da Microsoft; Módulo 3: descrever as funcionalidades de segurança do Microsoft Sentinel; Unidade 3: descrever as funcionalidades de detecção e mitigação de ameaças do Microsoft Sentinel"
---
--->

# Demonstração: Microsoft Sentinel

Essa demonstração é mapeada para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades da solução de segurança da Microsoft
- Módulo: descrever as funcionalidades de segurança do Microsoft Sentinel
- Unidade: descrever os recursos de detecção e mitigação de ameaças no Microsoft Sentinel

## Cenário da demonstração

Nesta demonstração, você percorrerá algumas das opções disponíveis com o Microsoft Sentinel, incluindo o uso do hub de conteúdo para encontrar soluções empacotadas que podem ser implantadas.  Mas, primeiro, você percorrerá o processo de configuração de permissões de controle de acesso baseadas em função para usuários que precisariam acessar seus recursos do Microsoft Sentinel.

### Demonstração parte 1

Uma instância do Microsoft Sentinel já deveria ter sido criada como parte da configuração de pré-demonstração. Verifique se ele foi criado.

1. Abra a guia do navegador, **Página Inicial – Microsoft Azure**.  Se você fechou a guia anteriormente, abra uma página do navegador e, na barra de endereços, insira **https://portal.azure.com** . Entre com as credenciais do Azure fornecidas pelo hoster de laboratório autorizado (ALH).  Em seguida, você será direcionado à página inicial dos serviços do Azure.

1. Na caixa de pesquisa, na barra azul no topo da página, perto de onde está escrito Microsoft Azure, digite **Microsoft Sentinel** e selecione **Microsoft Sentinel** nos resultados da pesquisa.  

1. Na página do Microsoft Sentinel, você deverá ver sua instância do Sentinel listada e selecioná-la.  Se ela não estiver listada, crie-a agora.
    1. Na página do Microsoft Sentinel, selecione **Criar Microsoft Sentinel**.

    1. Na página Adicionar o Microsoft Sentinel a um workspace, selecione **Criar um workspace**. Na guia Básico da página Criar espaço de trabalho do Log Analytics, insira:
        1. Assinatura: mantenha o padrão.
        1. Grupo de recursos: selecione **Criar novo**, insira o nome **SC900-Sentinel-RG** e clique em **OK**.
        1. Nome: **SC900-LogAnalytics-workspace**.
        1. Região: **Leste dos EUA** (uma região padrão diferente pode ser selecionada com base em sua localização)
        1. Selecione **Revisar + Criar** (nenhuma marca será configurada).
        1. Verifique as informações inseridas e selecione **Criar**.
        1. Pode levar um ou dois minutos até que o novo workspace seja listado; caso ele ainda não seja exibido, selecione **Atualizar** e depois **Adicionar**.
        1. Depois que o novo workspace for adicionado, a página Microsoft Sentinel | Novidades e guias será exibida, indicando que a avaliação gratuita do Microsoft Sentinel está ativada.  Selecione **OK**.

1. Mantenha esta página aberta, pois você a usará em uma tarefa subsequente.

### Demonstração parte 2

Assim como acontece com todos os recursos do Azure, você deseja garantir que os usuários tenham as permissões adequadas para acessar seus recursos do Microsoft Sentinel. Aqui você mostrará as etapas para atribuir uma função e as funções disponíveis para uso com o Microsoft Sentinel.  

1. Na caixa de pesquisa, na barra azul no topo da página, perto de onde está escrito Microsoft Azure, digite **grupos de recursos** e selecione **Grupos de recursos** nos resultados da pesquisa. Atribuir a função a nível do grupo de recursos vai garantir que ela seja aplicada a todos os recursos implantados para comportar o Microsoft Sentinel.

1. Na página de Grupos de recursos, selecione o grupo de recursos que você criou com o Microsoft Sentinel, **SC900-Sentinel-RG**.

1. Na página do SC900-Sentinel-RG, selecione **Controle de acesso (IAM)** no painel de navegação à esquerda.

1. Na página Controle de acesso, selecione **Exibir meu acesso**.  Se você estiver usando a assinatura do Cloud Slice do Skillable, a atribuição de função será definida como Proprietário do LOD, que é uma atribuição de função personalizada configurada para esta assinatura do Cloud Slice e concederá as permissões necessárias. Para fins de demonstração, no entanto, é bom mostrar as funções específicas do Sentinel.  Selecione o **X** no canto superior direito da janela de tarefas para fechá-la.

    1. Na página Controle de acesso, selecione **+Adicionar** e depois **Adicionar atribuição de função**.

    1. A janela Adicionar atribuição de função vai ser aberta.  Na caixa de pesquisa, digite **Microsoft Sentinel** para visualizar as funções associadas ao Microsoft Sentinel.
    1. Em qualquer uma das funções listadas, selecione a **Exibir** para ver os detalhes dessa função.  Como prática recomendada, você deve atribuir o privilégio mínimo exigido para a função.  

    1. Feche a janela selecionando o **X** no canto superior direito.

1. Na página de controle de acesso, selecione **X** no canto superior direito da janela para fechá-la.

### Demonstração parte 3

Nesta parte da demonstração, você mostrará as etapas usadas para se conectar a uma fonte de dados. Vários conectores de dados são implantados como parte de uma solução Microsoft Sentinel, junto com regras de análise, pastas de trabalho e guias estratégicos relacionados. O hub de Conteúdo do Microsoft Sentinel é o local centralizado para descobrir e gerenciar conteúdo integrado (interno). Nesta etapa, você usará o hub de conteúdo para implantar a solução Microsoft Defender para Nuvem do Microsoft Sentinel.  Essa solução permite ingerir alertas de segurança relatados no Microsoft Defender para Nuvem.

1. Abra a guia do navegador do Microsoft Sentinel.

1. No painel de navegação à esquerda, selecione **Hub de conteúdo**.

1. Reserve um momento para rolar para baixo para ver a longa lista de soluções disponíveis e as opções para filtrar a lista.  Para essa demonstração, estamos procurando o **Microsoft Defender para Nuvem**.  Selecione-o na lista.  Na janela lateral que é aberta, leia a descrição e selecione **Instalar**.  Essa solução inclui um conector de dados e uma regra de análise. A instalação pode levar um minuto.  Selecione **Gerenciar**.

1. Selecione a caixa ao lado de onde diz Microsoft Defender para Nuvem.  Uma janela é aberta do lado direito da página.  Clique em **Abrir página do conector**.

1. Observe as instruções de configuração.  Selecione a caixa ao lado do nome da assinatura e selecione **Conectar**.  O status passará para conectado.  O conector agora está habilitado, embora possa levar algum tempo para que o conector apareça na página de conectores de dados.  

1. Agora, exiba informações sobre a regra de análise.  Na parte superior da página (na trilha), selecione **Microsoft Defender para Nuvem**.  Selecione a caixa ao lado de onde consta: "Detectar atividade de exclusão CoreBackUp de alertas de segurança relacionados". Na janela que é aberta, você verá informações sobre a regra e o que ela faz.  Você pode optar por percorrer as etapas para configurar a regra.  **OBSERVAÇÃO**: os detalhes da lógica de regra estão além do escopo dos conceitos básicos, mas você pode mostrar o tipo de informação que pode ser configurado como parte da regra.  
    1. Selecione **Configuração**.
    1. Selecione a regra **Detectar Atividade de Exclusão de CoreBackUp de alertas de segurança relacionados**.
    1. Na janela que é aberta no lado direito da página, selecione **Criar regra**.
    1. Percorra cada uma das páginas de configuração, brevemente e por alto e, em seguida, selecione **Examinar e criar**; em seguida, selecione **Salvar**.

1. Retorne à página do Sentinel selecionando **Microsoft Sentinel | Hub de conteúdo** na trilha na parte superior da página, acima de onde se lê Regras de análise.

1. Chame isso usando o hub de conteúdo, uma solução pode ser implantada com facilidade e rapidez.

1. Mantenha essa página aberta, pois você vai usá-la na próxima tarefa.

### Demonstração parte 4

Nesta parte da demonstração, você mostrará algumas das opções disponíveis no Sentinel.

1. No painel de navegação esquerdo, selecione **Buscar**.  Na parte superior da página, selecione a guia **Consultas**. Leia a descrição do que é uma consulta de busca. Consultas de busca podem ser adicionadas por meio do Hub de conteúdo. Todas as consultas instaladas anteriormente seriam listadas aqui. Selecione **Ir para o hub de conteúdo**.  O hub de conteúdo lista o conteúdo que inclui consultas como parte de uma solução ou como uma consulta autônoma.  Role para baixo para ver as opções disponíveis.

1. No painel de navegação esquerdo, selecione **MITRE ATT&CK**.  O MITRE ATT&CK é uma base de dados de conhecimento publicamente acessível de táticas e técnicas que são comumente usadas por invasores. Com o Microsoft Sentinel você pode visualizar as detecções já ativas em seu workspace e aquelas disponíveis para você configurar, para entender a cobertura de segurança da sua organização, com base nas táticas e técnicas do framework MITRE ATT&CK®.  Selecione qualquer célula da matriz e anote as informações disponíveis no lado direito da tela.  

1. À esquerda no painel de navegação, selecione **Comunidade**. Os analistas de segurança da Microsoft criam e adicionam constantemente novas pastas de trabalho, guias estratégicos, consultas de busca e muito mais, publicando-os na comunidade para uso em seu ambiente. Você pode baixar o conteúdo de exemplo no repositório do GitHub privado da comunidade para criar pastas de trabalho personalizadas, consultas de busca, notebooks e guias estratégicos para o Microsoft Sentinel.  Selecione **Integrar conteúdo da comunidade**.  Uma nova guia para o repositório GitHub, em que você pode baixar conteúdo para habilitar seus cenários, é aberta.  Retorne à guia do Azure no navegador.

1. À esquerda no painel de navegação, selecione **Análise**.  Deve haver duas regras ativas, uma disponível por padrão e a regra que você criou na tarefa anterior. Selecione a regra padrão **Detecção avançada de ataque multiestágio**.  Leia as informações detalhadas.  O Microsoft Sentinel usa o Fusion, um mecanismo de correlação baseado em algoritmos de aprendizado de máquina escaláveis, para detectar automaticamente ataques de vários estágios (também conhecidos como ameaças persistentes avançadas) identificando combinações de comportamentos anômalos e atividades suspeitas que são observadas em vários estágios da cadeia de eliminação. Com base nessas descobertas, o Microsoft Sentinel gera incidentes que, de outra forma, seriam difíceis de detectar.

1. À esquerda no painel de navegação, selecione **Automação**.  Aqui você pode criar regras de automação simples, integrá-las aos guias estratégicos existentes ou criar guias estratégicos.  Selecione **+ Criar** e clique em **Regra de Automação**.  Observe a janela que é aberta no lado direito da tela e as opções de criação de condições e ações são disponibilizadas.  Selecione **Cancelar** na parte inferior da tela.

1. À esquerda no painel de navegação, selecione **Pastas de trabalho**. Leia a descrição do que é uma pasta de trabalho do Microsoft Sentinel.  As pastas de trabalho podem ser adicionadas por meio do Hub de conteúdo. Todas as pastas de trabalho instaladas anteriormente seriam listadas aqui. Selecione **Ir para o hub de conteúdo**.  O hub de conteúdo lista o conteúdo que inclui pastas de trabalho como parte de uma solução ou como uma pasta de trabalho autônoma. Role para baixo para ver as opções disponíveis.

1. Feche a janela selecionando o **X** no canto superior direito.

1. No canto superior esquerdo da janela, logo abaixo da barra azul, selecione **Página Inicial** para retornar à home page do portal do Azure.  

### Revisão

Nesta demonstração, você percorreu as etapas para conectar o Microsoft Sentinel a fontes de dados, configurou uma pasta de trabalho e percorreu várias opções disponíveis no Microsoft Sentinel.
