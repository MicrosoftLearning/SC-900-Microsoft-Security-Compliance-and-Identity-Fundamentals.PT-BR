---
ms.openlocfilehash: d2377516343cb85c279c1a2d6347c59f573d73c7
ms.sourcegitcommit: 15658ca1c7bae8a4dbaa33ab6f897070bde521b9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2022
ms.locfileid: "147892192"
---
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

Neste laboratório, vamos explorar a função dos grupos de segurança de rede no Azure.  Para isso, vamos criar uma VM sem nenhum NDG (grupo de segurança de rede). Então, você vai ter a experiência de criar um NSG e atribuir a interface da VM a esse NSG.  Depois de configurado, você observará as regras de entrada e saída padrão e criará novas regras.
  
**Tempo estimado**: 15 a 20 minutos

### <a name="task-1"></a>Tarefa 1:

Nesta tarefa, vamos criar uma máquina virtual Windows 10.

1. Abra o Microsoft Edge.  Na barra de endereços, insira **portal.azure.com**.

1. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é sua ID de locatário exclusiva fornecida pelo provedor de hospedagem de laboratório) e selecione **Avançar**.

    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem de laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**.
1. No canto superior esquerdo da tela, perto de Microsoft Azure, selecione o ícone para mostrar o menu (as três linhas horizontais, também conhecidas como ícone de hambúrguer). Depois, selecione **Todos os Serviços**.  
1. Na janela principal, em Em destaque, selecione Máquinas Virtuais.  Se você não encontrar Máquinas Virtuais na lista, insira o termo na barra de pesquisa e selecione a partir dos resultados exibidos.
1. Na parte superior esquerda da página, selecione **+Criar** e clique em **Máquina Virtual do Azure**.
1. Na guia Básico, preencha as informações a seguir (para o que não estiver na lista, mantenha a configuração padrão):
    1. Assinatura: confirme se a configuração padrão é Azure Pass – Sponsorship.

    1. Grupo de recursos: selecione **Criar** e, no campo Nome, insira **LabsSC900-RG** e selecione **OK**.
    1. Nome da máquina virtual:  insira **SC900-WinVM**.
    1. Região: se o campo de região não estiver pré-preenchido, selecione a região mais próxima de sua localização.
    1. Imagem: no menu suspenso, selecione **Windows 10 Pro, Versão 21H2 – Gen 2**.
    1. Tamanho: selecione **exibir todos os tamanhos** no menu suspenso, escolha **B2s** e **Selecionar** na parte inferior da página.
    1. Nome de usuário:  Insira um nome de usuário de sua escolha.  Tome nota do valor, pois você precisará dele para acessar a VM.
    1. Senha:  Insira uma senha de sua escolha.  Tome nota do valor, pois você precisará dele para acessar a VM.
    1. Portas de entrada públicas: deixe o padrão, **Permitir portas selecionadas**.
    1. Selecione portas de entrada: deixe o padrão, **RDP 3389**.
    1. Licenciamento: selecione **Confirmo que tenho uma licença do Windows 10 qualificada com direitos de hospedagem multilocatário**, para que apareça uma marca de seleção na caixa.
    1. Selecione **Avançar: Discos**.
1. Agora estamos na guia Discos para configurar a VM.  Deixe todas as configurações como padrão e selecione **Avançar: Rede >** .
1. Agora estamos na guia Rede para configurar a VM.  Para o grupo de segurança de rede NIC, selecione **Nenhum**. Mantenha todas as outras configurações com seus valores padrão.  Observação: a finalidade de selecionar nenhum nesta etapa é percorrer as etapas de criação de um grupo de segurança de rede do zero, na tarefa subsequente.
1. Na parte inferior da página, selecione **Avançar: Examinar + Criar>** . Depois que a validação for aprovada, selecione **criar**. Pode levar alguns minutos até a implantação da VM ser concluída.
1. Após a conclusão da implantação da VM, selecione **Ir para o recurso**.
1. Agora estamos na página SC900-WinVM.
1. No topo da página, selecione **Conectar** e depois **RDP** no menu suspenso.
1. Observe que o pré-requisito de porta não é atendido.  Para atender ao pré-requisito, uma regra de segurança de rede de entrada com a porta de destino 3389, usada pelo RDP, deve ser configurada.  Você fará isso na próxima tarefa quando criar um grupo de segurança de rede.
1. Deixe esta guia do navegador aberta.

### <a name="task-2"></a>Tarefa 2:

Crie um grupo de segurança de rede, atribua a interface de rede da VM a esse NSG e crie uma regra de entrada para o tráfego RDP.

1. Abra a guia SC900-WinVM – Microsoft Azure no seu navegador.

1. No canto superior esquerdo da página, perto de Microsoft Azure, selecione o ícone para mostrar o menu (as três linhas horizontais, também conhecidas como ícone de hambúrguer). Depois, selecione **Todos os Serviços**.
1. Na caixa Filtrar serviços, perto de Todos os serviços, insira **Grupos de segurança de rede** e, a partir dos resultados, selecione **Grupos de segurança de rede** (não selecione Grupos de segurança de rede Clássico).
1. No topo da página Grupos de segurança de rede, selecione **+Criar**.
1. Na guia Básico da página Criar grupo de segurança de rede, especifique as seguintes configurações:
    1. Assinatura:  Azure Pass – Sponsorship

    1. Grupo de recursos:  **LabsSC900**
    1. Nome:  **NSG-SC900**
    1. Região:  mantenha o valor padrão.
    1. Selecione **Revisar + criar** e depois **Criar**.
1. Após a conclusão da implantação, selecione **Ir para o recurso**.
1. Observe as regras de entrada e saída no NSG.  Embora o NSG tenha sido criado e haja regras padrão para filtrar o tráfego, nenhuma interface foi associada ao NSG.
1. À esquerda no painel de navegação, na página NSG-SC900, em Configurações, selecione **Adaptadores de rede**.
1. Selecione **+Associar**, acima da caixa de pesquisa.
1. No lado direito da página, está um campo para selecionar o adaptador de rede a ser associado ao NSG. Selecione a seta para baixo, escolha **sc900-winvmXXX** (o XXX será específico para a interface de rede da VM) e selecione **ok** na parte inferior da janela.
1. Quando o adaptador tiver sido associado ao NSG, ele vai aparecer no topo da lista.
1. No painel de navegação esquerdo, selecione **Regras de segurança de entrada**.
1. As regras de entrada padrão negam todo o tráfego de entrada que não é de uma Vnet ou de um balanceador de carga do Azure, portanto, você precisa configurar uma regra para permitir o tráfego RDP de entrada (tráfego na porta 3389). Lembre-se de que não é possível remover as regras padrão, mas você pode substituí-las criando regras com prioridades mais altas.
1. Na parte superior da página, selecione **Adicionar**:
1. Na janela Adicionar regra de segurança de entrada, especifique as seguintes configurações:
    1. Fonte:  **Qualquer**

    1. Intervalos de portas de origem: **\***
    1. Destino:  **Qualquer**
    1. Serviço:  **RDP**
    1. Ação:  **Permitir**
    1. Prioridade:  **300**; Observação: regras com números menores têm maior prioridade e são processadas primeiro.
    1. Nome:  **AllowRDP**
1. Selecione **Adicionar**
1. Depois que a regra for provisionada, ela aparecerá na lista de regras de entrada (talvez seja necessário atualizar a tela).
1. Agora veja se você consegue se conectar à VM usando o RDP.  Selecione o campo de pesquisa na parte superior da página, ao lado de onde está o Microsoft Azure, para exibir os serviços recentes.  Selecione **Máquinas virtuais**.
1. Selecione a VM, **SC900-WinVM**.
1. No topo da página, selecione **Conectar** e depois **RDP** no menu suspenso.
1. Verifique se o endereço IP está configurado como Endereço IP público, deixe o número da porta como padrão e selecione **Baixar arquivo DRP**.
1. Abra o arquivo baixado e selecione **Conectar**.
1. Suas credenciais serão solicitadas.  Insira o nome de usuário e a senha que você usou quando criou a VM.
1. Vai aparecer uma janela para conectar a Área de Trabalho Remota dizendo “Não foi possível verificar a identidade do computador remoto.  Deseja conectar mesmo assim?”  Selecione **Sim**.
1. Agora você se conectou à VM. Nesse caso, foi possível se conectar à VM porque a regra de tráfego de entrada que você criou permite o tráfego de entrada para a VM via RDP.
1. Deixe a VM aberta; vamos usá-la na próxima tarefa.

### <a name="task-3"></a>Tarefa 3

As regras de saída padrão de NSG permitem o tráfego de saída na internet, então vamos verificar se você pode se conectar à internet.  Você vai ter a experiência de criar uma regra de saída personalizada para bloquear o tráfego de saída na internet e testar essa regra.

1. Na VM, selecione **Edge** para abrir o navegador.  
1. Insira **www.bing.com** na barra de endereços e confirme se é possível se conectar ao mecanismo de pesquisa.
1. Feche o navegador na VM, mas continue com ela aberta; nós vamos precisar dela nas próximas etapas.
1. Volte ao Portal do Azure e abra a guia SC900-WinVM – Microsoft Azure no navegador.
1. Do lado esquerdo do painel de navegação, em Configurações, selecione **Rede**.
1. Selecione a guia **Regras da porta de saída**.  Você encontrará as regras de saída padrão.  Observe a regra padrão “PermitirSaídaDeInternet”. Essa regra permite qualquer tráfego de internet de saída. Não é possível remover a regra padrão, mas você pode substitui-la criando uma regra com prioridade mais alta. Do lado direito da página, selecione **Adicionar regra da porta de saída**.
1. Na página Adicionar regra de segurança de saída, especifique as seguintes configurações:
    1. Fonte:  **Qualquer**

    1. Intervalos de portas de origem:  **\***
    1. Destino:  **Marca de serviço**
    1. Marca de serviço de destino:  **Internet**
    1. Serviço:  **Personalizado** (mantenha o padrão)
    1. Intervalos de porta de destino: * (coloque um asterisco no campo dos intervalos de porta de destino)
    1. Protocolo: **Qualquer**
    1. Ação: **Negar**
    1. Prioridade:  **4000**
    1. Nome:  **DenyInternet**
1. Selecione **Adicionar**
1. Quando a regra for provisionada, ela vai aparecer na lista de regras de saída.  Embora ela apareça na lista, vai levar alguns minutos para ela funcionar (espere alguns minutos antes de ir para as próximas etapas).  
1. Volte à sua VM
1. Abra o navegador Edge na VM e insira **www.bing.com**. A página não deve ser exibida.  Observação: se você conseguir se conectar à internet mesmo verificando que todos os parâmetros da regra de saída foram configurados corretamente, é porque demora alguns minutos até a regra produzir efeito.  Feche o navegador, espere alguns minutos e tente de novo.
1. Feche a conexão da área de trabalho remota selecionando o **X** na parte superior central da página, onde o endereço IP é exibido.  Uma janela pop-up vai indicar que sua sessão remota será desconectada. Selecione **OK**.
1. Nesta tarefa, você configurou uma rega de saída com sucesso no NSG para bloquear o tráfego de internet de saída.

### <a name="tear-down"></a>Desativar

As VMs são um recurso cobrado e, embora o custo da execução delas nesta demonstração seja minúsculo, é recomendável excluir o grupo de recursos que contém a VM e os recursos associados ao concluir o curso.

1. Abra a guia SC900-WinVM – Microsoft Azure no seu navegador.

1. No canto superior esquerdo da página, selecione **Todos os Serviços**.
1. Na caixa Filtrar serviços, perto de Todos os serviços, insira **Grupos de recursos** e, a partir dos resultados, selecione **Grupos de recursos**.
1. Selecione **LabsSC900**.
1. No centro superior da página LabsSC900, selecione **Excluir grupo de recursos**.
1. Na nova janela aberta, insira o nome do grupo de recursos, **LabsSC900**, para confirmar a exclusão do grupo de recursos e de todos os seus recursos. Depois, selecione **Excluir** na parte inferior da página.
1. Pode levar alguns minutos para que todos os recursos e o grupo de recursos sejam excluídos.
1. Feche todas as guias abertas do navegador.

### <a name="review"></a>Revisão

Neste laboratório, você percorreu o processo de configuração de um NSG (grupo de segurança de rede), associando esse NSG à interface de rede de uma máquina virtual e adicionando novas regras ao NSG para permitir o tráfego RDP de entrada e bloquear o tráfego da Internet de saída.
