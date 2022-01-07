---
Demo:
    title: 'NSGs (Grupos de Segurança de Rede) do Azure'
    module: 'Módulo 3 – Lição 1: Descrever os recursos das soluções de segurança da Microsoft: Descrever os recursos básicos de segurança no Azure.'
---

# Demonstração: NSGs (Grupos de Segurança de Rede) do Azure

### Cenário da demonstração
Nesta demonstração, você mostrará a funcionalidade de um NSG (grupo de segurança de rede) no Azure.  Você fará isso criando primeiro uma VM (máquina virtual) sem nenhum NSG, como parte da configuração pré-demonstração. Você também criará um NSG sem nenhuma interface ou sub-rede associada.  Como parte da demonstração, você mostrará as regras padrão de entrada e saída do NSG. Em seguida, você passará pelo processo de atribuição da interface da VM ao NSG.  Uma vez configurado, você testará a conexão com a VM, usando as regras de NSG padrão e também as regras que você criará.
  

#### Configuração pré-demonstração, parte 1
 Instrutores, é recomendado que vocês façam isso **ANTES** da aula, uma vez que pode levar vários minutos para criar uma VM. Nesta configuração, você criará uma máquina virtual do Windows 10.

1. Abra a guia **Página Inicial – Microsoft Azure** no seu navegador.  Se você fechou a guia anteriormente, abra uma página do navegador e, na barra de endereços, insira portal.azure.com e entre novamente.

1. Na caixa de pesquisa, na barra azul na parte superior da página ao lado de onde está escrito Microsoft Azure, insira **Máquinas virtuais** e selecione **Máquinas virtuais** nos resultados da pesquisa.  

1. No canto superior esquerdo da página, selecione **+Adicionar** e selecione **+Máquina virtual**.

1. Na guia Básico, preencha as seguintes informações (para os itens não listados, deixe as configurações padrão):
    1. **Assinatura**: verifique se a configuração padrão é Azure Pass – Sponsorship.
    1. **Grupo de recursos**: selecione **Criar novo** e, no campo Nome, insira **LabsSC900-RG** e selecione **OK**.
    1. **Nome da máquina virtual**:  Insira **SC900-WinVM**.
    1. **Região**:  mantenha o padrão.
    1. **Opções de disponibilidade**: selecione **Nenhuma redundância de infraestrutura necessária**.  OBSERVAÇÃO: é muito importante que as opções de disponibilidade sejam definidas como Nenhuma redundância de infraestrutura necessária, caso contrário, a demonstração não funcionará como planejado.  Ter uma opção de disponibilidade requer um NSG e estamos criando intencionalmente a VM sem um NSG.
    1. **Imagem**:  no menu suspenso, selecione **Windows 10 Pro, Versão 20H2 – 1ª Geração**.
    1. **Tamanho**:  selecione **Ver todos os tamanhos** no menu suspenso, selecione **B2s** e pressione **Selecionar** na parte inferior da página.
    1. **Nome de usuário**:  insira **AzureUser**.
    1. **Senha**:  insira **SC900AzureLabs**.
    1. **Portas de entrada públicas**:  você pode deixar a configuração padrão (não importa o que você selecionar aqui, pois as configurações de rede substituirão o que você fizer aqui).
    1. **Licenciamento**  selecione **Confirmo que tenho uma licença do Windows 10 qualificada com direitos de hospedagem multilocatário**, para que apareça uma marca de seleção na caixa.
    1. Selecione **Avançar**: **Discos**.

1. Agora você está na guia Discos para a configuração da VM.  Deixe todas as Configurações padrão e selecione **Avançar: Rede >**.

1. Agora você está na guia Rede para a configuração da VM.  Preencha as seguintes informações (para os itens não listados, deixe as configurações padrão):
    1. Grupo de segurança de rede NIC:  selecione **Nenhum**.  Observação: Ao selecionar Nenhum, você está garantindo que a NIC não tenha um NSG.  Em uma etapa seguinte da demonstração, você criará um NSG e atribuirá a NIC da VM ao NSG criado.
    1. Como as outras configurações da VM serão mantidas como padrão, prossiga e selecione Avançar: **Revisar + Criar >**.

1. Revise a configuração da sua VM.  Alguns pontos a serem observados: Esta VM possui um endereço IP público e nenhum grupo de segurança de rede NIC.  Do ponto de vista da segurança, isso deixa a VM exposta.  Abordaremos isso em uma tarefa seguinte. Selecione **Criar**.  Pode levar vários minutos para que a implantação da VM seja concluída.

1. Observe o nome da interface de rede, **sc900-winvmXXX** (o XXX será específico para a interface de rede da sua VM).

1. Assim que a implantação da VM for concluída, selecione **Ir para o recurso**.  Agora você está na página da SC900-WinVM.  Observe o endereço IP público.

1. No painel de navegação esquerdo, selecione **Rede** e observe a interface de rede **sc900-winvmXXX** (o XXX será específico para a interface de rede da sua VM).  Não deve haver regras de entrada ou saída associadas à interface.  

1. Na parte superior da página, selecione **Conectar**, pois é importante verificar se você já pode se conectar à VM.
    1. Na parte superior da página, verifique se **RDP** está selecionado (sublinhado).
    1. Verifique se o endereço IP está definido como endereço IP público, deixe o número da porta padrão e selecione **Baixar arquivo DRP**.
    1. **Abra** o arquivo baixado e na janela que for exibida, selecione **Conectar**.
    1. Uma janela será aberta solicitando suas credenciais. Se a janela padrão solicitar um PIN, selecione **Mais opções** e selecione **Usar uma conta diferente**.   Suas credenciais serão solicitadas.  Em Nome de usuário, insira **AzureUser**.  Em Senha, insira **SC900AzureLabs**.
    1. Uma janela de conexão da Área de Trabalho Remota é aberta indicando: A identidade do computador remoto não pode ser verificada.  Você quer se conectar mesmo assim?  Selecione **Sim**.
    1. Agora você está conectado à VM do Windows que acabou de criar. Conclua a configuração do Windows. Embora você tenha se conectado à VM via RDP e uma porta RDP geralmente usada, essa VM tem todas as portas abertas e não há nada que esteja filtrando o tráfego.  Feche a conexão da área de trabalho remota, selecionando o **X** na parte superior central da página onde o endereço IP é exibido.  Uma janela pop-up abrirá com: Sua sessão remota será desconectada. Selecione **OK**.

1. Agora você está de volta à página da SC900-WinVM no portal do Azure.  Deixe esta guia do navegador aberta para a próxima tarefa.

#### Configuração pré-demonstração, parte 2
Crie um grupo de segurança de rede, mas NÃO atribua a interface de rede da VM a esse NSG.  

1. Abra a guia SC900-WinVM – Microsoft Azure no seu navegador.

1. Na caixa de pesquisa, na barra azul na parte superior da página ao lado de onde está escrito Microsoft Azure, insira **grupo de segurança de rede** e selecione **Grupos de segurança de rede** nos resultados da pesquisa.  Não selecione Grupos de segurança de rede clássicos.

1. Na parte superior da página Grupos de segurança de rede, selecione **+ Criar**.

1. Na guia Básico da página Criar grupo de segurança de rede, especifique as seguintes configurações:
    1. Assinatura:  Azure Pass – Sponsorship
    1. Grupo de recursos:  **LabsSC900-RG**
    1. Nome:  **NSG-SC900**
    1. Região:  Mantenha o padrão **(EUA) Leste dos EUA**
    1. Selecione **Revisar + criar** e selecione **Criar**.

1. Assim que a implantação for concluída, selecione **Ir para o recurso** e verifique se tudo está correto.  Deve haver 3 regras de entrada padrão, 3 regras de saída padrão, nenhuma sub-rede e nenhuma interface associada ao NSG.  Retorne para a **Página Inicial** do portal do Azure.  

#### Demonstração
Faça o passo a passo das configurações de um NSG.  Neste caso, você fará o passo a passo para um NSG existente (aquele que você criou na configuração acima) que ainda não foi atribuído a uma interface de VM. Em seguida, você mostrará o processo de associação de uma interface ao NSG e o processo de criação de regras de entrada e saída.

1. Abra a guia do navegador, **Página Inicial – Microsoft Azure**.  Se você fechou a guia anteriormente, abra uma página do navegador e, na barra de endereços, insira portal.azure.com e entre novamente.

1. Na caixa de pesquisa, na barra azul na parte superior da página ao lado de onde está escrito Microsoft Azure, insira **grupo de segurança de rede** e selecione **Grupos de segurança de rede** nos resultados da pesquisa.  Não selecione Grupos de segurança de rede clássicos.

1. Na página de NSG, selecione o NSG que você criou na configuração, **NSG-SC900**.

1. A guia **Visão geral** no painel de navegação esquerdo é realçada.  Observe as regras de entrada e saída padrão no NSG. Embora o NSG tenha sido criado e haja regras padrão para filtrar o tráfego, nenhuma interface foi associada ao NSG. Você pode ver isso no canto superior direito da página, onde diz 'Associado a: 0 sub-redes, 0 interfaces de rede'.  Para que um NSG funcione adequadamente, ele deve ser atribuído a algo.  Em nosso caso, atribuiremos à interface de rede da VM que foi criada anteriormente.

1. No painel de navegação esquerdo na página NSG-SC900, em Configurações, selecione **Interfaces de rede**.

1. Selecione **+ Associar**, acima da caixa de pesquisa e, na lista suspensa, selecione **sc900-winvmXXX** (o XXX será específico para a interface de rede da sua VM) e selecione **OK**. Enquanto a interface é associada, você verá uma caixa de notificação no canto superior direito da tela. Assim que a interface for associada ao NSG, ela aparecerá na lista.

1. Volte para a guia **Visão geral**.  Observe que no canto superior direito da página, você verá 'Associado a: 0 sub-rede, 1 interface de rede' — a interface agora está atribuída ao NSG. Além disso, realce para os alunos as regras padrão. Para entrada, apenas o tráfego de outras redes virtuais do Azure e do Azure Load Balancer será permitido. Qualquer outro tráfego de entrada para a VM será negado. Também destaque as regras de saída padrão.  Apenas o tráfego de saída para outras VNets e o tráfego de saída da Internet são permitidos.  Como parte da demonstração, é recomendável que você reserve um minuto para mostrar que o tráfego de entrada é negado.
    1. Na barra de pesquisa, na parte superior da página, insira e selecione **Máquinas Virtuais**.
    1. Na página de Máquinas Virtuais, selecione **SC900-WinVM**.
    1. Na parte superior da página da SC900-WinVM, selecione **Conectar** e selecione **RDP**.
    1. Verifique se o endereço IP está definido como endereço IP público, deixe o número da porta padrão e selecione **Baixar arquivo DRP**.
    1. **Abra** o arquivo baixado e selecione **Conectar**.
    1. Depois de alguns segundos tentando se conectar, você verá a mensagem de falha, indicando que a Área de Trabalho Remota não pode se conectar ao computador remoto. Selecione **OK**.

1. Agora que você mostrou o impacto das regras de entrada padrão do NSG, você precisa criar uma nova regra para permitir o tráfego RDP de entrada.  Destaque que não é possível excluir as regras padrão existentes, que só é possível criar novas com prioridade mais alta.
    1. No painel de navegação esquerdo, em Configurações, selecione **Rede**.  Você está na página de rede da VM e, embora possa criar uma regra de entrada e uma regra de saída a partir daqui, volte para a página de NSG, afinal a demonstração é sobre o NSG.  **Selecione NSG-SC900**. É o link no meio da janela.

1. Agora você está na página da visão geral do NSG.  Observe as informações sobre o NSG. No painel de navegação esquerdo da página do NSG, em Configurações, selecione **Regras de segurança de entrada** e selecione **+ Adicionar** na parte superior da página. Na página Adicionar regra de segurança de entrada, fale sobre as várias configurações. É recomendável que você realmente crie a regra para permitir o tráfego RDP de entrada, com as seguintes configurações:
    1. Fonte: **Qualquer**
    1. Intervalos de portas de origem: **\***
    1. Destino: **Qualquer**
    1. Serviço: **RDP**
    1. Ação: **Permitir**
    1. Prioridade: **300**. Observação: regras com números menores têm prioridade mais alta e são processadas primeiro. Portanto, a prioridade dessa nova regra precisa ser maior do que a prioridade da regra existente que nega todo o tráfego de entrada.
    1. Nome: **AllowRDP**
    1. Selecione **Adicionar**
    1. Assim que a regra for provisionada, ela será exibida na lista de regras de entrada.

1. Agora verifique as **Regras de segurança de saída**.  Selecione **+ Adicionar** na parte superior da página e fale sobre as várias configurações.  Recomendo criar a regra: As configurações abaixo criam uma regra para negar o tráfego de saída da Internet:
    1. Fonte: **Qualquer**
    1. Intervalos de portas de origem: **\***
    1. Destino: **Marca de serviço**
    1. Marca de serviço de destino: **Internet**
    1. Serviço: **Personalizar** (mantenha o padrão).
    1. Intervalos de portas de destino: **\*** (lembre-se de colocar um asterisco no campo de intervalos de portas de destino).
    1. Protocolo: **Qualquer**
    1. Ação: **Negar**
    1. Prioridade: **4000** (o ponto a ser realçado é que a prioridade precisa ser mais alta do que a prioridade para a regra existente que permite o tráfego de saída da Internet).
    1. Nome: **DenyInternet**
    1. Selecione **Adicionar**
    1. Assim que a regra for provisionada, ela será exibida na lista de regras de saída.

1. Agora volte para sua VM e teste as regras.  Na parte superior da página, selecione **SC900-VM**, acima de onde está escrito Regras de segurança de saída.

1. Teste a regra de entrada verificando se você pode se conectar à VM usando RDP.
    1. No painel de navegação esquerdo, selecione **Conectar**.
    1. Verifique se o endereço IP está definido como endereço IP público, deixe o número da porta padrão e selecione **Baixar arquivo DRP**.
    1. **Abra** o arquivo baixado e selecione **Conectar**.
    1. Suas credenciais serão solicitadas. Em Nome de usuário, insira **AzureUser**. Em Senha, insira **SC900AzureLabs**.  Se a janela que solicita suas credenciais solicitar um PIN, selecione **Mais opções** e selecione **Usar uma conta diferente**.
    1. Uma janela de conexão da Área de Trabalho Remota é aberta indicando: A identidade do computador remoto não pode ser verificada. Você quer se conectar mesmo assim? Selecione **Sim**.
    1. Agora você está conectado à VM. Realce ao o aluno que, neste caso, você conseguiu se conectar à VM porque a regra de tráfego de entrada que você criou permite o tráfego de entrada para a VM via RDP.

1. Agora teste a regra de saída do NSG.
    1. Abra o navegador Edge na VM.
    1. Insira **https://www.bing.com**. A página não deve ser exibida. Observação: se você conseguir se conectar à Internet e verificar se todos os parâmetros da regra de saída foram definidos corretamente, é provável que leve alguns minutos para que a regra entre em vigor. Aguarde alguns minutos e tente novamente.

1. Feche a conexão da área de trabalho remota, selecionando o **X** na parte superior central da página onde o endereço IP é exibido. Uma janela pop-up abrirá com: Sua sessão remota será desconectada. Selecione **OK**.

1. Retorne à página inicial do portal do Azure selecionando **Microsoft Azure** na barra azul na parte superior da página.

#### Desativar
**IMPORTANTE**: Nesta tarefa você excluirá o grupo de recursos e todos os recursos que ele contém.   É importante para evitar cobranças adicionais.

1. Abra a guia SC900-WinVM – Microsoft Azure no seu navegador.

1. No canto superior esquerdo da página, selecione **Todos os serviços**.

1. Na caixa Filtrar serviços ao lado de onde está escrito Todos os serviços, insira **Grupos de recursos** e dos resultados selecione **Grupos de recursos**.

1. Selecione **LabsSC900-RG**.

1. Na parte superior central da página LabsSC900-RG, selecione **Excluir grupo de recursos**.

1. Na janela aberta, insira o nome do grupo de recursos, **LabsSC900-RG**, para confirmar a exclusão do grupo de recursos e todos os recursos e selecione **Excluir** na parte inferior da página.

1. Pode levar alguns minutos para que todos os recursos e o grupo de recursos sejam excluídos.

#### Revisão

Nesta demonstração, você mostrou as informações e configurações associadas a um NSG, incluindo o processo para associar uma interface ao NSG, mostrou as regras padrão de entrada e saída e, por fim, as etapas para criar uma nova regra.
