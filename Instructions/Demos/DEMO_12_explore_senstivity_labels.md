<!---
---
Demonstração: Título: 'Rótulos de confidencialidade no Microsoft Purview' Roteiro de aprendizagem/Módulo/Unidade: 'Roteiro de aprendizagem: descrever as funcionalidades do Microsoft Priva e Microsoft Purview; Módulo 2: descrever as soluções de segurança de dados do Microsoft Purview; Unidade 4: descrever os rótulos e políticas de confidencialidade na Proteção de informações do Microsoft Purview'
---
--->

# Demonstração: Rótulos de confidencialidade no Microsoft Purview

Essa demonstração é mapeada para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades do Microsoft Priva e do Microsoft Purview
- Módulo: Descrever as soluções de segurança de dados do Microsoft Purview
- Unidade: descrever os rótulos e políticas de confidencialidade na Proteção de informações do Microsoft Purview

## Cenário de demonstração

Nesta demonstração, você mostrará as funcionalidades dos rótulos de confidencialidade.  Você percorrerá as configurações dos rótulos de confidencialidade que foram criados e a política correspondente para publicá-lo.   Depois, você verá como aplicar o rótulo e o impacto dele da perspectiva do usuário.

**OBSERVAÇÃO**: Na primeira vez que você usar o Word online com seu locatário do Microsoft 365, poderá levar 15 minutos até que a opção Confidencialidade apareça na faixa de opções. É recomendável que os apresentadores abram o Word online (conforme mostrado na parte 3 da demonstração) antes de iniciar a demonstração completa para garantir tempo suficiente para que a opção apareça.

### Demonstração parte 1 (opcional)

Se esta for a primeira instância em que você demonstra uma solução do Microsoft Purview, é recomendável que você passe alguns minutos apresentando o portal do Microsoft Purview antes de entrar em rótulos de confidencialidade.

1. Abra um Microsoft Edge e, na barra de endereços, insira **https://purview.microsoft.com**, faça logon com as credenciais fornecidas pelo host de laboratório autorizado e selecione **Introdução**.  

1. Antes de entrar em rótulos de confidencialidade, reserve alguns minutos para explorar o portal do Microsoft Purview.

1. Selecione o bloco **Exibir todas as soluções** para ver o agrupamento das soluções do Microsoft Purview.

1. No painel de navegação esquerdo, você verá as opções de Soluções, Saiba mais, Configurações e as soluções selecionadas recentemente.
    1. **Soluções.** Isso abre um novo painel com todas as soluções e portais relacionados.
    1. **Saiba mais** para exibir links para documentos, vídeos e blogs.
    1. **Configurações**. Explore essas opções como quiser. A partir daqui, você pode configurar funções e escopos, conector de dados e todas as configurações da solução.

1. Retorne à home page clicando em **Página Inicial** no painel de navegação à esquerda.

### Demonstração parte 2

Nesta demonstração, você apresentará as configurações de um rótulo de confidencialidade existente e a política correspondente para publicá-lo.

1. Você deve estar na página de aterrissagem do portal do Microsoft Purview.  Caso contrário, abra uma guia do navegador no Microsoft Edge, entre **`https://puriview.microsoft.com`** e faça logon com as credenciais fornecidas pelo host de laboratório autorizado.

1. Na página de aterrissagem do novo portal do Microsoft Purview, selecione o bloco **Exibir todas as soluções** e, em seguida, selecione o bloco **Proteção de Informações**. Como alternativa, selecione **Soluções** no painel de navegação esquerdo e, em seguida, selecione **Proteção de informações**.

1. Você chegará à página de visão geral. No painel de navegação à esquerda, selecione **Rótulos de confidencialidade**. Se você visualizar uma faixa amarela indicando que sua organização não habilitou a capacidade de processar conteúdo em arquivos do Office online que possuem rótulos de confidencialidade criptografados aplicados e que estão armazenados no OneDrive e no SharePoint.  Selecione **Habilitar agora**

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
    1. Configurações padrão para reuniões e eventos de calendário: Examine as opções e observe a opção de aplicar herança entre a reunião da equipe e os artefatos. Não altere nenhuma configuração.  Selecione **Avançar**.
    1. Configurações padrão para conteúdo do Fabric e do Power BI: Não altere nenhuma configuração.  Selecione **Avançar**.
    1. Nomeie sua política: Como você está editando a política, o campo de nome está esmaecido.  Selecione **Avançar**.
    1. Examine e conclua: Como nada foi alterado, selecione **Cancelar**.

1. No painel de navegação à esquerda, dentro de Proteção de informações, escolha a opção de Rotulagem automática. Examine a descrição. Observe que você cria políticas de rotulagem automática para aplicar automaticamente os rótulos de confidencialidade às mensagens de email ou aos arquivos do OneDrive e do SharePoint que contêm informações confidenciais. Se houver políticas de rotulagem automática configuradas, selecione uma e revise as informações da política no painel de detalhes.  Se nenhuma política estiver listada, você poderá optar por percorrer as etapas para criar uma, se o tempo permitir.

1. No painel de navegação esquerdo, selecione Página Inicial para retornar ao portal do Microsoft Purview.

1. Mantenha essa guia do navegador aberta.

### Demonstração parte 3

Nesta etapa, você passará pelo processo de aplicação de um rótulo de confidencialidade a um documento do Microsoft Word e, em seguida, exibirá a marca do conteúdo (rodapé) gerada pelo rótulo. OBSERVAÇÃO: ao usar o Microsoft Word online, você pode sofrer um atraso antes que a opção para selecionar rótulos de confidencialidade apareça na faixa de opções superior.  É recomendável que você conclua todos os laboratórios restantes e retorne a esta tarefa.

1. Você ainda deve estar na home page do portal do Microsoft Purview. 
1. No portal do Microsoft Purview, selecione o **ícone do inicializador de aplicativos** ao lado de onde está escrito Microsoft Purview. Selecione o **ícone do Word**.  

1. Em Criar, selecione **Documento em branco** e insira algum texto na página.  Na parte superior da página, ao lado do ícone do Word, selecione onde está escrito **Documento** e renomeie o arquivo para **Test-label** e então, pressione **Enter** em seu teclado.

1. No canto direito da barra de menu superior (também conhecida como faixa de opções), você encontrará uma seta para baixo. Selecione-a e depois escolha **Faixa de Opções Clássica**.  Isso vai ajudar a identificar o ícone de confidencialidade mais facilmente. Selecione **Confidencialidade**, que está ao lado do ícone do microfone. No menu suspenso, selecione **Altamente confidencial** e, em seguida, selecione **Todos os Funcionários**.  

1. Na barra de menu superior, selecione **Exibição** e depois **Modo de Exibição de Leitura**.

1. Observe como o documento inclui o rodapé "Classificado como altamente confidencial".  

1. Feche as guias do Microsoft Word que estão abertas no navegador para sair do Word, mas mantenha a guia do navegador para a página inicial do Microsoft Purview aberta.

### Revisão

Nesta demonstração, você apresentou as configurações que podem ser definidas para os rótulos de confidencialidade e as configurações de políticas para publicar rótulos de confidencialidade. Você também mostrou como aplicar uma etiqueta.
