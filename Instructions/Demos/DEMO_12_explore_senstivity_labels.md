<a name="---"></a><!---
---
Demonstração: Título: 'Rótulos de confidencialidade no Microsoft Purview' Roteiro de aprendizagem/Módulo/Unidade: 'Roteiro de Aprendizagem: descrever as funcionalidades de conformidade da Microsoft; Módulo 3: descrever a proteção de informações e o gerenciamento de ciclo de vida de dados no Microsoft Purview; Unidade 4: descrever rótulos de confidencialidade'
---
--->

# <a name="demo-sensitivity-labels-in-microsoft-purview"></a>Demonstração: Rótulos de confidencialidade no Microsoft Purview

Essa demonstração é mapeada para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades de conformidade da Microsoft
- Módulo: descrever a proteção de informações e o gerenciamento do ciclo de vida de dados no Microsoft Purview
- Unidade: descrever rótulos de confidencialidade

## <a name="demo-scenario"></a>Cenário da demonstração

Nesta demonstração, você mostrará as funcionalidades dos rótulos de confidencialidade.  Você percorrerá as configurações dos rótulos de confidencialidade que foram criados e a política correspondente para publicá-lo.   Depois, você verá como aplicar o rótulo e o impacto dele da perspectiva do usuário.  **OBSERVAÇÃO**: Na primeira vez que você usa o Word online com seu locatário do Microsoft 365, pode levar 15 minutos para que a opção Confidencialidade apareça na faixa de opções.  Os apresentadores devem executar a parte 2 da demonstração antes da aula a fim de garantir que haja tempo suficiente para que a opção apareça.

### <a name="demo-part-1"></a>Demonstração parte 1

Nesta demonstração, você apresentará as configurações de um rótulo de confidencialidade existente e a política correspondente para publicá-lo.

1. Abra o Microsoft Edge. Na barra de endereços, insira **admin.microsoft.com**.

1. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é a sua ID de locatário exclusiva fornecida pelo provedor de hospedagem do laboratório) e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**. Vamos ser direcionados à página Centro de administração do Microsoft 365.

1. À esquerda no painel de navegação do Centro de administração do Microsoft 365, selecione **Mostrar todos**.

1. Em Centros de administração, selecione **Conformidade**.  A página inicial do portal de conformidade do Microsoft Purview é aberta em uma nova página do navegador.  

1. À esquerda no painel de navegação do portal de conformidade do Microsoft Purview, selecione **Mostrar todos**.

1. Do lado esquerdo do painel de navegação, em soluções, selecione **Proteção de informações**.

1. Na página de visão geral, observe que a caixa de informações amarela indica que a sua organização não habilitou o processamento de conteúdo em arquivos online do Office com rótulos de confidencialidade criptografados e que estão armazenados no OneDrive e no SharePoint.  Selecione **Habilitar agora**.  Depois de habilitar, pode ter um atraso para a configuração ser propagada no sistema.  Analise também as informações disponíveis nesta página de visão geral.

1. Selecione a guia **Rótulos** na parte superior da página.

1. No meio da página, observe que há três rótulos já criados.  Selecione **Confidencial - Finanças**.  Uma janela será aberta com informações sobre este rótulo.  Observe que este rótulo está configurado para comportar tanto criptografia quanto marcação de conteúdo.  Selecione **Editar rótulo** na parte superior da página para exibir algumas configurações básicas.
    1. A configuração começa informando o nome e a descrição do rótulo.  Não altere nada.  Selecione **Avançar** na parte inferior da página.
    1. Observe o escopo deste rótulo.  O escopo é definido para Arquivos e emails aos quais é possível configurar a Criptografia e marcação de conteúdo para proteger emails rotulados e arquivos do office.  Não altere nada.  Selecione **Avançar** na parte inferior da página.
    1. Para o escopo selecionado, Arquivos e emails, é possível configurar a criptografia e/ou marcação de conteúdo.  Observe como as configurações de proteção para arquivos e emails são definidas para a criptografia e a marcação de conteúdo dos arquivos.  Verifique a definição de cada um.  Não altere nada.  Selecione **Avançar** na parte inferior da página.
    1. A janela Criptografia mostra as configurações de criptografia.  Não altere nada.  Verifique a caixa de informações em Configurar criptografia e também as configurações definidas. Observe como o acesso do usuário ao conteúdo é definido para não expirar nunca.  Também é possível atribuir permissões para usuários e grupos específicos para que eles possam interagir com o conteúdo a que o rótulo se aplica.  Em usuários e grupos, o locatário é definido para que todos os usuários do seu locatário possam encontrar o conteúdo com este rótulo.  A equipe de finanças também aparece listada e tem permissões de cocriação.  Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Na página de marcações de conteúdo, observe a caixa de informações no topo da página.  As marcações de conteúdo serão aplicadas a todos os documentos, mas apenas os cabeçalhos e notas de rodapé serão aplicados às mensagens de email. Em outras palavras, as marcas d’água não serão aplicadas aos emails.  A marcação de conteúdo associada a este rótulo é uma marca-d’água.  Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Agora estamos na janela Rotulamento automático de arquivos e emails.  Leia a descrição de rotulamento automático no topo da página e a caixa de informações abaixo delas.  Observe também que este rótulo está definido para o rotulamento automático para condições específicas. Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. A próxima janela define as configurações de proteção para equipes, grupos e sites que têm este rótulo aplicado. Isso não está habilitado; selecione **Avançar** na parte inferior da página.
    1. A próxima janela é uma versão prévia do recurso de aplicar automaticamente este rótulo às colunas do banco de dados do Azure (como SQL, Synapse, etc.), que contêm os tipos de informações confidenciais escolhidos por você.  O recurso não está habilitado. Selecione **Cancelar** na parte inferior da página para sair do assistente de configuração de rótulos e voltar à página Proteção de Informações.

1. Na parte superior da página Proteção de informações, selecione **Políticas de rótulo**.  É por meio das políticas de rótulo que os rótulos de confidencialidade podem ser publicados.  

1. Nesse caso, selecione **Política de rótulo de confidencialidade global**.  Uma janela será aberta com informações sobre a política.  Observe a descrição: essa é a política de rótulo de confidencialidade padrão para todos os usuários e grupos. Essa política serve para publicar a maioria dos rótulos listados na guia Rótulos e é publicada para todos.  

1. Selecione **Editar** política na parte superior da janela.
    1. Leia a descrição em “Escolher rótulos de confidencialidade para publicar”.  Observe o rótulo que está listado.  Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Leia a descrição em “Publicar para usuários e grupos”.  Observe que esse rótulo está disponível para todos os usuários.  Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Verifique as configurações da política.  Selecionando **Exigir que os usuários apliquem um rótulo aos emails e documentos**.  Selecione **Avançar** na parte inferior da página.
    1. Leia a descrição em "Aplicar um rótulo padrão a documentos".  Observe que não há nenhum rótulo padrão. No campo Rótulo padrão, selecione a seta para baixo e escolha **Geral/Todos os Funcionários (irrestrito)** .  Selecione **Avançar** na parte inferior da página.
    1. Leia a descrição em "Aplicar um rótulo padrão aos emails". Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Leia a descrição em "Aplicar um rótulo padrão ao conteúdo do Power BI". Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. A última opção de configuração é para nomear a política.  Como você está editando a política, o campo de nome fica esmaecido. Selecione **Avançar** na parte inferior da página.
    1. Analise as configurações de política, selecione **Enviar** e escolha **Concluído** para voltar à página Proteção de informações.

1. Na página Proteção de informações, selecione Rotulamento automático.  Observe que não há uma política de rotulamento automático configurada.  Não altere nenhuma configuração.  Se você estiver se perguntando por que não há nenhuma política aqui, considerando que a configuração de rótulos está definida para o rotulamento automático de arquivos e emails, volte às etapas em que você viu as definições de configuração de rótulos e leia a descrição e as caixas de informações associadas ao Rotulamento automático de arquivos e emails.  Dica:  Na guia de rotulamento automático do laboratório de confidencialidade, é informado que:  “Para aplicar este rótulo automaticamente a arquivos que já estão salvos (no SharePoint e no OneDrive) ou emails já processados pelo Exchange, é preciso criar uma política de rotulamento automático.”

1. À esquerda no painel de navegação, selecione Página Inicial para voltar ao portal de conformidade do Microsoft Purview.

1. Mantenha essa página aberta, pois você vai usá-la na próxima tarefa.

### <a name="demo-part-2"></a>Demonstração parte 2

Nesta etapa, você mostrará o processo de aplicação de um rótulo da perspectiva do usuário (neste caso, o usuário é o administrador).  Para ver o impacto da aplicação do rótulo, você selecionará o rótulo Confidencial – Finanças, porque esse rótulo aplica uma marca d'água.

1. Na página inicial do portal de conformidade do Microsoft Purview, selecione o **ícone de inicialização do aplicativo** ao lado de Contoso Electronics. Selecione o **ícone do Word**.  

1. Selecione **+ Novo documento em branco** e insira algum texto na página.  Na barra azul na parte superior da página, selecione a seta para baixo, ao lado de Documento – Salvo, insira **Rótulo-teste** e pressione a tecla **ENTER** no teclado.

1. Na barra de menus superior, selecione **Ícone de confidencialidade** (o ícone à direita do ícone de microfone), se você não vir essa opção imediatamente, atualize a página. No menu suspenso, selecione **Confidencial – Finanças**.  
1. 
1. Na barra de menu superior, selecione **Exibição** e depois **Modo de Exibição de Leitura**.

1. Observe que o documento inclui a marca-d’água.  

1. Feche as guias do Microsoft Word abertas no seu navegador para sair do Word.

### <a name="demo-part-3-optional"></a>Demonstração parte 3 (opcional)

Lembre-se da primeira parte da demonstração de que o rótulo Confidencial – Finanças está configurado para criptografia. De acordo com as permissões que foram configuradas com esse rótulo, os usuários no locatário da Contoso têm permissões de visualizador em qualquer documento/email com o rótulo aplicado.  Nesta seção, você enviará um documento criado anteriormente, que inclui o rótulo Confidencial – Finanças, para um endereço de email ao qual você tem acesso (ou seja, um endereço de email pessoal ou seu email Microsoft) e que NÃO faz parte do domínio WWLxZZZZ.OnMicrosoft.com.  

1. Na página inicial do portal de conformidade do Microsoft Purview, selecione o **ícone de inicialização do aplicativo** ao lado de Contoso Electronics. Selecione o **ícone do Outlook**

1. Selecione **Nova mensagem** na no canto superior esquerdo da tela.  Insira um endereço de email ao qual você tem acesso e que não faça parte do domínio WWLxZZZZ.OnMicrosoft.com. Depois, insira **Teste** no assunto.

1. Selecionar **Anexar**.

1. Selecione **Procurar localizações na nuvem**.

1. Na lista aberta, selecione o documento criado, ao qual aplicamos o rótulo **Rótulo-teste**. Selecione **Avançar** e depois **Anexar como cópia**.  Pressione **Enviar**.

1. Verifique o email a que você enviou o documento.  Lembre-se de que o email pode ter sido direcionado à pasta de lixo eletrônico.  O email foi enviado com sucesso, mas quando você tentar abrir o arquivo do Word anexado, que foi originalmente rotulado como Confidencial – Finanças, verá uma notificação informando que não tem permissão para abrir o documento.

1. Feche as guias do navegador abertas.

### <a name="review"></a>Revisão

Nesta demonstração, você mostrou os rótulos de confidencialidade.  Você mostrou as configurações dos rótulos de sensibilidade existentes que foram criados e a política correspondente para publicar o rótulo. Em seguida, você mostrou como aplicar um rótulo e o impacto dele da perspectiva de um usuário.

