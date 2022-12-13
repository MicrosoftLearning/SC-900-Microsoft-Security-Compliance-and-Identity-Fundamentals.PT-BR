<a name="---"></a><!---
---
Laboratório: Título: 'Explorar NSGs (Grupos de Segurança de Rede do Azure)' Roteiro de Aprendizagem/Módulo/Unidade: 'Roteiro de aprendizagem: descrever as funcionalidades das soluções de segurança da Microsoft; Módulo 1: descrever as funcionalidades básicas de segurança no Azure; Unidade 6: Descrever grupos de Segurança de Rede do Azure'
---
--->

# <a name="lab-explore-azure-network-security-groups-nsgs"></a>Laboratório: Explore os Grupos de Segurança de Rede (NSGs) do Azure

Esse laboratório é mapeado para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades da solução de segurança da Microsoft
- Módulo: descrever as funcionalidades básicas de segurança no Azure
- Unidade: descrever grupos de segurança de rede do Azure

## <a name="lab-scenario"></a>Cenário do laboratório

Neste laboratório, você vai explorar a função dos grupos de segurança de rede no Azure.  Você fará isso criando um NSG (grupo de segurança de rede) e atribuindo o NSG à interface de uma VM (máquina virtual) pré-existente.  Após a configuração, você vai observar as regras de entrada e de saída padrão, criar regras e testá-las.  Neste laboratório, a VM que você usará com o NSG será criada para você, ou seja, primeiro, você verá algumas das informações associadas a essa VM.
  
**Tempo estimado**: 30 a 45 minutos

### <a name="task-1"></a>Tarefa 1:

Nesta tarefa, você verá alguns dos parâmetros associados à VM que foi criada para uso com este laboratório.

1. Abra o Microsoft Edge.  Na barra de endereços, insira **portal.azure.com**.

1. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira o nome de usuário fornecido pelo provedor de hospedagem do laboratório e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Se for exibida uma mensagem perguntando se você deseja permanecer conectado, selecione **Sim**.

1. Na parte superior da página, abaixo de Serviços do Azure, selecione **Máquinas Virtuais**.  Se essa opção não estiver listada, na caixa de pesquisa, na barra azul na parte superior da página ao lado de Microsoft Azure, insira **Máquinas Virtuais** e selecione **Máquinas Virtuais** nos resultados da pesquisa.

1. Na página Máquinas virtuais, selecione a VM listada **SC900-WinVM**.

1. Agora você está na página da SC900-WinVM.  Observe o nome do grupo de recursos, LabsSC900, no qual a VM se encontra.

1. No topo da página, selecione **Conectar** e depois **RDP** no menu suspenso. Observe que o pré-requisito de porta não é atendido.  Para atender ao pré-requisito, uma regra de segurança de rede de entrada com a porta de destino 3389, usada pelo RDP, deve ser configurada.  Você fará isso na próxima tarefa, quando criar um grupo de segurança de rede.

1. No painel de navegação à esquerda, selecione **Rede**.  
    1. A exibição padrão destina-se às regras de porta de entrada.  Observe que o adaptador de rede dessa VM não tem grupos de segurança de rede configurados.  O mesmo será verdadeiro se você selecionar Regras de porta de saída.
    1. Selecione **Regras de segurança efetivas** ao lado de Adaptador de rede.  Observe a mensagem: "Nenhum grupo de segurança de rede ou grupo de segurança de aplicativos está associado ao adaptador de rede".
1. Deixe esta guia do navegador aberta.

### <a name="task-2"></a>Tarefa 2:

Nesta tarefa, você criará um grupo de segurança de rede, atribuirá o adaptador de rede da VM a esse NSG e criará uma regra de entrada para o tráfego RDP.

1. Abra a guia SC900-WinVM – Microsoft Azure no seu navegador.

1. Na barra de pesquisa azul na parte superior da página, insira **Grupos de segurança de rede**. Nos resultados, selecione **Grupos de segurança de rede** (não selecione Grupos de segurança de rede clássicos).

1. No topo da página Grupos de segurança de rede, selecione **+Criar**.

1. Na guia Básico da página Criar grupo de segurança de rede, especifique as seguintes configurações:
    1. Assinatura: mantenha o valor padrão (essa é a assinatura do Azure fornecida pelo hoster do laboratório autorizado)
    1. Grupo de recursos:  **LabsSC900**
    1. Nome:  **NSG-SC900**
    1. Região:  mantenha o valor padrão.
    1. Selecione **Revisar + criar** e depois **Criar**.

1. Após a conclusão da implantação, selecione **Ir para o recurso**.

1. Na parte superior da página Informações Gerais, você verá algumas informações básicas sobre o NSG que criou.  Dois pontos a serem observados são que não há regras de segurança personalizada e que não há sub-redes nem adaptadores de rede associados a esse NSG.  Embora não haja regras de segurança personalizadas, há regras de entrada e de saída padrão incluídas em cada NSG, conforme mostrado na página.  Revise as regras de entrada e de saída. As regras de entrada padrão negam todo o tráfego de entrada que não é de uma rede virtual ou de um balanceador de carga do Azure.  As regras de saída negam todo o tráfego de saída, exceto o tráfego entre as redes virtuais e o tráfego de saída para a Internet.

1. À esquerda no painel de navegação, na página NSG-SC900, em Configurações, selecione **Adaptadores de rede**.
    1. Selecione **Associar**.
    2. No campo de associações do adaptador de rede, selecione a **seta para baixo**, **sc900-winvmXXX e** **OK** na parte inferior da janela. Quando o adaptador tiver sido associado ao NSG, ele vai aparecer no topo da lista.

1. No painel de navegação esquerdo, selecione **Regras de segurança de entrada**.

1. As regras de entrada padrão negam todo o tráfego de entrada que não é de uma rede virtual ou de um balanceador de carga do Azure, ou seja, você precisa configurar uma regra para permitir o tráfego RDP de entrada (tráfego na porta 3389). Lembre-se de que não é possível remover as regras padrão, mas você pode substituí-las criando regras com prioridades mais altas.

1. Na parte superior da página, selecione **Adicionar**. Na janela Adicionar regra de segurança de entrada, especifique as seguintes configurações:
    1. Fonte:  **Qualquer**
    1. Intervalos de portas de origem: **\***
    1. Destino:  **Qualquer**
    1. Serviço:  **RDP**
    1. Ação:  **Permitir**
    1. Prioridade: **1000**. Observação: as regras com números menores têm maior prioridade e são processadas primeiro.
    1. Nome: mantenha o nome padrão ou crie um nome descritivo próprio.
    1. Observe o sinal de aviso na parte inferior da página.  Estamos usando o RDP apenas para fins de teste e para demonstrar a funcionalidade do NSG.
    1. Selecione **Adicionar**

1. Depois que a regra for provisionada, ela aparecerá na lista de regras de entrada (talvez seja necessário atualizar a tela). Na regra recém-adicionada, você verá um sinal de aviso.  Conforme indicado acima, estamos usando o RDP apenas para fins de teste e para demonstrar a funcionalidade do NSG. Selecione a regra recém-adicionada.

### <a name="task-3"></a>Tarefa 3

Nesta tarefa, você testará a regra NSG de entrada recém-criada para confirmar se você pode estabelecer uma conexão RDP (área de trabalho remota) com a VM.  Quando estiver na VM, você trabalhará para verificar a conectividade de saída com a Internet na VM.

1. Abra a guia SC900-WinVM – Microsoft Azure no seu navegador. Se você fechou anteriormente a guia do navegador, selecione a barra de pesquisa azul na parte superior da página, escolha Máquinas virtuais e selecione a VM, **SC900-WinVM**.

1. Na parte superior da página, selecione **Conectar** e **RDP**.

1. Verifique se o endereço IP está configurado como Endereço IP público, deixe o número da porta como padrão e selecione **Baixar arquivo DRP**.

1. Na janela pop-up exibida, selecione **Abrir arquivo**.

1. Uma janela da Conexão de Área de Trabalho Remota será aberta. Selecione **Conectar**.

1. Suas credenciais serão solicitadas.  Insira o nome de usuário e a senha (veja a guia Recursos no painel de instruções do laboratório).

1. Vai aparecer uma janela para conectar a Área de Trabalho Remota dizendo “Não foi possível verificar a identidade do computador remoto.  Deseja conectar mesmo assim?”  Selecione **Sim**.

1. Agora você está conectado à VM. Nesse caso, foi possível se conectar à VM porque a regra de tráfego de entrada que você criou permite o tráfego de entrada para a VM via RDP.

1. Após alguns segundos na tela Boas-vindas, você verá uma janela para escolher configurações de privacidade para seu dispositivo. Selecione **Aceitar**.  Na janela Redes, selecione **Não**.

1. Com a VM em execução, teste a conectividade de saída com a Internet na VM.
    1. Na VM, selecione **Microsoft Edge** para abrir o navegador.  Como esta é a primeira vez que você abre o Microsoft Edge, talvez você veja uma janela pop-up. Selecione **Iniciar sem os seus dados**, **Continuar sem esses dados** e **Confirmar e iniciar a navegação**.
    1. Insira **www.bing.com** na barra de endereços e confirme se é possível se conectar ao mecanismo de pesquisa.
    1. Depois de confirmar se consegue acessar www.bing.com, feche a janela do navegador na VM, mas mantenha a VM ativa.

1. Minimize a VM selecionando o sublinhado **_** na guia azul que mostra o endereço IP da VM. Isso levará você novamente à página SC900-WinVM | Conectar. 

1. No painel de navegação à esquerda, selecione **Rede**.

1. Mantenha a guia do navegador aberta, pois você vai usá-la na próxima tarefa.

### <a name="task-4"></a>Tarefa 4

Na tarefa anterior, você confirmou que podia estabelecer uma conexão RDP com a VM. Quando estava na VM, você também confirmou se podia estabelecer uma conexão de saída com a Internet.  O tráfego de saída da Internet foi permitido porque as regras de saída padrão do NSG permitem o tráfego de saída da Internet.  Nesta tarefa, você acompanhará o processo de criação de uma regra de saída personalizada para bloquear o tráfego de saída da Internet e testar essa regra.

1. Você estará na página SC900-WinVM | Rede. Se você fechou anteriormente a guia do navegador, selecione a barra de pesquisa azul na parte superior da página, escolha Máquinas virtuais, a VM, **SC900-WinVM**, e **Rede**.

1. Selecione a guia **Regras da porta de saída**. Você encontrará as regras de saída padrão.  Observe a regra padrão “PermitirSaídaDeInternet”. Essa regra permite qualquer tráfego de internet de saída. Não é possível remover a regra padrão, mas você pode substitui-la criando uma regra com prioridade mais alta. Do lado direito da página, selecione **Adicionar regra da porta de saída**.

1. Na página Adicionar regra de segurança de saída, especifique as seguintes configurações:
    1. Fonte:  **Qualquer**
    1. Intervalos de portas de origem:  **\***
    1. Destino:  **Marca de serviço**
    1. Marca de serviço de destino:  **Internet**
    1. Serviço:  **Personalizado** (mantenha o padrão)
    1. Intervalos de porta de destino: * (coloque um asterisco no campo dos intervalos de porta de destino)
    1. Protocolo: **Qualquer**
    1. Ação: **Negar**
    1. Prioridade: **1000**
    1. Nome: mantenha o nome padrão ou crie um nome descritivo próprio.
    1. Selecione **Adicionar**

1. Quando a regra for provisionada, ela vai aparecer na lista de regras de saída.  Embora ela apareça na lista, vai levar alguns minutos para ela funcionar (espere alguns minutos antes de ir para as próximas etapas).  

1. Volte à VM (o ícone da VM será mostrado na barra de tarefas na parte inferior da página).

1. Abra o navegador Microsoft Edge na VM e insira **www.bing.com**. A página não deve ser exibida.  Observação: se você conseguir se conectar à Internet mesmo verificando que todos os parâmetros da regra de saída foram configurados corretamente, isso é porque leva alguns minutos para que a regra entre em vigor.  Feche o navegador, espere alguns minutos e tente de novo.  Observação: as assinaturas do Azure no ambiente de laboratório podem enfrentar atrasos mais longos do que o normal.

1. Feche a conexão da área de trabalho remota selecionando o **X** na parte superior central da página, onde o endereço IP é exibido.  Será exibida uma janela pop-up, indicando que a sessão remota será desconectada. Selecione **OK**.

1. Feche todas as guias abertas do navegador.

### <a name="review"></a>Revisão

Neste laboratório, você percorreu o processo de configuração de um NSG (grupo de segurança de rede) associando o NSG ao adaptador de rede de uma máquina virtual e adicionando novas regras ao NSG para permitir o tráfego RDP de entrada e bloquear o tráfego de saída da Internet.
