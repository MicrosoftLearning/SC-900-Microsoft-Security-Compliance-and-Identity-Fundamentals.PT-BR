---
lab:
  title: Explorar os NSGs (Grupos de Segurança de Rede) do Azure
  module: Describe the basic security capabilities in Azure
---

# Laboratório: explorar NSGs (grupos de segurança de rede) do Azure

Esse laboratório é mapeado para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades das soluções de segurança da Microsoft
- Módulo: descrever as funcionalidades básicas de segurança no Azure
- Unidade: descrever grupos de segurança de rede do Azure

## Cenário do laboratório

Neste laboratório, você vai explorar a função dos grupos de segurança de rede no Azure.  Você fará isso criando um NSG (grupo de segurança de rede) e atribuindo o NSG à interface de uma VM (máquina virtual) pré-existente.  Após a configuração, você vai observar as regras de entrada e de saída padrão, criar regras e testá-las.  Neste laboratório, a VM que você usará com o NSG será criada para você, ou seja, primeiro, você verá algumas das informações associadas a essa VM.
  
**Tempo estimado**: 45 minutos

### Tarefa 1

Nesta tarefa, você verá alguns dos parâmetros associados à VM que foi criada para uso com este laboratório.

1. Abra o Microsoft Edge.  Na barra de endereços, insira **https://portal.azure.com** .

1. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira o nome de usuário fornecido pelo provedor de hospedagem do laboratório e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Dependendo do host do laboratório e se esta for a primeira vez que você está fazendo logon no locatário, pode ser que seja solicitado a concluir o processo de registro de MFA. Se este for o caso, siga as instruções na tela para configurar a MFA.

1. Na parte superior da página, abaixo de Serviços do Azure, selecione **Máquinas Virtuais**.  Se essa opção não estiver listada, na caixa de pesquisa, na barra azul na parte superior da página ao lado de Microsoft Azure, insira **Máquinas Virtuais** e selecione **Máquinas Virtuais** nos resultados da pesquisa.

1. Na página Máquinas virtuais, selecione a VM listada **SC900-WinVM**.

1. Agora você está na página da SC900-WinVM.  Anote algumas das informações básicas sobre a VM.

1. No painel de navegação à esquerda, expanda **Rede** e selecionet **Configurações de Rede**.  As seções essenciais da janela principal mostram a interface de rede para a VM.  Observe como não há algo listado ao lado do grupo de segurança de rede, pois não há NSG atribuído à interface.

1. Mantenha essa guia aberta.

### Tarefa 2

Nesta tarefa, você criará um grupo de segurança de rede, atribuirá o adaptador de rede da VM a esse NSG e criará uma regra de entrada para o tráfego RDP.

1. Na guia Azure aberta, *clique com o botão direito do mouse* no link **Página Inicial** na parte superior da página e selecione **Abrir link na nova guia** para abrir outra página nos serviços do Azure.

1. Na barra de pesquisa azul na parte superior da página, insira **Grupos de segurança de rede** e, nos resultados, escolha **Grupos de segurança de rede**. Não selecione *Grupos de segurança de rede (clássico)* .

1. No centro da página, selecione o botão azul denominado **Criar grupo de segurança de rede**.  Como alternativa, você pode selecionar **+ Criar** na parte superior da página Grupos de segurança de rede.

1. Na guia Noções básicas da página Criar grupo de segurança de rede, especifique as seguintes configurações:
    1. Assinatura: mantenha o valor padrão (essa é a assinatura do Azure fornecida pelo hoster do laboratório autorizado)
    1. Grupo de recursos: **LabsSC900**
    1. Nome:  **NSG-SC900**
    1. Região:  mantenha o valor padrão.
    1. Selecione **Revisar + criar** e **Criar**.

1. Após a conclusão da implantação, selecione **Ir para o recurso**.

1. Você deve estar na página de visão geral do NSG recém-criado.  Caso contrário, no painel de navegação esquerdo, selecione **Visão geral**. Na parte superior da página Informações Gerais, você verá algumas informações básicas sobre o NSG que criou.  Dois pontos a serem observados são que não há regras de segurança personalizada e que não há sub-redes nem adaptadores de rede associados a esse NSG.  Embora não haja regras de segurança personalizadas, há regras de entrada e de saída padrão incluídas em cada NSG, conforme mostrado na página.  Revise as regras de entrada e de saída. As regras de entrada padrão negam todo o tráfego de entrada que não é de uma rede virtual ou de um balanceador de carga do Azure.  As regras de saída negam todo o tráfego de saída, exceto o tráfego entre as redes virtuais e o tráfego de saída para a Internet.

1. No painel de navegação à esquerda, na página NSG-SC900, expanda **Configurações** e selecione **Interfaces de rede**.
    1. Selecione **Associar**.
    2. No campo de associações do adaptador de rede, selecione a **seta para baixo**, **sc900-winvmXXX e** **OK** na parte inferior da janela. Uma vez que a interface é associada ao NSG, ela aparecerá na lista.  O NSG agora é atribuído à interface de rede da sua VM.

1. Volte para a guia **SC900-WinWM – Microsoft Azure** no navegador.  Atualize a página. Ao lado de Grupo de segurança de rede, você agora deve ver o nome do NSG que você acabou de criar.  Se você ainda não vê-lo, aguarde mais um minuto e, em seguida, atualize a página novamente.

1. No painel de navegação esquerdo, selecione **Conectar**. Na janela principal, ao lado de onde mostra o número da porta 3389, selecione **Verificar acesso**. A função de verificação de acesso envia sinais (tráfego) para a porta RDP padrão 3389 da VM para verificar se ela está acessível. Pode demorar um minuto, mas você verá Não acessível.  Isso é esperado, porque a regra DenyAllInBound NSG nega todo o tráfego de entrada para a VM.

1. Volte para a guia **NSG-SC900 – Microsoft Azure** no navegador.

1. No painel de navegação esquerdo, selecione **Regras de segurança de entrada**. As regras de entrada padrão negam todo o tráfego de entrada que não é de uma rede virtual ou de um balanceador de carga do Azure, ou seja, você precisa configurar uma regra para permitir o tráfego RDP de entrada (tráfego na porta 3389). Lembre-se de que não é possível remover as regras padrão, mas você pode substituí-las criando regras com prioridades mais altas.

1. Na parte superior da página, selecione **Adicionar**. Na janela Adicionar regra de segurança de entrada, especifique as seguintes configurações:
    1. Origem: **Qualquer**
    1. Intervalos de portas de origem: **\***
    1. Destino: **Qualquer**
    1. Serviço: **RDP**
    1. Ação: **Permitir**
    1. Prioridade: **1000**. As regras com números menores têm maior prioridade e são processadas primeiro.
    1. Nome: mantenha o nome padrão ou crie um nome descritivo próprio.
    1. Observe o sinal de aviso na parte inferior da página.  Estamos usando o RDP apenas para fins de teste e para demonstrar a funcionalidade do NSG.
    1. Selecione **Adicionar**

1. Depois que a regra for provisionada, ela aparecerá na lista de regras de entrada (talvez seja necessário atualizar a tela).

1. Deixe esta guia do navegador aberta.  

### Tarefa 3

Nesta tarefa, você testará a regra NSG de entrada recém-criada para confirmar se você pode estabelecer uma conexão RDP (área de trabalho remota) com a VM.  Quando estiver na VM, você vai trabalhar para verificar a conectividade de saída com a Internet na VM.

1. Abra a guia SC900-WinVM – Microsoft Azure no navegador.

1. No painel de navegação à esquerda, selecione **Conectar**.

1. Selecione **Verificar acesso** (verifique se a porta está definida como 3389).  O status será exibido como “Acessível”.  Se você ainda estiver vendo "Não acessível", atualize a página e tente novamente. Pode levar alguns minutos para que a nova regra de entrada seja vista pela opção de verificação de acesso.

1. Agora se conecte diretamente à VM clicando em **Selecionar** na caixa RDP nativo.
   
    1. Na janela RDP nativo que será aberta, selecione **Baixar arquivo RDP**.
    1. Se um aviso de download for exibido, selecione **Manter** e, na janela pop-up exibida, selecione **Abrir arquivo**.
    1. Uma janela da conexão da Área de Trabalho Remota será aberta. Selecione **Conectar**.
    1. Suas credenciais serão solicitadas.  Insira o nome de usuário e a senha da VM (consulte a guia Recursos no painel de instruções do laboratório).
    1. Uma janela da conexão da Área de Trabalho Remota será aberta indicando: *Não foi possível verificar a identidade do computador remoto. Deseja se conectar mesmo assim?*  Selecione **Sim**.

1. Agora você está conectado à VM. Neste caso, você conseguiu se conectar à VM porque a regra de tráfego de entrada criada permite o tráfego de entrada para a VM via RDP.  Após alguns segundos na tela de boas-vindas, talvez você veja uma janela para escolher as configurações de privacidade para seu dispositivo. Selecione **Aceitar**.  Se a janela Redes for exibida, selecione **Não**.

1. Com a VM na sessão do RDP em execução, teste a conectividade de saída com a Internet na VM.
    1. Na VM aberta, selecione **Microsoft Edge** para abrir o navegador. Como esta é a primeira vez que você está abrindo a VM e o navegador, pode ser solicitado que você faça algumas configurações básicas.  
    1. Pode ser solicitado que você escolha configurações de privacidade para o seu dispositivo. Deixe o que for padrão e clique em **Aceitar**.  
    1. Um painel lateral de Redes poderá ser exibido.  Selecione **Não**.
    1. Pode aparecer uma janela que diz "Navegue na web com o navegador de melhor desempenho no Windows". Clique em **Continuar**, **Iniciar sem seus dados**, **Confirmar e continuar**, **Continuar sem esses dados** e, por último, **Confirmar e começar a navegar**.
    1. Insira **www.bing.com** na barra de endereços e confirme se é possível se conectar ao mecanismo de pesquisa.
    1. Depois de confirmar se consegue acessar www.bing.com, feche a janela do navegador na VM, mas mantenha a VM ativa.

1. Minimize a VM selecionando o sublinhado **_** na guia azul que mostra o endereço IP da VM. Isso levará você novamente à página SC900-WinVM \| Conectar.

1. Mantenha a guia do navegador aberta, pois você vai usá-la na próxima tarefa.

### Tarefa 4

Na tarefa anterior, você confirmou que podia estabelecer uma conexão RDP com a VM. Quando estava na VM, você também confirmou se podia estabelecer uma conexão de saída com a Internet.  O tráfego de saída da Internet foi permitido porque as regras de saída padrão do NSG permitem o tráfego de saída da Internet.  Nesta tarefa, você vai percorrer o processo de criação de uma regra de saída personalizada para bloquear o tráfego de saída da Internet e testar essa regra.

1. Você estará na página SC900-WinVM \| Conectar. No painel de navegação à esquerda, selecione **Rede**. Se você fechou anteriormente a guia do navegador, selecione a barra de pesquisa azul na parte superior da página, escolha Máquinas virtuais, a VM, **SC900-WinVM**, e **Rede**.

1. Selecione a guia **Regras da porta de saída**. Você encontrará as regras de saída padrão.  Observe a regra padrão "AllowInternetOutBound". Essa regra permite qualquer tráfego de saída da Internet. Não é possível remover as regras padrão, mas você pode substituí-las criando regras com prioridades mais altas. No lado direito da página, selecione **+Criar regra de porta** e, na lista suspensa, selecione **Regra de porta de saída**.

1. Na página Adicionar regra de segurança de saída, especifique as seguintes configurações:
    1. Origem: **Qualquer**
    1. Intervalos de portas de origem:  **\***
    1. Destino: **Marca de Serviço**
    1. Marca de serviço de destino: **Internet**
    1. Serviço: **Personalizado** (deixe o padrão)
    1. Intervalos da porta de destino: **\*** (coloque um asterisco no campo dos intervalos da porta de destino)
    1. Protocolo: **Qualquer**
    1. Ação: **Negar**
    1. Prioridade: **1000**
    1. Nome: mantenha o nome padrão ou crie um nome descritivo próprio.
    1. Selecione **Adicionar**

1. Uma vez que a regra for provisionada, ela aparecerá na lista de regras de saída.  Embora ela apareça na lista, levará alguns minutos para entrar em vigor (aguarde alguns minutos antes de continuar com as próximas etapas).  


1. Volte à VM (o ícone do RDP da VM será mostrado na barra de tarefas na parte inferior da página).

1. Abra o navegador Microsoft Edge na VM e insira **www.bing.com**. Essa página não deve ser exibida. Se você consegue se conectar à Internet e verificou que todos os parâmetros da regra de saída foram configurados corretamente, isso ocorre porque são necessários alguns minutos para que a regra entre em vigor.  Feche o navegador, aguarde alguns minutos e tente novamente. As assinaturas do Azure no ambiente de laboratório podem enfrentar atrasos mais longos do que o normal.

1. Feche a conexão da Área de Trabalho Remota, selecionando o **X** no centro superior da página onde o endereço IP é mostrado.  Será exibida uma janela pop-up, indicando que a sessão remota será desconectada. Selecione **OK**.

1. No canto superior esquerdo da janela, logo abaixo da barra azul indicando Microsoft Azure, selecione **Página Inicial** para voltar à home page dos serviços do Azure.

1. Mantenha a guia do Azure aberta no seu navegador.

### Revisão

Neste laboratório, você percorreu o processo de configuração de um NSG (grupo de segurança de rede) associando o NSG ao adaptador de rede de uma máquina virtual e adicionando novas regras ao NSG para permitir o tráfego RDP de entrada e bloquear o tráfego de saída da Internet.
