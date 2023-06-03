<a name="---"></a><!---
---
Demonstração: Título: 'NSGs (Grupos de Segurança de Rede do Azure)' Roteiro de aprendizagem/Módulo/Unidade: 'Roteiro de aprendizagem: descrever as funcionalidades das soluções de segurança da Microsoft; Módulo 1: descrever as funcionalidades básicas de segurança no Azure; Unidade 6: descrever os grupos da Segurança de Rede do Azure'
---
--->

# <a name="demo-azure-network-security-groups-nsgs"></a>Demonstração: Grupos de Segurança de Rede (NSGs) do Azure

Essa demonstração é mapeada para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades da solução de segurança da Microsoft
- Módulo: descrever as funcionalidades básicas de segurança no Azure
- Unidade: descrever grupos de segurança de rede do Azure

## <a name="demo-scenario"></a>Cenário da demonstração

Nesta demonstração, você vai explorar a função dos grupos de segurança de rede no Azure e aplicar um NSG a uma máquina virtual criada previamente. Você começará mostrando brevemente as informações sobre a VM que foi criada previamente pelo ALH (hoster do laboratório autorizado). Em seguida, você vai mostrar o processo de criação do NSG, apresentar as regras de entrada e de saída padrão, criar uma regra RDP para permitir a conexão com a VM e testá-la.

### <a name="demo-part-1"></a>Demonstração parte 1

Nesta parte, você verá alguns dos parâmetros associados à VM que foi criada para uso com este laboratório.

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

### <a name="demo-part-2"></a>Demonstração – Parte 2

Nesta parte, você criará um grupo de segurança de rede, atribuirá o adaptador de rede da VM ao NSG e criará uma regra de entrada para o tráfego RDP.

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

1. Na parte superior da página Informações Gerais, você verá algumas informações básicas sobre o NSG que criou.  Dois pontos a serem observados são que não há regras de segurança PERSONALIZADA e que não há sub-redes nem adaptadores de rede associados a esse NSG.  Embora não haja regras de segurança personalizadas, há regras de entrada e de saída padrão incluídas em cada NSG, conforme mostrado na página.  Revise as regras de entrada e de saída. As regras de entrada padrão negam todo o tráfego de entrada que não é de uma rede virtual ou de um balanceador de carga do Azure.  As regras de saída negam todo o tráfego de saída, exceto o tráfego entre as redes virtuais e o tráfego de saída para a Internet.

1. No painel de navegação à esquerda, na página NSG-SC900, em Configurações, selecione **Adaptadores de rede**.
    1. Selecione **Associar**.
    1. No campo de seleção das associações do adaptador de rede, selecione a **seta para baixo**, **sc900-winvmXXX** e **OK** na parte inferior da janela. Quando o adaptador tiver sido associado ao NSG, ele vai aparecer no topo da lista.

1. No painel de navegação esquerdo, selecione **Regras de segurança de entrada**. As regras de entrada padrão negam todo o tráfego de entrada que não é de uma rede virtual ou de um balanceador de carga do Azure, ou seja, você precisa configurar uma regra para permitir o tráfego RDP de entrada (tráfego na porta 3389). Lembre-se de que não é possível remover as regras padrão, mas você pode substituí-las criando regras com prioridades mais altas.

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

1. Depois que a regra for provisionada, ela aparecerá na lista de regras de entrada (talvez seja necessário atualizar a tela). Na regra recém-adicionada, você verá um sinal de aviso.  Conforme mencionado acima, estamos usando o RDP apenas para fins de teste e para demonstrar a funcionalidade do NSG.

### <a name="demo-part-3"></a>Demonstração – Parte 3

Com o NSG criado e associado à sua VM e à regra RDP criada, você mostrará o impacto do NSG testando a conectividade RDP com a VM.

1. Abra a guia SC900-WinVM – Microsoft Azure no seu navegador. Se você fechou anteriormente a guia do navegador, selecione a barra de pesquisa azul na parte superior da página, escolha Máquinas virtuais e selecione a VM, **SC900-WinVM**.

1. Teste a regra de entrada verificando se você pode se conectar à VM usando RDP.
    1. Selecione **Soluções**, à esquerda no painel de navegação.
    1. Verifique se o endereço IP está configurado como Endereço IP público, deixe o número da porta como padrão e selecione **Baixar arquivo DRP**.
    1. **Abra** o arquivo baixado e selecione **Conectar**.
    1. Suas credenciais serão solicitadas. Insira o nome de usuário e a senha que você usou quando criou a VM.  Se a janela que solicita suas credenciais solicitar um PIN, selecione **Mais opções** e selecione **Usar uma conta diferente**.
    1. Vai aparecer uma janela para conectar a Área de Trabalho Remota dizendo “Não foi possível verificar a identidade do computador remoto. Deseja conectar mesmo assim?” Selecione **Sim**.
    1. Agora você está conectado à VM. Destaque para o aluno que, neste caso, você conseguiu se conectar à VM porque a regra de tráfego de entrada criada permite o tráfego de entrada para a VM via RDP.

1. Como você já está na VM, pode mostrar a conectividade de saída da Internet com a Internet, que é habilitada por uma das regras de saída padrão.
    1. Na VM, selecione **Microsoft Edge** para abrir o navegador.  Como esta é a primeira vez que você abre o Microsoft Edge, talvez você veja uma janela pop-up. Selecione **Iniciar sem os seus dados**, **Continuar sem esses dados** e **Confirmar e iniciar a navegação**.
    1. Insira **www.bing.com** na barra de endereços e confirme se é possível se conectar ao mecanismo de pesquisa.
    1. Depois de confirmar se consegue acessar www.bing.com, feche a janela do navegador na VM, mas mantenha a VM ativa.

1. Minimize a VM selecionando o sublinhado **_** na guia azul que mostra o endereço IP da VM. Isso levará você novamente à página SC900-WinVM | Conectar.  

### <a name="optional-demo-part-4"></a>OPCIONAL Demonstração – Parte 4

Se o tempo de sala de aula permitir, o ideal é criar uma regra de NSG de saída para bloquear o tráfego de saída da Internet na VM.

1. No painel de navegação à esquerda, selecione **Rede**. Você estará na página SC900-WinVM | Rede.

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

1. Como melhor prática geral, é útil parar ou destruir a VM para evitar a geração de custos, se ela está sendo usada apenas para fins de demonstração ou de teste. Nesse caso, no entanto, NÃO destrua a VM, pois ela ajudará a alimentar os dados de gerenciamento da postura de segurança da nuvem na demonstração do Microsoft Defender para Nuvem.  A VM será destruída quando o laboratório for cancelado.

#### <a name="review"></a>Revisão

Nesta demonstração, você mostrou as informações e as configurações associadas a um NSG, incluindo o processo para associar uma interface ao NSG, mostrou as regras padrão de entrada e de saída e, por fim, as etapas necessárias para criar uma regra.
