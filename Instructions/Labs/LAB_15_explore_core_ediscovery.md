---
lab:
  title: Explorar o fluxo de trabalho da Descoberta Eletrônica Principal
  module: 'Module 4 Lesson 5: Describe the capabilities of Microsoft compliance solutions: Describe the eDiscovery and audit capabilities of Microsoft 365'
ms.openlocfilehash: 0754237aa892e9fe31ad2eea0811642bce929fe8
ms.sourcegitcommit: c14538b208890797642cfe5c35abf6bea45364bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/15/2022
ms.locfileid: "142614369"
---
# <a name="lab-explore-the-core-ediscovery-workflow"></a>Laboratório: Explorar o fluxo de trabalho da Descoberta Eletrônica Principal

## <a name="lab-scenario"></a>Cenário do laboratório
Neste laboratório, vamos acompanhar as etapas necessárias para configurar a Descoberta Eletrônica Principal. Depois, vamos explorar o fluxo de trabalho da Descoberta Eletrônica Principal, criando uma retenção de Descoberta Eletrônica e uma consulta de pesquisa, e exportando os resultados da pesquisa.  Observação:  O licenciamento para a Descoberta Eletrônica Principal exige a assinatura apropriada da organização e o licenciamento por usuário. Se não tiver certeza de quais licenças comportam a Descoberta Eletrônica principal, visite a Introdução à Descoberta Eletrônica Principal.


**Tempo estimado**: 20 a 25 minutos

#### <a name="task-1--to-access-core-ediscovery-or-be-added-as-a-member-of-a-core-ediscovery-case-a-user-must-be-assigned-the-appropriate-permissions-in-this-task-you-as-the-global-admin-will-add-specific-users-as-members-of-the-ediscovery-manager-role-group"></a>Tarefa 1:  Para acessar a Descoberta Eletrônica Principal ou ser adicionado como membro de um caso de Descoberta Eletrônica Principal, um usuário deve receber as permissões apropriadas. Nesta tarefa, como administrador global, você vai adicionar usuários específicos como membros do grupo de função Gerente de Descoberta Eletrônica.

 Abra o Microsoft Edge. Na barra de endereços, insira **admin.microsoft.com**.

1. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é sua ID de locatário exclusiva fornecida pelo provedor de hospedagem de laboratório) e selecione **Avançar**.
    
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem de laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**. Vamos ser direcionados à página Centro de administração do Microsoft 365.

1. À esquerda no painel de navegação do Centro de administração do Microsoft 365, selecione **Mostrar todos**.

1. Em Centros de administração, selecione **Conformidade**.  A página inicial do centro de conformidade do Microsoft 365 vai ser aberta no navegador.  

1. No painel de navegação esquerdo, selecione **Permissões**. 

1. Na página Permissões e funções, em Centro de conformidade, selecione **Funções**.

1. No campo de pesquisa, insira **Descoberta Eletrônica** e selecione o ícone de pesquisa (lupa).  Selecione **Gerente de Descoberta Eletrônica**.

1. Na janela aberta, observe que há dois subgrupos, o Gerente de Descoberta Eletrônica e o Administrador de Descoberta Eletrônica.  Leia a descrição de cada um deles.  Para este laboratório, vamos adicionar membros ao subgrupo Administrador de Descoberta Eletrônica. Selecione **Editar**, perto de Administrador de Descoberta Eletrônica.  Como prática geral recomendada, o privilégio mínimo exigido para a função deve ser atribuído aos usuários.

1. Para adicionar membros a esse grupo de função, verifique se você está na guia **Escolher Administrador de Descoberta Eletrônica** e selecione **Escolher Administrador de Descoberta Eletrônica**.

1. Selecione **+ Adicionar** na parte superior da página.

1. A partir da lista de nomes, selecione **Administrador MOD**, **Megan Bowen**, e depois **Adicionar** na parte inferior da página. Então, selecione **Concluído** na parte inferior da página.

1. Verifique se os membros adicionados estão corretos e selecione **Salvar**.

1. Na parte inferior da janela Descoberta Eletrônica, selecione **Fechar**.

1. Deixe essa guia do navegador aberta; vamos usá-la na próxima tarefa.

#### <a name="task-2--in-this-task-you-as-an-ediscovery-administrator-mod-admin-is-an-ediscovery-administrator-will-create-a-case-to-start-using-core-ediscovery"></a>Tarefa 2:  Nesta tarefa, como Administrador de Descoberta Eletrônica (o administrador MOD é um administrador de descoberta eletrônica), você vai criar um processo para começar a usar a Descoberta Eletrônica Principal.

1. Você ainda deve estar na página Funções do Centro de conformidade. Se você fechou a guia do navegador da tarefa anterior, abra uma nova guia e insira **compliance.microsoft.com**

1. À esquerda no painel de navegação, em Soluções, selecione **Descoberta Eletrônica** e depois **Principal**.

1. No topo da página Descoberta Eletrônica Principal, selecione **+ Criar um processo**.

1. Na janela Novo processo, insira um nome para o Processo, **SC900 Processo Teste**. Depois, selecione **Salvar** na parte inferior da página.

1. Agora, o processo deve aparecer na lista.

1. Como você criou o processo e tem privilégios de Administrador de Descoberta Eletrônica, é possível começar a trabalhar nele.  

1. Deixe essa guia do navegador aberta; vamos usá-la na próxima tarefa.

#### <a name="task-3--now-that-you-have-created-a-core-ediscovery-case-you-can-begin-to-work-with-the-case--in-this-task-you-will-create-an-ediscovery-hold-for-the-case-for-you-just-created--specifically-you-will-crate-a-hold-for-the-the-exchange-mailbox-belonging-to-adele-vance"></a>Tarefa 3:  Agora que criamos um processo de Descoberta Eletrônica, é possível começar a trabalhar nele.  Nesta tarefa, vamos criar uma retenção de Descoberta Eletrônica para o processo recém-criado.  Especificamente, vamos criar uma retenção para a caixa de correio exchange pertencente à Adele Vance.

1. Abra a guia Descoberta Eletrônica Principal no navegador.

1. Na página Descoberta Eletrônica Principal, selecione o processo criado na guia anterior, **SC900 Processo Teste**. 

1. Na Página Inicial do processo, selecione a guia **Retenção** e depois **+Criar**.

1. No campo do nome, insira **Retenção teste** e depois selecione Avançar.

1. Na página Escolher localizações, selecione o botão de alternância próximo a **Caixas de correio do Exchange** para definir o status como **Ativado** e selecione **Escolher usuários, grupos ou equipes**.  Na caixa de pesquisa, insira **Adele** e pressione o enter no teclado. A partir dos resultados da pesquisa, selecione **Adele Vance** e depois Escolher. Em seguida, selecione **Concluído**.

1. Na página Escolher localizações, selecione **Avançar**.  Por uma questão de conveniência para o laboratório, nenhuma outra localização vai ser incluída nesta retenção.

1. A página Consultar condições permite criar uma retenção com base em Palavras-chave ou Condições atendidas. Selecione **+Condições** para exibir as opções disponíveis.  Selecione **Avançar**. Quando não tiver nenhuma condição, a retenção preserva todo o conteúdo da localização especificada.

1. Verifique as configurações e selecione **Enviar**; isso pode levar um minuto. Depois, selecione **Concluído**.  A Retenção teste deve aparecer na lista.  Se você não a encontrar de imediato, selecione **Atualizar**

1. Deixe essa guia do navegador aberta; vamos usá-la na próxima tarefa.

#### <a name="task-4--with-a-hold-in-place-you-will-create-a-search-query--once-your-search-is-complete-you-will-go-export-and-download-the-results-for-future-investigation---note--searches-associated-with-a-core-ediscovery-case-are-not-listed-on-the-content-search-page-in-the-microsoft-365-compliance-center-these-searches-are-listed-only-on-the-searches-page-of-the-associated-core-ediscovery-case"></a>Tarefa 4:  Com uma retenção estabelecida, vamos criar uma consulta de pesquisa.  Quando a pesquisa estiver concluída, vamos exportar e baixar os resultados para uma investigação futura.   Observação:  As pesquisas associadas ao processo de Descoberta Eletrônica Principal não são listadas na página Pesquisar conteúdo do centro de conformidade do Microsoft 365. Essas pesquisas são listadas apenas na página Pesquisas do processo de Descoberta Eletrônica Principal associado.

1. Abra a guia do Processo teste SC900 no navegador.

1. Na página Retenções do processo, selecione **Pesquisas**.

1. Na página Pesquisa, selecione **+ Nova Pesquisa**.

1. No campo de Nome, insira **Retenção Teste – Pesquisa de Vendas** e depois selecione **Avançar** na parte inferior da página.

1. Na página Escolher locais, selecione **locais em espera** e desmarque **Adicionar Conteúdo do Aplicativo para usuários locais**, pois seu ambiente de laboratório não tem usuários locais e, em seguida, selecione **Avançar**.

1. A página Consultar condições permite criar uma pesquisa com base em Palavras-chave ou Condições atendidas. No campo de palavra-chave, insira **Vendas** e selecione **Avançar**.

1. Verifique as configurações e selecione **Enviar**; isso pode levar um minuto. Depois, selecione **Concluído**.  A pesquisa deve aparecer na lista.  Se você não a encontrar de imediato, selecione **Atualizar**

1. Na janela Pesquisas, selecione a pesquisa que acabamos de criar, **Retenção Teste - Pesquisa de Vendas**.  Uma janela será aberta com a guia Resumo selecionada.  Quando a pesquisa for concluída, o status indicará isso.  Você vai encontrar a guia Estatísticas da pesquisa (se não encontrar, a pesquisa ainda pode estar em execução e pode levar alguns minutos para ser concluída).  Selecione **Estatísticas da pesquisa** e selecione o menu suspenso próximo de Pesquisar conteúdo.  Também é possível encontrar mais informações para o Relatório de condições e as Localizações principais.  

1. Na parte inferior da página, selecione **Ações**.  Observe as opções disponíveis e selecione **Exportar resultados**.
    
    1. Na janela Exportar resultados, mantenha o padrão e selecione **Exportar** na parte inferior da página. Voltaremos automaticamente à janela “Retenção Teste - Pesquisa de Vendas”. Selecione **fechar** na parte inferior da página.
    
    1. Na página SC900 - Processo teste, selecione **Exportações** na parte superior da página.
    1. Selecione **Retenção Teste - Pesquisa de Vendas_Export**
    1. Na janela aberta, “Retenção Teste - Pesquisa de Vendas_Export”, encontramos uma Chave de exportação. Selecione **Copiar à área de transferência**.
    1. Na parte superior da janela, selecione **Baixar resultados**. Uma nova página é aberta no navegador e uma janela pop-up aparece perguntando se você deseja abrir este arquivo. Selecione **Abrir**.
    1. Se esta for a primeira vez que você baixa uma pesquisa de conteúdo, aparecerá uma solicitação para instalar o Microsoft Office 365 e a ferramenta de Exportação de Descoberta Eletrônica.  Selecione **Instalar**.
    1. Quando a instalação for concluída, a janela da ferramenta de exportação de descoberta eletrônica será aberta.  No primeiro campo, cole a chave de exportação copiada à área de transferência (use o Control V no teclado ou clique com o botão direito do mouse e selecione colar).
    1. No segundo campo, selecione a localização desejada para armazenar o arquivo exportado. Depois, selecione **Iniciar**.  Quando o processo de download for concluído, selecione **Fechar** e fecha essa guia do navegador.
    1. Estamos de volta à janela “Retenção Teste - Pesquisa de Vendas_Export”.  Selecione **Fechar**.
    1. Verifique a localização do download para conferir se ele foi concluído com sucesso. 


#### <a name="review"></a>Revisão

Neste laboratório, acompanhamos as etapas necessárias de introdução à Descoberta Eletrônica principal, incluindo a configuração das permissões de funções para a Descoberta Eletrônica e a criação de um processo de Descoberta Eletrônica.  Com o processo criado, acompanhamos o fluxo de trabalho da Descoberta Eletrônica Principal, criando uma retenção de Descoberta Eletrônica e uma consulta de pesquisa, e exportando os resultados da pesquisa para uso em investigações futuras.