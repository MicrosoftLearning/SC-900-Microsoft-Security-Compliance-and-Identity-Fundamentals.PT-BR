<!---
---
Laboratório: Título: 'Explorar rótulos de confidencialidade no Microsoft Purview' Roteiro de aprendizagem/Módulo/Unidade: 'Roteiro de Aprendizagem: descrever as funcionalidades de conformidade da Microsoft; Módulo 3: descrever a proteção de informações e o gerenciamento de ciclo de vida de dados no Microsoft Purview; Unidade 4: descrever rótulos de confidencialidade'
---
--->

# Laboratório: Explorar rótulos de confidencialidade no Microsoft Purview

Esse laboratório é mapeado para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades de conformidade da Microsoft
- Módulo: descrever a proteção de informações e o gerenciamento do ciclo de vida de dados no Microsoft Purview
- Unidade: descrever rótulos de confidencialidade

## Cenário do laboratório

Neste laboratório, você vai explorar as funcionalidades dos rótulos de confidencialidade.  Você percorrerá as configurações dos rótulos de confidencialidade que foram criados e a política correspondente para publicá-lo.   Depois, você verá como aplicar o rótulo e o impacto dele da perspectiva do usuário.

**Tempo estimado**: 20 a 25 minutos

### Tarefa 1:

Nesta tarefa, você obterá uma compreensão do que os rótulos de confidencialidade podem fazer acompanhando as configurações de um rótulo de confidencialidade existente e a política correspondente para publicá-lo.

1. Abra a guia do navegador para a página inicial do Microsoft Purview.  Se você a fechou anteriormente, abra uma nova guia do navegador e insira **https://admin.microsoft.com** . Entre com as credenciais de administrador para o locatário do Microsoft 365 fornecido pelo hoster de laboratório autorizado (ALH). No painel de navegação à esquerda do Centro de administração do Microsoft 365, selecione **Mostrar tudo** e depois **Conformidade**.  A página inicial do portal de conformidade do Microsoft Purview é aberta em uma nova página do navegador.   

1. No painel de navegação à esquerda, em soluções, expanda **Proteção de informações** e selecione **Visão geral**. Observe o aviso na parte superior da página e role para baixo para exibir as informações disponíveis.
   1. Na página de visão geral, observe que a caixa de informações amarela indica que a sua organização não habilitou o processamento de conteúdo em arquivos online do Office com rótulos de confidencialidade criptografados e que estão armazenados no OneDrive e no SharePoint.  Selecione **Habilitar agora**.  Depois de fazer isso, pode haver um atraso para a configuração se propagar pelo sistema e há etapas adicionais que devem ser concluídas para proteger o Teams, sites do SharePoint e Grupos do Microsoft 365.

1. No painel de navegação à esquerda, selecione **Rótulos**.
   1. Na página Rótulos, observe que a caixa de informações amarela indica que a sua organização não habilitou o processamento de conteúdo em arquivos online do Office com rótulos de confidencialidade criptografados e que estão armazenados no OneDrive e no SharePoint.  Selecione **Habilitar agora**.  Depois de fazer isso, pode haver um atraso para a configuração se propagar pelo sistema e há etapas adicionais que devem ser concluídas para proteger o Teams, sites do SharePoint e Grupos do Microsoft 365.
1. Alguns rótulos foram pré-configurados em seu locatário de laboratório do Microsoft 365, para sua conveniência. Expanda o rótulo chamado **Altamente confidencial** selecionando o **>** e, em seguida, selecione **Todos os funcionários**.  Uma janela será aberta com informações sobre este rótulo.  Observe que este rótulo está configurado para comportar tanto criptografia quanto marcação de conteúdo.  Selecione o **ícone de lápis** na parte superior da página para visualizar algumas configurações básicas. Se você não vir o ícone de lápis, selecione as reticências.
    1. A configuração começa informando o nome e a descrição do rótulo.  Não altere nada.  Selecione **Avançar** na parte inferior da página.
    1. Observe o escopo deste rótulo.  O escopo é definido como Arquivos e emails.  Não altere nada.  Selecione **Avançar** na parte inferior da página.
    1. Esta próxima tela é onde você pode escolher as configurações de proteção para os itens rotulados. Observe que esse rótulo está configurado para dar suporte à criptografia e à marcação de conteúdo. Não altere nada.  Selecione **Avançar** na parte inferior da página.
        1. A janela Criptografia mostra as configurações de criptografia. Examine as configurações atuais, mas não altere nada. Observe como o acesso do usuário ao conteúdo é definido para nunca expirar e sempre permitir o acesso offline.  Também é possível atribuir permissões para usuários e grupos específicos para que eles possam interagir com o conteúdo a que o rótulo se aplica.  Em usuários e grupos, o locatário é definido para que todos os usuários do seu locatário possam encontrar o conteúdo com este rótulo.  Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
        1. Na página de marcações de conteúdo, observe a caixa de informações no topo da página.  As marcações de conteúdo serão aplicadas a todos os documentos, mas apenas os cabeçalhos e notas de rodapé serão aplicados às mensagens de email. Em outras palavras, as marcas d’água não serão aplicadas aos emails.  A marcação de conteúdo associada a este rótulo é um rodapé.  Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Agora estamos na janela Rotulamento automático de arquivos e emails.  Leia a descrição de rotulamento automático no topo da página e a caixa de informações abaixo delas.  Observe também que este rótulo está definido para o rotulamento automático para condições específicas. Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. A próxima janela define as configurações de proteção para equipes, grupos e sites que têm este rótulo aplicado. Isso não está habilitado; selecione **Avançar** na parte inferior da página.
    1. A próxima janela é uma versão prévia do recurso de aplicação automática do rótulo aos ativos de dados esquematizados no Mapa de Dados do Microsoft Purview (como o SQL, o Synapse, entre outros) que contêm os tipos de informações confidenciais escolhidos por você.  O recurso não está habilitado. Selecione **Cancelar** na parte inferior da página para sair do assistente de configuração de rótulos e voltar à página Proteção de Informações.

1. No painel de navegação à esquerda, selecione **Políticas de rótulo**.  É por meio das políticas de rótulo que os rótulos de confidencialidade podem ser publicados.  O locatário do Microsoft 365 foi configurado com algumas políticas de rótulo, para sua conveniência.

1. Nesse caso, selecione **Política de rótulo de confidencialidade global**.  Uma janela será aberta com informações sobre a política.  Observe que a descrição dessa política de rótulo foi configurada para servir como a política de rótulo de confidencialidade padrão para todos os usuários e grupos. Essa política serve para publicar a maioria dos rótulos que foi pré-configurada para esse locatário do laboratório do Microsoft 365 e está listada na guia Rótulos.  

1. Selecione **Editar política** na parte superior da janela.
    1. Leia a descrição de "Escolher rótulos de confidencialidade para publicar".  Observe os rótulos listados.  Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Examine a descrição de "Atribuir unidades de administração". As unidades de administração são definidas como o diretório completo; não altere nenhuma configuração. Selecione **Avançar**.  
    1. Examine a descrição em “Publicar para usuários e grupos”.  Observe que esse rótulo está disponível para todos os usuários.  Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Verifique as configurações da política. Selecione **Exigir que os usuários apliquem um rótulo a seus emails e documentos** e examine a descrição fornecida. Selecione **Avançar** na parte inferior da página.
    1. Examine a descrição de "Aplicar um rótulo padrão a documentos". Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Examine a descrição de "Aplicar um rótulo padrão a emails" e "Herdar rótulo de anexos". Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Examine a descrição de "Aplicar um rótulo padrão a reuniões e eventos de calendário". Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Examine a descrição de "Aplicar um rótulo padrão ao conteúdo do Power BI". Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. A última opção de configuração é para nomear a política.  Como você está editando a política, o campo de nome fica esmaecido. Selecione **Avançar** na parte inferior da página.
    1. Verifique as configurações da política. Selecione **Cancelar** para descartar as alterações e retornar à página Políticas de rótulo.

1. Na página Proteção de informações, selecione Rotulamento automático. Examine a descrição. Observe que você cria políticas de rotulagem automática para aplicar automaticamente rótulos de confidencialidade a mensagens de email ou arquivos do OneDrive e do SharePoint que contêm informações confidenciais. Nenhuma política de rótulo automático foi pré-configurada em nosso locatário. Para criar uma nova política de rótulo automático, selecione **Criar política de rótulo automático**.  Aqui, você percorrerá as etapas para criar uma nova política.
    1. Você começa escolhendo as informações às quais deseja que esse rótulo seja aplicado.  Observe as opções disponíveis.  Selecione **Medicina e saúde** e, em seguida, selecione um dos modelos disponíveis.  Selecione **Avançar**.
    1. Você pode nomear sua política de rótulo automático ou usar o nome padrão.  Selecione **Avançar**.
    1. Você pode atribuir as unidades de administração às quais essa política se aplica.  Deixe o padrão definido como diretório completo e selecione **Avançar**.
    1. Observe os locais disponíveis em que você deseja aplicar o rótulo.  Mantenha o padrão e selecione **Avançar**.
    1. Você pode configurar regras comuns ou avançadas que definem a qual conteúdo o rótulo é aplicado.  Deixe o padrão definido como Regras comuns e selecione **Avançar**.
    1. Você pode definir regras para conteúdo em todos os locais.  O rótulo será aplicado ao conteúdo que corresponde às regras definidas nesta página.  Para o modelo selecionado, você deverá ver um item de linha. Expanda-o para exibir as condições que se aplicam.  Mantenha todas as configurações padrão e selecione **Avançar**.
    1. Escolha um rótulo a ser aplicado automaticamente selecionando **Escolher um rótulo**.  Escolha um rótulo e selecione **Adicionar**. Selecione **Avançar**.
    1. Configurações adicionais podem ser definidas para o email. Mantenha o padrão e selecione **Avançar**.
    1. Você pode decidir testar a política agora ou depois.  Selecione **Deixar a política desativada** e selecione **Avançar**.
    1. Examine as configurações e selecione **Criar política** e, em seguida, selecione **Concluído**.

1. À esquerda no painel de navegação, selecione **Página Inicial** para voltar ao portal de conformidade do Microsoft Purview.

1. Mantenha essa página aberta, pois você vai usá-la na próxima tarefa.

### Tarefa 2:

Nesta tarefa, você passará pelo processo de aplicação de um rótulo de confidencialidade a um documento do Microsoft Word e, em seguida, exibirá a marca do conteúdo (marca d'água) gerada pelo rótulo. OBSERVAÇÃO: ao usar o Microsoft Word online, você pode sofrer um atraso antes que a opção para selecionar rótulos de confidencialidade apareça na faixa de opções superior.  É recomendável que você conclua todos os laboratórios restantes e retorne a esta tarefa.

1. Na página inicial do portal de conformidade do Microsoft Purview, selecione o **ícone de inicialização do aplicativo** ao lado de Contoso Electronics. Selecione o **ícone do Word**.  

1. Em Criar, selecione **Documento em branco** e insira algum texto na página.  Na parte superior da página, selecione a seta para baixo, ao lado de Documento – Salvo e, na caixa Nome do Arquivo, insira **Rótulo-teste** e pressione **ENTER** no teclado.

1. Na barra de menus superior, selecione o **ícone de confidencialidade**, o ícone à direita do ícone de microfone (dependendo do tamanho da tela, pode ser necessário selecionar as reticências e a confidencialidade). Na lista suspensa, selecione **Altamente confidencial** e, em seguida, selecione **Todos os funcionários**.  OBSERVAÇÃO: ao usar o Microsoft Word online, você pode sofrer um atraso antes que a opção para selecionar rótulos de confidencialidade apareça na faixa de opções superior.  É recomendável que você conclua todos os laboratórios restantes e retorne a esta tarefa.

1. Na barra de menu superior, selecione **Exibição** e depois **Modo de Exibição de Leitura**.

1. Observe como o documento inclui o rodapé "Classificado como altamente confidencial".  

1. Feche as guias do Microsoft Word abertas no seu navegador para sair do Word.

### Tarefa 3 (opcional)

Lembre-se, da primeira parte da demonstração, que o rótulo Altamente confidencial – todos os funcionários está configurado para criptografia. De acordo com as permissões que foram configuradas com esse rótulo, os usuários no locatário da Contoso têm permissões de visualizador em qualquer documento/email com o rótulo aplicado.  Nesta seção, você enviará o documento criado anteriormente, que inclui o rótulo Altamente confidencial – todos os funcionários, para um endereço de email ao qual você tem acesso (um endereço de email pessoal ou seu email Microsoft) e que NÃO faz parte do domínio WWLxZZZZ.OnMicrosoft.com.  

1. Na página inicial do portal de conformidade do Microsoft Purview, selecione o **ícone de inicialização do aplicativo** ao lado de Contoso Electronics. Selecione o **ícone do Outlook**.

1. Selecione **Nova mensagem** no canto superior esquerdo da tela.  Insira um endereço de email ao qual você tem acesso e que não faça parte do domínio WWLxZZZZ.OnMicrosoft.com. Depois, insira **Teste** no assunto.

1. Selecione **Anexar** (o ícone de clipe de papel).

1. Selecione **OneDrive**.

1. Verifique se a guia **Recente** no painel de navegação à esquerda está selecionada.  Na lista que é aberta, selecione o documento **Test-label.docx** criado por você, ao qual você aplicou o rótulo Altamente confidencial – todos os funcionários. Selecione a seta suspensa **Compartilhar link** e selecione **Anexar**.  Pressione **Enviar**.

1. Verifique o email a que você enviou o documento.  Observação: o email pode ter sido direcionado à pasta de lixo eletrônico.  O email foi enviado com sucesso, mas quando você tentar abrir o arquivo do Word anexado, que foi originalmente rotulado como Altamente confidencial – todos os funcionários, verá uma notificação informando que não tem permissão para abrir o documento.

1. Feche o Outlook, mas mantenha a guia do navegador na página inicial do Microsoft Purview aberta.

### Revisão

Neste laboratório, você vai explorar as funcionalidades dos rótulos de confidencialidade.  Você percorrerá as configurações dos rótulos de confidencialidade que já foram criados e a política correspondente para publicá-lo.   Depois, você verá como aplicar o rótulo e o impacto dele da perspectiva do usuário.
