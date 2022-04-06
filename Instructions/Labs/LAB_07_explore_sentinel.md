---
lab:
  title: Explorar o Microsoft Sentinel
  module: 'Module 3 Lesson 3: Describe the capabilities of Microsoft security solutions: Describe security capabilities of Microsoft Sentinel'
ms.openlocfilehash: c5a7ba866c82f15a4f78099326fd93a734caead8
ms.sourcegitcommit: a341c2fc38e9b37dafb792d82e3c948f7ba4a099
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2022
ms.locfileid: "137893747"
---
# <a name="lab-explore-microsoft-sentinel"></a>Laboratório: Explorar o Microsoft Sentinel 

## <a name="lab-scenario"></a>Cenário do laboratório
Neste laboratório, vamos passar pelo processo de criação de uma instância do Microsoft Sentinel.  Também vamos configurar as permissões para garantir o acesso aos recursos que serão implantados para dar suporte ao Microsoft Sentinel.  Depois dessa configuração básica, veremos as etapas necessárias para conectar o Microsoft Sentinel às suas fontes de dados e usar funções analíticas integradas para receber notificações sobre suspeitas. Por último, vamos explorar os recursos de automação.  

  

**Tempo estimado**: 30 a 45 minutos

#### <a name="task-1--create-an-microsoft-sentinel-instance"></a>Tarefa 1:  Criar uma instância do Microsoft Sentinel.

1. Abra o Microsoft Edge. Na barra de endereços, insira **portal.azure.com**.

2. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é sua ID de locatário exclusiva fornecida pelo provedor de hospedagem de laboratório) e selecione **Avançar**.
    
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem de laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**.

3. No canto superior esquerdo da tela, perto de Microsoft Azure, selecione o ícone para mostrar o menu (as três linhas horizontais, também conhecidas como ícone de hambúrguer). Depois, selecione **Todos os Serviços**.  

4. Na caixa para filtrar serviços, insira **Microsoft Sentinel** e selecione **Microsoft Sentinel** na lista.

5. Na página do Microsoft Sentinel, selecione **Criar Microsoft Sentinel**.

6. Na página Adicionar o Microsoft Sentinel a um workspace, selecione **Criar um workspace**.

7. Na guia Básico da página Criar espaço de trabalho do Log Analytics, insira:
    1. Assinatura:  **Azure Pass – Sponsorship**
   
    1. Grupo de recursos: selecione **Criar Novo**, insira o nome **SC900-ResourceGroup** e selecione **OK**.
    1. Nome: **SC900-LogAnalytics-workspace**.
    1. Região: **Leste dos EUA** (manter padrão)
    1. Selecione **Avançar: Tipo de preço >**

8. Para o Tipo de Preço, deixe as configurações padrão: **Pago conforme o uso (por GB 2018)** . Depois, selecione **Avançar: Marcas >** .

9. Pode deixar Marcas em branco. Depois, selecione **Revisar + Criar**.

10. Verifique as informações inseridas e selecione **Criar**.

11. Se você não encontrar o espaço de trabalho na lista, selecione **Atualizar** e selecione **Adicionar**.

12. Uma vez que o espaço de trabalho estiver adicionado, a página Microsoft Sentinel | Notícias e Guias será exibida.  Veja as três etapas listadas na página de Introdução.

13. Deixe essa página aberta; vamos usá-la na próxima tarefa.

#### <a name="task-2--with-the-microsoft-sentinel-instance-created-you-will-want-to-make-sure-that-you-have-the-necessary-access-to-the-resources-that-get-deployed-to-support-microsoft-sentinel--in-this-task-you-will-go-to-the-access-control-iam-page-for-the-resource-group-that-you-created-with-the-instance-of-microsoft-sentinel-view-the-available-roles-and-assign-yourself-mod-administrator-the-required-role-assigning-the-role-at-the-resource-group-level-will-ensure-the-role-will-apply-to-all-the-resources-that-are-deployed-to-support-microsoft-sentinel"></a>Tarefa 2:  Com a instância do Microsoft Sentinel criada, é prudente verificar se você tem o acesso necessário aos recursos implantados para dar suporte ao Microsoft Sentinel.  Nesta tarefa, vamos abrir a página de controle de acesso (IAM) do grupo de recursos criado com a instância do Microsoft Sentinel, visualizar as funções disponíveis e atribuir a você a função necessária (administrador MOD). Atribuir a função a nível do grupo de recursos vai garantir que ela seja aplicada a todos os recursos implantados para comportar o Microsoft Sentinel.

1. No canto superior esquerdo da página Microsoft Sentinel, em cima de Microsoft Sentinel, selecione **Todos os Serviços**.

2. Na caixa para filtrar serviços, insira grupos de recursos e selecione **Grupos de recursos** na lista gerada.

3. Na página Grupos de recursos, selecione o grupo de recursos que você criou com o Microsoft Sentinel, **SC900-ResourceGroup**.

4. Na página SC900-ResourceGroup, selecione **Controle de acesso (IAM)** , à esquerda no painel de navegação.

5. Na página Controle de acesso, selecione **Exibir meu acesso**.  Observe que a função atual é Administrador de segurança.  Feche a janela de atribuições do Administrador MOD selecionando o **X** no canto superior direito da tela.

6. Na página Controle de acesso, selecione **+Adicionar** e depois **Adicionar atribuição de função**.

7. A janela Adicionar atribuição de função vai ser aberta.  Selecione a seta para baixo no campo Selecionar função para exibir as funções disponíveis.  Para este laboratório, selecione **Proprietário**.  OBSERVAÇÃO:  Como prática recomendada, você deve atribuir o privilégio mínimo exigido para a função.  Verifique as permissões no Microsoft Sentinel para referência:  https://docs.microsoft.com/en-us/azure/sentinel/roles

8. Na lista de usuários exibida, selecione **Administrador MOD**.

9. Escolha **Salvar** na parte inferior da página.

10. Na página de Controle de acesso, selecione **Exibir meu acesso** para confirmar que a função foi adicionada. Em seguida, feche a janela selecionando o **X** no canto superior direito.

11. Volte à página Todos os serviços selecionando **Todos os Serviços** no canto superior esquerdo da página, em cima de Grupos de recursos.

#### <a name="task-3--in-this-task-you-will-walk-through-the-process-of-connecting-microsoft-sentinel-to-your-data-source-to-begin-to-collect-data-note-it-can-take-a-bit-time-to-show-the-connected-status-of-a-connector-30-minutes-depending-on-the-tenant"></a>Tarefa 3:  Nesta tarefa, vamos acompanhar o processo de conexão do Microsoft Sentinel à sua fonte de dados para começar a coletar dados. Observação: pode levar algum tempo para o conector ter o status alterado para conectado (~30 minutos dependendo do locatário).

1. Na caixa Filtrar serviços da página Todos os serviços, insira **Microsoft Sentinel** e selecione **Microsoft Sentinel** na lista de resultados. 

2. Na página Microsoft Sentinel, selecione o espaço de trabalho criado com a instância do Microsoft Sentinel, **SC900-LogAnalytics-workspace**.

3. A primeira etapa com o Microsoft Sentinel é conseguir coletar dados. À esquerda no painel de navegação, em configuração, selecione **Conectores de dados**.

4. Na página Conectores de dados, role para baixo na janela principal para exibir a extensa lista de conectores disponíveis. Na caixa Pesquisar da página dos conectores de dados, insira **Azure** e selecione **Azure Active Directory** na lista de resultados.

5. A janela do conector do Azure Active Directory será aberta.  Clique em **Abrir página do conector**.

6. Na página Conector do Azure Active Directory, verifique a descrição e observe o conteúdo relacionado, incluindo pastas de trabalho, consultas e modelos de regras analíticas.  

7. A guia de instruções, na janela principal, apresenta os pré-requisitos para integrar o Microsoft Sentinel ao Azure Active Directory.   Em configuração, selecione **Logs de entrada** e depois Aplicar Mudanças (é possível escolher múltiplos conectores).

8. Na guia Próximas etapas, observe a lista de pastas de trabalho recomendadas.   Nas pastas de trabalho recomendadas, selecione **Logs de entrada do Azure** (é possível escolher pastas de trabalho adicionais).

9. Na página de pastas de trabalho e com a guia de modelos selecionada (sublinhada), selecione **Logs de entrada do Azure**. 

10. Na janela Logs de entrada do Azure aberta, verifique a descrição e selecione **Exibir modelo**.  Saia do modelo selecionando o **X** no canto superior direito da tela.  Selecione **Salvar** na parte inferior da página e depois **OK** para salvar a pasta de trabalho na localização padrão.

11. No canto superior esquerdo da página Pastas de trabalho, acima de onde está escrito Pastas de trabalho, clique em **Microsoft Sentinel**. Você vai voltar à página Conectores de Dados do Microsoft Sentinel.

12. O topo da página Conectores de dados deve exibir 1 conexão, indicando que agora você se conectou ao Azure Active Directory.

13. À esquerda no painel de navegação, selecione **Pastas de trabalho**.

14. Na página Pastas de trabalho, selecione a guia **Minhas pastas de trabalho**, que fica acima da caixa de pesquisa.  A pasta de trabalho que você acaba de salvar está listada e disponível para exibir e monitorar seus dados.

15. Deixe essa página aberta; vamos usá-la na próxima tarefa.

#### <a name="task-4--in-this-task-you-will-walk-through-the-process-of-using-a-built-in-analytics-rule-template-to-create-a-rule-to-get-notified-when-something-suspicious-occurs"></a>Tarefa 4:  Nesta tarefa, vamos acompanhar o uso de um modelo interno de regra de análise para criar uma regra de notificação sobre atividades suspeitas.

1. À esquerda no painel de navegação, selecione **Análise**.

2. A página Análise mostra regras ativas (a Detecção avançada de ataques multiestágio está habilitada por padrão) e permite acessar os modelos de Regras.  Selecione a guia **Modelos de regras**.  Observe a lista de modelos disponíveis e as diferentes formas de filtrar essa lista.  Com os alertas internos de análise no workspace do Microsoft Sentinel, você será notificado quando algo suspeito ocorrer.

3. Na barra de pesquisa, insira **Portal do Azure**.  Selecione **Falha de logon no Portal do Azure**.  

4. Na janela que abrir, leia a descrição e as informações associadas ao modelo.  Selecione **Criar regra** na parte inferior da página.

5. No Assistente de regra de análise, revise as informações e selecione **Avançar: Definir lógica de regra >** .

6. A página Definir lógica de regra é onde você define a lógica da nova regra de análise. O modelo já apresenta algumas lógicas e configurações predefinidas.  Role a página para verificar as configurações disponíveis.  Mantenha as configurações padrão. Selecione **Avançar: Configurações de incidente (versão prévia)>** .

7. Com as Configurações de incidentes, é possível agrupar os alertas do Microsoft Sentinel em um único Incidente a ser analisado. Você pode definir se os alertas disparados por essa regra de análise devem gerar incidentes.  Mantenha o padrão e selecione **Avançar: Resposta automatizada >** .

8. Na guia Resposta automatizada, observe que é possível adicionar um guia estratégico para automatizar a resposta.  Do mesmo modo, também é possível criar uma regra de automatização de incidente.  Selecione **+ Adicionar** novo em Automação de incidentes.  Uma janela vai ser aberta para criar a nova regra de automação.  Toda regra de automação criada nesta página é disparada pela regra de análise que você está criando. Observe que é possível adicionar condições e definir ações para a regra.   Selecione **Cancelar** para sair dessa janela.

9. Selecione **Avançar: Revisão>** para revisar todos os detalhes relacionados à regra com base no modelo escolhido. Aqui, é possível escolher se você quer criar a regra, selecionando **Criar**, ou sair sem criar a regra, selecionando **X** no canto superior direito da página.

10. Deixe essa página aberta; vamos usá-la na próxima tarefa.

#### <a name="task-5--in-the-previous-task-you-created-an-analytics-rule-to-be-alerted-of-suspicious-activities--embedded-in-that-wizard-is-the-option-to-automate-the-response-to-an-incident-based-on-the-specific-rule--but-you-can-also-create-automation-rules-by-going-directly-to-the-automation-configuration-option"></a>Tarefa 5:  Na tarefa anterior, nós criamos uma regra de análise para sermos alertados de atividades suspeitas.  O assistente também permite automatizar a resposta a um incidente com base nessa regra específica.  Você também pode criar regras de automação diretamente na opção de configuração de automação.

1. À esquerda no painel de navegação, selecione **Automação**.  

2. Selecione **+ Criar**. No menu suspenso, observe que é possível adicionar tanto um novo guia estratégico quanto uma nova regra.  Selecione **Adicionar nova regra**.  

3. Uma janela vai ser aberta para criar a nova regra de automação.  Observe que é possível adicionar condições e definir ações para a regra.  A única diferença é que a primeira condição é associar as regras de análise a que você quer aplicar essa regra de automação.  Ela aparecia acinzentada na tarefa anterior porque a automação estava sendo configurada para a regra específica.  Selecione **Cancelar** para sair da janela Criar nova regra de automação.

4. Deixe essa página aberta; vamos usá-la na próxima tarefa.


#### <a name="task-6--delete-microsoft-sentinel-resource-group--microsoft-sentinel-is-billed-based-on-the-volume-of-data-ingested-for-analysis-in-microsoft-sentinel-although-the-amount-of-data-ingested-as-a-result-of-this-lab-is-minimal-it-is-recommended-that-you-delete-the-microsoft-sentinel-resource-group-when-you-are-done-exploring-the-features-of-capabilities-of-microsoft-sentinel"></a>Tarefa 6:  Excluir grupo de recursos do Microsoft Sentinel.  O Microsoft Sentinel é cobrado de acordo com o volume da ingestão de dados para análise. Embora a quantidade de dados ingeridos durante este laboratório seja mínima, recomendamos que o grupo de recursos do Microsoft Sentinel seja excluído quando você terminar de explorar suas funcionalidades.

1. No canto superior esquerdo da página Microsoft Sentinel, em cima de Microsoft Sentinel, selecione **Todos os Serviços**.

2. Na caixa para filtrar serviços, insira grupos de recursos e selecione **Grupos de recursos** na lista gerada.

3. Na página Grupos de recursos, selecione o grupo de recursos que você criou com o Microsoft Sentinel, **SC900-ResourceGroup**.

4. Na parte superior central da página, selecione **Excluir grupo de recursos**.  Verifique o aviso de segurança.  Insira o nome do grupo de recursos, **SC900-ResourceGroup**, e selecione **Excluir** na parte inferior da página.  Vai levar alguns minutos para excluir o grupo de recursos.

5. Após verificar que o grupo de recursos foi excluído, feche a página do navegador. 


#### <a name="review"></a>Revisão

Neste laboratório, acompanhamos o processo de criação de uma instância do Microsoft Sentinel.  Além disso, também configuramos as permissões para garantir o acesso aos recursos associados a essa instância do Microsoft Sentinel.  Por meio da nova instância do Microsoft Sentinel, pudemos acompanhar as etapas de conexão do Microsoft Sentinel às fontes de dados, usar regras de análise internas para notificar suspeitas e explorar a capacidade de automação. Você concluiu o laboratório excluindo o grupo de recursos associado à instância do Microsoft Sentinel que criou.
