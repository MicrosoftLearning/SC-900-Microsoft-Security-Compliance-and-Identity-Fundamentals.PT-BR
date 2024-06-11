<!---
---
Configuração de pré-demonstração: Título: 'Instalação de demonstração'
---
--->

## Locatários do WWL – Termos de uso

Se você estiver recebendo um locatário como parte de uma entrega de treinamento com instrutor, observe que o locatário é disponibilizado com a finalidade de dar suporte aos laboratórios práticos no treinamento com instrutor.

Os locatários não devem ser compartilhados ou usados para fins fora dos laboratórios práticos. O locatário usado neste curso é um locatário de avaliação e não pode ser usado ou acessado após o fim da aula e não está qualificado para extensão.

Os locatários não podem ser convertidos em uma assinatura paga. Os locatários obtidos como parte deste curso permanecem a propriedade da Microsoft Corporation e reservamos o direito de obter acesso e a qualquer momento.

## Configuração de pré-demonstração do locatário do Microsoft 365

### Habilitar o log de auditoria do Microsoft 365

Nesta tarefa de configuração, você habilitará a funcionalidade de log de auditoria do Microsoft 365.  Embora a documentação indique que o log de auditoria está ativado por padrão, a maioria dos locatários do laboratório não tem este recurso habilitado e pode levar horas para que isso entre em vigor.  É útil habilitar este recurso, porque o Microsoft 365 usa os logs de auditoria para os insights de usuário e as atividades identificadas nas políticas e nos insights de análise.

1. Abra o Microsoft Edge. Na barra de endereços, insira **https://admin.microsoft.com** .

1. Entre com as credenciais de administrador do locatário do Microsoft 365 fornecido pelo ALH (hoster de laboratório autorizado).

1. À esquerda no painel de navegação do Centro de administração do Microsoft 365, selecione **Mostrar todos**.

1. Em Centros de administração, selecione **Conformidade**.  A página inicial do portal de conformidade do Microsoft Purview é aberta em uma nova página do navegador.  

1. À esquerda no painel de navegação do portal de conformidade do Microsoft Purview, selecione **Mostrar todos**.

1. Em Soluções, no painel de navegação esquerdo, selecione **Auditoria**.  Observação: a funcionalidade de auditoria também pode ser acessada por meio da página inicial do Microsoft 365 Defender.

1. Verifique se a guia **Pesquisar** está selecionada (sublinhada).

1. Depois de acessar a página Auditoria, aguarde de 2 a 3 minutos.  Se a Auditoria NÃO estiver habilitada, você verá uma barra azul na parte superior da página indicando "Começar a registrar atividade do usuário e do administrador".  Selecione **Iniciar a atividade de gravação de usuário e administrador**.  Depois que a auditoria estiver habilitada, a barra azul desaparecerá.  Se a barra azul não estiver presente, isso indicará que a auditoria já está habilitada e não é necessário realizar nenhuma ação adicional.

1. Volte à página inicial do portal de conformidade do Microsoft Purview selecionando **Página Inicial** no painel de navegação esquerdo.

### Monitoramento de arquivos do Microsoft Defender para Aplicativos de Nuvem

Nesta tarefa de instalação, você vai habilitar o monitoramento de arquivos no Microsoft Defender para Aplicativos de Nuvem.

1. Abra a guia do navegador no centro de administração do Microsoft 365.  Se você a fechou anteriormente, abra uma nova guia do navegador, insira **https://admin.microsoft.com** na barra de endereços, e, no painel de navegação à esquerda do centro de administração do Microsoft 365, selecione **Mostrar tudo**.

1. Em Centros de administração, selecione **Segurança**.  A página inicial do portal do Microsoft 365 Defender é aberta em uma nova página do navegador.  

1. No painel de navegação à esquerda, selecione **Arquivos**, listado em Aplicativos de nuvem.

1. Se isso ainda não estiver habilitado, escolha **Habilitar monitoramento de arquivos**, selecione a caixa ao lado do texto **Habilitar monitoramento de arquivos** e escolha **Salvar**.  

1. No painel de navegação à esquerda, em Aplicativos de nuvem, selecione **Arquivos** para voltar à página de arquivos.  Se você habilitar o monitoramento de arquivos com sucesso, verá as opções de filtro na parte superior da página.  Pode levar algum tempo para que os arquivos do locatário do laboratório configurado previamente sejam exibidos.

## Configuração de pré-demonstração da assinatura da Fatia de Nuvem do Azure

Para essa configuração, você está usando o ambiente da Fatia de Nuvem do Azure, que é separado do locatário do Microsoft 365 fornecido. Faça logoff do locatário do Microsoft 365 e logon usando as credenciais da Fatia de Nuvem do Azure.

### Máquina Virtual do Azure

Verifique se uma VM já foi criada. Caso contrário, configure-a agora. Você usará a VM como parte da demonstração do NSG.

1. Abra o Microsoft Edge.  Na barra de endereços, insira **https://portal.azure.com** e entre com as credenciais do Azure fornecidas pelo hoster de laboratório autorizado (ALH).  Isso o levará você à página inicial dos serviços do Azure.

1. Na caixa de pesquisa azul na parte superior da página, insira **Máquinas Virtuais** e selecione **Máquinas Virtuais** nos resultados da pesquisa.

1. Se uma VM já estiver listada, ignore as etapas seguintes, caso contrário, você precisará criar uma.  Selecione **Criar** e, no menu suspenso, escolha **Máquina virtual do Azure**. Configure os parâmetros a seguir (se um parâmetro não estiver listado, mantenha o valor padrão).
    1. Grupo de recursos: selecione **Criar**, insira **LabsSC900** e escolha **OK**.
    1. Nome da máquina virtual: insira **SC900-WinVM**.
    1. Opções de disponibilidade: na lista suspensa, selecione **Nenhuma redundância de infraestrutura necessária**.
    1. Imagem: na lista suspensa, selecione **Windows 11 Pro, versão 22H2 – x64 Gen2** (ou qualquer imagem do Windows 10 ou do Windows 11 listada).
    1. Tamanho: selecione **Ver todos os tamanhos** e escolha **Standard_B1s** e **Selecionar** na parte inferior da página.
    1. Nome de usuário: insira **SC900-VM-User**
    1. Senha: insira uma senha e anote-a, pois você vai precisar dela mais tarde.
    1. Confirmar senha: insira a senha novamente.
    1. Portas de entrada públicas: **Nenhuma**.
    1. Licenciamento: selecione a opção “Confirmo que tenho uma licença do Windows 10/11 qualificada com direitos de hospedagem multilocatário”.  Uma marca de seleção será exibida.
    1. Selecione **Avançar: Discos**
    1. Tipo de disco do sistema operacional: na lista suspensa, selecione **SSD Standard**.
    1. Selecione **Avançar: Rede**
    1. Grupo de segurança de rede da NIC: selecione **Nenhum**.  Você criará um NSG como parte da demonstração, portanto, não faça isso aqui.
    1. Excluir IP público e NIC quando a VM for excluída: marque a caixa para que uma marca de seleção seja exibida.
    1. Escolha **Revisar + criar** e após a validação ser aprovada, selecione **Criar**.
    1. Depois que a implantação da VM for concluída, selecione **Página Inicial** na parte superior da página.

1. Mantenha a guia do navegador do Azure aberta para continuar com a configuração de pré-demonstração.

### Grupo de segurança de rede

Verifique se um NSG já foi criado. Se o NSG não tiver sido criado, configure-o agora, mas não associe nenhuma interface a ele nem crie nenhuma regra. Essas etapas serão feitas como parte da demonstração do NSG.

1. Na barra de pesquisa azul na parte superior da página, insira **Grupos de segurança de rede**. Nos resultados, selecione **Grupos de segurança de rede** (não selecione Grupos de segurança de rede clássicos).

1. Selecione **Criar grupo de segurança de rede**. Na guia Noções básicas da página Criar grupo de segurança de rede, especifique as seguintes configurações:
    1. Assinatura: mantenha o valor padrão (essa é a assinatura do Azure fornecida pelo hoster do laboratório autorizado)
    1. Grupo de recursos: **LabsSC900**
    1. Nome:  **NSG-SC900**
    1. Região:  mantenha o valor padrão.
    1. Selecione **Revisar + criar** e **Criar**.
    1. Uma vez concluída a implantação (isso acontece muito rapidamente), selecione **Ir para o recurso**.

### Microsoft Defender para Nuvem

O objetivo aqui é apenas acessar o Microsoft Defender para Nuvem pela primeira vez. Isso é importante, pois pode levar até 24 horas para que o Defender para Nuvem reflita uma pontuação de segurança inicial.  

1. Abra a guia Página Inicial – Microsoft Azure no navegador.

1. Na barra de pesquisa azul, insira **Microsoft Defender para Nuvem** e, na lista de resultados, selecione **Microsoft Defender para Nuvem**.

1. Se esta for a primeira vez que você entra no Microsoft Defender para Nuvem com sua assinatura, você poderá chegar à página Introdução e precisar fazer a atualização.  Role a página até a parte inferior e selecione **Pular**.  Você será direcionado à página Visão geral.

1. Todas as assinaturas têm o CSPM fundamental habilitado por padrão, o que fornece uma pontuação de segurança, mas pode levar até 24 horas para que o Defender para Nuvem reflita uma pontuação de segurança inicial.

1. Selecione **Página Inicial** na parte superior da página.

1. Mantenha a guia do navegador aberta para continuar com a configuração de pré-demonstração.

### Microsoft Sentinel

Verifique se uma instância do Microsoft Sentinel já foi criada. Caso contrário, configure-a agora, pois você vai precisar dela como parte da demonstração passo a passo no Microsoft Sentinel.

1. Abra a guia Página Inicial – Microsoft Azure no navegador.

1. Na caixa de pesquisa, na barra azul no topo da página, perto de onde está escrito Microsoft Azure, digite **Microsoft Sentinel** e selecione **Microsoft Sentinel** nos resultados da pesquisa.

1. Na página do Microsoft Sentinel, selecione **Criar Microsoft Sentinel**.

1. Na página Adicionar o Microsoft Sentinel a um workspace, selecione **Criar um workspace**.

1. Na guia Básico do workspace Criar Log Analytics, insira o seguinte:
    1. Assinatura: mantenha o padrão.
    1. Grupo de recursos: selecione **Criar novo**, insira o nome **SC900-Sentinel-RG** e selecione **OK**.
    1. Nome: **SC900-LogAnalytics-workspace**.
    1. Região: **Leste dos EUA** (uma região padrão diferente pode ser selecionada de acordo com sua localização)
    1. Selecione **Revisar + Criar** (nenhuma marca será configurada).
    1. Verifique se você inseriu as informações corretas e, em seguida, selecione **Criar**.
    1. Pode levar um ou dois minutos para que o workspace seja listado. Se você ainda não conseguir vê-lo, selecione **Atualizar** e, em seguida, selecione **Adicionar**.

1. Depois que o novo workspace for adicionado, a página Microsoft Sentinel | Novidades e guias será exibida, indicando que a avaliação gratuita do Microsoft Sentinel está ativada.  Selecione **OK**.

### Revisão

Nesta configuração, você habilitou a funcionalidade de log de auditoria no seu locatário do Microsoft 365 e verificou que uma VM foi configurada previamente no ambiente da Fatia de Nuvem do Azure. Você também preparou seu ambiente do Defender para Nuvem e do Microsoft Sentinel.
