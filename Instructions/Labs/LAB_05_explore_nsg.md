---
lab:
    title: 'Explorar os Grupos de Segurança de Rede (NSGs) do Azure'
    module: 'Módulo 3 Lição 1: Descrever as funcionalidades das soluções de segurança da Microsoft: Descrever recursos básicos de segurança do Azure.'
---


# Laboratório: Explorar os Grupos de Segurança de Rede (NSGs) do Azure.

## Visão geral do laboratório
Neste laboratório, vamos explorar a função dos grupos de segurança de rede no Azure.  Para isso, vamos criar uma VM sem nenhum grupo de segurança de rede (NSG).  Assim, sem nenhum NSG para filtrar o tráfego, todas as portas da VM ficam expostas à internet pública.  Então, você vai ter a experiência de criar um NSG e atribuir a interface da VM a esse NSG.  Após a configuração, vamos testar a conexão à VM usando as regras padrão de NSG e também as regras criadas por você.
  

**Tempo estimado**: 15-20 minutos

#### Tarefa 1:  Nesta tarefa, vamos criar uma máquina virtual Windows 10.    
1.	Abra o Microsoft Edge.  Na barra de endereços, insira **portal.azure.com**.

1. Entre com suas credenciais de administrador.
    1. Na janela de acesso, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (sendo ZZZZZZ o único ID de locatário fornecido pelo provedor de hospedagem do laboratório) e selecione **Avançar**.

    1. Insira sua senha de administrador fornecida pelo provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Ao receber um aviso do Microsoft Edge para permanecer conectado, selecione **Sim**.
1. No canto superior esquerdo da tela, perto de Microsoft Azure, selecione o ícone para mostrar o menu (as três linhas horizontais, também conhecidas como ícone de hambúrguer). Depois, selecione **Todos os Serviços**.  
1. Na janela principal, sob Em destaque, selecione Máquinas Virtuais.  Se você não encontrar Máquinas Virtuais na lista, insira o termo na barra de pesquisa e selecione a partir dos resultados exibidos.
1. No topo da página à esquerda, selecione **+Criar** e depois **+Máquina virtual**.
1. Na guia Básico, preencha as informações a seguir (para o que não estiver na lista, mantenha a configuração padrão):
    1. Assinatura: confirme se a configuração padrão é Azure Pass – Sponsorship.

    1. Grupo de recursos:  Selecione **Criar novo** e insira **LabsSC900** no campo do Nome. Depois, selecione **OK**.
    1. Nome das máquinas virtuais:  insira **SC900-WinVM**.
    1. Imagem:  No menu suspenso, selecione **Windows 10 Pro, Version 20H2 – Gen 1**.
    1. Tamanho:  selecione **exibir todos os tamanhos** no menu suspenso, depois selecione **B2s** e pressione **Selecionar** na parte inferior da página.
    1. Nome de usuário:  insira **AzureUser**.
    1. Senha:  insira **SC900AzureLabs**.
    1. Portas de entrada públicas:  selecione **Nenhuma**.
    1. Licenciamento:  selecione **Eu confirmo que tenho uma licença compatível do Windows 10, com direitos de hospedagem multilocatária** para marcar essa caixa.
    1. Selecione **Avançar: Discos**. 
1. Agora estamos na guia Discos para configurar a VM.  Deixe todas as configurações como padrão e selecione **Avançar: Rede >**.
1. Agora estamos na guia Rede para configurar a VM.  Preencha as informações a seguir (para o que não estiver na lista, mantenha a configuração padrão):
    1. Grupo de segurança de rede NIC:  selecione **Nenhum**.

    1. selecione **Avançar:  Gerenciamento >**.
1. Agora estamos na guia Gerenciamento para configurar a VM.  Deixe todas as configurações como padrão e selecione **Avançar: Avançado>**.
1. Agora estamos na guia Avançado para configurar a VM.  Deixe todas as configurações como padrão e selecione **Avançar: Marcas>**.
1. Agora estamos na guia Marcas para configurar a VM.  Deixe todas as configurações como padrão e selecione **Avançar: Revisar+ Criar>**.
1. Revise a configuração da VM.  Alguns pontos a observar: O endereço IP dessa VM é público e ela não tem um grupo de segurança de rede NIC.  Em termos de segurança, a VM está exposta.  Nós vamos abordar essa questão em uma próxima tarefa. Selecione Criar.  Pode levar alguns minutos até a implantação da VM ser concluída.
1. Observe o nome do adaptador de rede, **sc900-winvmXXX** (o XXX é específico do adaptador de rede da VM).
1. Após a conclusão da implantação da VM, selecione **Ir para o recurso**.
1. Agora estamos na página SC900-WinVM.  Observe o endereço IP público. 
1. No topo da página, selecione **Conectar** e depois **RDP** no menu suspenso.
1. Verifique se o endereço IP está configurado como Endereço IP público, deixe o número da porta como padrão e selecione **Baixar arquivo DRP**. 
1. Abra o arquivo baixado e selecione **Conectar**. 
1. Suas credenciais serão solicitadas.  Para nome de usuário, insira **AzureUser**.  Para senha, insira **SC900AzureLabs**. 
1. Vai aparecer uma janela para conectar a Área de Trabalho Remota dizendo “Não foi possível verificar a identidade do computador remoto.  Deseja conectar mesmo assim?”  Selecione **Sim**.
1. Você acaba de se conectar à VM do Windows criada agora mesmo. Siga as solicitações para concluir a configuração do Windows. Embora você tenha se conectado à VM via RDP e uma Porta RDP comum, todas as portas dessa VM estão abertas e não tem nada filtrando o tráfego. 
1. Feche a conexão da área de trabalho remota selecionando o **X** na parte superior central da página, onde o endereço IP é exibido.  Uma janela pop-up vai indicar que sua sessão remota será desconectada. Selecione **OK**.
1. Você está de volta à página SC900-WinVM no portal do Azure.  Deixe esta guia do navegador aberta para a próxima tarefa.

#### Tarefa 2:  Criar um grupo de segurança de rede e atribuir o adaptador de rede da VM a esse NSG.

1. Abra a guia SC900-WinVM – Microsoft Azure no seu navegador.

1. No canto superior esquerdo da página, perto de Microsoft Azure, selecione o ícone para mostrar o menu (as três linhas horizontais, também conhecidas como ícone de hambúrguer). Depois, selecione **Todos os Serviços**.
1. Na caixa Filtrar serviços, perto de Todos os serviços, insira **Grupos de segurança de rede** e, a partir dos resultados, selecione **Grupos de segurança de rede** (não selecione Grupos de segurança de rede Clássico).
1. No topo da página Grupos de segurança de rede, selecione **+Criar**.
1. Na guia Básico da página Criar grupo de segurança de rede, especifique as seguintes configurações:
    1. Assinatura:  Azure Pass – Sponsorship

    1. Grupo de recursos:  **LabsSC900**
    1. Nome:  **NSG-SC900**
    1. Região:  mantenha a padrão **(EUA) Leste dos EUA**
    1. Selecione **Revisar + criar** e depois **Criar**.
1. Após a conclusão da implantação, selecione **Ir para o recurso**.
1. Observe as regras de entrada e saída no NSG.  Apesar de o NSG ter sido criado e existirem regras padrão para filtrar o tráfego, nenhuma interface foi associada ao NSG. A VM ainda está vulnerável, com todas as portas expostas à internet pública.
1. À esquerda no painel de navegação, na página NSG-SC900, em Configurações, selecione **Adaptadores de rede**.
1. Selecione **+Associar**, acima da caixa de pesquisa.
1. Na página para associar o adaptador de rede, selecione **sc900-winvmXXX** (o XXX é específico do adaptador de rede da VM).  Durante a associação do adaptador, você encontra uma caixa de notificação no canto superior direito da tela.
1. Quando o adaptador tiver sido associado ao NSG, ele vai aparecer no topo da lista.
1. Com a interface da VM associada ao grupo de segurança de rede e as regras padrão de NSG, qualquer tentativa de conexão à VM vai dar em falha.  
1. No canto superior esquerdo da página, selecione **Todos os serviços**. Em Recursos, selecione **Máquinas Virtuais**.
1. Na página Máquinas Virtuais, selecione **SC900-WinVM**.
1. No topo da página **SC900-WinVM**, selecione **Conectar** e depois **RDP**.
1. Verifique se o endereço IP está configurado como Endereço IP público, deixe o número da porta como padrão e selecione **Baixar arquivo DRP**.
1. Abra o arquivo baixado e selecione **Conectar**.
1. Depois de alguns segundos, vai aparecer uma mensagem de falha indicando que não foi possível se conectar à Área de Trabalho remota.  Selecione **OK**.

#### Tarefa 3: nesta tarefa, vamos criar uma regra de NSG para permitir o tráfego de entrada utilizando RDP na porta 3389.  Depois, vamos testar essa regra tentando nos conectar à VM via RDP. 

1. Abra a guia SC900-WinVM – Microsoft Azure no seu navegador.

1. Do lado esquerdo do painel de navegação, em Configurações, selecione **Rede**.
1. Ao selecionar a guia Regras da porta de entrada, você encontra as regras de entrada padrão. Não é possível remover as regras padrão, mas você pode substituí-las criando regras com prioridades mais altas. Do lado direito da página, selecione **Adicionar regra da porta de entrada**:
1. Na página Adicionar regra de segurança de entrada, especifique as seguintes configurações:
    1. Fonte:  **Qualquer**

    1. Intervalos de portas de origem: *
    1. Destino:  **Qualquer**
    1. Serviço:  **RDP**
    1. Ação:  **Permitir**
    1. Prioridade:  **300**; Observação: regras com números menores têm maior prioridade e são processadas primeiro.
    1. Nome:  **AllowRDP**
1. Selecione **Adicionar**
1. Quando a regra for provisionada, ela vai aparecer na lista de regras de entrada.
1. Agora veja se você consegue se conectar à VM usando o RDP.  Selecione **Soluções**, à esquerda no painel de navegação.
1. Verifique se o endereço IP está configurado como Endereço IP público, deixe o número da porta como padrão e selecione **Baixar arquivo DRP**.
1. Abra o arquivo baixado e selecione **Conectar**.
1. Suas credenciais serão solicitadas.  Para nome de usuário, insira **AzureUser**.  Para senha, insira **SC900AzureLabs**.
1. Vai aparecer uma janela para conectar a Área de Trabalho Remota dizendo “Não foi possível verificar a identidade do computador remoto.  Deseja conectar mesmo assim?”  Selecione **Sim**.
1. Agora você se conectou à VM. Nesse caso, foi possível se conectar à VM porque a regra de tráfego de entrada que você criou permite o tráfego de entrada para a VM via RDP.
1. Deixe a VM aberta; vamos usá-la na próxima tarefa.

#### Tarefa 4:  As regras de saída padrão de NSG permitem o tráfego de saída na internet, então vamos verificar se você pode se conectar à internet.  Você vai ter a experiência de criar uma regra de saída personalizada para bloquear o tráfego de saída na internet e testar essa regra.

1. Na VM, selecione **Edge** para abrir o navegador.  
1. Insira **https://www.bing.com** na barra de endereços e confirme se é possível se conectar ao mecanismo de pesquisa.
1. Feche o navegador na VM, mas continue com ela aberta; nós vamos precisar dela nas próximas etapas.
1. Volte ao Portal do Azure e abra a guia SC900-WinVM – Microsoft Azure no navegador.
1. Do lado esquerdo do painel de navegação, em Configurações, selecione **Rede**.
1. Selecione a guia **Regras da porta de saída**.  Você encontrará as regras de saída padrão.  Observe a regra padrão “PermitirSaídaDeInternet”. Essa regra permite qualquer tráfego de internet de saída. Não é possível remover a regra padrão, mas você pode substitui-la criando uma regra com prioridade mais alta. Do lado direito da página, selecione **Adicionar regra da porta de saída**.
1. Na página Adicionar regra de segurança de saída, especifique as seguintes configurações:
    1. Fonte:  **Qualquer**

    1. Intervalos de portas de origem:  *
    1. Destino:  **Marca de Serviço**
    1. Marca de serviço de destino:  **Internet**
    1. Serviço:  **Personalizado** (mantenha o padrão)
    1. Intervalos de portas de destino:  * (coloque um asterisco no campo dos intervalos de porta de destino)
    1. Protocolo: **Qualquer**
    1. Ação: **Negar**
    1. Prioridade:  **4000**
    1. Nome:  **DenyInternet**
1. Selecione **Adicionar**
1. Quando a regra for provisionada, ela vai aparecer na lista de regras de saída.  Embora ela apareça na lista, vai levar alguns minutos para ela funcionar (espere alguns minutos antes de ir para as próximas etapas).  
1. Volte à sua VM
1. Abra o navegador Edge na VM e insira **https://www.bing.com**.  A página não deve ser exibida.  Observação: se você conseguir se conectar à internet mesmo verificando que todos os parâmetros da regra de saída foram configurados corretamente, é porque demora alguns minutos até a regra produzir efeito.  Feche o navegador, espere alguns minutos e tente de novo.
1. Feche a conexão da área de trabalho remota selecionando o **X** na parte superior central da página, onde o endereço IP é exibido.  Uma janela pop-up vai indicar que sua sessão remota será desconectada. Selecione **OK**.
1. Nesta tarefa, você configurou uma rega de saída com sucesso no NSG para bloquear o tráfego de internet de saída.

#### Tarefa 5:  IMPORTANTE: Nesta tarefa, vamos excluir o grupo de recursos e todos os recursos contidos nele.   Isso é importante para evitar preços adicionais.

1. Abra a guia SC900-WinVM – Microsoft Azure no seu navegador.

1. No canto superior esquerdo da página, selecione **Todos os Serviços**.
1. Na caixa Filtrar serviços, perto de Todos os serviços, insira **Grupos de recursos** e, a partir dos resultados, selecione **Grupos de recursos**.
1. Selecione **LabsSC900**.
1. No centro superior da página LabsSC900, selecione **Excluir grupo de recursos**.
1. Na nova janela aberta, insira o nome do grupo de recursos, **LabsSC900**, para confirmar a exclusão do grupo de recursos e de todos os seus recursos. Depois, selecione **Excluir** na parte inferior da página.
1. Pode levar alguns minutos para que todos os recursos e o grupo de recursos sejam excluídos.

#### Revisão

Neste laboratório, tivemos a experiência de configurar a VM com e sem um grupo de segurança de rede (NSG) e observamos as regras de NSG padrão.  Além disso, também passamos pela criação de regras de NSG.