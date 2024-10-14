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

Neste laboratório, você vai explorar as funcionalidades dos rótulos de confidencialidade.  Você percorrerá as configurações dos rótulos de confidencialidade que foram criados e a política correspondente para publicá-lo.   Depois, você verá como aplicar o rótulo e o impacto dele da perspectiva do usuário.

**Tempo estimado**: 45 minutos

### Tarefa 1

Nesta tarefa, você entenderá o que os rótulos de confidencialidade podem fazer ao passar pelo processo de criar um novo rótulo e uma política para publicá-lo.

1. Abra a guia do navegador na home page do Microsoft Purview.  Se você a fechou anteriormente, abra uma nova guia do navegador e insira **https://admin.microsoft.com** . Entre com as credenciais de administrador para o locatário do Microsoft 365 fornecido pelo hoster de laboratório autorizado (ALH). Se você já fez login como administrador, será solicitado que você conclua uma autenticação secundária, como parte da MFA. Se você não tiver feito login anteriormente como administrador, será solicitado que você conclua o processo de registro de MFA. Siga as instruções na tela para configurar a MFA.

1. No painel de navegação à esquerda do Centro de administração do Microsoft 365, selecione **Mostrar tudo** e depois **Conformidade**.  Uma nova página inicial do portal do Microsoft Purview será aberta em uma nova página do navegador.

1. No painel de navegação à esquerda, selecione **Soluções** e, depois, **Proteção de informações**.  Você está na página de visão geral. Role para baixo para ver as informações disponíveis.

1. No painel de navegação à esquerda, selecione **Rótulos de confidencialidade**.

1. Alguns rótulos foram pré-configurados em seu locatário de laboratório do Microsoft 365, para sua conveniência. Selecione o rótulo denominado **Confidencial – Finanças**.  Uma janela será aberta com informações sobre este rótulo.  Observe as configurações dessa etiqueta.  Clique em **Editar rótulo**. Se não vir essa opção, clique nos três pontos.
    1. A configuração começará com o fornecimento de detalhes básicos para o rótulo.  Não altere nada.  Selecione **Avançar** na parte inferior da página.
    1. Observe o escopo desta etiqueta. Não altere nada.  Selecione **Avançar** na parte inferior da página.
    1. Esta próxima tela é onde você pode escolher as configurações de proteção para os itens rotulados. Observe que essa etiqueta está configurada para dar suporte à marcação de conteúdo. Não altere nada.  Selecione **Avançar** na parte inferior da página.
        1. Na página de marcações de conteúdo, observe a caixa de informações no topo da página.  Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Agora você está na janela Rotulamento automático de arquivos e emails.  Leia a descrição de rotulamento automático no topo da página e a caixa de informações abaixo delas.  Observe também que este rótulo está definido para o rotulamento automático para condições específicas. Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. A janela define as configurações de proteção para grupos e sites em que esse rótulo está aplicado. Isso não está habilitado; selecione **Avançar** na parte inferior da página.
    1. Esta janela é uma versão prévia do recurso de aplicação automática da etiqueta aos ativos de dados esquematizados no Mapa de Dados do Microsoft Purview (como o SQL, o Synapse, entre outros) que contêm os tipos de informações confidenciais escolhidos por você.  O recurso não está habilitado. Selecione **Cancelar** na parte inferior da página para sair do assistente de configuração de rótulos e voltar à página Proteção de Informações.

1. No painel de navegação à esquerda, expanda **Políticas** e selecione **Políticas de publicação**.  É por meio das políticas de rótulo que os rótulos de confidencialidade podem ser publicados.  O locatário do Microsoft 365 foi configurado com algumas políticas de rótulo, para sua conveniência.

1. Selecione **Confidencial – Política de finanças**.  Uma janela será aberta com informações sobre a política. Selecione **Editar política** na parte superior da janela.  Aqui você vai percorrer as configurações sem alterar nada.
    1. Leia a descrição de "Escolher rótulos de confidencialidade para publicar".  Observe o rótulo que está listado.  Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Examine a descrição de "Atribuir unidades de administração". As unidades de administração são definidas como o diretório completo; não altere nenhuma configuração. Selecione **Avançar**.  
    1. Examine a descrição em “Publicar para usuários e grupos”.  Observe que esse rótulo está disponível para todos os usuários.  Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Verifique as configurações da política. Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Examine a descrição de "Aplicar um rótulo padrão a documentos". Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Examine a descrição de "Aplicar um rótulo padrão a emails" e "Herdar rótulo de anexos". Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Examine a descrição de "Aplicar um rótulo padrão a reuniões e eventos de calendário". Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Examine a descrição de "Aplicar um rótulo padrão ao conteúdo do Power BI". Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. A última opção de configuração é para nomear a política.  Como você está editando a política, o campo de nome fica esmaecido. Selecione **Avançar** na parte inferior da página.
    1. Verifique as configurações da política. Selecione **Cancelar** para descartar as alterações e retornar à página Políticas de rótulo.

1. No painel de navegação à esquerda, dentro de Proteção de informações, escolha a opção de Rotulagem automática. Examine a descrição. Observe que você cria políticas de rotulagem automática para aplicar automaticamente rótulos de confidencialidade a mensagens de email ou arquivos do OneDrive e do SharePoint que contêm informações confidenciais. Nenhuma política de rótulo automático foi pré-configurada em nosso locatário. Para criar uma nova política de rótulo automático, selecione **Criar política de rótulo automático**.  Aqui, você percorrerá as etapas para criar uma nova política.
    1. Você começa escolhendo as informações às quais deseja que esse rótulo seja aplicado.  Observe as opções disponíveis.  Selecione **Medicina e saúde** e, em seguida, selecione um dos modelos disponíveis.  Selecione **Avançar**.
    1. Você pode nomear sua política de rótulo automático ou usar o nome padrão.  Selecione **Avançar**.
    1. Você pode atribuir as unidades de administração às quais essa política se aplica.  Deixe o padrão definido como diretório completo e selecione **Avançar**.
    1. Observe os locais disponíveis em que você deseja aplicar o rótulo.  Deixe os padrões e selecione **Avançar**.
    1. Você pode configurar regras comuns ou avançadas que definem a qual conteúdo o rótulo é aplicado.  Deixe o padrão definido como Regras comuns e selecione **Avançar**.
    1. Você pode definir regras para conteúdo em todos os locais.  O rótulo será aplicado ao conteúdo que corresponde às regras definidas nesta página.  Para o modelo selecionado, você deverá ver um item de linha. Expanda-o para exibir as condições que se aplicam.  Mantenha todas as configurações padrão e selecione **Avançar**.
    1. Escolha um rótulo a ser aplicado automaticamente selecionando **Escolher um rótulo**.  Escolha um rótulo e selecione **Adicionar**. Selecione **Avançar**.
    1. Configurações adicionais podem ser definidas para o email. Deixe os padrões e selecione **Avançar**.
    1. Você pode decidir testar a política agora ou depois.  Selecione **Deixar a política desativada** e selecione **Avançar**.
    1. Examine as configurações e selecione **Criar política** e, em seguida, selecione **Concluído**.

1. À esquerda no painel de navegação, selecione **Página Inicial** para voltar ao portal de conformidade do Microsoft Purview.

1. Mantenha essa página aberta, pois você vai usá-la na próxima tarefa.

### Tarefa 2:

Nesta tarefa, você passará pelo processo de aplicação de um rótulo de confidencialidade a um documento do Microsoft Word e, em seguida, exibirá a marca do conteúdo (marca d'água) gerada pelo rótulo. OBSERVAÇÃO: ao usar o Microsoft Word online, você pode sofrer um atraso antes que a opção para selecionar rótulos de confidencialidade apareça na faixa de opções superior.  É recomendável que você conclua todos os laboratórios restantes e retorne a esta tarefa.

1. Na página inicial do portal de conformidade do Microsoft Purview, selecione o **ícone de inicialização do aplicativo** ao lado de Contoso Electronics. Selecione o **ícone do Word**.  

1. Em Criar, selecione **Documento em branco** e insira algum texto na página.  Na parte superior da página, selecione a seta para baixo, ao lado de Documento – Salvo e, na caixa Nome do Arquivo, insira **Rótulo-teste** e pressione **ENTER** no teclado.

1. No canto direito da barra de menu superior (também conhecida como faixa de opções), você encontrará uma seta para baixo. Selecione-a e depois escolha **Faixa de Opções Clássica**.  Isso vai ajudar a identificar o ícone de confidencialidade mais facilmente. Selecione **Confidencialidade**, que está ao lado do ícone do microfone. No menu suspenso, selecione **Confidencial-Finanças**.  

1. Na barra de menu superior, selecione **Exibição** e depois **Modo de Exibição de Leitura**.

1. Observe que o documento inclui a marca-d’água–DADOS FINANCEIROS confidenciais.  

1. Feche as guias do Microsoft Word que estão abertas no navegador para sair do Word, mas mantenha a guia do navegador para a página inicial do Microsoft Purview aberta.

### Revisão

Neste laboratório, você vai explorar as funcionalidades dos rótulos de confidencialidade.  Você percorrerá as configurações dos rótulos de confidencialidade que já foram criados e a política correspondente para publicá-lo.   Então você verá como aplicar uma etiqueta.
