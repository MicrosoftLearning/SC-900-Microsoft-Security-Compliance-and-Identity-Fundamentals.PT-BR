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

Nesta demonstração, você mostrará as funcionalidades dos rótulos de confidencialidade.  Você percorrerá as configurações dos rótulos de confidencialidade que foram criados e a política correspondente para publicá-lo.   Depois, você verá como aplicar o rótulo e o impacto dele da perspectiva do usuário.  **OBSERVAÇÃO**: na primeira vez que você usa o Word online com seu locatário do Microsoft 365, pode levar 15 minutos para que a opção Confidencialidade apareça na faixa de opções.  Os apresentadores devem executar a parte 2 da demonstração antes da aula a fim de garantir que haja tempo suficiente para que a opção apareça.

### Demonstração parte 1

Nesta demonstração, você apresentará as configurações de um rótulo de confidencialidade existente e a política correspondente para publicá-lo.

1. Abra uma nova aba no navegador Microsoft Edge e, na barra de endereços, digite **https://purview.microsoft.com**. Para acessar o novo portal do Microsoft Purview, marque a caixa ao lado de onde diz **Eu concordo com os termos de divulgação de fluxo de dados e políticas de privacidade** e selecione **Introdução**.  

1. Na página de aterrissagem do novo portal do Microsoft Purview, selecione o bloco **Exibir todas as soluções** e, em seguida, selecione o bloco **Gerenciador de informações**. Como alternativa, selecione **Soluções** no painel de navegação esquerdo e, em seguida, selecione **Proteção de informações**.

1. Você chegará à página de visão geral. No painel de navegação à esquerda, selecione **Rótulos de confidencialidade**.

1. Alguns rótulos foram pré-configurados em seu locatário de laboratório do Microsoft 365, para sua conveniência. Selecione o rótulo denominado **Confidencial – Finanças**.  Uma janela será aberta com informações sobre este rótulo.  Observe as configurações dessa etiqueta.  Selecione o **Editar rótulo** (também pode aparecer como um ícone de lápis) na parte superior da página para visualizar algumas configurações básicas. Caso não encontre essa opção, selecione os três pontinhos.
    1. A configuração começa informando o nome e a descrição do rótulo.  Não altere nada.  Selecione **Avançar** na parte inferior da página.
    1. Observe o escopo desta etiqueta. Não altere nada.  Selecione **Avançar** na parte inferior da página.
    1. Esta próxima tela é onde você pode escolher as configurações de proteção para os itens rotulados. Observe que essa etiqueta está configurada para dar suporte à marcação de conteúdo. Não altere nada.  Selecione **Avançar** na parte inferior da página.
        1. Na página de marcações de conteúdo, observe a caixa de informações no topo da página.  Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. Agora você está na janela Rotulamento automático de arquivos e emails.  Leia a descrição de rotulamento automático no topo da página e a caixa de informações abaixo delas.  Observe também que este rótulo está definido para o rotulamento automático para condições específicas. Não altere nenhuma configuração.  Selecione **Avançar** na parte inferior da página.
    1. A próxima janela define as configurações de proteção para equipes, grupos e sites que têm esta etiqueta aplicada. Isso não está habilitado; selecione **Avançar** na parte inferior da página.
    1. Esta janela é uma versão prévia do recurso de aplicação automática da etiqueta aos ativos de dados esquematizados no Mapa de Dados do Microsoft Purview (como o SQL, o Synapse, entre outros) que contêm os tipos de informações confidenciais escolhidos por você.  O recurso não está habilitado. Selecione **Cancelar** na parte inferior da página para sair do assistente de configuração de rótulos e voltar à página Proteção de Informações.

1. No painel de navegação à esquerda, selecione **Políticas** e então, selecione **Políticas de publicação**.  É por meio das políticas de rótulo que os rótulos de confidencialidade podem ser publicados.  O locatário do Microsoft 365 foi configurado com algumas políticas de rótulo, para sua conveniência.

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

1. No painel de navegação à esquerda, dentro de Proteção de informações, escolha a opção de Rotulagem automática. Examine a descrição. Observe que você cria políticas de rotulagem automática para aplicar automaticamente os rótulos de confidencialidade às mensagens de email ou aos arquivos do OneDrive e do SharePoint que contêm informações confidenciais. Se houver políticas de rotulagem automática configuradas, selecione uma e revise as informações da política no painel de detalhes.  Se nenhuma política estiver listada, você poderá optar por percorrer as etapas para criar uma, se o tempo permitir.

1. No painel de navegação esquerdo, selecione Página Inicial para retornar ao portal do Microsoft Purview.

1. Mantenha essa guia do navegador aberta.

### Demonstração parte 2

Nesta etapa, você mostrará o processo de aplicação de um rótulo da perspectiva do usuário (neste caso, o usuário é o administrador).  Para ver o impacto da aplicação do rótulo, você selecionará o rótulo Confidencial – Finanças, porque esse rótulo aplica uma marca d'água.

1. Na home page do portal de conformidade do Microsoft Purview, selecione o **ícone do inicializador de aplicativos** ao lado de onde está escrito "Microsoft Purview" (em cima do ícone de página inicial). Selecione o **ícone do Word**.  

1. Selecione **Documento em branco** e insira um texto na página.  Na barra azul na parte superior da página, selecione a seta para baixo, ao lado de Documento – Salvo, insira **Rótulo-teste** e pressione a tecla **ENTER** no teclado.

1. No canto direito da barra de menu superior (também conhecida como faixa de opções), você encontrará uma seta para baixo, selecione-a depois escolha **Faixa de Opções Clássica**.  Isso vai ajudar a identificar o ícone de confidencialidade mais facilmente. Selecione **Confidencialidade**, que está ao lado do ícone do microfone. No menu suspenso, selecione **Confidencial-Finanças**.  

1. Na barra de menu superior, selecione **Exibição** e depois **Modo de Exibição de Leitura**.

1. Observe que o documento inclui a marca-d’água.  

1. Feche as guias do Microsoft Word abertas no seu navegador para sair do Word.

1. Mantenha a guia do navegador do Microsoft Purview aberta para a próxima demonstração.

### Revisão

Nesta demonstração, você apresentou as configurações que podem ser definidas para os rótulos de confidencialidade e as configurações de políticas para publicar rótulos de confidencialidade. Você também mostrou como aplicar uma etiqueta.
