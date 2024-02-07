<!---
---
Laboratório: Título: 'Explorar o gerenciamento de risco interno no Microsoft Purview' Roteiro de aprendizagem/Módulo/Unidade: 'Roteiro de aprendizagem: descrever as funcionalidades de conformidade da Microsoft; Módulo 4: descrever as funcionalidades de risco interno no Microsoft Purview; Unidade 2: descrever o gerenciamento de risco interno'
---
--->

# Laboratório: Explorar o gerenciamento de riscos internos no Microsoft Purview

Esse laboratório é mapeado para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades de conformidade da Microsoft
- Módulo: descrever as funcionalidades de risco interno no Microsoft Purview
- Unidade: descrever o gerenciamento de risco interno

## Cenário do laboratório

Neste laboratório, você acompanhará o processo de configuração de uma política de risco interno, acompanhado dos pré-requisitos básicos para configurar e utilizar as políticas de risco interno.  Observação: este laboratório apresenta o que é exigido para configurar o Gerenciamento de risco interno e as opções associadas com a criação de uma política.  Este laboratório não inclui a tarefa de disparar a política, pois o número de eventos que precisariam ocorrer para disparar uma política e o tempo necessário estão fora do escopo deste exercício.

**Tempo estimado**: 45 a 60 minutos

### Tarefa 1

Nesta tarefa, você, como administrador global, habilitará permissões para o gerenciamento de risco interno.  Especificamente, você vai adicionar usuários ao grupo de função de Gerenciamento de Risco Interno para garantir que os usuários designados possam acessar e gerenciar os recursos de gerenciamento de risco interno.  Pode levar até 30 minutos para que as permissões do grupo de funções sejam aplicadas aos usuários em toda a organização.

1. Abra a guia do navegador na home page do Microsoft Purview.  Se você a fechou anteriormente, abra uma nova guia do navegador e insira **https://admin.microsoft.com** . Entre com as credenciais de administrador para o locatário do Microsoft 365 fornecido pelo hoster de laboratório autorizado (ALH). No painel de navegação à esquerda do Centro de administração do Microsoft 365, selecione **Mostrar tudo** e depois **Conformidade**.  A página inicial do portal de conformidade do Microsoft Purview é aberta em uma nova página do navegador.  

1. No painel de navegação esquerdo, expanda **Funções e escopos** e selecione **Permissões**.

1. Em Soluções do Microsoft Purview, selecione **Funções**.

1. No campo de pesquisa, digite **Risco interno** e pressione Enter no teclado.  Observe as várias funções que aparecem.  Cada um deles tem diferentes níveis de acesso.  Selecione **Gerenciamento de risco interno** e leia a descrição.  Role a página para baixo até o ponto em que ela mostra os membros e observe que o Administrador MOD e Mila Moraes estão listados. Feche a janela selecionando o **X** no canto superior direito.

1. No painel de navegação à esquerda, selecione **Página Inicial** para voltar à página do portal de conformidade do Microsoft Purview.

1. Mantenha essa guia do navegador aberta, pois você voltará a ela na tarefa seguinte.

### Tarefa 2 (OBSERVAÇÃO: IGNORE a Tarefa 2 se já tiver realizado a tarefa do laboratório de configuração para habilitar o log de auditoria).

O gerenciamento de risco interno usa os logs de auditoria do Microsoft 365 para os insights de usuário e as atividades identificadas nas políticas e nos insights de análise. Nesta tarefa, você habilitará a funcionalidade de pesquisa do log de auditoria. Observação: depois de ativar a pesquisa de log de auditoria, pode levar várias horas para que os resultados ao pesquisar o log de auditoria sejam retornados.  Embora possa levar várias horas até que você possa pesquisar o log de auditoria, isso não afetará a capacidade de concluir outras tarefas neste laboratório.

1. Selecione a guia do navegador rotulada **Página inicial de conformidade do Microsoft 365**.  Se você tiver fechado essa guia, abra o Microsoft Edge e insira **compliance.microsoft.com** na barra de endereços. Entre com suas credenciais de administrador.

1. Em Soluções, no painel de navegação esquerdo, selecione **Auditoria**.

1. Verifique se a guia **Nova Pesquisa** está selecionada (sublinhada).

1. Depois de acessar a página Auditoria, aguarde de 2 a 3 minutos.  Se a Auditoria NÃO estiver habilitada, você verá uma barra azul na parte superior da página indicando "Começar a registrar atividade do usuário e do administrador".  Selecione **Iniciar a atividade de gravação de usuário e administrador**.  Depois que a auditoria estiver habilitada, a barra azul desaparecerá.  Se a barra azul não estiver presente, isso indicará que a auditoria já está habilitada e não é necessário realizar nenhuma ação adicional.

1. Volte à página inicial do portal de conformidade do Microsoft Purview selecionando **Página Inicial** no painel de navegação esquerdo.

1. Mantenha essa guia do navegador aberta, pois você vai usá-la na próxima tarefa.

### Tarefa 3

Nesta tarefa, você acompanhará as configurações associadas à solução de Gerenciamento de Risco Interno.  As configurações de gerenciamento de risco interno se aplicam a todas as políticas de gerenciamento de risco interno, independentemente do modelo escolhido ao criar uma política.

1. Você deve estar na página inicial do portal de conformidade do Microsoft Purview. Caso contrário, abra a guia do navegador **Página inicial – Conformidade do Microsoft 365**.

1. No painel de navegação esquerdo, em Soluções, selecione **Gerenciamento de risco interno**.

1. Antes de você começar a configurar uma política, há algumas configurações com as quais um administrador deve estar familiarizado e configurar conforme necessário para sua organização. Na página Gerenciamento de Risco Interno, selecione o **ícone de engrenagem de configurações** no canto superior direito da janela de gerenciamento de risco interno para acessar as configurações de Risco Interno.  
    1. Verifique se você está na guia **Privacidade**: para usuários que realizam atividades correspondentes às políticas de risco interno, essa configuração vai determinar se é desejável mostrar nomes reais ou usar versões anônimas para mascarar a identidade.  Para fins deste passo a passo, você pode manter a configuração padrão.
    1. Selecione a guia **Indicadores de política**. Uma vez que um evento de disparo de política ocorre, as atividades mapeadas para os indicadores selecionados são usadas na determinação da pontuação de risco, para o usuário. Os indicadores de política selecionados aqui estão incluídos nos modelos de política de risco interno.  Percorra a página para ver todos os indicadores disponíveis e todas informações associadas. Em **Indicadores do Office**, escolha **Selecionar tudo** e **Salvar** na parte inferior da página (você precisará rolá-la para baixo).
    1. Selecione a guia **Prazos de política**. Os prazos escolhidos aqui entram em vigor para um usuário quando ele aciona uma correspondência para uma política de risco interno.   A janela Ativação determina por quanto tempo as políticas detectarão ativamente a atividade dos usuários e será acionada quando um usuário executar a primeira atividade correspondente a uma política. A detecção de atividade anterior determina até onde uma política deve ir para detectar a atividade do usuário e é acionada quando um usuário executa a primeira atividade correspondente a uma política.  Mantenha os valores padrão.
    1. Selecione a guia **Detecções inteligentes** e analise as opções.  Observe as configurações dos domínios e como eles se relacionam com os indicadores.
    1. Explore outros itens listados nas configurações e observe que muitos estão em versão prévia.

1. Para retornar à visão geral do gerenciamento de risco interno, selecione **Gerenciamento de risco interno** no canto superior esquerdo da página, acima de onde está escrito Configurações.

1. Mantenha essa guia do navegador aberta, pois você vai usá-la na próxima tarefa.

### Tarefa 4

Nesta tarefa, você percorrerá as configurações para criar uma política.  O objetivo é simplesmente ter uma noção das várias opções e a flexibilidade associadas à criação de uma política.

1. Você deve estar na página Gerenciamento de risco interno.  Se ainda não estiver lá, abra a guia do navegador rotulada como **Gerenciamento de risco interno – Conformidade com o Microsoft 365**.

1. Na página Visão geral do gerenciamento de risco interno, selecione a guia **Políticas** e depois **+ Criar política**.  Configure cada uma das guias de política a seguir.

    1. Modelo de política: na categoria Vazamentos de dados, selecione **Vazamentos de dados**.  Leia os detalhes associados a este modelo. Nos pré-requisitos, a política DLP é mostrada com uma marca de seleção em um círculo verde para indicar que o pré-requisito foi satisfeito.  Há uma política DLP pré-configurada para esse locatário do laboratório. Selecione **Avançar**. 
    1. Nome e descrição: insira um nome **SC900-InsiderRiskPolicy** e depois selecione **Avançar**.
    1. Usuários e grupos: analise a caixa de informações.  Deixe a configuração padrão, **Incluir todos os usuários e grupos**.  Selecione **Avançar**.
    1. Conteúdo a ser priorizado: de acordo com a descrição, as pontuações de risco são aumentadas para qualquer atividade que tenha um conteúdo prioritário, o que, por sua vez, aumenta a chance de gerar um alerta de alta gravidade. Para simplificar, selecione **Não quero priorizar o conteúdo no momento** e selecione **Avançar**.
    1. Gatilhos: o evento de gatilho determina quando uma política começará a atribuir pontuações de risco à atividade de um usuário.  Você pode escolher entre uma política DLP existente ou se o usuário executará uma atividade de exfiltração. Selecione **O usuário corresponde a uma política DLP (prevenção contra perda de dados)** e, na lista suspensa, selecione **Dados Financeiros dos EUA**. Selecione **Avançar**.
    1. Indicadores: observe que todos os indicadores do Office selecionados na tarefa anterior estão marcados (você pode ver isso selecionando a tecla de seta para baixo ao lado dos indicadores do Office) e selecione **Avançar**.
    1. Na página Opções de detecção, mantenha todas as configurações padrão, mas leia a descrição associada às várias opções e posicione o mouse sobre o ícone de informações para obter informações mais detalhadas sobre uma configuração específica.  Selecione **Avançar**.
    1. Na página “Decida se deseja usar os limites de indicador padrão ou do cliente”, mantenha a configuração padrão **Aplicar limites fornecidos pela Microsoft** e selecione **Avançar**.
    1. Concluir: examine as configurações e selecione **Enviar**.
    1. Examine a descrição do que acontece a seguir e selecione **Concluído**.

1. Você está novamente na guia Políticas da página Gerenciamento de risco interno.  A política que você criou estará listada.  Se você não a vir, selecione o ícone **Atualizar**.

1. Como administrador, você pode começar imediatamente a atribuir pontuações de risco aos usuários com base na atividade detectada pelas políticas selecionadas. Isso ignora o requisito de que um evento de gatilho (como uma correspondência de política DLP) seja detectado primeiro.  Um administrador fará isso selecionando o quadrado vazio ao lado do nome da política para selecionar a política. Depois, ele selecionará **Começar atividade de pontuação para os usuários**, que é mostrada acima da tabela da política.  Uma nova janela será aberta, que exige que o administrador preencha os campos disponíveis. Mantenha os campos vazios, pois você não vai configurar essa opção, mas para obter mais informações sobre por que um administrador deseja fazer isso, selecione **Por que eu faria isso?**.  Saia da janela selecionando o **X** no canto superior direito.

1. No painel de navegação à esquerda, selecione **Página Inicial** para voltar à página de aterrissagem do portal de conformidade do Microsoft Purview.

1. Mantenha a guia do navegador aberta.

### Revisão

Neste laboratório, você acompanhará o processo de configuração de uma política de risco interno, junto com os pré-requisitos básicos para configurar e utilizar as políticas de gerenciamento de risco interno.
