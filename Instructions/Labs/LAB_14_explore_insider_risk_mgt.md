---
ms.openlocfilehash: 553860b67fc7cc2b181e874e4c57fb4bc972822b
ms.sourcegitcommit: 15658ca1c7bae8a4dbaa33ab6f897070bde521b9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2022
ms.locfileid: "147892696"
---
<a name="---"></a><!--->
---
Laboratório: Título: 'Explorar o gerenciamento de risco interno no Microsoft Purview' Roteiro de aprendizagem/Módulo/Unidade: 'Roteiro de aprendizagem: descrever as funcionalidades de conformidade da Microsoft; Módulo 4: descrever as funcionalidades de risco interno no Microsoft Purview; Unidade 2: descrever o gerenciamento de risco interno'
---
--->

# <a name="lab-explore-insider-risk-management-in-microsoft-purview"></a>Laboratório: Explorar o gerenciamento de riscos internos no Microsoft Purview

Esse laboratório é mapeado para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades de conformidade da Microsoft
- Módulo: descrever as funcionalidades de risco interno no Microsoft Purview
- Unidade: descrever o gerenciamento de risco interno

## <a name="lab-scenario"></a>Cenário do laboratório

Neste laboratório, vamos acompanhar o processo de configuração de uma política de gerenciamento de risco interno, junto com os pré-requisitos básicos para configurar e utilizar políticas de gerenciamento de risco interno.  Observação: este laboratório apresenta o que é exigido para configurar o Gerenciamento de risco interno e as opções associadas com a criação de uma política.  Este laboratório não inclui a tarefa de disparar a política, já que o número de eventos que precisariam ocorrer para disparar uma política está fora do escopo deste exercício.

**Tempo estimado**: 25-30 minutos

### <a name="task-1"></a>Tarefa 1:

Nesta tarefa, você enquanto administrador global vau habilitar permissões para o Gerenciamento de Risco Interno.  Especificamente, você vai adicionar usuários ao grupo de função de Gerenciamento de Risco Interno para garantir que os usuários designados possam acessar e gerenciar os recursos de gerenciamento de risco interno.  Pode levar até 30 minutos para que as permissões do grupo de função sejam aplicadas aos usuários de toda a organização.

1. Abra o Microsoft Edge. Na barra de endereços, insira **admin.microsoft.com**.

1. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é sua ID de locatário exclusiva fornecida pelo provedor de hospedagem de laboratório) e selecione **Avançar**.

    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem de laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**. Vamos ser direcionados à página Centro de administração do Microsoft 365.

1. À esquerda no painel de navegação do Centro de administração do Microsoft 365, selecione **Mostrar todos**.

1. Em Centros de administração, selecione **Conformidade**.  A página inicial do portal de conformidade do Microsoft Purview é aberta em uma nova página do navegador.  

1. À esquerda no painel de navegação do portal de Conformidade do Microsoft Purview, selecione **Permissões**.

1. Na página de permissões e funções, em que se diz "Exibir e gerenciar funções usadas para executar tarefas específicas de solução no centro de conformidade.", selecione **Funções**.

1. No campo de pesquisa, insira **Risco interno** e selecione o ícone de pesquisa (lupa).  Observe as várias funções que aparecem.  Cada uma delas tem diferentes níveis de acesso.  Selecione **Gerenciamento de risco interno**.

1. Na janela aberta, próximo de Membros, selecione **Editar**.

1. Para adicionar mesmos a esse grupo de função, selecione **Escolher membros**.

1. Selecione **+ Adicionar** na parte superior da página.

1. A partir da lista de nomes, selecione **Administrador MOD**, **Megan Bowen**, e depois **Adicionar** na parte inferior da página. Então, selecione **Concluído** na parte inferior da página.

1. Verifique se os membros adicionados estão corretos e selecione **Salvar**.

1. Na parte inferior da janela Gerenciamento de Risco Interno, selecione **Fechar**.

1. À esquerda no painel de navegação, selecione **Página Inicial** para voltar à página do portal de conformidade do Microsoft Purview.

1. Mantenha essa guia do navegador aberta; vamos voltar a ela na próxima tarefa.

### <a name="task-2-skip-if-you-did-the-setup-lab-task-to-enable-the-audit-log"></a>Tarefa 2 (IGNORE se já tiver realizado a tarefa do laboratório de configuração para habilitar o log de auditoria)

O gerenciamento de risco interno usa logs de auditoria do Microsoft 365 para insights do usuário e atividades identificadas nas políticas e insights de análise. Nesta tarefa, vamos habilitar a Capacidade de pesquisa do log de auditoria. Observação:  Depois de ativar a pesquisa de log de auditoria, pode levar algumas horas até podermos gerar resultados a partir da pesquisa de log de auditoria.  Apesar de poder levar algumas horas até podermos pesquisar o log de auditoria, isso não afeta a possibilidade de concluir outras tarefas neste laboratório.

1. Selecione a guia do navegador rotulada **Página inicial de conformidade do Microsoft 365**.  Se você tiver fechado essa guia, abra o Microsoft Edge e insira **compliance.microsoft.com** na barra de endereços. Entre com as suas credenciais de administrador.

1. Do lado esquerdo do painel de navegação, em soluções, selecione **Auditoria**.

1. Verifique se a guia **Pesquisa** está selecionada (sublinhada).

1. Após abrir a página Auditoria, aguarde de 2 a 3 minutos.  Se a Auditoria NÃO estiver habilitada, você vai ver uma barra azul no topo da página dizendo começar a registrar atividade de usuário e administrador.  Selecione **Começar a registrar atividade de usuário e administrador**.  Quando a auditoria estiver habilitada, a barra azul desaparece.  Se a barra azul não aparecer, é porque a auditoria já está habilitada e não é necessário realizar nenhuma ação adicional.

1. Volte à página inicial do portal de conformidade do Microsoft Purview selecionando **Página Inicial** no painel de navegação esquerdo.

1. Deixe essa guia do navegador aberta; vamos usá-la na próxima tarefa.

### <a name="task-3"></a>Tarefa 3

Nesta tarefa, vamos acompanhar as configurações associadas à solução de Gerenciamento de Risco Interno.  As configurações de gerenciamento de risco interno se aplicam a todas as políticas de gerenciamento de risco interno, independentemente do modelo escolhido ao criar a política.

1. Você deve estar na página inicial do portal de conformidade do Microsoft Purview. Se não estiver, abra a guia do navegador **Página Inicial - Conformidade do Microsoft 365**.

1. Do lado esquerdo do painel de navegação, em Soluções, selecione **Gerenciamento de risco interno**.

1. Antes de começar a configurar a política, algumas configurações precisam ser realizadas.  Na página Gerenciamento de Risco Interno, selecione o **ícone de engrenagem de configurações** no canto superior direito da página para acessar as configurações de Risco Interno.  
    1. Verifique se você está na guia **Privacidade**: para usuários que realizam atividades correspondentes às políticas de risco interno, essa configuração vai determinar se é desejável mostrar nomes reais ou usar versões anônimas para mascarar a identidade.  Selecione **Não mostrar versões anônimas de nomes de usuários** e depois **Salvar**.

    1. Selecione a guia **Indicadores de política**. Quando ocorre um evento gatilho de política, atividades que mapeiam os indicadores selecionados são usadas para determinar a pontuação de risco para o usuário. Os Indicadores de política selecionados aqui são incluídos nos modelos de Política de risco interno.  Role a página para exibir todos os indicadores disponíveis e as informações relacionadas. Em **Indicares do Office**, selecione **Selecionar todos** e depois **Salvar**.
    1. Selecione a guia **Períodos de tempo de política**. Os períodos de tempo escolhidos aqui entram em vigor ao usuário quando é disparada alguma correspondência a uma política de risco interno.   A janela Ativação determina por quanto tempo as políticas detectam ativamente as atividades para usuários e é disparada quando um usuário realiza a primeira atividade correspondente a uma política. A Detecção de atividades anteriores determina até que ponto a política deve voltar para detectar atividades de usuário e é disparada quando um usuário realiza a primeira atividade correspondente a uma política.  Mantenha os valores padrão.  Selecione a guia **Detecções inteligentes**.
    1. Selecione a guia **Detecções inteligentes**. Verifique as opções aqui.  Observe as configurações dos domínios e como elas são relacionadas aos indicadores.
    1. Explore outros itens listados nas configurações e observe que muitos estão em versão prévia.

1. Para voltar à visão geral do Gerenciamento de risco interno, selecione **Gerenciamento de risco interno** no canto superior esquerdo da página, acima de Configurações.

1. Deixe essa guia do navegador aberta; vamos usá-la na próxima tarefa.

### <a name="task-4"></a>Tarefa 4

Nesta tarefa, vamos acompanhar a criação de uma política.

1. Você deve estar na página Gerenciamento de risco interno.  Se não estiver, abra a guia do navegador rotulada **Gerenciamento de risco interno - Conformidade do Microsoft 365**.

1. Na página Visão geral do gerenciamento de risco interno, selecione a guia **Políticas** e depois **+ Criar política**.  Configure cada uma das guias de política a seguir.

    1. Modelo de política:  Na lista de categorias, selecione **Vazamento de dados** e depois **Vazamentos de dados gerais**.  Observe que os modelos dentro das categorias podem ter pré-requisitos adicionais.  Leia os detalhes associados a este modelo e depois selecione **Avançar**.

    1. Nome e descrição: insira um nome **SC900-InsiderRiskPolicy** e depois selecione **Avançar**.
    1. Usuários e grupos:  Verifique a caixa de informações.  Mantenha as configurações padrão **Incluir todos os usuários e grupos**.  Selecione **Avançar**.
    1. Conteúdo a ser priorizado: Leia a descrição. Selecione **Eu quero especificar sites do SharePoint, rótulos de confidencialidade e/ou tipos de informações confidenciais como conteúdo prioritário** e depois selecione **Avançar**.
        1. Site do SharePoint: Para este exemplo de política, deixe em branco e selecione **Avançar**
        1. Tipos de informações confidenciais: para este exemplo de política, deixe em branco e selecione **Avançar**.
        1. Rótulos de confidencialidade: selecione **+ Adicionar ou editar rótulos de confidencialidade**.  Selecione os rótulos listados:  **Finanças Confidenciais** e **Altamente confidencial/Projeto – Falcon**; selecione **Adicionar** e depois **Avançar**.
    1. Gatilhos: Verifique as informações detalhadas.  A política é disparada quando o usuário desempenha uma atividade de exfiltração conforme definido (selecione os ícones de informação para cada marcador da lista para mais detalhes) OU uma correspondência a uma política existente de Prevenção Contra Perda de Dados (DLP).  Como você não tem nenhuma política DLP configurada como parte deste exercício, selecione **O usuário desempenha uma atividade de exfiltração**.  Observe que os indicadores da política que nós habilitamos na tarefa anterior estão marcados.   Lembre-se de que esses indicadores só vão ser ativados quando a política for disparada e as atividades que mapeiam esses indicadores vão ser usadas para calcular a pontuação de risco para o usuário. Selecione **Avançar**.
    1. Limites de indicador: aqui é possível especificar limites padrão ou personalizar os limites associados aos indicadores.  Lembre-se de que os indicadores são ativados apenas depois que a política é disparada, então esses limites não influenciam no disparo da política. Selecione **Especificar limites personalizados**. Ao selecionar essa opção, é possível verificar os valores padrão atuais. Mantenha o padrão e selecione **Avançar**.  
    1. Indicadores: Observe que todos os indicadores do escritório que você selecionou na tarefa anterior estão selecionados.  Percorra a página para ver outros indicadores de política disponíveis e outros itens que são selecionados automaticamente.   A detecção de sequência está habilitada.  Se, conforme definido, uma sequência de atividades for detectada, é indicado um risco maior.  Passe o mouse sobre o ícone de informações para obter informações detalhadas.  Esses itens exigem que certos indicadores sejam selecionados e que os dispositivos estejam integrados.  Para facilitar e porque não temos dispositivos integrados neste locatário, desmarque **Selecionar todos**.
    1. Terminar: verifique as configurações, selecione **Enviar** e depois **Concluído**.

1. Estamos de volta à guia Políticas da página Gerenciamento de risco interno.  A política que acabamos de criar aparecerá listada.  

1. Na política recém-criada, o campo “Usuários no escopo” representa os usuários a que são atribuídas pontuações de risco pela política.  A atribuição de pontuações de risco aos usuários ocorre quando a política é disparada, por isso o valor está indicando 0.  Um administrador pode configurar que a política comece a atribuir pontuações de risco a usuários específicos, com base na atividade detectada pelas políticas selecionadas, E que ignora o requisito de que um evento disparador deve ser detectado primeiro.  Para fazer isso, selecione o círculo vazio próximo ao nome da política para selecionar a política. Depois, selecione **Começar atividade de pontuação para os usuários**, que aparece acima da tabela da política.  Preencha todos os campos e depois selecione **Começar a atividade de pontuação**.  Pode levar 24 horas para os usuários aparecerem na guia ‘Usuários’. Após esse período, é possível selecionar os usuários a partir dessa guia para verificar as atividades detectadas.  Selecione **Fechar** na parte inferior da janela.

1. Feche todas as guias abertas do navegador.

### <a name="review"></a>Revisão

Neste laboratório, acompanhamos o processo de configuração de uma política de gerenciamento de risco interno, junto com os pré-requisitos básicos para configurar e utilizar políticas de gerenciamento de risco interno.
