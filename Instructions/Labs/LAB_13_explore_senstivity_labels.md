---
lab:
  title: Explorar rótulos de confidencialidade no Microsoft Purview
  module: 'Module 4 Lesson 3: Describe the capabilities of Microsoft compliance solutions: Describe information protection and data lifecycle management of Microsoft Purview'
ms.openlocfilehash: 65cf71c24e66e5c94fb27a1479693338a3cd7091
ms.sourcegitcommit: b8b861a8c884a56f094213e47a59be48ba898ca1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "146741838"
---
# <a name="lab-explore-sensitivity-labels-in-microsoft-purview"></a>Laboratório: Explorar rótulos de confidencialidade no Microsoft Purview

## <a name="lab-scenario"></a>Cenário do laboratório

Neste laboratório, vamos explorar as funcionalidades dos rótulos de confidencialidade.  Vamos passar pelas configurações dos rótulos de confidencialidade que já foram criados e a respectiva política para a publicação do rótulo.   Depois, vamos ver como aplicar o rótulo e o impacto dele da perspectiva do usuário.

**Tempo estimado**: 20 a 25 minutos

### <a name="task-1"></a>Tarefa 1:

Nesta tarefa, vamos ver o que os rótulos de confidencialidade podem fazer, acompanhando as configurações dos rótulos de confidencialidade existentes e a respectiva política para a publicação do rótulo.

1. Abra o Microsoft Edge. Na barra de endereços, insira **admin.microsoft.com**.

1. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é sua ID de locatário exclusiva fornecida pelo provedor de hospedagem de laboratório) e selecione **Avançar**.

    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem de laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**. Vamos ser direcionados à página Centro de administração do Microsoft 365.

1. À esquerda no painel de navegação do Centro de administração do Microsoft 365, selecione **Mostrar todos**.

1. Em Centros de administração, selecione **Conformidade**.  A página inicial do portal de conformidade do Microsoft Purview é aberta em uma nova página do navegador.  

1. Do lado esquerdo do painel de navegação, em soluções, selecione **Proteção de informações**.

1. Selecione a guia **Rótulos** na parte superior da página.

1. Uma caixa de informações amarela é exibida indicando que a "Sua organização não habilitou o processamento de conteúdo em arquivos online do Office com rótulos de confidencialidade criptografados e que se encontram armazenados no OneDrive e no SharePoint..."  Selecione **Habilitar agora**.  Após você fazer isso, pode haver um atraso para a configuração ser propagada no sistema.** **

1. No meio da página, observe que há três rótulos já criados.  Selecione **Confidencial - Finanças**.  Uma janela será aberta com informações sobre este rótulo.  Observe que este rótulo está configurado para comportar tanto criptografia quanto marcação de conteúdo.  Selecione Editar Rótulo no topo da página para exibir algumas configurações básicas.

1. A configuração começa informando o nome e a descrição do rótulo.  Não altere nada.  Selecione **Avançar** na parte inferior da página.

1. Observe o escopo deste rótulo.  O escopo é definido para Arquivos e emails aos quais é possível configurar a Criptografia e marcação de conteúdo para proteger emails rotulados e arquivos do office.  Não altere nada.  Selecione **Avançar** na parte inferior da página.

1. Para o escopo selecionado, Arquivos e emails, é possível configurar a criptografia e/ou marcação de conteúdo.  Observe como as configurações de proteção para arquivos e emails são definidas tanto para a criptografia quanto para a marcação de conteúdo dos arquivos.  Verifique a definição de cada um.  Não altere nada.  Selecione **Avançar** na parte inferior da página.

1. A janela Criptografia mostra as configurações de criptografia.  Não altere nada.  Verifique a caixa de informações em Configurar criptografia e também as configurações definidas. Observe como o acesso do usuário ao conteúdo é definido para não expirar nunca.  Também é possível atribuir permissões para usuários e grupos específicos para que eles possam interagir com o conteúdo a que o rótulo se aplica.  Em usuários e grupos, o locatário é definido para que todos os usuários do seu locatário possam encontrar o conteúdo com este rótulo.  A equipe de finanças também aparece listada e tem permissões de cocriação.  Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.

1. Na página de marcações de conteúdo, observe a caixa de informações no topo da página.  As marcações de conteúdo serão aplicadas a todos os documentos, mas apenas os cabeçalhos e notas de rodapé serão aplicados às mensagens de email. Em outras palavras, as marcas d’água não serão aplicadas aos emails.  A marcação de conteúdo associada a esse rótulo é uma marca-d'água em que se lê ALTAMENTE CONFIDENCIAL.  Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.

1. Agora estamos na janela Rotulamento automático de arquivos e emails.  Leia a descrição de rotulamento automático no topo da página e a caixa de informações abaixo delas.  Observe também que este rótulo está definido para o rotulamento automático para condições específicas. Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.

1. A próxima janela define as configurações de proteção para equipes, grupos e sites que têm este rótulo aplicado. Isso não está habilitado; selecione **Avançar** na parte inferior da página.

1. A próxima janela é uma versão prévia do recurso de aplicar automaticamente este rótulo às colunas do banco de dados do Azure (como SQL, Synapse, etc.), que contêm os tipos de informações confidenciais escolhidos por você.  Esse recurso não está habilitado. Selecione **Cancelar** na parte inferior da página para sair do assistente de configuração de rótulos e voltar à página Proteção de Informações.

1. Na parte superior da página Proteção de informações, selecione **Políticas de rótulo**.  É por meio das políticas de rótulo que os rótulos de confidencialidade podem ser publicados.  

1. Selecione **Política de Finanças-Confidencial**.  Uma janela será aberta com informações sobre a política.  Esta política destina-se para a publicação dos rótulos da Política de Finanças-Confidencial e proteção dos dados que contêm informações financeiras da Contoso.  Observe também que esta política é publicada a todos.  

1. Selecione **Editar** política na parte superior da janela.

1. Leia a descrição em “Escolher rótulos de confidencialidade para publicar”.  Observe o rótulo que está listado.  Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.

1. Leia a descrição em “Publicar para usuários e grupos”.  Observe que este rótulo está disponível para todos os usuários.  Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.

1. Verifique as configurações da política.  Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Leia a descrição em "Aplicar um rótulo padrão a documentos".  Observe que não há nenhum rótulo padrão. Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Leia a descrição em "Aplicar um rótulo padrão a emails".  Selecione a seta para baixo na caixa de entrada para exibir as opções disponíveis. Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Leia a descrição em "Aplicar um rótulo padrão ao conteúdo do Power BI".  Observe que não há nenhum rótulo padrão. Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.

1. A última opção de configuração é para nomear a política.  Não altere nenhuma configuração.  Selecione **Cancelar** na parte inferior da página para sair da configuração da política e voltar à página Proteção de Informações.

1. Na página Proteção de informações, selecione Rotulamento automático.  Observe que não tem uma política de rotulamento automático configurada.  Não altere nenhuma configuração.  Se você estiver se perguntando o porquê não tem nenhuma política aqui, já que a configuração de rótulos está definida para rotulamento automático de arquivos e emails, volte às etapas em que acompanhamos as configurações de rótulos e verifique a descrição e a caixa de informações associada ao Rotulamento automático de arquivos e emails.  Dica:  Na guia de rotulamento automático do laboratório de confidencialidade, é informado que:  “Para aplicar este rótulo automaticamente a arquivos que já estão salvos (no SharePoint e no OneDrive) ou emails já processados pelo Exchange, é preciso criar uma política de rotulamento automático.”

1. À esquerda no painel de navegação, selecione Página Inicial para voltar ao portal de conformidade do Microsoft Purview.

1. Deixe essa página aberta; vamos usá-la na próxima tarefa.

### <a name="task-2"></a>Tarefa 2:

Nesta tarefa, vamos acompanhar o processo de aplicação de rótulos da perspectiva do usuário (no caso, o usuário é o administrador) e verificar a marcação de conteúdo gerada pelo rótulo.

1. Na página inicial do Centro de conformidade do Microsoft 365, selecione o **ícone lançador do aplicativo**, ao lado de onde ele diz Contoso Electronics. **clique com o botão direito do mouse no ícone do Word** e selecione **Abrir na nova guia**.  

1. Selecione **+ Novo documento em branco** e insira algum texto na página.  Na barra azul no topo da página, selecione a seta para baixo, perto de DocumentoXX - Salvo, e insira **Rótulo-teste** na caixa do Nome do Arquivo.

1. Na barra do menu superior, selecione **Confidencialidade**. Se você não vir essa opção imediatamente, atualize a página. No menu suspenso, selecione **Confidencial - Finanças**.  OBSERVAÇÃO:  A opção Confidencialidade pode levar até 15 minutos para aparecer.

1. Na barra de menu superior, selecione **Exibição** e depois **Modo de Exibição de Leitura**.

1. Observe que o documento inclui a marca-d’água.  

1. Feche as guias do Microsoft Word abertas no seu navegador para sair do Word.

### <a name="task-3-optional"></a>Tarefa 3 (opcional)

Além da marcação de conteúdo, a configuração de proteção de rótulos foi definida para criptografia. De acordo com as permissões configuradas com este rótulo, os membros do grupo de finanças podem cocriar documentos com este rótulo aplicado e os usuários no locatário da Contoso podem exibi-los.  Nesta tarefa, vamos enviar este documento a um endereço de email ao qual temos acesso (i.e., um endereço de email pessoal) e que NÃO faz parte do domínio WWLxZZZZ.OnMicrosoft.com e verificar o que acontece quando tentamos abrir o anexo.

1. Na página inicial do portal de conformidade do Microsoft Purview, selecione o **ícone de inicialização do aplicativo** ao lado de Contoso Electronics. **clique com o botão direito do mouse no ícone do Outlook** e selecione **Abrir na nova guia**.

1. Selecione **Nova mensagem** na no canto superior esquerdo da tela.  Insira um endereço de email ao qual você tem acesso e que não faça parte do domínio WWLxZZZZ.OnMicrosoft.com. Depois, insira **Teste** no assunto.

1. Selecionar **Anexar**.

1. Selecione **Procurar localizações na nuvem**.

1. Na lista aberta, selecione o documento criado, ao qual aplicamos o rótulo **Rótulo-teste**. Selecione **Avançar** e depois **Anexar como cópia**.  Pressione **Enviar**.

1. Usando o navegador da Web na VM do laboratório, faça logon na conta de email para a qual você enviou o documento.  Lembre-se de que o email pode ter sido direcionado à pasta de lixo eletrônico.  Quando tentar abrir o arquivo do word em anexo, encontramos uma notificação de que não temos permissão para abrir o arquivo.

1. Feche todas as guias abertas do navegador.

### <a name="review"></a>Revisão

Neste laboratório, vamos explorar as funcionalidades dos rótulos de confidencialidade.  Vamos passar pelas configurações dos rótulos de confidencialidade que já foram criados e a respectiva política para a publicação do rótulo.   Depois, vamos ver como aplicar o rótulo e o impacto dele da perspectiva do usuário.
