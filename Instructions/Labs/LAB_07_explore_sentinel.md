---
lab:
    title: 'Explorar o Microsoft Sentinel'
    module: 'Módulo 3 – Lição 3: Descrever as funcionalidades das soluções de segurança da Microsoft Descrever os recursos de segurança do Microsoft Sentinel'
---


# Laboratório: Explorar o Microsoft Sentinel 

## Cenário do laboratório
Neste laboratório, vamos acompanhar o processo de criação de uma instância do Microsoft Sentinel.  Também vamos configurar as permissões para garantir o acesso aos recursos que serão implantados para dar suporte ao Microsoft Sentinel.  Depois de concluir essa configuração básica, será possível acompanhar as etapas de conexão do Microsoft Sentinel às fontes de dados, usar análises internas para notificar suspeitas e, por fim, vamos explorar a capacidade de automação.  

  

**Tempo estimado**: 30-45 minutos

#### Tarefa 1:  Criar uma instância do Microsoft Sentinel.

1. Abra o Microsoft Edge. Na barra de endereço, digite **portal.azure.com**.

2. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (onde ZZZZZZ é sua ID de locatário exclusiva fornecida por seu provedor de hospedagem de laboratório) e selecione **Avançar**.
    
    1. Insira a senha de administrador que deve ser fornecida por seu provedor de hospedagem de laboratório. Selecione **Entrar**.
    1. Se você receber um aviso para permanecer conectado, selecione **Sim**.

3. No canto superior esquerdo da tela, perto de Microsoft Azure, selecione o ícone para mostrar o menu (as três linhas horizontais, também conhecidas como ícone de hambúrguer). Depois, selecione **Todos os Serviços**.  

4. Na caixa para filtrar serviços, insira **Microsoft Sentinel** e selecione **Microsoft Sentinel** na lista.

5. Na página do Microsoft Sentinel, selecione **Criar Microsoft Sentinel**.

6. Na página Adicionar o Microsoft Sentinel a um workspace, selecione **Criar um novo workspace**.

7. Na guia básica Criar workspace do Log Analytics, insira o seguinte:
    1. Assinatura:  **Azure Pass – Sponsorship**
   
    1. Grupo de recursos: selecione **Criar Novo**, insira o nome **SC900-ResourceGroup** e selecione **OK**.
    1. Nome: **SC900-LogAnalytics-workspace**.
    1. Região: **Leste dos EUA** (manter padrão)
    1. Selecione **Avançar: Tipo de preço >**

8. Para o Tipo de Preço, deixe as configurações padrão: **Pagamento conforme o uso (por GB 2018)**. Depois, selecione **Avançar: Tags >**.

9. Para as tags, você pode deixar a opção em branco e selecionar **Revisar + Criar**.

10. Verifique as informações inseridas e clique em **Criar**.

11. Se você não encontrar o espaço de trabalho na lista, selecione **Atualizar** e selecione **Adicionar**.

12. Assim que o novo workspace for adicionado, a página Novidades | e Guias do Microsoft Sentinel será exibida.  Veja as três etapas listadas na página de Introdução.

13. Mantenha esta página aberta, pois ela será usada na próxima tarefa.

#### Tarefa 2:  Com a instância do Microsoft Sentinel criada, é prudente verificar se você tem o acesso necessário aos recursos implantados para dar suporte ao Microsoft Sentinel.  Nesta tarefa, você vai entrar na página de controle de acesso (IAM) do grupo de recursos criado com a instância do Microsoft Sentinel, verificar os papéis disponíveis e atribuir a você a função necessária (administrador de MOD). A atribuição do papel no nível do grupo de recursos garante que ele será aplicado a todos os recursos implantados para dar suporte ao Microsoft Sentinel.

1. No canto superior esquerdo da página do Microsoft Sentinel, em cima de Microsoft Sentinel, selecione **Todos os Serviços**.

2. Na caixa para filtrar serviços, insira grupos de recursos e selecione **Grupos de recursos** na lista fornecida.

3. Na página Grupos de recursos, selecione o grupo de recursos que você criou com o Microsoft Sentinel, **SC900-ResourceGroup**.

4. Na página SC900-ResourceGroup, selecione **Controle de acesso (IAM)**, à esquerda no painel de navegação.

5. Na página Controle de acesso, selecione **Exibir meu acesso**.  Observe que a função atual é Administrador de segurança.  Feche a janela de atribuições do Administrador MOD selecionando o **X** no canto superior direito da tela.

6. Na página Controle de acesso, selecione **+Adicionar** e depois **Adicionar atribuição de função**.

7. A janela Adicionar atribuição de função vai ser aberta.  Selecione a seta para baixo no campo Selecionar função para exibir as funções disponíveis.  Para este laboratório, selecione **Proprietário**.  OBSERVAÇÃO:  Uma prática recomendada é atribuir o menor privilégio necessário para a função.  Como referência, revise as permissões no Microsoft Sentinel:  https://docs.microsoft.com/pt-br/azure/sentinel/roles

8. Na lista de usuários exibida, selecione **Administrador MOD**.

9. Selecione **Salvar** na parte inferior da página.

10. Na página de controle de acesso, selecione **Exibir meu acesso** para confirmar a função adicionada. Depois, feche a janela selecionando o **X** no canto superior direito.

11. Volte à página Todos os serviços selecionando **Todos os Serviços** no canto superior esquerdo da página, em cima de Grupos de recursos.

#### Tarefa 3:  Nesta tarefa, vamos acompanhar o processo de conexão do Microsoft Sentinel à sua fonte de dados para começar a coletar dados. Observação: pode levar um tempo até que o status de um conector seja exibido como conectado (aproximadamente 30 minutos, dependendo do locatário).

1. Na caixa Filtrar serviços da página Todos os serviços, insira **Microsoft Sentinel** e selecione **Microsoft Sentinel** na lista de resultados. 

2. Na página do Microsoft Sentinel, selecione o workspace que você criou com a instância do Microsoft Sentinel, **SC900-LogAnalytics-workspace**.

3. A primeira etapa com o Microsoft Sentinel é conseguir coletar dados. À esquerda no painel de navegação, em configuração, selecione **Conectores de dados**.

4. Na página Conectores de dados, role para baixo na janela principal para exibir a extensa lista de conectores disponíveis. Na caixa Pesquisar da página dos conectores de dados, insira **Azure** e selecione **Azure Active Directory** na lista de resultados.

5. A janela do conector do Azure Active Directory será aberta.  Selecione **Abrir página do conector**.

6. Na página Conector do Azure Active Directory, verifique a descrição e observe o conteúdo relacionado, incluindo pastas de trabalho, consultas e modelos de regras analíticas.  

7. A guia de instruções, na janela principal, apresenta os pré-requisitos para integrar o Microsoft Sentinel ao Azure Active Directory.   Em configuração, selecione **Logs de entrada** e depois Aplicar Mudanças (é possível escolher múltiplos conectores).

8. Na guia Próximas etapas, observe a lista de pastas de trabalho recomendadas.   Nas pastas de trabalho recomendadas, selecione **Logs de entrada do Azure** (é possível escolher pastas de trabalho adicionais).

9. Na página de pastas de trabalho e com a guia de modelos selecionada (sublinhada), selecione **Logs de entrada do Azure**. 

10. Na janela de logs de entrada do Azure AD que será aberta, revise a descrição e selecione **Exibir modelo**.  Saia do modelo clicando no **X** do canto superior direito da tela.  Selecione **Salvar** na parte inferior da página e clique em **OK** para salvar a pasta de trabalho no local padrão.

11. No canto superior esquerdo da página Pastas de trabalho, acima de onde está escrito Pastas de trabalho, selecione **Microsoft Sentinel**. Você voltará para a página Conectores de dados do Microsoft Sentinel.

12. A parte superior dessa página deve mostrar a mensagem “1 conectado”, informando que você agora está conectado ao Azure Active Directory.

13. À esquerda no painel de navegação, selecione **Pastas de trabalho**.

14. Na página Pastas de trabalho, selecione a guia **Minhas pastas de trabalho**, que fica acima da caixa de pesquisa.  A pasta de trabalho que você acaba de salvar está listada e disponível para exibir e monitorar seus dados.

15. Deixe essa página aberta; vamos usá-la na próxima tarefa.

#### Tarefa 4:  Nesta tarefa, vamos acompanhar o uso de um modelo interno de regra de análise para criar uma regra de notificação sobre atividades suspeitas.

1. À esquerda no painel de navegação, selecione **Análise**.

2. A página Análise mostra regras ativas (a Detecção avançada de ataques multiestágio está habilitada por padrão) e permite acessar os modelos de Regras.  Selecione a guia **Modelos de regras**.  Observe a lista de modelos disponíveis e as diferentes formas de filtrar essa lista.  Com os alertas internos de análise no espaço de trabalho do Microsoft Sentinel, você recebe uma notificação quando algo suspeito acontece.

3. Na barra de pesquisa, insira **Portal do Azure**.  Selecione **Falha de logon no Portal do Azure**.  

4. Na janela que abrir, leia a descrição e as informações associadas ao modelo.  Selecione **Criar regra** na parte inferior da página.

5. No Assistente de regra de análise, revise as informações e selecione **Avançar: Definir lógica de regra >**.

6. A página Definir lógica de regra é onde você define a lógica da nova regra de análise. O modelo já apresenta algumas lógicas e configurações predefinidas.  Role a página para verificar as configurações disponíveis.  Mantenha as configurações padrão. Selecione **Avançar: Configurações de incidentes (prévia)>**.

7. Com as Configurações de incidentes, é possível agrupar os alertas do Microsoft Sentinel em um único Incidente a ser analisado. Você pode definir se os alertas disparados por essa regra de análise devem gerar incidentes.  Mantenha o padrão e selecione **Avançar: Resposta automatizada >**.

8. Na guia Resposta automatizada, observe que é possível adicionar um guia estratégico para automatizar a resposta.  Do mesmo modo, também é possível criar uma regra de automatização de incidente.  Selecione **+Adicionar** novo em automação de incidente.  Uma janela será aberta para criar a nova regra de automação.  Toda regra de automação criada nesta página é disparada pela regra de análise que você está criando. Observe que é possível adicionar condições e definir ações para a regra.   Selecione **Cancelar** para sair dessa janela.

9. Selecione **Avançar: Revisão>** para revisar todos os detalhes relacionados à regra com base no modelo escolhido. Aqui, é possível escolher se você quer criar a regra, selecionando **Criar**, ou sair sem criar a regra, selecionando **X** no canto superior direito da página.

10. Deixe essa página aberta; vamos usá-la na próxima tarefa.

#### Tarefa 5:  Na tarefa anterior, nós criamos uma regra de análise para sermos alertados de atividades suspeitas.  O assistente também permite automatizar a resposta a um incidente com base nessa regra específica.  Você também pode criar regras de automação diretamente na opção de configuração de automação.

1. À esquerda no painel de navegação, selecione **Automação**.  

2. Selecione **+ Criar**. No menu suspenso, observe que é possível adicionar tanto um novo guia estratégico quanto uma nova regra.  Selecione **Adicionar nova regra**.  

3. Uma janela será aberta para criar a nova regra de automação.  Observe que é possível adicionar condições e definir ações para a regra.  A única diferença é que a primeira condição é associar as regras de análise a que você quer aplicar essa regra de automação.  Ela aparecia acinzentada na tarefa anterior porque a automação estava sendo configurada para a regra específica.  Selecione **Cancelar** para sair da janela Criar nova regra de automação.

4. Deixe essa página aberta; vamos usá-la na próxima tarefa.


#### Tarefa 6:  Exclua o Grupo de recursos do Microsoft Sentinel.  O Microsoft Sentinel é cobrado de acordo com o volume da ingestão de dados para análise no Microsoft Sentinel. Embora a quantidade de dados ingeridos durante este laboratório seja mínima, recomendamos que o grupo de recursos do Microsoft Sentinel seja excluído quando você terminar de explorar suas funcionalidades.

1. No canto superior esquerdo da página do Microsoft Sentinel, em cima de Microsoft Sentinel, selecione **Todos os Serviços**.

2. Na caixa para filtrar serviços, insira grupos de recursos e selecione **Grupos de recursos** na lista fornecida.

3. Na página Grupos de recursos, selecione o grupo de recursos que você criou com o Microsoft Sentinel, **SC900-ResourceGroup**.

4. No centro superior da página, selecione **Excluir grupo de recursos**.  Verifique o aviso de segurança.  Insira o nome do grupo de recursos, **SC900-ResourceGroup**, e selecione **Excluir** na parte inferior da página.  Vai levar alguns minutos para excluir o grupo de recursos.

5. Após verificar que o grupo de recursos foi excluído, feche a página do navegador. 


#### Revisão

Neste laboratório, acompanhamos o processo de criação de uma instância do Microsoft Sentinel.  Além disso, também configuramos as permissões para garantir o acesso aos recursos associados a essa instância do Microsoft Sentinel.  Por meio da nova instância do Microsoft Sentinel, pudemos acompanhar as etapas de conexão do Microsoft Sentinel às fontes de dados, usar regras de análise internas para notificar suspeitas e explorar a capacidade de automação. Por fim, concluímos o laboratório excluindo o grupo de recursos associado à instância do Microsoft Sentinel que criamos.
