---
Demo:
    title: 'Rótulos de confidencialidade no Microsoft 365'
    module: 'Módulo 4 – Lição 2: Descrever os recursos das soluções de conformidade da Microsoft: Descrever os recursos de proteção de informações e de governança do Microsoft 365'
---


# Demonstração: Rótulos de confidencialidade no Microsoft 365

### Cenário da demonstração
Nesta demonstração, você mostrará os recursos dos rótulos de confidencialidade.  Você passará pelas configurações dos rótulos de sensibilidade existentes que foram criados e a política correspondente para publicar o rótulo.   Em seguida, você verá como aplicar um rótulo e o impacto desse rótulo, da perspectiva de um usuário.


#### Demonstração – Parte 1: Nesta demonstração, você mostrará as configurações de um rótulo de confidencialidade existente e a política correspondente para publicá-lo.

1. Abra o Microsoft Edge. Na barra de endereços, insira **admin.microsoft.com**.

1. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (onde ZZZZZZ é sua ID de locatário exclusiva fornecida por seu provedor de hospedagem de laboratório) e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida por seu provedor de hospedagem de laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**. Isso leva você para a página do centro de administração do Microsoft 365.

1. No painel de navegação esquerdo do centro de administração do Microsoft 365, selecione **Mostrar tudo**.

1. Em Centros de administração, selecione **Conformidade**.  Uma nova página do navegador é aberta na página de boas-vindas do Centro de conformidade do Microsoft 365.  

1. No painel de navegação esquerdo do Centro de conformidade do Microsoft 365, selecione **Mostrar tudo**.

1. No painel de navegação esquerdo, em Soluções, selecione **Proteção de Informações**.

1. Na caixa de informações amarela, haverá uma indicação de que sua organização não ativou o recurso de processar conteúdo em arquivos online do Office com rótulos de confidencialidade criptografados aplicados e armazenados no OneDrive e no SharePoint.  Selecione Ativar agora.  Depois de fazer isso, pode haver um atraso para que a configuração se propague pelo sistema.

1. Verifique se a guia **Rótulos** na parte superior da página está selecionada (sublinhada).

1. No meio da página, observe como já existem três rótulos criados.  Selecione **Confidencial – Finanças**.  É aberta uma janela que fornece informações sobre esse rótulo.  Observe como esse rótulo é definido para suportar criptografia e marcação de conteúdo.  Selecione **Editar rótulo** na parte superior da página para exibir algumas configurações básicas.

    1. A configuração começa fornecendo um nome e uma descrição para seu rótulo.  Não altere nada.  Selecione **Avançar** na parte inferior da página.

    1. Observe o escopo desse rótulo.  O escopo é definido como Arquivos e emails para os quais você pode definir as configurações de criptografia e marcação de conteúdo para proteger emails rotulados e arquivos do Office.  Não altere nada.  Selecione **Avançar** na parte inferior da página.

    1. Para o escopo selecionado, Arquivos e emails, você pode configurar para criptografar e/ou marcar o conteúdo.  Observe como as configurações de proteção para arquivos e emails são definidas para criptografar e marcar o conteúdo dos arquivos.  Revise a definição de cada um.  Não altere nada.  Selecione **Avançar** na parte inferior da página.

    1. A janela Criptografia mostra a configuração das configurações de criptografia.  Não altere nada.  Revise a caixa de informações em Definir configurações de criptografia e revise as configurações definidas. Observe como o acesso do usuário ao conteúdo é definido para nunca expirar.  Você também pode atribuir permissões a usuários e grupos específicos para que apenas eles possam interagir com o conteúdo que tem esse rótulo aplicado.  Em usuários e grupos, o locatário é definido para que todos os usuários em seu locatário possam visualizar o conteúdo que tem esse rótulo.  A equipe de finanças também está listada e tem permissões de cocriar.  Não altere as configurações.  Selecione **Avançar** na parte inferior da página.

    1. Na página de marcações de conteúdo, observe a caixa de informações na parte superior da página.  As marcações de conteúdo serão aplicadas aos documentos, mas apenas cabeçalhos e rodapés serão aplicados às mensagens de email. Em outras palavras, as marcas-d'água não são aplicadas a emails.  A marcação de conteúdo associada a esse rótulo é uma marca-d'água.  Não altere as configurações.  Selecione **Avançar** na parte inferior da página.

    1. Agora você está na janela Rotulamento automático para arquivos e emails.  Leia a descrição do rotulamento automático na parte superior da página e a caixa de informações abaixo dela.  Observe também que esse rótulo é definido para rotulamento automático para condições específicas. Não altere as configurações.  Selecione **Avançar** na parte inferior da página.

    1. A próxima janela define as configurações de proteção para equipes, grupos e sites que têm esse rótulo aplicado. Isso não está habilitado, selecione **Avançar** na parte inferior da página. 

    1. A próxima janela é uma versão prévia do recurso para aplicar automaticamente esse rótulo às colunas do banco de dados do Azure (como SQL, Synapse entre outros) que contêm os tipos de informações confidenciais que você escolher.  Esse recurso não está habilitado. Selecione **Cancelar** na parte inferior da página para sair do assistente de configuração de rótulos e retornar à página Proteção de informações. 

1. Na parte superior da página Proteção de informações, selecione **Políticas de rótulo**.  É por meio de políticas de rótulos que os rótulos de confidencialidade podem ser publicados.  

1. Selecione **Confidencial – Política de finanças**.  É aberta uma janela que fornece informações sobre a política.  Essa política serve para publicar os rótulos de Confidencial – Política de Finanças e protege os dados que contêm dados financeiros da Contoso.  Observe também como essa política é publicada para todos.  

1. Selecione **Editar** política, na parte superior da janela.

    1. Leia a descrição em 'Escolha os rótulos de confidencialidade para publicar'.  Observe o rótulo que está listado.  Não altere as configurações.  Selecione **Avançar** na parte inferior da página.

    1. Leia a descrição em 'Publicar para usuários e grupos'.  Observe que esse rótulo está disponível para todos os usuários.  Não altere as configurações.  Selecione **Avançar** na parte inferior da página.

    1. Revise as configurações da política.  Não altere as configurações.  Selecione **Avançar** na parte inferior da página.

    1. A última opção de configuração é nomear sua política.  Não altere as configurações.  Selecione **Cancelar** na parte inferior da página para sair da configuração da política e retornar à página Proteção de Informações.

1. Na página Proteção de Informações, selecione Rotulamento automático.  Observe que não existe política de rotulamento automático configurada.  Não altere as configurações.  Se você se questionar por que não existe nenhuma política aqui, visto que a configuração do rótulo está definida para rotulamento automático para arquivos e emails, volte para as etapas em que passou pelas definições de configuração do rótulo e revise as caixas de descrição e informações associadas ao Rotulamento automático para arquivos e emails.  Dica:  Na guia de rotulamento automático para o laboratório de confidencialidade, lê-se:  'Para aplicar automaticamente este rótulo a arquivos que já foram salvos (no SharePoint e OneDrive) ou emails que já foram processados pelo Exchange, você deve criar uma política de rotulamento automático.'

1. No painel de navegação esquerdo, selecione Página Inicial para retornar ao Centro de conformidade do Microsoft 365.

1. Deixe essa página aberta para ser usada na próxima tarefa.


#### Demonstração – Parte 2:  Nesta etapa, você mostrará o processo de aplicação de um rótulo da perspectiva do usuário (neste caso, o usuário é o administrador) e exibirá a marcação de conteúdo que é gerada pelo rótulo.

1. Na página inicial do Centro de conformidade do Microsoft 365, selecione o **ícone do inicializador de aplicativos**, próximo a Contoso Electronics. **Clique com o botão direito no ícone do Word** e selecione **Abrir em uma nova guia**.  

1. Selecione **+ Novo documento em branco** e insira algum texto na página.  Na barra azul na parte superior da página, selecione a seta para baixo, ao lado de DocumentoXX – Salvo e, na caixa Nome do arquivo, insira **Rótulo de teste**.

1. Na barra do menu superior, selecione **Confidencialidade**. Se você não vir essa opção imediatamente, atualize a página. No menu suspenso, selecione **Confidencial – Finanças**. 

1. Na barra do menu superior, selecione **Exibir** e selecione **Modo de exibição de leitura**.

1. Observe como o documento inclui a marca-d'água.  

1. Feche as guias do Microsoft Word que estão abertas em seu navegador para sair do Word.

#### Demonstração – Parte 3 (opcional): Além da marcação de conteúdo, a configuração de proteção de rótulo foi definida para criptografia. De acordo com as permissões configuradas com esse rótulo, os membros do grupo financeiro podem cocriar documentos com esse rótulo aplicado e os usuários no locatário da Contoso podem visualizar documentos/emails com o rótulo aplicado.  Nesta seção, você enviará esse documento para um endereço de email ao qual tenha acesso (por exemplo, um endereço de email pessoal ou seu email da Microsoft) e que NÃO faça parte do domínio WWLxZZZZ.OnMicrosoft.com e verá o que acontece quando você tenta para abrir o anexo.  

1. Na página inicial do Centro de conformidade do Microsoft 365, selecione o **ícone do inicializador de aplicativos**, próximo a Contoso Electronics. **Clique com o botão direito no ícone do Outlook** e selecione **Abrir em uma nova guia**.

1. Selecione **Nova mensagem** no canto superior esquerdo da tela.  Insira um endereço de email ao qual você tenha acesso e que não faça parte do domínio WWLxZZZZ.OnMicrosoft.com e insira **Teste** na linha do assunto.

1. Selecione **Anexar**.

1. Selecione **Procurar locais na nuvem**.

1. Na lista que é exibida, selecione o documento que você criou e ao qual aplicou o **Rótulo de teste**. Selecione **Avançar** e selecione **Anexar como uma cópia**.  Pressione **Enviar**.

1. Verifique o email para o qual você enviou o documento.  Observe que o email pode ser direcionado para sua pasta de lixo eletrônico.  Ao tentar abrir o arquivo do Word anexado, você verá uma notificação de que não tem permissão para abrir o documento.

1. Feche as guias do navegador.


#### Revisão
Nesta demonstração, você mostrou os rótulos de confidencialidade.  Você mostrou as configurações dos rótulos de sensibilidade existentes que foram criados e a política correspondente para publicar o rótulo. Em seguida, você mostrou como aplicar um rótulo e o impacto dele da perspectiva de um usuário.
