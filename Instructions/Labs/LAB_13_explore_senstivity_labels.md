---
lab:
  title: Explorar os rótulos de confidencialidade no Microsoft Purview
  module: Describe the data security solutions of Microsoft Purview
---

# Laboratório: Explorar rótulos de confidencialidade no Microsoft Purview

Esse laboratório é mapeado para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: Descrever as funcionalidades do Microsoft Priva e do Microsoft Purview
- Módulo: Descrever as soluções de segurança de dados do Microsoft Purview
- Unidade: descrever os rótulos e políticas de confidencialidade na Proteção de informações do Microsoft Purview

## Cenário do laboratório

Neste laboratório, você vai explorar as funcionalidades dos rótulos de confidencialidade.  Você percorrerá as configurações dos rótulos de confidencialidade que foram criados e a política correspondente para publicá-lo. Depois, você verá como aplicar o rótulo e o impacto dele da perspectiva do usuário.

**Tempo estimado**: 45 minutos

### Tarefa 1

Nesta tarefa, você entenderá o que os rótulos de confidencialidade podem fazer ao passar pelo processo de criar um novo rótulo e uma política para publicá-lo.

1. Abra a guia do navegador na home page do Microsoft Purview.  Se você a fechou anteriormente, abra uma nova guia do navegador e insira **`https://admin.microsoft.com`** . Entre com as credenciais de administrador para o locatário do Microsoft 365 fornecido pelo hoster de laboratório autorizado (ALH).

1. No painel de navegação à esquerda do centro de administração do Microsoft 365, selecione **Mostrar tudo** e, em seguida, **Microsoft Purview**.  Uma nova página inicial do portal do Microsoft Purview será aberta em uma nova página do navegador.

1. No painel de navegação à esquerda, selecione **Soluções** e, depois, **Proteção de informações**.  Você está na página de visão geral. Role para baixo para ver as informações disponíveis.

1. No painel de navegação à esquerda, selecione **Rótulos de confidencialidade**.
1. Você verá um banner amarelo que indica que a sua organização não habilitou o processamento de conteúdo em arquivos online do Office com rótulos de confidencialidade criptografados e que se encontram armazenados no OneDrive e no SharePoint.  Selecione **Habilitar agora**.

1. Alguns rótulos foram pré-configurados em seu locatário de laboratório do Microsoft 365, para sua conveniência. Expanda o rótulo chamado **Altamente Confidencial** e selecione **Todos os Funcionários**.  Uma janela será aberta com informações sobre este rótulo.  Observe as configurações dessa etiqueta.  Clique em **Editar rótulo**. Se não vir essa opção, clique nos três pontos.
    1. A configuração começará com o fornecimento de detalhes básicos para o rótulo.  Não altere nada.  Selecione **Avançar** na parte inferior da página.
    1. Observe o escopo desta etiqueta. Não altere nada.  Selecione **Avançar** na parte inferior da página.
    1. Esta próxima tela é onde você pode escolher as configurações de proteção para os itens rotulados. Esse rótulo controla quem pode acessar e exibir itens rotulados e também aplica a marcação de conteúdo.  Selecione **Avançar** para exibir os detalhes.
        1. Controle de acesso: Examine as configurações, mas não altere nada.  Selecione **Avançar**.
        1. Marcação de conteúdo: Observe que o rótulo aplica um rodapé.  Depois, selecione **Avançar**.
        1. Rotulagem automática para arquivos e emails: Leia a descrição de rotulamento automático no topo da página e a caixa de informações abaixo delas.  Observe também que esse rótulo está definido para rotulagem automática quando números de cartão de crédito são detectados. Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Defina as configurações de proteção para grupos e sites: Examine as opções de configurações de proteção e aplique automaticamente as configurações.  Nada foi configurado nesta janela.  Não altere nada. Selecione **Avançar** na parte inferior da página.
    1. Examine suas configurações e conclua: Examine suas configurações.  Como nada foi alterado, selecione **Cancelar**.

1. No painel de navegação à esquerda, expanda **Políticas** e selecione **Políticas de publicação de rótulos**.  É por meio das políticas de rótulo que os rótulos de confidencialidade podem ser publicados.  O locatário do Microsoft 365 foi configurado com algumas políticas de rótulo, para sua conveniência. Selecione **Política Altamente Confidencial**.  Uma janela será aberta com informações sobre a política. Selecione **Editar política** na parte superior da janela.  Aqui você vai percorrer as configurações sem alterar nada.
    1. Escolha rótulos de confidencialidade para publicar:  Observe os rótulos listados.  Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Atribua unidades de administração: As unidades de administração são definidas como o diretório completo; não altere nenhuma configuração. Selecione **Avançar**.  
    1. Publique em usuários e grupos:  Observe que esse rótulo está disponível para todos os usuários.  Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Configurações de política: Observe as opções disponíveis. Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Configurações padrão para documentos: Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Configurações padrão para emails: Examine as opções e observe que os emails podem herdar um rótulo de um anexo com prioridade mais alta, se configurado para isso. Selecione **Avançar**.
    1. Configurações padrão para reuniões e eventos de calendário: Examine as opções e observe a opção de aplicar herança entre a reunião de equipes e os artefatos. Não altere nenhuma configuração.  Selecione **Avançar**.
    1. Configurações padrão para conteúdo do Fabric e do Power BI: Não altere nenhuma configuração.  Selecione **Avançar**.
    1. Nomeie sua política: Como você está editando a política, o campo de nome está esmaecido.  Selecione **Avançar**.
    1. Examine e conclua: Como nada foi alterado, selecione **Cancelar**.

1. No painel de navegação à esquerda, dentro de Proteção de informações, escolha **Políticas de rotulagem automática**. Examine a descrição. Observe que você cria políticas de rotulagem automática para aplicar automaticamente rótulos de confidencialidade a mensagens de email ou arquivos do OneDrive e do SharePoint que contêm informações confidenciais. Nenhuma política de rótulo automático foi pré-configurada em nosso locatário. Para criar uma nova política de rótulo automático, selecione **Criar política de rótulo automático**.  Aqui, você percorrerá as etapas envolvidas na criação de uma política.
    1. Você começa escolhendo as informações às quais deseja que esse rótulo seja aplicado.  Observe as opções disponíveis.  Selecione **Medicina e integridade** e escolha um dos regulamentos disponíveis que servirá como modelo.  Selecione **Avançar**.
    1. Você pode nomear sua política de rótulo automático ou usar o nome padrão.  Selecione **Avançar**.
    1. Em seguida, você irá escolher um rótulo para aplicar automaticamente.  Selecione **+ Escolher um rótulo**.  Escolha um rótulo na lista e, em seguida, selecione **Adicionar**.
    1. Você pode atribuir as unidades de administração às quais essa política se aplica.  Deixe o padrão definido como diretório completo e selecione **Avançar**.
    1. Escolha os locais em que você deseja aplicar o rótulo.  Examine as informações fornecidas e os locais disponíveis que você pode selecionar. Para este exercício, selecione a caixa ao lado do **Email do Exchange** e selecione **Avançar**.
    1. Você pode configurar regras comuns ou avançadas que definem a qual conteúdo o rótulo é aplicado.  Deixe o padrão definido como Regras comuns e selecione **Avançar**.
    1. Você pode definir regras para conteúdo em todos os locais.  O rótulo será aplicado ao conteúdo que corresponde às regras definidas nesta página.  Para o modelo selecionado, você deverá ver um item de linha. Expanda-o para exibir as condições que se aplicam.  Mantenha todas as configurações padrão e selecione **Avançar**.
    1. Configurações adicionais podem ser definidas para o email. Deixe os padrões e selecione **Avançar**.
    1. Você pode decidir testar a política agora ou depois.  Selecione **Deixar a política desativada** e selecione **Avançar**.
    1. Examine as configurações. Para este exercício, você pode cancelar sem a criação da política. Selecione **Cancelar**.

1. No painel de navegação esquerdo, selecione **Página Inicial** para retornar ao portal do Microsoft Purview.

1. Mantenha essa página aberta, pois você vai usá-la na próxima tarefa.

### Tarefa 2:

Nesta tarefa, você passará pelo processo de aplicação de um rótulo de confidencialidade a um documento do Microsoft Word e, em seguida, exibirá a marca do conteúdo (rodapé) gerada pelo rótulo. OBSERVAÇÃO: ao usar o Microsoft Word online, você pode sofrer um atraso antes que a opção para selecionar rótulos de confidencialidade apareça na faixa de opções superior.  É recomendável que você conclua todos os laboratórios restantes e retorne a esta tarefa.

1. Você ainda deve estar na home page do portal do Microsoft Purview. 
1. No portal do Microsoft Purview, selecione o **ícone do inicializador de aplicativos** ao lado de onde está escrito Microsoft Purview. Selecione o **ícone do Word**.  

1. Em Criar, selecione **Documento em branco** e insira algum texto na página.  Na parte superior da página, ao lado do ícone do Word, selecione onde está escrito **Documento** e renomeie o arquivo para **Test-label** e então, pressione **Enter** em seu teclado.

1. No canto direito da barra de menu superior (também conhecida como faixa de opções), você encontrará uma seta para baixo. Selecione-a e depois escolha **Faixa de Opções Clássica**.  Isso vai ajudar a identificar o ícone de confidencialidade mais facilmente. Selecione **Confidencialidade**, que está ao lado do ícone do microfone. No menu suspenso, selecione **Altamente Confidencial** e, em seguida, selecione **Todos os Funcionários**.  

1. Na barra de menu superior, selecione **Exibição** e depois **Modo de Exibição de Leitura**.

1. Observe como o documento inclui o rodapé "Classificado como Altamente Confidencial".  

1. Feche as guias do Microsoft Word que estão abertas no navegador para sair do Word, mas mantenha a guia do navegador para a página inicial do Microsoft Purview aberta.

### Revisão

Neste laboratório, você explorou os recursos de rótulos de confidencialidade.  Você explorou as configurações de um rótulo de confidencialidade existente e a política correspondente para publicá-lo.  Você aplicou o rótulo e, como o rótulo incluía marcações de conteúdo, você pôde ver essa marcação no documento ao qual aplicou o rótulo.
