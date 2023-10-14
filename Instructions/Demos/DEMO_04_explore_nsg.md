<!---
---
Demonstração: Título: 'NSGs (Grupos de Segurança de Rede do Azure)' Roteiro de aprendizagem/Módulo/Unidade: 'Roteiro de aprendizagem: descrever as funcionalidades das soluções de segurança da Microsoft; Módulo 1: descrever as funcionalidades básicas de segurança no Azure; Unidade 6: descrever os grupos da Segurança de Rede do Azure'
---
--->

# Demonstração: Grupos de Segurança de Rede (NSGs) do Azure

Essa demonstração é mapeada para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades da solução de segurança da Microsoft
- Módulo: descrever as funcionalidades básicas de segurança no Azure
- Unidade: descrever grupos de segurança de rede do Azure

## Cenário da demonstração

Nesta demonstração, você vai explorar a função dos grupos de segurança de rede no Azure e aplicar um NSG a uma máquina virtual criada previamente. Você começará mostrando brevemente as informações sobre a VM que foi criada previamente pelo ALH (hoster do laboratório autorizado). Em seguida, utilizando um NSG configurado como parte da configuração da pré-demonstração, você mostrará os parâmetros essenciais de um NSG e as regras padrão de entrada e saída. Você atribuirá uma interface de VM ao NSG, criará uma nova regra de protocolo RDP para permitir a conexão com a VM e, por fim, deverá testá-la.

### Demonstração parte 1

Nesta parte, você exibirá alguns dos parâmetros associados à VM criada como parte da demonstração de instalação (DEMO_00_pre_demo_setup.md).

1. Abra o Microsoft Edge.  Na barra de endereços, insira **https://portal.azure.com** e entre com as credenciais do Azure fornecidas pelo hoster de laboratório autorizado (ALH).  Isso o levará você à página inicial dos serviços do Azure.

1. Na caixa de pesquisa azul na parte superior da página, insira **Máquinas Virtuais** e selecione **Máquinas Virtuais** nos resultados da pesquisa.

1. Na página Máquinas virtuais, selecione a VM listada **SC900-WinVM**.  Essa VM deveria ter sido criada como parte da configuração da pré-demonstração.  Se não estiver listado, crie-o agora.

1. Agora você está na página da SC900-WinVM.  Anote algumas das informações básicas sobre a VM.

1. No painel de navegação à esquerda, selecione **Rede**.  
    1. A exibição padrão destina-se às regras de porta de entrada.  Observe que o adaptador de rede dessa VM não tem grupos de segurança de rede configurados.  O mesmo será verdadeiro se você selecionar Regras de porta de saída.
    1. Selecione **Regras de segurança efetivas** ao lado de Adaptador de rede.  Observe a mensagem: "Nenhum grupo de segurança de rede ou grupo de segurança de aplicativos está associado ao adaptador de rede".

1. Observação para o apresentador: se você tentar verificar o status da porta na página de conexão, receberá a mensagem "Não é possível verificar".  Isso não significa necessariamente que as portas não estejam expostas.  Como você observará, ao executar a mesma ação com o NSG atribuído, você obterá a mensagem "Não acessível", indicando que o tráfego nessa porta está bloqueado.


1. Deixe esta guia do navegador aberta.

### Demonstração – Parte 2

Nesta parte, você atribuirá uma interface ao NSG e falará sobre as regras padrão de entrada e saída, mostrando como as regras funcionam.  Como parte da configuração de pré-demonstraçã, uma VM deve atribuir a interface de rede da VM a esse NSG e criar uma nova regra de entrada para o tráfego do protocolo RDP.

1. Abra uma nova guia do navegador no portal do Microsoft Azure (portal.azure.com) e, na barra de pesquisa azul na parte superior da página, insira os grupos **Grupos de segurança de rede**. Nos resultados, selecione **Grupos de segurança de rede** (não selecione Grupos de segurança de rede clássicos).

1. Selecione o NSG criado como parte da configuração pré-demonstração. Se você não o criou previamente, faça-o agora. Selecione **Criar grupo de segurança de rede** e especifique as seguintes configurações:
    1. Assinatura: mantenha o valor padrão (essa é a assinatura do Azure fornecida pelo hoster do laboratório autorizado)
    1. Grupo de recursos:  **LabsSC900** (o mesmo grupo de recursos utilizado pela VM).
    1. Nome:  **NSG-SC900**
    1. Região:  mantenha o valor padrão.
    1. Selecione **Revisar + criar** e depois **Criar**.
    1. Uma vez concluída a implantação (isso acontece muito rapidamente), selecione **Ir para o recurso**.

1. Na parte superior da página Informações Gerais, você verá algumas informações básicas sobre o NSG que criou.  Dois pontos a serem observados são que não há regras de segurança PERSONALIZADA e que não há sub-redes nem adaptadores de rede associados a esse NSG.  Embora não haja regras de segurança personalizadas, há regras de entrada e de saída padrão incluídas em cada NSG, conforme mostrado na página.  Revise as regras de entrada e de saída. As regras de entrada padrão negam todo o tráfego de entrada que não é de uma rede virtual ou de um balanceador de carga do Azure.  As regras de saída negam todo o tráfego de saída, exceto o tráfego entre as redes virtuais e o tráfego de saída para a Internet.

1. No painel de navegação à esquerda, na página NSG-SC900, em Configurações, selecione **Adaptadores de rede**.
    1. Selecione **Associar**.
    1. No campo de seleção das associações do adaptador de rede, selecione a **seta para baixo**, **sc900-winvmXXX** e **OK** na parte inferior da janela. Quando o adaptador tiver sido associado ao NSG, ele vai aparecer no topo da lista.

1. Retorne a VM selecionando a guia do navegador para a VM.  Você verá que agora existe um NSG anexado à interface da VM.  A tabela de regras da porta de entrada é exibida. As regras de entrada padrão negam todo o tráfego de entrada que não é de uma rede virtual ou de um balanceador de carga do Azure.  Para testar isso, você deve verificar o status da porta do protocolo RDP, 3389.
    1. Na parte superior da página, selecione **Conectar** e, em seguida, **Verificar acesso** para a porta 3389 (RDP); você verá a mensagem "Não acessível".  
    1. Embora você esteja testando apenas a porta 3389 do protocolo RDP, todo o tráfego de rede de entrada que não seja de outra rede virtual ou balanceador de carga está bloqueado.  

1. Agora você criará uma regra para permitir o tráfego de entrada na porta do protocolo RDP.  No painel de navegação à esquerda, selecione **Rede**. A tabela Regras de porta de entrada será exibida (a guia Regras de porta de entrada está sublinhada).  No lado direito da página, selecione **Adicionar regra de porta de entrada**. Um ponto importante a ser chamado a atenção é que você não pode remover as regras padrão, mas pode substituí-las criando regras com prioridades mais altas. Na janela Adicionar regra de segurança de entrada, especifique as seguintes configurações:
    1. Fonte:  **Qualquer**
    1. Intervalos de portas de origem: **\***
    1. Destino:  **Qualquer**
    1. Serviço:  **RDP**
    1. Ação:  **Permitir**
    1. Prioridade: **1000**. Observação: as regras com números menores têm maior prioridade e são processadas primeiro.
    1. Nome: mantenha o nome padrão ou crie um nome descritivo próprio.
    1. Observe o sinal de aviso na parte inferior da página.  Estamos usando o RDP apenas para fins de teste e para demonstrar a funcionalidade do NSG.
    1. Selecione **Adicionar**

1. Depois que a regra for provisionada, ela aparecerá na lista de regras de entrada (talvez seja necessário atualizar a tela).

### Demonstração – Parte 3

Com o NSG  associado à sua VM e a regra RDP criada, você mostrará o impacto do NSG testando a conectividade do RDP com a VM.

1. Abra a guia SC900-WinVM – Microsoft Azure no seu navegador. 

1. Selecione **Soluções**, à esquerda no painel de navegação.
    1. Você pode simplesmente selecionar **verificar acesso**.  O status deve ser mostrado como "Acessível". Alternativamente, se você tiver tempo, poderá conectar-se à VM abrindo uma instância da Conexão de Área de Trabalho Remota no Windows.  Essa opção abrirá a VM ao conectar-se a ela com êxito.  Abaixo estão listadas as etapas:
        1. Na barra de pesquisa do Windows, insira **Conexão de área de trabalho remota** e selecione **Abrir**.
        1. No campo em que está escrito **Computador**, insira o endereço IP público da sua VM.
        1. Uma vez inserido o endereço IP, o nome do usuário deve aparecer abaixo do campo em que foi inserido o endereço IP. Caso contrário, expanda **Mostrar Opções** e insira o nome de usuário da sua VM e selecione **Conectar**.
        1. Vai aparecer uma janela para conectar a Área de Trabalho Remota dizendo “Não foi possível verificar a identidade do computador remoto. Deseja conectar mesmo assim?” Selecione **Sim**.
        1. Agora você está conectado à VM. Destaque para o aluno que, neste caso, você conseguiu se conectar à VM porque a regra de tráfego de entrada criada permite o tráfego de entrada para a VM via RDP.
        1. Minimize a VM selecionando o sublinhado **_** na guia azul que mostra o endereço IP da VM. Isso levará você novamente à página SC900-WinVM | Conectar.

1. No painel de navegação à esquerda, selecione **Rede de trabalho** e, na janela principal, selecione **Regras da portas de saída**.  Fale com as regras de saída padrão. As regras padrão permitem o tráfego de saída da VNet de qualquer rede virtual para qualquer outra rede virtual e permitem o tráfego de saída da Internet. Qualquer outro tipo de tráfego de saída é negado.  Você não pode remover a regra padrão, mas pode substituí-la criando uma regra com prioridade mais alta da mesma forma que você criou uma regra de entrada.

1. Se o seu temporizador permitir e você quiser mostrar etapas semelhantes para o tráfego de saída, acesse a parte de demonstração opcional listada abaixo.  Caso contrário, saia da VM, mas mantenha a guia Azure aberta no seu navegador para a próxima demonstração.

### OPCIONAL Demonstração – Parte 4

Nesta parte, você mostrará que as regras de saída atuais do NSG permitem o tráfego de saída da Internet a partir da VM.  Em seguida, você criará uma regra para bloquear o tráfego de saída da Internet a partir da VM. Por fim, você mostrará o impacto da regra recém-criada tentando acessar a Internet a partir da VM.

1. Abra a VM que você minimizou na etapa anterior. Aqui você mostrará a conectividade de saída com a Internet, que está habilitada por uma das regras de saída padrão. Uma vez que a VM for aberta e você tiver feito logon como usuário, selecione **Microsoft Edge** para abrir o navegador.  Como esta é a primeira vez que você abre o Microsoft Edge, talvez você veja uma janela pop-up. Selecione **Iniciar sem os seus dados**, **Continuar sem esses dados** e **Confirmar e iniciar a navegação**.
    1. Insira **www.bing.com** na barra de endereços e confirme se é possível se conectar ao mecanismo de pesquisa.
    1. Depois de confirmar se consegue acessar www.bing.com, feche a janela do navegador na VM, mas mantenha a VM ativa.

1. Minimize a VM selecionando o sublinhado **_** na guia azul que mostra o endereço IP da VM. Isso levará você novamente à página SC900-WinVM | Conectar.  

1. No painel de navegação à esquerda, selecione **Rede**.

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

1. Mantenha a guia Azure aberta em seu navegador para a próxima demonstração do Azure.

### Revisão

Nesta demonstração, você mostrou as informações e as configurações associadas a um NSG, incluindo o processo para associar uma interface ao NSG, mostrou as regras padrão de entrada e de saída e, por fim, as etapas necessárias para criar uma regra.
