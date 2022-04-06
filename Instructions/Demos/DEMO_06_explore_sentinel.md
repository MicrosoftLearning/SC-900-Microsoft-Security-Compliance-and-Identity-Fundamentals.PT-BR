---
Demo:
  title: Microsoft Sentinel
  module: 'Module 3 Lesson 3: Describe the capabilities of Microsoft security solutions: Describe security capabilities of Microsoft Sentinel'
ms.openlocfilehash: 607c8097d17041f711aa1f40601e8433fcfce7f0
ms.sourcegitcommit: a341c2fc38e9b37dafb792d82e3c948f7ba4a099
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2022
ms.locfileid: "137893771"
---
# <a name="demo-microsoft-sentinel"></a>Demonstração: Microsoft Sentinel 

### <a name="demo-scenario"></a>Cenário da demonstração
Nesta demonstração, vamos passar pelo processo de criação de uma instância do Microsoft Sentinel.  Também vamos configurar as permissões para garantir o acesso aos recursos que serão implantados para dar suporte ao Microsoft Sentinel.  Depois dessa configuração básica, veremos as etapas necessárias para conectar o Microsoft Sentinel às suas fontes de dados e usar funções analíticas integradas para receber notificações sobre suspeitas. Por último, vamos explorar os recursos de automação.  

#### <a name="demo-part-1--create-an-microsoft-sentinel-instance"></a>Demonstração – Parte 1:  Criar uma instância do Microsoft Sentinel

1. Abra a guia do navegador, **Página Inicial – Microsoft Azure**.  Se você fechou a guia anteriormente, abra uma página do navegador e, na barra de endereços, insira portal.azure.com e entre novamente.

1. Na caixa de pesquisa, na barra azul no topo da página, perto de onde está escrito Microsoft Azure, digite **Microsoft Sentinel** e selecione **Microsoft Sentinel** nos resultados da pesquisa.

1. Na página do Microsoft Sentinel, selecione **Criar Microsoft Sentinel**.

1. Na página Adicionar o Microsoft Sentinel a um workspace, selecione **Criar um workspace**.

1. Na guia Básico da página Criar espaço de trabalho do Log Analytics, insira:
    1. Assinatura:  **Azure Pass – Sponsorship**
    1. Grupo de recursos: selecione **Criar novo**, insira o nome **SC900-Sentinel-RG** e clique em **OK**.
    1. Nome: **SC900-LogAnalytics-workspace**.
    1. Região: **Leste dos EUA** (manter padrão)
    1. Selecione **Avançar: Tipo de preço >**

1. Para o Tipo de Preço, deixe as configurações padrão: **Pago conforme o uso (por GB 2018)** . Depois, selecione **Avançar: Marcas >** .

1. Pode deixar Marcas em branco. Depois, selecione **Revisar + Criar**.

1. Verifique as informações inseridas e selecione **Criar**.

1. Pode levar um ou dois minutos até que o novo workspace seja listado; caso ele ainda não seja exibido, selecione **Atualizar** e depois **Adicionar**.

1. Uma vez que o espaço de trabalho estiver adicionado, a página Microsoft Sentinel | Notícias e Guias será exibida.  Veja as três etapas listadas na página de Introdução.

1. Deixe essa página aberta; vamos usá-la na próxima tarefa.

#### <a name="demo-part-2--with-the-microsoft-sentinel-instance-created-you-will-want-to-make-sure-that-you-have-the-necessary-access-to-the-resources-that-get-deployed-to-support-microsoft-sentinel--in-this-task-you-will-go-to-the-access-control-iam-page-for-the-resource-group-that-you-created-with-the-instance-of-microsoft-sentinel-view-the-available-roles-and-assign-yourself-mod-administrator-the-required-role-assigning-the-role-at-the-resource-group-level-will-ensure-the-role-will-apply-to-all-the-resources-that-are-deployed-to-support-microsoft-sentinel"></a>Demonstração — Parte 2:  Com a instância do Microsoft Sentinel criada, é prudente verificar se você tem o acesso necessário aos recursos implantados para dar suporte ao Microsoft Sentinel.  Nesta tarefa, vamos abrir a página de controle de acesso (IAM) do grupo de recursos criado com a instância do Microsoft Sentinel, visualizar as funções disponíveis e atribuir a você a função necessária (administrador MOD). Atribuir a função a nível do grupo de recursos vai garantir que ela seja aplicada a todos os recursos implantados para comportar o Microsoft Sentinel.

1. Na caixa de pesquisa, na barra azul no topo da página, perto de onde está escrito Microsoft Azure, digite **grupos de recursos** e selecione **Grupos de recursos** nos resultados da pesquisa.

1. Na página de Grupos de recursos, selecione o grupo de recursos que você criou com o Microsoft Sentinel, **SC900-Sentinel-RG**.

1. Na página do SC900-Sentinel-RG, selecione **Controle de acesso (IAM)** no painel de navegação à esquerda.

1. Na página Controle de acesso, selecione **Exibir meu acesso**.  Veja que a função atual é de Administrador de serviços.  Feche a janela de atribuições do Administrador MOD selecionando o **X** no canto superior direito da tela.

1. Na página Controle de acesso, selecione **+Adicionar** e depois **Adicionar atribuição de função**.

1. A janela Adicionar atribuição de função vai ser aberta.  Selecione a seta para baixo no campo Selecionar função para exibir as funções disponíveis. Na caixa de pesquisa de seleção de função, digite **Microsoft Sentinel** para ver as quatro funções associadas ao Microsoft Sentinel. Como prática recomendada, você deve atribuir o privilégio mínimo exigido para a função.  Para os fins deste laboratório, digite **Proprietário** na caixa de pesquisa e selecione **Proprietário** nos resultados.  Verifique as permissões no Microsoft Sentinel para referência:  https://docs.microsoft.com/en-us/azure/sentinel/roles

1. Na lista de usuários exibida, selecione **Administrador MOD**.

1. Escolha **Salvar** na parte inferior da página.

1. Na página de Controle de acesso, selecione **Exibir meu acesso** para confirmar que a função foi adicionada. Em seguida, feche a janela selecionando o **X** no canto superior direito.

#### <a name="demo-part-3--in-this-part-of-the-demo-you-will-walk-through-the-process-of-connecting-microsoft-sentinel-to-your-data-source-to-begin-to-collect-data--note-it-can-take-a-bit-time-to-show-the-connected-status-of-a-connector-30-minutes-depending-on-the-tenant"></a>Demonstração — Parte 3:  Nesta parte da demonstração, você verá como é o processo para conectar o Microsoft Sentinel com a sua fonte de dados para começar a coletar dados.  Observação: pode levar algum tempo para o conector ter o status alterado para conectado (~30 minutos dependendo do locatário).

1. Na caixa de pesquisa, na barra azul no topo da página, perto de onde está escrito Microsoft Azure, digite **Microsoft Sentinel** e selecione **Microsoft Sentinel** nos resultados da pesquisa.

1. Na página Microsoft Sentinel, selecione o espaço de trabalho criado com a instância do Microsoft Sentinel, **SC900-LogAnalytics-workspace**.

1. A primeira etapa com o Microsoft Sentinel é conseguir coletar dados. À esquerda no painel de navegação, em configuração, selecione **Conectores de dados**.

1. Na página Conectores de dados, role para baixo na janela principal para exibir a extensa lista de conectores disponíveis. Na caixa Pesquisar da página dos conectores de dados, insira **Azure** e selecione **Azure Active Directory** na lista de resultados.

1. A janela do conector do Azure Active Directory será aberta.  Clique em **Abrir página do conector**.

1. Na página Conector do Azure Active Directory, verifique a descrição e observe o conteúdo relacionado, incluindo pastas de trabalho, consultas e modelos de regras analíticas.  

1. A guia de instruções, na janela principal, apresenta os pré-requisitos para integrar o Microsoft Sentinel ao Azure Active Directory.   Em configuração, selecione **Logs de entrada** e depois Aplicar Mudanças (é possível escolher múltiplos conectores).  Observação: pode levar um tempo até que o status do conector seja exibido como conectado (aproximadamente 30 minutos ou mais).  Como referência:
    1. Revisar as permissões no Microsoft Sentinel:  https://docs.microsoft.com/en-us/azure/sentinel/roles
    1. Conectar o Azure Active Directory:  https://docs.microsoft.com/en-us/azure/sentinel/connect-azure-active-directory

1. Na guia Próximas etapas, observe a lista de pastas de trabalho recomendadas.   Nas pastas de trabalho recomendadas, selecione **Logs de entrada do Azure** (é possível escolher pastas de trabalho adicionais).

1. Na página de pastas de trabalho e com a guia de modelos selecionada (sublinhada), selecione **Logs de entrada do Azure**.

1. Na janela Logs de entrada do Azure aberta, verifique a descrição e selecione **Exibir modelo**.  Saia do modelo selecionando o **X** no canto superior direito da tela.  Selecione **Salvar** na parte inferior da página e depois **OK** para salvar a pasta de trabalho na localização padrão.

1. No canto superior esquerdo da página Pastas de trabalho, acima de onde está escrito Pastas de trabalho, clique em **Microsoft Sentinel**. Você vai voltar à página Conectores de Dados do Microsoft Sentinel.

1. O topo da página Conectores de dados deve exibir 1 conexão, indicando que agora você se conectou ao Azure Active Directory.

1. À esquerda no painel de navegação, selecione **Pastas de trabalho**.

1. Na página Pastas de trabalho, selecione a guia **Minhas pastas de trabalho**, que fica acima da caixa de pesquisa.  A pasta de trabalho que você acaba de salvar está listada e disponível para exibir e monitorar seus dados.  Os próximos logons serão refletidos na pasta de trabalho; você pode escolher mostrar essas informações.

1. Deixe essa página aberta; vamos usá-la na próxima tarefa.

#### <a name="demo-part-4-optional--in-this-part-of-the-demo-you-will-walk-through-the-process-of-using-a-built-in-analytics-rule-template-to-create-a-rule-to-get-notified-when-something-suspicious-occurs"></a>Parte 4 da demonstração (opcional):  Nesta parte da demonstração, você verá como é o processo de usar um modelo de regra analítica integrado para criar uma regra e ser notificado quando ocorrer algo suspeito.

1. À esquerda no painel de navegação, selecione **Análise**.

1. A página Análise mostra regras ativas (a Detecção avançada de ataques multiestágio está habilitada por padrão) e permite acessar os modelos de Regras.  Selecione a guia **Modelos de regras**.  Observe a lista de modelos disponíveis e as diferentes formas de filtrar essa lista.  Com os alertas internos de análise no workspace do Microsoft Sentinel, você será notificado quando algo suspeito ocorrer.

1. Na barra de pesquisa, insira **Portal do Azure**.  Selecione **Falha de logon no Portal do Azure**.  

1. Na janela que abrir, leia a descrição e as informações associadas ao modelo.  Selecione **Criar regra** na parte inferior da página.
    1. No Assistente de regra de análise, revise as informações e selecione **Avançar: Definir lógica de regra >** .
    1. A página Definir lógica de regra é onde você define a lógica da nova regra de análise. O modelo já apresenta algumas lógicas e configurações predefinidas.  Role a página para verificar as configurações disponíveis.  Mantenha as configurações padrão. Selecione **Avançar: Configurações de incidente (versão prévia)>** .
    1. Com as Configurações de incidentes, é possível agrupar os alertas do Microsoft Sentinel em um único Incidente a ser analisado. Você pode definir se os alertas disparados por essa regra de análise devem gerar incidentes.  Mantenha o padrão e selecione **Avançar: Resposta automatizada >** .
    1. Na guia Resposta automatizada, observe que é possível adicionar um guia estratégico para automatizar a resposta.  Do mesmo modo, também é possível criar uma regra de automatização de incidente.  Selecione **+ Adicionar** novo em Automação de incidentes.  Uma janela vai ser aberta para criar a nova regra de automação.  Qualquer regra de automação criada nesta página é disparada pela regra analítica selecionada originalmente, que neste caso é Falha de logon no Portal do Azure.  Observe que é possível adicionar condições e definir ações para a regra.   Selecione **Cancelar** para sair dessa janela.
    1. Selecione **Avançar: Revisão>** para revisar todos os detalhes relacionados à regra com base no modelo escolhido. Aqui, é possível escolher se você quer criar a regra, selecionando **Criar**, ou sair sem criar a regra, selecionando **X** no canto superior direito da página.

1. Deixe essa página aberta; vamos usá-la na próxima tarefa.

#### <a name="demo-step-5-optional--in-the-previous-step-you-created-an-analytics-rule-to-be-alerted-of-suspicious-activities--embedded-in-that-wizard-is-the-option-to-automate-the-response-to-an-incident-based-on-the-specific-rule--but-you-can-also-create-automation-rules-by-going-directly-to-the-automation-configuration-option"></a>Parte 5 da demonstração (opcional):  Na etapa anterior, você criou uma regra analítica para ser alertado a respeito de atividades suspeitas.  O assistente também permite automatizar a resposta a um incidente com base nessa regra específica.  Você também pode criar regras de automação diretamente na opção de configuração de automação.

1. À esquerda no painel de navegação, selecione **Automação**.  

1. Selecione **+ Criar**. No menu suspenso, observe que é possível adicionar tanto um novo guia estratégico quanto uma nova regra.  Selecione **Adicionar nova regra**.  
    1. Uma janela vai ser aberta para criar a nova regra de automação.  Observe que é possível adicionar condições e definir ações para a regra.  A única diferença é que a primeira condição é associar as regras de análise a que você quer aplicar essa regra de automação.  Ela aparecia acinzentada na tarefa anterior porque a automação estava sendo configurada para a regra específica.  Selecione **Cancelar** para sair da janela Criar nova regra de automação.

1. Deixe essa página aberta; vamos usá-la na próxima tarefa.

#### <a name="step-6-tear-down---instructor-do-this-step-after-class-delete-microsoft-sentinel-resource-group--microsoft-sentinel-is-billed-based-on-the-volume-of-data-ingested-for-analysis-in-microsoft-sentinel-although-the-amount-of-data-ingested-as-a-result-of-this-lab-is-minimal-it-is-recommended-that-you-delete-the-microsoft-sentinel-resource-group-when-you-are-done-exploring-the-features-of-capabilities-of-microsoft-sentinel"></a>Etapa 6: DESATIVAÇÃO – Instrutor realiza esta etapa após a aula. Excluir grupo de recursos do Microsoft Sentinel.  O Microsoft Sentinel é cobrado de acordo com o volume da ingestão de dados para análise. Embora a quantidade de dados ingeridos durante este laboratório seja mínima, recomendamos que o grupo de recursos do Microsoft Sentinel seja excluído quando você terminar de explorar suas funcionalidades.

1. No canto superior esquerdo da página Microsoft Sentinel, em cima de Microsoft Sentinel, selecione **Todos os Serviços**.

1. Na caixa para filtrar serviços, insira grupos de recursos e selecione **Grupos de recursos** na lista gerada.

1. Na página de Grupos de recursos, selecione o grupo de recursos que você criou com o Microsoft Sentinel, **SC900-Sentinel-RG**.

1. Na parte superior central da página, selecione **Excluir grupo de recursos**.  Verifique o aviso de segurança.  Insira o nome do grupo de recursos, **SC900-Sentinel-RG**, e clique em **Excluir** na parte inferior da página.  Vai levar alguns minutos para excluir o grupo de recursos.

1. Após verificar que o grupo de recursos foi excluído, feche a página do navegador. 

#### <a name="review"></a>Revisão

Nesta demonstração, você mostrou o processo de criação de uma instância do Microsoft Sentinel.  Você também mostrou como configurar as permissões para garantir o acesso aos recursos associados à sua instância do Microsoft Sentinel.  Com a instância do Microsoft Sentinel criada, você percorreu as etapas necessárias para conectar o Microsoft Sentinel a fontes de dados, descobriu como usar regras analíticas integradas para receber notificações sobre suspeitas e, por último, explorou os recursos de automação. Você concluiu a demonstração excluindo o grupo de recursos associado à instância do Microsoft Sentinel que criou.