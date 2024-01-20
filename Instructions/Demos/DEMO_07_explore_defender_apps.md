<!---
---
Demonstração: Título: Microsoft Defender for Cloud Apps ' Módulo: 'Roteiro de aprendizagem: descrever as funcionalidades das soluções de segurança da Microsoft; Module 4: descrever as funcionalidades de proteção contra ameaças do Microsoft 365; Unidade 5: descrever o Microsoft Defender for Cloud Apps'
---
--->

# Demonstração: aplicativos do Microsoft Defender para Nuvem

Essa demonstração é mapeada para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades das soluções de segurança da Microsoft
- Módulo: descrever as funcionalidades de proteção contra ameaças do Microsoft 365
- Unidade: descrever o Microsoft Defender for Cloud Apps

## Cenário de demonstração

Nesta demonstração, você apresentará as funcionalidades do Microsoft Defender para Aplicativos de Nuvem.  Você mostrará ao aprendiz as informações disponíveis no painel do Cloud Discovery, o catálogo de aplicativos na nuvem, as funcionalidades disponíveis para investigar as descobertas com o Log de atividades e os Arquivos e as formas de controlar o impacto na sua organização por meio de Políticas.  Observação: uma organização precisa ter uma licença para usar o Microsoft Defender para Aplicativos de Nuvem, pois este é um serviço por assinatura baseado no usuário.  

### Demonstração – Parte 1: Explorar o Cloud Discovery

1. Na barra de endereços, insira **admin.microsoft.com**. Entre com as credenciais de administrador do locatário do Microsoft 365 fornecido pelo ALH (hoster de laboratório autorizado) para acessar o centro de administração do Microsoft 365.

1. À esquerda no painel de navegação do Centro de administração do Microsoft 365, selecione **Mostrar todos**.

1. Em Centros de administração, selecione **Segurança**.  A página inicial do portal do Microsoft 365 Defender é aberta em uma nova página do navegador.  

1. Se esta for a primeira vez que você visita o portal do Microsoft 365 Defender, você pode obter uma janela pop-up para fazer um tour rápido.

1. No painel de navegação à esquerda, selecione **Aplicativos de nuvem** para expandir a lista e selecione **Cloud Discovery**. Isso levará você para a exibição Painel.  Fale de acordo com as informações disponíveis no painel. Na exibição de painel, você poderá selecionar diferentes guias na parte superior da página.  Percorra cada guia na parte superior da página.

1. Selecione **Aplicativos descobertos**. A janela de aplicativos descobertos fornece uma visão mais detalhada dos aplicativos descobertos, incluindo pontuação de risco, tráfego, número de usuários e muito mais.
    1. Em um dos itens da lista, selecione as **reticências** na coluna de ações da tabela.  Observe as várias opções disponíveis, incluindo a capacidade de marcar um aplicativo como sancionado ou não sancionado.  Selecione as reticências de novo para fechar a caixa de ações.
    1. A seleção de um item de linha específico abre uma página de detalhes para o aplicativo específico.  Selecione um item na lista.  Para o item selecionado, selecione a guia **Uso do aplicativo na nuvem** para ver informações mais detalhadas, incluindo **Uso**, **Usuários, IP**, **Endereços** e **Alertas**. Quando terminar de explorar a página de detalhes, volte à página de aplicativos descobertos selecionando **Cloud Discovery** na navegação estrutural na parte superior da página.  Se você selecionar Cloud Discovery no painel de navegação à esquerda, isso levará você novamente ao exibição de painel.
    1. Na parte superior da página, selecione a guia **Endereços IP**. Aqui, você encontrará dados, incluindo o número de transações, a quantidade de tráfego e os valores de upload, por endereço IP.  Observe que você também pode filtrar por endereço IP específico ou exportar os dados para análise posterior.
    1. Na parte superior da página, selecione **Usuários**.  Esse é o mesmo tipo de informação fornecida quando você seleciona os endereços IP, mas aqui ela é listada por usuários individuais.  Aqui, novamente, você filtra por usuário específico e exporta dados para análise posterior.

1. Um ponto importante a ser enfatizado é que as informações apresentadas na página Cloud Discovery e nas guias relacionadas são baseadas em relatórios de instantâneos dos logs de tráfego carregados manualmente dos firewalls e dos proxies ou em relatórios contínuos que analisam todos os logs encaminhados da sua rede por meio do Cloud App Security.  Para ver o local em que é feita essa configuração, selecione **Ações** no canto superior direito da página.
    1. Selecione a primeira opção, **Criar relatório de instantâneo do Cloud Discovery** e escolha **Avançar**. Aqui você preencheria os detalhes solicitados e carregaria logs de tráfego para gerar e carregar um relatório.  Selecione **Sair** e, se o prompt Tem certeza? for exibido, escolha **Sair** novamente.  Os dados que você vê no locatário do laboratório são provenientes de um Relatório de instantâneo. É possível ver essa informação na parte superior da janela Cloud Discovery.
    1. Para ver a opção de relatórios contínuos, selecione **Ações** no canto superior direito da página e, no menu suspenso, escolha **Configurar upload automático**.  Não há fontes de dados conectadas, mas é aqui que você adicionaria uma fonte de dados. Selecione **Adicionar uma fonte de dados** e escolha a seta para baixo no campo **Selecionar dispositivo** para ver os tipos de dispositivos que você pode conectar como uma fonte de dados.  Selecione **Cancelar** para sair.
    1. No painel de navegação à esquerda, selecione **Cloud Discovery** para voltar à página do Cloud Discovery.

1. Com o Microsoft 365 Defender para Aplicativos de Nuvem, você pode se conectar aos aplicativos diretamente configurando conectores de aplicativos que fornecerão maior visibilidade e controle sobre seus aplicativos de nuvem. No canto superior direito da tela, selecione **Ações** e escolha **Configurações do Cloud Discovery**.  Observe as configurações disponíveis.
    1. No painel de navegação à esquerda da janela Configurações de aplicativos de nuvem, selecione **Conectores de aplicativo** (talvez seja necessário rolar a página para baixo).
    1. A página Conectores de aplicativo é o local em que você verá todos os conectores de aplicativo já configurados e em que poderá adicionar um conector de aplicativo.
    1. Você verá o Microsoft 365 listado. Se um erro de conexão estiver sendo exibido, acesse as reticências verticais no lado direito do item de linha e selecione **Editar configurações**.  Para se reconectar, selecione **Conectar o Office 365** na parte inferior da página. A página agora mostrará que o Office 365 está conectado. Selecione **Concluído**.  O status agora será exibido com um sinal de aviso amarelo, indicando que não há nenhum status recente.  Levará algum tempo para que o status seja atualizado, pois o período de verificação retroativo varia de acordo com o aplicativo, e os locatários do laboratório podem enfrentar atrasos mais longos do que o normal.
    1. Para configurar um novo conector de aplicativo.  Selecione **+Conectar um aplicativo**.  A lista suspensa mostrará uma lista de opções.  O ideal também é indicar que a lista inclui a opção **Sugerir mais aplicativos**.  
    1. Opcionalmente, talvez você queira adicionar o conector do Microsoft Azure. Na lista suspensa, selecione **Microsoft Azure**.  Na janela pop-up do Microsoft Azure, selecione **Conectar Microsoft Azure** e escolha **Concluído**.  Você verá um status conectado (se não o vir, atualize o navegador) e informações sobre a verificação de usuários, dados e atividades.  

1. Na página Configurações de aplicativos de nuvem, vale a pena gastar alguns minutos explorando também algumas das outras configurações do Cloud Discovery.  
    1. Selecione **Aplicativos do Controle de Aplicativos de Acesso Condicional** e observe a descrição: “O Controle de Aplicativos de Acesso Condicional adiciona funcionalidades de monitoramento e controle em tempo real aos seus aplicativos”.
    1. Selecione Proteção de Informações da Microsoft e fale com as configurações disponíveis.
    1. Explore as outras à vontade. Indique o nível de integração e flexibilidade.

1. Volte ao painel do Cloud Discovery selecionando **Cloud Discovery** no painel de navegação mais à esquerda.

1. Mantenha essa página aberta, pois você vai usá-la na próxima parte.

### Demonstração – Parte 2: Explorar o Catálogo de aplicativos na nuvem

Nesta parte da demonstração, você mostrará as funcionalidades do catálogo de aplicativos na nuvem. O Cloud Discovery analisa seus logs de tráfego com base no catálogo de mais de 31 mil aplicativos de nuvem do Microsoft Defender para Aplicativos de Nuvem. Os aplicativos são classificados e pontuados com base em mais de 80 fatores de risco para fornecer visibilidade contínua do uso da nuvem, do shadow IT e o risco que o shadow IT representa para sua organização.  

1. No painel de navegação à esquerda, selecione **catálogo de aplicativos na nuvem**.

1. O catálogo de aplicativos de nuvem permite que você escolha quais aplicativos atendem aos requisitos de segurança da sua organização. Os administradores podem fazer a filtragem básica de aplicativos, conforme mostrado na parte superior da página, o que inclui se o aplicativo é sancionado, não sancionado ou não tem marca, pontuação de risco, fator de risco de conformidade e fator de risco de segurança.  Por exemplo, a filtragem por fator de risco de conformidade permite que você pesquise padrões específicos, certificação e conformidade com os quais o aplicativo pode estar em conformidade. Exemplos incluem HIPAA, ISO 27001, SOC 2 e PCI-DSS. Selecione **Fator de risco de conformidade** para ver as opções disponíveis.  Você pode filtrar ainda mais o conteúdo por pontuação de risco, movendo os controles deslizantes na pontuação de risco na parte superior da página. Se você moveu o controle deslizante, defina-o para que o intervalo seja definido como 0 a 10.

1. Os administradores também podem pesquisar aplicativos por categoria.  Por exemplo, no campo Pesquisar categoria, insira **Rede social** e selecione **Rede social**.  Selecione qualquer item da lista para obter uma exibição detalhada.  Se você posicionar o cursor sobre um tópico de determinada categoria, verá um ícone de informações que poderá selecionar para obter mais informações sobre o tópico.

1. Mantenha essa página aberta, pois você vai usá-la na próxima tarefa.

### Demonstração – Parte 3: Explorar o Log de atividades e os Arquivos

Explore as maneiras de investigar as atividades gravadas com o log de atividades e os arquivos.

1. No painel de navegação à esquerda, selecione **Log de Atividades**. Aqui você consegue ver todas as atividades dos seus aplicativos conectados. Talvez você não veja nenhum dado listado, pois pode levar várias horas para executar verificações retroativas depois que a auditoria estiver habilitada e os locatários do laboratório poderão enfrentar atrasos mais longos do que o normal. Observe as opções de filtro disponíveis e a opção para criar uma política por meio da pesquisa.

1. Para fornecer proteção de dados, o Microsoft Defender para Aplicativos de Nuvem fornece visibilidade de todos os arquivos de seus aplicativos conectados; por exemplo, todos os arquivos armazenados no SharePoint e no Salesforce. No painel de navegação esquerdo, selecione e explore a opção **Arquivos**.
    1. A capacidade de verificar arquivos deve ser habilitada como parte das configurações de Proteção de informações de aplicativos do Microsoft 365 Cloud.  Selecione **Habilitar monitoramento de arquivos** e selecione a caixa ao lado de onde diz **Habilitar monitoramento de arquivos** e, em seguida, selecione **Salvar**.  
    1. Volte aos arquivos selecionando **Arquivos**, listado em Aplicativos de nuvem, no painel de navegação à esquerda. Talvez você não veja nada listado, pois podem ser necessários vários dias para que você veja os arquivos. No entanto, vale a pena indicar que, depois que os arquivos forem listados, você poderá filtrar os dados por aplicativo, proprietário, nível de acesso, tipo de arquivo e política correspondente. Além disso, você vai criar uma política por meio da pesquisa e da exportação dos dados.

1. Mantenha essa página aberta, pois você vai usá-la na próxima tarefa.

### Demonstração – Parte 4: Explorar as políticas

Nesta parte, você mostrará as opções disponíveis para as políticas do Microsoft Defender para Aplicativos de Nuvem.

1. No painel de navegação à esquerda, selecione **Políticas**.
    1. Selecione **Gerenciamento de políticas**.  As políticas listadas fornecem informações sobre o número de alertas gerados pela política, gravidade, etc. A seleção de um item de linha fornece informações mais detalhadas sobre a política. Escolha um item da lista para visualizar informações detalhadas sobre a política.  Fale com algumas das opções e selecione **Cancelar**.
    2. Observe que você também pode criar uma política. Selecione **+ Criar política** para ver os tipos de políticas que você pode criar.  Selecione **Política de atividade** para ver as diferentes opções disponíveis para criar a política.  Selecione **Cancelar** para sair da janela de configuração.
    3. Observe que você também pode ter a opção de exportar as informações da política.

1. No painel de navegação à esquerda, selecione **Modelos de política**. Para criar uma política com base em um dos modelos disponíveis, selecione o **+** no lado direito do item de linha do modelo.  Veja as diferentes opções de configuração da política.  Selecione **Cancelar** para sair da página.

1. No painel de navegação à esquerda, selecione **Página Inicial** para voltar à home page do Microsoft 365 Defender.

1. Mantenha a guia do navegador aberta se você pretende continuar com a próxima demonstração.

### Revisão

Nesta demonstração, você mostrou os recursos do Microsoft Defender for Cloud Apps.  Você mostrou as informações disponíveis no painel do Cloud Discovery, o Catálogo de aplicativos na nuvem, as funcionalidades disponíveis para investigar as descobertas com o Log de atividades e os Arquivos e as formas de controlar o impacto na sua organização por meio de Políticas
