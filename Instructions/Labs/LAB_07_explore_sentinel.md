<!---
---
Laboratório: Título: 'Explorar o Microsoft Sentinel' Roteiro de Aprendizagem/Módulo/Título: 'Roteiro de Aprendizagem: descrever as capacidades das soluções de segurança da Microsoft; Módulo 3: descrever as capacidades de segurança do Microsoft Sentinel; Unidade 3: descrever as capacidades de detecção e mitigação de ameaças no Microsoft Sentinel'
---
--->

# Laboratório: Explorar o Microsoft Sentinel

Esse laboratório é mapeado para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades da solução de segurança da Microsoft
- Módulo: descrever as funcionalidades de segurança do Microsoft Sentinel
- Unidade: descrever as capacidades de detecção e mitigação de ameaças no Microsoft Sentinel

## Cenário do laboratório

, você conhecerá o processo de criação de uma instância do Microsoft Sentinel.  Você também vai configurar as permissões para garantir o acesso aos recursos que serão implantados para dar suporte ao Microsoft Sentinel.  Depois que essa configuração básica for concluída, você vai seguir as etapas para conectar o Microsoft Sentinel às suas fontes de dados, configurar uma pasta de trabalho e mostrar um breve passo a passo de algumas das principais funcionalidades disponíveis no Microsoft Sentinel.

**Tempo estimado**: 45 a 60 minutos

### Tarefa 1:

Criar uma instância do Microsoft Sentinel

1. Que será a página inicial dos serviços do Azure.  Se você tiver fechado o navegador previamente, abra o Microsoft Edge. Na barra de endereços, insira **portal.azure.com** e entre com suas credenciais de administrador.

1. Na caixa de pesquisa azul na parte superior da página, insira **Microsoft Sentinel** e selecione **Microsoft Sentinel** nos resultados da pesquisa.

1. Na página do Microsoft Sentinel, selecione **Criar Microsoft Sentinel**.

1. Na página Adicionar o Microsoft Sentinel a um workspace, selecione **Criar um workspace**.

1. Na guia Básico da página Criar espaço de trabalho do Log Analytics, insira:
    1. Assinatura: mantenha o padrão. Esta é a assinatura do Azure fornecida pelo ALH (Hoster do Laboratório Autorizado).
    1. Grupo de recursos: selecione **SC900-Sentinel-RG**. Se esse grupo de recursos não estiver listado, crie-o selecionando **Criar**, insira **SC900-Sentinel-RG** e selecione **OK**.
    1. Nome: **SC900-LogAnalytics-workspace**.
    1. Região: **Leste dos EUA** (uma região padrão diferente pode ser selecionada com base em sua localização)
    1. Selecione **Revisar + Criar** (nenhuma marca será configurada).
    1. Verifique as informações inseridas e selecione **Criar**.
    1. Pode levar um ou dois minutos até que o novo workspace seja listado; caso ele ainda não seja exibido, selecione **Atualizar** e depois **Adicionar**.

1. Depois que o novo workspace for adicionado, a página Microsoft Sentinel | Novidades e guias será exibida, indicando que a avaliação gratuita do Microsoft Sentinel está ativada.  Selecione **OK**.  Veja as três etapas listadas na página de Introdução.

1. Mantenha essa página aberta, pois você vai usá-la na próxima tarefa.

### Tarefa 2:

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

1. No canto superior esquerdo da janela, logo abaixo da barra azul indicando Microsoft Azure, selecione **Página Inicial** para voltar à home page dos serviços do Azure.

1. Mantenha a guia do Azure aberta no seu navegador.

### Tarefa 3

O objetivo desta tarefa é orientar você pelas etapas envolvidas na conexão com uma fonte de dados. Muitos conectores de dados são implantados como parte de uma solução do Microsoft Sentinel, juntamente com conteúdos relacionados, como regras de análise, pastas de trabalho e guias estratégicos. O Hub de Conteúdo do Microsoft Sentinel é o local centralizado para descobrir e gerenciar o conteúdo pronto para uso (interno). Nesta etapa, você usará o Hub de Conteúdo para implantar a solução Microsoft Defender para Nuvem para o Microsoft Sentinel.  Essa solução permite a você ingerir os alertas de segurança relatados no Microsoft Defender para Nuvem.

1. Na página inicial dos serviços do Azure, selecione Microsoft Sentinel e, em seguida, selecione a instância que você criou, **SC900-LogAnalytics-workspace**.

1. No painel de navegação à esquerda, selecione **Hub de Conteúdo**.

1. Reserve um momento para rolar para baixo e ver a longa lista de soluções disponíveis e as opções para filtrar a lista.  Para essa tarefa, você está procurando o **Microsoft Defender para Nuvem**.  Selecione-o na lista.  Na janela lateral que se abre, leia a descrição e selecione **Instalar**.  Essa solução inclui um conector de dados e uma regra de análise. A instalação pode demorar um pouco.  Selecione **Gerenciar**.

1. Selecione a caixa ao lado do local em que está escrito Microsoft Defender para Nuvem.  Uma janela é aberta no lado direito da página.  Clique em **Abrir página do conector**.

1. Anote as instruções de configuração.  Selecione a caixa ao lado do nome da assinatura e selecione **Conectar**.  Pode aparecer uma janela pop-up indicando que somente as assinaturas nas quais você tem permissões do Leitor de Segurança começarão a transmitir alertas do Microsoft Defender para Nuvem.  Selecione **OK**.  O status passará para conectado.  O conector agora está habilitado, embora possa levar algum tempo para que o conector seja mostrado na página de conectores de dados.  

1. Agora, exiba informações sobre a regra de análise.  Na parte superior da página (na trilha), selecione **Microsoft Defender para Nuvem**. Desmarque a caixa próxima ao local no qual está escrito Microsoft Defender para Nuvem, pois você já configurou o conector (pode levar algum tempo até que o ícone de aviso desapareça). Selecione a caixa ao lado do local no qual está escrito **Detectar a Atividade de Exclusão do CoreBackUp a partir dos alertas de segurança relacionados**. Na janela que se abre, você verá informações sobre a regra e o que ela faz.  
    1. Embora os detalhes da lógica da regra estejam além do escopo dos princípios básicos, siga as etapas de configuração da regra para exibir o tipo de informação que deve ser configurada como parte da regra. Selecione **Configuração**.
    1. Selecione a regra **Detectar a Atividade de Exclusão do CoreBackUp a partir dos alertas de segurança relacionados**.
    1. Na janela que se abre no lado direito da página, selecione **Criar regra**.
    1. Percorra cada uma das páginas de configuração, depois selecione **Revisar e criar** e, em seguida, selecione **Salvar**.

1. Retorne à página do Sentinel selecionando **Microsoft Sentinel | Hub de Conteúdo** no menu suspenso na parte superior da página, acima do local em que está escrito Regras de análise.

1. Mantenha essa página aberta, pois você vai usá-la na próxima tarefa.


### Tarefa 4

Nesta tarefa, você percorrerá algumas das opções disponíveis no Sentinel.

1. No painel de navegação esquerdo, selecione **Buscar**.  Na parte superior da página, selecione a guia **Consultas**. Leia a descrição do que será uma consulta de busca. As consultas de busca podem ser adicionadas em um Hub de Conteúdo. Todas as consultas previamente instaladas seriam listadas aqui. Selecione **Acessar o hub de conteúdo**.  O Hub de Conteúdo lista o conteúdo que inclui consultas como parte de uma solução ou como uma consulta autônoma.  Role a tela para baixo para ver as opções disponíveis. Feche o hub de conteúdo selecionando o **X** no canto superior direito da janela.

1. No painel de navegação esquerdo, selecione **MITRE ATT&CK**.  O MITRE ATT&CK é uma base de dados de conhecimento publicamente acessível de táticas e técnicas que são comumente usadas por invasores. Com o Microsoft Sentinel você pode visualizar as detecções já ativas em seu workspace e aquelas disponíveis para você configurar, para entender a cobertura de segurança da sua organização, com base nas táticas e técnicas do framework MITRE ATT&CK®.  Selecione qualquer célula da matriz e anote as informações disponíveis no lado direito da tela. **OBSERVAÇÃO**: talvez você precise selecionar o " **<<** " no lado direito da janela para ver o painel de informações.

1. À esquerda no painel de navegação, selecione **Comunidade**. Os analistas de segurança da Microsoft criam e adicionam constantemente novas pastas de trabalho, guias estratégicos, consultas de busca e muito mais, publicando-os na comunidade para uso em seu ambiente. No lado direito da tela, selecione **Integrar conteúdo da comunidade**.  Uma nova guia para o repositório GitHub, em que você pode baixar conteúdo para habilitar seus cenários, é aberta. Role a página para baixo até a seção README.md e leia a descrição. Retorne à guia do Azure no navegador.

1. À esquerda no painel de navegação, selecione **Análise**.  Devem existir duas regras ativas, uma que está disponível por padrão e a regra que você criou na tarefa anterior. Selecione a regra padrão **Advanced Multistage Attack Detection**.  Leia as informações detalhadas.  O Microsoft Sentinel usa o Fusion, um mecanismo de correlação baseado em algoritmos de aprendizado de máquina escaláveis, para detectar automaticamente ataques de vários estágios (também conhecidos como ameaças persistentes avançadas) identificando combinações de comportamentos anômalos e atividades suspeitas que são observadas em vários estágios da cadeia de eliminação. Com base nessas descobertas, o Microsoft Sentinel gera incidentes que, de outra forma, seriam difíceis de detectar. **OBSERVAÇÃO**: talvez você precise selecionar o " **<<** " no lado direito da janela para ver o painel de informações.

1. À esquerda no painel de navegação, selecione **Automação**.  Aqui você pode criar regras de automação simples, integrá-las aos guias estratégicos existentes ou criar guias estratégicos.  Selecione **+ Criar** e clique em **Regra de Automação**.  Observe a janela que é aberta no lado direito da tela e as opções de criação de condições e ações são disponibilizadas.  Selecione **Cancelar** na parte inferior da tela.

1. À esquerda no painel de navegação, selecione **Pastas de trabalho**. Leia a descrição do que é uma pasta de trabalho do Microsoft Sentinel.  As pastas de trabalho podem ser adicionadas em um Hub de Conteúdo. Todas as pastas de trabalho previamente instaladas serão listadas aqui. Selecione **Acessar o hub de conteúdo**.  O Hub de Conteúdo lista o conteúdo que inclui pastas de trabalho como parte de uma solução ou como uma pasta de trabalho autônoma. Role a tela para baixo para ver as opções disponíveis.

1. Feche a janela selecionando o **X** no canto superior direito.

1. No canto superior esquerdo da janela, logo abaixo da barra azul, selecione **Página Inicial** para retornar à home page do portal do Azure.

1. Desconecte-se e feche todas as guias abertas do navegador.

### Revisão

Neste lV, você percorreu as etapas para conectar o Microsoft Sentinel a fontes de dados, configurou uma pasta de trabalho e percorreu várias opções disponíveis no Microsoft Sentinel.
