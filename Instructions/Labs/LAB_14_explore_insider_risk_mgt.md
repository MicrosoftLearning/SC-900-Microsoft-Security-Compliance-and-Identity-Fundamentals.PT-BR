---
lab:
    title: 'Explorar o Gerenciamento de Risco Interno no Microsoft 365'
    module: 'Módulo 4 Lição 3: Descrever as funcionalidades das soluções de conformidade da Microsoft: Descrever as funcionalidades de risco interno no Microsoft 365'
---


# Laboratório: Explorar o Gerenciamento de Risco Interno no Microsoft 365

## Visão geral do laboratório
Neste laboratório, vamos acompanhar o processo de configuração de uma política de gerenciamento de risco interno, junto com os pré-requisitos básicos para configurar e utilizar políticas de gerenciamento de risco interno.  Observação:  Este laboratório apresenta o que é exigido para configurar o Gerenciamento de risco interno e as opções associadas com a criação de uma política.  Este laboratório não inclui a tarefa de disparar a política, já que o número de eventos que precisariam ocorrer para disparar uma política está fora do escopo deste exercício.


**Tempo estimado**: 25-30 minutos

#### Tarefa 1: Nesta tarefa, você enquanto administrador global vau habilitar permissões para o Gerenciamento de Risco Interno.  Especificamente, você vai adicionar usuários ao grupo de função de Gerenciamento de Risco Interno para garantir que os usuários designados possam acessar e gerenciar os recursos de gerenciamento de risco interno.  Pode levar até 30 minutos para que as permissões do grupo de função sejam aplicadas aos usuários de toda a organização. 

1. Abra o Microsoft Edge. Na barra de endereços, insira **admin.microsoft.com**.

1. Entre com suas credenciais de administrador.
    1. Na janela de acesso, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (sendo ZZZZZZ o único ID de locatário fornecido pelo provedor de hospedagem do laboratório) e selecione **Avançar**.
    
    1. Insira sua senha de administrador fornecida pelo provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Ao receber um aviso do Microsoft Edge para permanecer conectado, selecione **Sim**. Vamos ser direcionados à página Centro de administração do Microsoft 365.

1. À esquerda no painel de navegação do Centro de administração do Microsoft 365, selecione **Mostrar todos**.

1. Em Centros de administração, selecione **Segurança**.  A página inicial do Portal do Microsoft 365 Defender vai ser aberta no navegador.  

1. À esquerda no painel de navegação do portal do Microsoft 365 Defender, selecione **Permissões e funções**.  Pode ser necessário rolar a página para ver essa opção.

1. Na página Permissões e funções, em **Email e funções de colaboração**, selecione **Funções**.

1. Na barra de pesquisa, insira **Risco interno** e selecione o ícone de pesquisa (lupa).  Observe as cinco funções exibidas.  Cada uma delas tem diferentes níveis de acesso.  Selecione **Gerenciamento de risco interno**. 

1. Na janela aberta, próximo de Membros, selecione **Editar**.

1. Para adicionar mesmos a esse grupo de função, selecione **Escolher membros**.

1. Selecione **+ Adicionar** na parte superior da página.

1. A partir da lista de nomes, selecione **Administrador MOD**, **Megan Bowen**, e depois **Adicionar** na parte inferior da página. Então, selecione **Concluído** na parte inferior da página.

1. Verifique se os membros adicionados estão corretos e selecione **Salvar**.

1. Na parte inferior da janela Gerenciamento de Risco Interno, selecione **Fechar**.

1. Mantenha essa guia do navegador aberta; vamos voltar a ela na próxima tarefa.


#### Tarefa 2 (PULAR se já tiver feito a tarefa do laboratório de configuração do log de auditoria): O gerenciamento de risco interno usa logs de auditoria do Microsoft 365 para insights do usuário e atividades identificadas nas políticas e insights de análise. Nesta tarefa, vamos habilitar a Capacidade de pesquisa do log de auditoria. Observação:  Depois de ativar a pesquisa de log de auditoria, pode levar algumas horas até podermos gerar resultados a partir da pesquisa de log de auditoria.  Apesar de poder levar algumas horas até podermos pesquisar o log de auditoria, isso não afeta a possibilidade de concluir outras tarefas neste laboratório.

1. Selecione a guia do navegador rotulada **Centro de administração do Microsoft 365 - Página Inicial**.  Se você tiver fechado essa guia, abra o Microsoft Edge e insira **admin.microsoft.com** na barra de endereços. Entre com as suas credenciais de administrador.

1. Em Centros de administração, selecione **Conformidade**.  A página inicial do centro de conformidade do Microsoft 365 vai ser aberta no navegador.  

1. À esquerda no painel de navegação do centro de conformidade do Microsoft 365, selecione **Mostrar todos**.

1. Do lado esquerdo do painel de navegação, em soluções, selecione **Auditoria**.

1. Verifique se a guia **Pesquisa** está selecionada (sublinhada).

1. Após abrir a página Auditoria, aguarde de 2 a 3 minutos.  Se a Auditoria NÃO estiver habilitada, você vai ver uma barra azul no topo da página dizendo começar a registrar atividade de usuário e administrador.  Selecione **Começar a registrar atividade de usuário e administrador**.  Quando a auditoria estiver habilitada, a barra azul desaparece.  Se a barra azul não aparecer, é porque a auditoria já está habilitada e não é necessário realizar nenhuma ação adicional.

1. Volte à página inicial do centro de conformidade do Microsoft 365 selecionando **Página Inicial** à esquerda no painel de navegação.

1. Deixe essa guia do navegador aberta; vamos usá-la na próxima tarefa.

#### Tarefa 3: Nesta tarefa, vamos acompanhar as configurações associadas à solução de Gerenciamento de Risco Interno.  As configurações de gerenciamento de risco interno se aplicam a todas as políticas de gerenciamento de risco interno, independentemente do modelo escolhido ao criar a política. 

1. Você deve estar na página inicial do centro de conformidade do Microsoft 365. Se não estiver, abra a guia do navegador **Página Inicial - Conformidade do Microsoft 365**.

1. Do lado esquerdo do painel de navegação, em Soluções, selecione **Gerenciamento de risco interno**.

1. Antes de começar a configurar a política, algumas configurações precisam ser realizadas.  Na página Gerenciamento de Risco Interno, selecione o **ícone de engrenagem de configurações** no canto superior direito da página para acessar as configurações de Risco Interno.  
    1. Guia Privacidade:  para usuários que realizam atividades correspondentes às políticas de risco interno, essa configuração vai determinar se é desejável mostrar nomes reais ou usar versões anônimas para mascarar a identidade.  Selecione **Não mostrar versões anônimas de nomes de usuários** e depois **Salvar**.  Selecione a guia **Indicadores de política**.
    
    1. Guia Indicadores de política: Quando ocorre um evento gatilho de política, atividades que mapeiam os indicadores selecionados são usadas para determinar a pontuação de risco para o usuário. Os Indicadores de política selecionados aqui são incluídos nos modelos de Política de risco interno.  Role a página para exibir todos os indicadores disponíveis e as informações relacionadas. Em **Indicares do Office**, selecione **Selecionar todos** e depois **Salvar**.  Selecione a guia **Períodos de tempo de política**.
    1. Guia Períodos de tempo de política:  Os períodos de tempo escolhidos aqui entram em vigor ao usuário quando é disparada alguma correspondência a uma política de risco interno.   A janela Ativação determina por quanto tempo as políticas detectam ativamente as atividades para usuários e é disparada quando um usuário realiza a primeira atividade correspondente a uma política. A Detecção de atividades anteriores determina até que ponto a política deve voltar para detectar atividades de usuário e é disparada quando um usuário realiza a primeira atividade correspondente a uma política.  Mantenha os valores padrão.  Selecione a guia **Detecções inteligentes**.
    1. Guia Detecções inteligentes:  Verifique as opções aqui.  Observe as configurações dos domínios e como elas são relacionadas aos indicadores.
    1. Outros itens listados nas configurações são versões preliminares.  Explorar esses itens a seu critério e observe que, enquanto versão preliminar, eles estão sujeitos a mudanças.

1. Para voltar à visão geral do Gerenciamento de risco interno, selecione **Gerenciamento de risco interno** no canto superior esquerdo da página, acima de Configurações.

1. Deixe essa guia do navegador aberta; vamos usá-la na próxima tarefa.

#### Tarefa 4:  Nesta tarefa, vamos acompanhar a criação de uma política.

1. Você deve estar na página Gerenciamento de risco interno.  Se não estiver, abra a guia do navegador rotulada **Gerenciamento de risco interno - Conformidade do Microsoft 365**.

1. Na página Visão geral do gerenciamento de risco interno, selecione a guia **Políticas** e depois **+ Criar**.  Configure cada uma das guias de política a seguir.

    1. Modelo de política:  Na lista de categorias, selecione **Vazamento de dados** e depois **Vazamentos de dados gerais**.  Observe que os modelos dentro das categorias podem ter pré-requisitos adicionais.  Leia os detalhes associados a este modelo e depois selecione **Avançar**.
    
    1. Nome e descrição:  insira um nome **SC900-PolíticaDeRiscoInterno** e depois selecione **Avançar**.
    1. Usuários e grupos:  Verifique a caixa de informações.  Mantenha as configurações padrão **Incluir todos os usuários e grupos**.  Selecione **Avançar**.
    1. Conteúdo a ser priorizado: Leia a descrição. Selecione **Eu quero especificar sites do SharePoint, rótulos de confidencialidade e/ou tipos de informações confidenciais como conteúdo prioritário** e depois selecione **Avançar**.
        1. Site do SharePoint: Para este exemplo de política, deixe em branco e selecione **Avançar**
        1. Tipos de informações confidenciais: para este exemplo de política, deixe em branco e selecione **Avançar**. 
        1. Rótulos de confidencialidade: selecione **+ Adicionar ou editar rótulos de confidencialidade**.  Selecione os rótulos listados:  **Finanças Confidenciais** e **Altamente confidencial/Projeto – Falcon**; selecione **Adicionar** e depois **Avançar**.
    1. Indicadores e evento disparador: Verifique as informações detalhadas.  A política é disparada quando o usuário desempenha uma atividade de exfiltração conforme definido (selecione os ícones de informação para cada marcador da lista para mais detalhes) OU uma correspondência a uma política existente de Prevenção Contra Perda de Dados (DLP).  Como você não tem nenhuma política DLP configurada como parte deste exercício, selecione **O usuário desempenha uma atividade de exfiltração**.  Role a página para exibir o que é selecionado automaticamente.  Observe que os indicadores da política que nós habilitamos na tarefa anterior estão marcados.   Lembre-se de que esses indicadores só vão ser ativados quando a política for disparada e as atividades que mapeiam esses indicadores vão ser usadas para calcular a pontuação de risco para o usuário.  Além disso, a Detecção de sequência está habilitada.  Se, conforme definido, uma sequência de atividades for detectada, é indicado um risco maior.  Selecione o ícone de informação para informações detalhadas sobre quais indicadores são exigidos.  Essa seleção exige que certos indicadores sejam selecionados e que os dispositivos estejam integrados.  Para facilitar e porque não temos dispositivos integrados neste locatário, desmarque **Selecionar todos**.  Selecione **Avançar**.
    1. Limites dos Indicadores:  aqui é possível especificar limites padrão ou personalizar os limites associados aos indicadores.  Lembre-se de que os indicadores são ativados apenas depois que a política é disparada, então esses limites não influenciam no disparo da política. Selecione **Especificar limites personalizados**. Ao selecionar essa opção, é possível verificar os valores padrão atuais. Mantenha o padrão e selecione **Avançar**.  
    1. Concluir:  verifique as configurações, selecione **Enviar** e depois **Concluído**.

1. Estamos de volta à guia Políticas da página Gerenciamento de risco interno.  A política que acabamos de criar aparecerá listada.  

1. Na política recém-criada, o campo “Usuários no escopo” representa os usuários a que são atribuídas pontuações de risco pela política.  A atribuição de pontuações de risco aos usuários ocorre quando a política é disparada, por isso o valor está indicando 0.  Um administrador pode configurar que a política comece a atribuir pontuações de risco a usuários específicos, com base na atividade detectada pelas políticas selecionadas, E que ignora o requisito de que um evento disparador deve ser detectado primeiro.  Para fazer isso, selecione o círculo vazio próximo ao nome da política para selecionar a política. Depois, selecione **Começar atividade de pontuação para os usuários**, que aparece acima da tabela da política.  Preencha todos os campos e depois selecione **Começar a atividade de pontuação**.  Pode levar 24 horas para os usuários aparecerem na guia ‘Usuários’. Após esse período, é possível selecionar os usuários a partir dessa guia para verificar as atividades detectadas.

#### Revisão
Neste laboratório, acompanhamos o processo de configuração de uma política de gerenciamento de risco interno, junto com os pré-requisitos básicos para configurar e utilizar políticas de gerenciamento de risco interno.
