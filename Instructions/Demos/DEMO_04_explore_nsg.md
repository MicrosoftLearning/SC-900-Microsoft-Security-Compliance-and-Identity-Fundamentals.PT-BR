---
Demo:
  title: Grupos de Segurança de Rede (NSGs) do Azure
  module: 'Module 3 Lesson 1: Describe the capabilities of Microsoft security solutions: Describe basic security capabilities in Azure.'
ms.openlocfilehash: a136022cd3458d513011b10c408827d33fbc8caa
ms.sourcegitcommit: b8b861a8c884a56f094213e47a59be48ba898ca1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "146741850"
---
# <a name="demo-azure-network-security-groups-nsgs"></a>Demonstração: Grupos de Segurança de Rede (NSGs) do Azure

## <a name="demo-scenario"></a>Cenário da demonstração

Nesta demonstração, você mostrará a funcionalidade de um NSG (grupo de segurança de rede) no Azure.  Você fará isso criando primeiro uma VM (máquina virtual) sem nenhum NSG, como parte da configuração pré-demonstração. Você também criará um NSG sem nenhuma interface ou sub-rede associada.  Como parte da demonstração, você mostrará as regras padrão de entrada e saída do NSG. Em seguida, você passará pelo processo de atribuição da interface da VM ao NSG.  Após a configuração, vamos testar a conexão à VM usando as regras padrão de NSG e também as regras criadas por você.
  
### <a name="pre-demo-setup-part-1"></a>Configuração pré-demonstração, parte 1

 Instrutores, é recomendado que vocês façam isso **ANTES** da aula, uma vez que pode levar vários minutos para criar uma VM. Nesta configuração, você criará uma máquina virtual do Windows 10.

1. Abra a guia **Página Inicial – Microsoft Azure** no seu navegador.  Se você fechou a guia anteriormente, abra uma página do navegador e, na barra de endereços, insira portal.azure.com e entre novamente.

1. Na caixa de pesquisa, na barra azul na parte superior da página ao lado de onde está escrito Microsoft Azure, insira **Máquinas virtuais** e selecione **Máquinas virtuais** nos resultados da pesquisa.  

1. No canto superior esquerdo da página, selecione **+Adicionar** e selecione **+Máquina virtual**.

1. Na guia Básico, preencha as informações a seguir (para o que não estiver na lista, mantenha a configuração padrão):
    1. **Assinatura**: verifique se a configuração padrão é Azure Pass – Sponsorship.
    1. **Grupo de recursos**: selecione **Criar novo** e, no campo Nome, insira **LabsSC900-RG** e selecione **OK**.
    1. **Nome da máquina virtual**:  insira **SC900-WinVM**.
    1. **Região**:  mantenha o valor padrão.
    1. **Opções de disponibilidade**: selecione **Nenhuma redundância de infraestrutura necessária**.  OBSERVAÇÃO: é muito importante que as opções de disponibilidade sejam definidas como Nenhuma redundância de infraestrutura necessária, caso contrário, a demonstração não funcionará como planejado.  Ter uma opção de disponibilidade requer um NSG e estamos criando intencionalmente a VM sem um NSG.
    1. **Imagem**: no menu suspenso, selecione **Windows 10 Pro, Versão 20H2 – Gen 1**.
    1. **Tamanho**: selecione **exibir todos os tamanhos** no menu suspenso, escolha **B2s** e **Selecionar** na parte inferior da página.
    1. **Nome de usuário**:  Insira um nome de usuário de sua escolha.  Tome nota do valor, pois você precisará dele para acessar a VM.
    1. **Senha**:  Insira uma senha de sua escolha.  Tome nota do valor, pois você precisará dele para acessar a VM.
    1. **Portas de entrada públicas**: você pode deixar a configuração padrão (não importa o que você selecionar aqui, pois as configurações de rede substituirão o que for selecionado).
    1. **Licenciamento**: selecione **Confirmo que tenho uma licença do Windows 10 qualificada com direitos de hospedagem multilocatário**, para que apareça uma marca de seleção na caixa.
    1. Selecione **Avançar: Discos**.

1. Agora estamos na guia Discos para configurar a VM.  Deixe todas as configurações como padrão e selecione **Avançar: Rede >** .

1. Agora estamos na guia Rede para configurar a VM.  Preencha as informações a seguir (para o que não estiver na lista, mantenha a configuração padrão):
    1. Grupo de segurança de rede NIC: selecione **Nenhum**.  Observação: Ao selecionar Nenhum, você está garantindo que a NIC não tenha um NSG.  Em uma etapa seguinte da demonstração, você criará um NSG e atribuirá a NIC da VM ao NSG criado.
    1. Como as outras configurações da VM serão mantidas como padrão, prossiga e selecione Avançar: **Revisar+ Criar>** .

1. Revise a configuração da VM.  Alguns pontos a observar: O endereço IP dessa VM é público e ela não tem um grupo de segurança de rede NIC.  Em termos de segurança, a VM está exposta.  Nós vamos abordar essa questão em uma próxima tarefa. Selecione **Criar**.  Pode levar alguns minutos até a implantação da VM ser concluída.

1. Observe o nome do adaptador de rede, **sc900-winvmXXX** (o XXX é específico do adaptador de rede da VM).

1. Após a conclusão da implantação da VM, selecione **Ir para o recurso**.  Agora estamos na página SC900-WinVM.  Observe o endereço IP público.

1. No painel de navegação esquerdo, selecione **Rede** e observe a interface de rede **sc900-winvmXXX** (o XXX será específico para a interface de rede da sua VM).  Não deve haver regras de entrada ou saída associadas à interface.  

1. Na parte superior da página, selecione **Conectar**, pois é importante verificar se você já pode se conectar à VM.
    1. Na parte superior da página, verifique se **RDP** está selecionado (sublinhado).
    1. Verifique se o endereço IP está configurado como Endereço IP público, deixe o número da porta como padrão e selecione **Baixar arquivo DRP**.
    1. **Abra** o arquivo baixado e na janela que for exibida, selecione **Conectar**.
    1. Uma janela será aberta solicitando suas credenciais. Se a janela padrão solicitar um PIN, selecione **Mais opções** e selecione **Usar uma conta diferente**.   Suas credenciais serão solicitadas.  Insira o nome de usuário e a senha que você usou quando criou a VM.
    1. Vai aparecer uma janela para conectar a Área de Trabalho Remota dizendo “Não foi possível verificar a identidade do computador remoto.  Deseja conectar mesmo assim?”  Selecione **Sim**.
    1. Você acaba de se conectar à VM do Windows criada agora mesmo. Conclua a configuração do Windows. Embora você tenha se conectado à VM via RDP e uma Porta RDP comum, todas as portas dessa VM estão abertas e não tem nada filtrando o tráfego.  Feche a conexão da área de trabalho remota selecionando o **X** na parte superior central da página, onde o endereço IP é exibido.  Uma janela pop-up vai indicar que sua sessão remota será desconectada. Selecione **OK**.

1. Você está de volta à página SC900-WinVM no portal do Azure.  Deixe esta guia do navegador aberta para a próxima tarefa.

### <a name="pre-demo-setup-part-2"></a>Configuração pré-demonstração, parte 2

Crie um grupo de segurança de rede, mas NÃO atribua a interface de rede da VM a esse NSG.  

1. Abra a guia SC900-WinVM – Microsoft Azure no seu navegador.

1. Na caixa de pesquisa, na barra azul na parte superior da página ao lado de onde está escrito Microsoft Azure, insira **grupo de segurança de rede** e selecione **Grupos de segurança de rede** nos resultados da pesquisa.  Não selecione Grupos de segurança de rede clássicos.

1. No topo da página Grupos de segurança de rede, selecione **+Criar**.

1. Na guia Básico da página Criar grupo de segurança de rede, especifique as seguintes configurações:
    1. Assinatura:  Azure Pass – Sponsorship
    1. Grupo de recursos:  **LabsSC900-RG**
    1. Nome:  **NSG-SC900**
    1. Região:  mantenha o valor padrão **(EUA) Leste dos EUA**
    1. Selecione **Revisar + criar** e depois **Criar**.

1. Assim que a implantação for concluída, selecione **Ir para o recurso** e verifique se tudo está correto.  Deve haver 3 regras de entrada padrão, 3 regras de saída padrão, nenhuma sub-rede e nenhuma interface associada ao NSG.  Retorne para a **Página Inicial** do portal do Azure.  

### <a name="demo"></a>Demonstração

Faça o passo a passo das configurações de um NSG.  Neste caso, você fará o passo a passo para um NSG existente (aquele que você criou na configuração acima) que ainda não foi atribuído a uma interface de VM. Em seguida, você mostrará o processo de associação de uma interface ao NSG e o processo de criação das regras de entrada e saída.

1. Abra a guia do navegador, **Página Inicial – Microsoft Azure**.  Se você fechou a guia anteriormente, abra uma página do navegador e, na barra de endereços, insira portal.azure.com e entre novamente.

1. Na caixa de pesquisa, na barra azul na parte superior da página ao lado de onde está escrito Microsoft Azure, insira **grupo de segurança de rede** e selecione **Grupos de segurança de rede** nos resultados da pesquisa.  Não selecione Grupos de segurança de rede clássicos.

1. Na página de NSG, selecione o NSG que você criou na configuração, **NSG-SC900**.

1. A guia **Visão geral** no painel de navegação esquerdo é realçada.  Observe as regras de entrada e saída no NSG. Embora o NSG tenha sido criado e haja regras padrão para filtrar o tráfego, nenhuma interface foi associada ao NSG. Você pode ver isso no canto superior direito da página, onde diz 'Associado a: 0 sub-redes, 0 interfaces de rede'.  Para que um NSG funcione adequadamente, ele deve ser atribuído a algo.  Em nosso caso, atribuiremos à interface de rede da VM que foi criada anteriormente.

1. À esquerda no painel de navegação, na página NSG-SC900, em Configurações, selecione **Adaptadores de rede**.

1. Selecione **+ Associar**, acima da caixa de pesquisa e, na lista suspensa, selecione **sc900-winvmXXX** (o XXX será específico para a interface de rede da sua VM) e selecione **OK**. Durante a associação do adaptador, você encontra uma caixa de notificação no canto superior direito da tela. Quando o adaptador tiver sido associado ao NSG, ele vai aparecer no topo da lista.

1. Volte para a guia **Visão geral**.  Observe que no canto superior direito da página, você verá 'Associado a: 0 sub-rede, 1 interface de rede' — a interface agora está atribuída ao NSG. Além disso, realce para os alunos as regras padrão. Para entrada, apenas o tráfego de outras redes virtuais do Azure e do Azure Load Balancer será permitido. Qualquer outro tráfego de entrada para a VM será negado. Também destaque as regras de saída padrão.  Apenas o tráfego de saída para outras VNets e o tráfego de saída da Internet são permitidos.  Como parte da demonstração, é recomendável que você reserve um minuto para mostrar que o tráfego de entrada é negado.
    1. Na barra de pesquisa, na parte superior da página, insira e selecione **Máquinas Virtuais**.
    1. Na página Máquinas Virtuais, selecione **SC900-WinVM**.
    1. Na parte superior da página da SC900-WinVM, selecione **Conectar** e selecione **RDP**.
    1. Verifique se o endereço IP está configurado como Endereço IP público, deixe o número da porta como padrão e selecione **Baixar arquivo DRP**.
    1. **Abra** o arquivo baixado e selecione **Conectar**.
    1. Depois de alguns segundos, vai aparecer uma mensagem de falha indicando que não foi possível se conectar à Área de Trabalho remota. Selecione **OK**.

1. Agora que você mostrou o impacto das regras de entrada padrão do NSG, você precisa criar uma nova regra para permitir o tráfego RDP de entrada.  Destaque que não é possível excluir as regras padrão existentes, que só é possível criar novas com prioridade mais alta.
    1. Do lado esquerdo do painel de navegação, em Configurações, selecione **Rede**.  Você está na página de rede da VM e, embora possa criar uma regra de entrada e uma regra de saída a partir daqui, volte para a página de NSG, afinal a demonstração é sobre o NSG.  **Selecione NSG-SC900**. É o link no meio da janela.

1. Agora você está na página da visão geral do NSG.  Observe as informações sobre o NSG. No painel de navegação esquerdo da página do NSG, em Configurações, selecione **Regras de segurança de entrada** e selecione **+ Adicionar** na parte superior da página. Na página Adicionar regra de segurança de entrada, fale sobre as várias configurações. É recomendável que você realmente crie a regra para permitir o tráfego RDP de entrada, com as seguintes configurações:
    1. Fonte: **Qualquer**
    1. Intervalos de portas de origem: **\***
    1. Destino: **Qualquer**
    1. Serviço: **RDP**
    1. Ação: **Permitir**
    1. Prioridade: **300**; Observação: regras com números menores têm maior prioridade e são processadas primeiro. Portanto, a prioridade dessa nova regra precisa ser maior do que a prioridade da regra existente que nega todo o tráfego de entrada.
    1. Nome: **AllowRDP**
    1. Selecione **Adicionar**
    1. Quando a regra for provisionada, ela vai aparecer na lista de regras de entrada.

1. Agora verifique as **Regras de segurança de saída**.  Selecione **+ Adicionar** na parte superior da página e fale sobre as várias configurações.  Recomendo criar a regra: As configurações abaixo criam uma regra para negar o tráfego de saída da Internet:
    1. Fonte: **Qualquer**
    1. Intervalos de portas de origem: **\***
    1. Destino: **Marca de serviço**
    1. Marca de serviço de destino: **Internet**
    1. Serviço: **Personalizado** (mantenha o padrão)
    1. Intervalos de porta de destino: **\*** (coloque um asterisco no campo dos intervalos de porta de destino).
    1. Protocolo: **Qualquer**
    1. Ação: **Negar**
    1. Prioridade: **4000** (o ponto a ser realçado é que a prioridade precisa ser mais alta do que a prioridade para a regra existente que permite o tráfego de saída da Internet).
    1. Nome: **DenyInternet**
    1. Selecione **Adicionar**
    1. Quando a regra for provisionada, ela vai aparecer na lista de regras de saída.

1. Agora volte para sua VM e teste as regras.  Na parte superior da página, selecione **SC900-VM**, acima de onde está escrito Regras de segurança de saída.

1. Teste a regra de entrada verificando se você pode se conectar à VM usando RDP.
    1. Selecione **Soluções**, à esquerda no painel de navegação.
    1. Verifique se o endereço IP está configurado como Endereço IP público, deixe o número da porta como padrão e selecione **Baixar arquivo DRP**.
    1. **Abra** o arquivo baixado e selecione **Conectar**.
    1. Suas credenciais serão solicitadas. Insira o nome de usuário e a senha que você usou quando criou a VM.  Se a janela que solicita suas credenciais solicitar um PIN, selecione **Mais opções** e selecione **Usar uma conta diferente**.
    1. Vai aparecer uma janela para conectar a Área de Trabalho Remota dizendo “Não foi possível verificar a identidade do computador remoto. Deseja conectar mesmo assim?” Selecione **Sim**.
    1. Agora você se conectou à VM. Destaque para o aluno que, neste caso, você conseguiu se conectar à VM porque a regra de tráfego de entrada criada permite o tráfego de entrada para a VM via RDP.

1. Agora teste a regra de saída do NSG.
    1. Abra o navegador Edge na VM.
    1. Insira **www.bing.com**. A página não deve ser exibida. Observação: se você conseguir se conectar à internet mesmo verificando que todos os parâmetros da regra de saída foram configurados corretamente, é porque demora alguns minutos até a regra produzir efeito. Aguarde alguns minutos e tente novamente.

1. Feche a conexão da área de trabalho remota selecionando o **X** na parte superior central da página, onde o endereço IP é exibido. Uma janela pop-up vai indicar que sua sessão remota será desconectada. Selecione **OK**.

1. Retorne à página inicial do portal do Azure selecionando **Microsoft Azure** na barra azul na parte superior da página.

### <a name="post-course-delivery-tear-down"></a>Desinstalação após a entrega do curso

As VMs são um recurso cobrado e, embora o custo da execução delas nesta demonstração seja minúsculo, é recomendável excluir o grupo de recursos que contém a VM e os recursos associados ao concluir o curso.

1. Abra a guia SC900-WinVM – Microsoft Azure no seu navegador.

1. No canto superior esquerdo da página, selecione **Todos os Serviços**.

1. Na caixa Filtrar serviços, perto de Todos os serviços, insira **Grupos de recursos** e, a partir dos resultados, selecione **Grupos de recursos**.

1. Selecione **LabsSC900-RG**.

1. Na parte superior central da página LabsSC900-RG, selecione **Excluir grupo de recursos**.

1. Na janela aberta, insira o nome do grupo de recursos, **LabsSC900-RG**, para confirmar a exclusão do grupo de recursos e todos os recursos e selecione **Excluir** na parte inferior da página.

1. Pode levar alguns minutos para que todos os recursos e o grupo de recursos sejam excluídos.

#### <a name="review"></a>Revisão

Nesta demonstração, você mostrou as informações e configurações associadas a um NSG, incluindo o processo para associar uma interface ao NSG, mostrou as regras padrão de entrada e saída e, por fim, as etapas para criar uma nova regra.
