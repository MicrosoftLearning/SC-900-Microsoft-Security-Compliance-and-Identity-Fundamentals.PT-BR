---
Demo:
    title: 'Microsoft Sentinel'
    module: 'Módulo 3 – Lição 3: Descrever as funcionalidades das soluções de segurança da Microsoft Descrever os recursos de segurança do Microsoft Sentinel'
---


# Demonstração: Microsoft Sentinel 

### Cenário da demonstração
Nesta demonstração, vamos passar pelo processo de criação de uma instância do Microsoft Sentinel.  Também vamos configurar as permissões para garantir o acesso aos recursos que serão implantados para dar suporte ao Microsoft Sentinel.  Depois dessa configuração básica, veremos as etapas necessárias para conectar o Microsoft Sentinel às suas fontes de dados e usar funções analíticas integradas para receber notificações sobre suspeitas. Por último, vamos explorar os recursos de automação.  

#### Parte 1 da demonstração:  Criar uma instância do Microsoft Sentinel

1. Abra a guia do navegador **Home-Microsoft Azure**.  Se você fechou a guia anteriormente, abra uma página do navegador e, na barra de endereços, insira portal.azure.com e entre novamente.

1. Na caixa de pesquisa, na barra azul no topo da página, perto de onde está escrito Microsoft Azure, digite **Sentinel** e selecione **Microsoft Sentinel** nos resultados da pesquisa.

1. Na página do Microsoft Sentinel, selecione **Criar Microsoft Sentinel**.

1. Na página Adicionar o Microsoft Sentinel a um workspace, selecione **Criar um novo workspace**.

1. Na guia básica Criar workspace do Log Analytics, insira o seguinte:
    1. Assinatura:  **Azure Pass – Sponsorship**
    1. Grupo de recursos: selecione **Criar novo**, insira o nome **SC900-Sentinel-RG** e clique em **OK**.
    1. Nome: **SC900-LogAnalytics-workspace**.
    1. Região: **Leste dos EUA** (manter padrão)
    1. Selecione **Avançar: Tipo de preço >**

1. Para o Tipo de Preço, deixe as configurações padrão: **Pagamento conforme o uso (por GB 2018)**. Depois, selecione **Avançar: Tags >**.

1. Para as tags, você pode deixar a opção em branco e selecionar **Revisar + Criar**.

1. Verifique as informações inseridas e clique em **Criar**.

1. Pode levar um ou dois minutos até que o novo workspace seja listado; caso ele ainda não seja exibido, selecione **Atualizar** e depois **Adicionar**.

1. Assim que o novo workspace for adicionado, a página Novidades | e Guias do Microsoft Sentinel será exibida.  Veja as três etapas listadas na página de Introdução.

1. Mantenha esta página aberta, pois ela será usada na próxima tarefa.

#### Parte 2 da demonstração:  Com a instância do Microsoft Sentinel criada, é prudente verificar se você tem o acesso necessário aos recursos implantados para dar suporte ao Microsoft Sentinel.  Nesta tarefa, você vai entrar na página de controle de acesso (IAM) do grupo de recursos criado com a instância do Microsoft Sentinel, verificar os papéis disponíveis e atribuir a você a função necessária (administrador de MOD). A atribuição do papel no nível do grupo de recursos garante que ele será aplicado a todos os recursos implantados para dar suporte ao Microsoft Sentinel.

1. Na caixa de pesquisa, na barra azul no topo da página, perto de onde está escrito Microsoft Azure, digite **grupos de recursos** e selecione **Grupos de recursos** nos resultados da pesquisa.

1. Na página de Grupos de recursos, selecione o grupo de recursos que você criou com o Microsoft Sentinel, **SC900-Sentinel-RG**.

1. Na página do SC900-Sentinel-RG, selecione **Controle de acesso (IAM)** no painel de navegação à esquerda.

1. Na página de Controle de acesso, selecione **Exibir meu acesso**.  Veja que a função atual é de Administrador de serviços.  Feche a janela de atribuições de Administrador de MOD clicando no **X** do canto superior direito da janela.

1. Na página de Controle de acesso, selecione **+ Adicionar** e, em seguida, **Adicionar atribuição de função**.

1. A janela Adicionar atribuição de função é aberta.  Clique na seta suspensa do campo Selecionar uma função para exibir as funções disponíveis. Na caixa de pesquisa de seleção de função, digite **Microsoft Sentinel** para ver as quatro funções associadas ao Microsoft Sentinel. Uma prática recomendada é atribuir o menor privilégio necessário para a função.  Para os fins deste laboratório, digite **Proprietário** na caixa de pesquisa e selecione **Proprietário** nos resultados.  Como referência, revise as permissões no Microsoft Sentinel:  https://docs.microsoft.com/pt-br/azure/sentinel/roles

1. Na lista de usuários exibida, selecione **Administrador MOD**.

1. Selecione **Salvar** na parte inferior da página.

1. Na página de controle de acesso, selecione **Exibir meu acesso** para confirmar a função adicionada. Depois, feche a janela selecionando o **X** no canto superior direito.

#### Parte 3 da demonstração:  Nesta parte da demonstração, você verá como é o processo para conectar o Microsoft Sentinel com a sua fonte de dados para começar a coletar dados.  Observação: pode levar um tempo até que o status de um conector seja exibido como conectado (aproximadamente 30 minutos, dependendo do locatário).

1. Na caixa de pesquisa, na barra azul no topo da página, perto de onde está escrito Microsoft Azure, digite **Sentinel** e selecione **Microsoft Sentinel** nos resultados da pesquisa.

1. Na página do Microsoft Sentinel, selecione o workspace que você criou com a instância do Microsoft Sentinel, **SC900-LogAnalytics-workspace**.

1. A primeira etapa com o Microsoft Sentinel é conseguir coletar dados. À esquerda no painel de navegação, em configuração, selecione **Conectores de dados**.

1. Na página Conectores de dados, role para baixo na janela principal para exibir a extensa lista de conectores disponíveis. Na caixa Pesquisar da página dos conectores de dados, insira **Azure** e selecione **Azure Active Directory** na lista de resultados.

1. A janela do conector do Azure Active Directory será aberta.  Selecione **Abrir página do conector**.

1. Na página Conector do Azure Active Directory, verifique a descrição e observe o conteúdo relacionado, incluindo pastas de trabalho, consultas e modelos de regras analíticas.  

1. A guia de instruções, na janela principal, apresenta os pré-requisitos para integrar o Microsoft Sentinel ao Azure Active Directory.   Em configuração, selecione **Logs de entrada** e depois Aplicar Mudanças (é possível escolher múltiplos conectores).  Observação: pode levar um tempo até que o status do conector seja exibido como conectado (aproximadamente 30 minutos ou mais).  Como referência:
    1. Reveja as Permissões no Microsoft Sentinel:  https://docs.microsoft.com/pt-br/azure/sentinel/roles
    1. Conectar o Azure Active Directory:  https://docs.microsoft.com/pt-br/azure/sentinel/connect-azure-active-directory

1. Na guia Próximas etapas, veja a lista de pastas de trabalho recomendadas.   Na seção Pastas de trabalho recomendadas, selecione **Logs de entrada do Azure** (outras pastas de trabalho podem ser selecionadas).

1. Na página de pastas de trabalho e com a guia “Modelos” selecionada (sublinhada), selecione **Logs de entrada do Azure**.

1. Na janela de logs de entrada do Azure AD que será aberta, revise a descrição e selecione **Exibir modelo**.  Saia do modelo clicando no **X** do canto superior direito da tela.  Selecione **Salvar** na parte inferior da página e clique em **OK** para salvar a pasta de trabalho no local padrão.

1. No canto superior esquerdo da página Pastas de trabalho, acima de onde está escrito Pastas de trabalho, selecione **Microsoft Sentinel**. Você voltará para a página Conectores de dados do Microsoft Sentinel.

1. A parte superior dessa página deve mostrar a mensagem “1 conectado”, informando que você agora está conectado ao Azure Active Directory.

1. À esquerda no painel de navegação, selecione **Pastas de trabalho**.

1. Na página Pastas de trabalho, selecione a guia **Minhas pastas de trabalho**, que fica acima da caixa de pesquisa.  A pasta de trabalho que você acaba de salvar está listada e disponível para exibir e monitorar seus dados.  Os próximos logons serão refletidos na pasta de trabalho; você pode escolher mostrar essas informações.

1. Mantenha esta página aberta, pois ela será usada na próxima tarefa.

#### Parte 4 da demonstração (opcional):  Nesta parte da demonstração, você verá como é o processo de usar um modelo de regra analítica integrado para criar uma regra e ser notificado quando ocorrer algo suspeito.

1. No painel de navegação à esquerda, selecione **Análises**.

1. A página de Análises mostrará regras ativas (a detecção avançada de ataques em vários estágios é ativada por padrão), além de dar acesso aos modelos de regras.  Selecione a guia **Modelos de regras**.  Observe a lista de modelos disponíveis e as diferentes formas de filtrar essa lista.  Com os alertas internos de análise no espaço de trabalho do Microsoft Sentinel, você recebe uma notificação quando algo suspeito acontece.

1. Na barra de pesquisa, insira **Portal do Azure**.  Selecione **Falha de logon no Portal do Azure**.  

1. Na janela que abrir, leia a descrição e as informações associadas ao modelo.  Selecione **Criar regra** na parte inferior da página.
    1. No Assistente de regra de análise, revise as informações e selecione **Avançar: Definir lógica de regra >**.
    1. A página Definir lógica de regra é onde você define a lógica da nova regra de análise. O modelo já apresenta algumas lógicas e configurações predefinidas.  Role a página para verificar as configurações disponíveis.  Mantenha as configurações padrão. Selecione **Avançar: Configurações de incidentes (prévia)>**.
    1. Com as Configurações de incidentes, é possível agrupar os alertas do Microsoft Sentinel em um único Incidente a ser analisado. Você pode definir se os alertas disparados por essa regra de análise devem gerar incidentes.  Mantenha o padrão e selecione **Avançar: Resposta automatizada >**.
    1. Na guia Resposta automatizada, observe que é possível adicionar um guia estratégico para automatizar a resposta.  Do mesmo modo, também é possível criar uma regra de automatização de incidente.  Selecione **+Adicionar** novo em automação de incidente.  Uma janela será aberta para criar a nova regra de automação.  Qualquer regra de automação criada nesta página é disparada pela regra analítica selecionada originalmente, que neste caso é Falha de logon no Portal do Azure.  Observe que é possível adicionar condições e definir ações para a regra.   Selecione **Cancelar** para sair dessa janela.
    1. Selecione **Avançar: Revisão>** para revisar todos os detalhes relacionados à regra com base no modelo escolhido. Aqui, é possível escolher se você quer criar a regra, selecionando **Criar**, ou sair sem criar a regra, selecionando **X** no canto superior direito da página.

1. Deixe essa página aberta; vamos usá-la na próxima tarefa.

#### Parte 5 da demonstração (opcional):  Na etapa anterior, você criou uma regra analítica para ser alertado a respeito de atividades suspeitas.  O assistente traz a opção integrada de automatizar a resposta a um incidente com base na regra específica.  No entanto, você também pode criar regras de automação acessando diretamente a opção de configuração de automação.

1. No painel de navegação à esquerda, selecione **Automação**.  

1. Selecione **+ Criar**. No menu suspenso, observe que é possível adicionar tanto um novo guia estratégico quanto uma nova regra.  Selecione **Adicionar nova regra**.  
    1. Uma janela será aberta para criar a nova regra de automação.  Observe que é possível adicionar condições e definir ações para a regra.  A única diferença é que a primeira condição é associar as regras de análise a que você quer aplicar essa regra de automação.  Ela aparecia acinzentada na tarefa anterior porque a automação estava sendo configurada para a regra específica.  Selecione **Cancelar** para sair da janela Criar nova regra de automação.

1. Deixe essa página aberta; vamos usá-la na próxima tarefa.

#### Etapa 6: DESATIVAÇÃO – Instrutor realiza esta etapa após a aula. Exclua o Grupo de recursos do Microsoft Sentinel.  O Microsoft Sentinel é cobrado de acordo com o volume da ingestão de dados para análise no Microsoft Sentinel. Embora a quantidade de dados ingeridos durante este laboratório seja mínima, recomendamos que o grupo de recursos do Microsoft Sentinel seja excluído quando você terminar de explorar suas funcionalidades.

1. No canto superior esquerdo da página do Microsoft Sentinel, em cima de Microsoft Sentinel, selecione **Todos os Serviços**.

1. Na caixa para filtrar serviços, insira grupos de recursos e selecione **Grupos de recursos** na lista fornecida.

1. Na página de Grupos de recursos, selecione o grupo de recursos que você criou com o Microsoft Sentinel, **SC900-Sentinel-RG**.

1. No centro superior da página, selecione **Excluir grupo de recursos**.  Verifique o aviso de segurança.  Insira o nome do grupo de recursos, **SC900-Sentinel-RG**, e clique em **Excluir** na parte inferior da página.  A exclusão do grupo de recursos levará alguns minutos.

1. Depois de verificar que o grupo de recursos foi excluído, feche a página do navegador. 

#### Revisão

Nesta demonstração, você mostrou o processo de criação de uma instância do Microsoft Sentinel.  Você também mostrou como configurar as permissões para garantir o acesso aos recursos associados à sua instância do Microsoft Sentinel.  Com a instância do Microsoft Sentinel criada, você percorreu as etapas necessárias para conectar o Microsoft Sentinel a fontes de dados, descobriu como usar regras analíticas integradas para receber notificações sobre suspeitas e, por último, explorou os recursos de automação. Você concluiu a demonstração excluindo o grupo de recursos associado à instância do Microsoft Sentinel que criou.