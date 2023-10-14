<!---
---
Laboratório: Título: 'Explorar o fluxo de trabalho da Descoberta Eletrônica (padrão)' Roteiro de aprendizagem/Módulo/Unidade: 'Roteiro de aprendizagem: descrever as funcionalidades de conformidade da Microsoft; Módulo 5: descrever as funcionalidades de Descoberta Eletrônica e auditoria do Microsoft Purview; Unidade 2: descrever as soluções de Descoberta Eletrônica no Microsoft 365'
---
--->

# Laboratório: Explorar o fluxo de trabalho da Descoberta Eletrônica (Standard)

Esse laboratório é mapeado para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades de conformidade da Microsoft
- Módulo: descrever as funcionalidades de Descoberta Eletrônica e auditoria do Microsoft Purview
- Unidade: Descrever as soluções de Descoberta Eletrônica no Microsoft Purview

## Cenário do laboratório

Neste laboratório, você acompanhará as etapas necessárias para configurar a Descoberta Eletrônica, incluindo a configuração de permissões de função, a criação de um caso de Descoberta Eletrônica, a criação de uma retenção de Descoberta Eletrônica e a criação de uma consulta de pesquisa.  Observação:  O licenciamento para a Descoberta Eletrônica (Standard) exige a assinatura apropriada da organização e licenciamento por usuário. Se você não sabe quais licenças dão suporte à Descoberta Eletrônica (Standard), visite [Introdução à Descoberta Eletrônica (Standard) no Microsoft Purview](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery?view=o365-worldwide).

**Tempo estimado**: 25-30 minutos

### Tarefa 1:

Para acessar a Descoberta Eletrônica (Standard) ou ser adicionado como membro de um caso da Descoberta Eletrônica, um usuário deve receber as permissões apropriadas. Nesta tarefa, como administrador global, você vai adicionar usuários específicos como membros do grupo de função Gerente de Descoberta Eletrônica.

1. Abra a guia do navegador na home page do Microsoft Purview.  Se você fechou a guia anteriormente, abra uma nova guia do navegador e insira **https://admin.microsoft.com** . Entre com as credenciais de administrador no locatário do Microsoft 365 fornecido pelo ALH (hoster de laboratório autorizado). No painel de navegação à esquerda do centro de administração do Microsoft 365, selecione **Mostrar todos** e depois **Conformidade**.  A página inicial do portal de conformidade do Microsoft Purview é aberta em uma nova página do navegador.  


1. No painel de navegação à esquerda, expanda (selecione a seta para baixo) **Funções e Escopos** e selecione **Permissões**.

1. Em Soluções do Microsoft Purview, selecione **Funções**.

1. No campo de pesquisa, insira **Descoberta Eletrônica** e pressione ENTER no teclado.  Selecione **Gerente de Descoberta Eletrônica**.

1. Selecione **Editar**.  Observe que há dois subgrupos: Gerente de Descoberta Eletrônica e Administrador de Descoberta Eletrônica.  
    1. A página “Gerenciar o Gerente de Descoberta Eletrônica” permite adicionar usuários à função de Gerente de Descoberta Eletrônica. Neste laboratório, vamos adicionar membros ao subgrupo Administrador de Descoberta Eletrônica. Portanto, selecione **Avançar**.
    1. Na página “Gerenciar o Administrador de Descoberta Eletrônica”, selecione **Escolher usuários**. Procure e selecione **Administrador MOD** e **Mila Moraes**. Em seguida, pressione **Selecionar** na parte inferior da página, escolha **Avançar** e **Salvar**.
    1. Na página “Você atualizou com sucesso o grupo de funções”, selecione **Concluído**.

1. Mantenha essa guia do navegador aberta, pois você vai usá-la na próxima tarefa.

### Tarefa 2:

Nesta tarefa, como Administrador da Descoberta Eletrônica (o administrador MOD é um administrador da Descoberta Eletrônica), você vai criar um caso para começar a usar a Descoberta Eletrônica (Standard).

1. Você ainda deve estar na página de funções do portal de conformidade. Se você fechou a guia do navegador da tarefa anterior, abra uma nova guia e insira **compliance.microsoft.com**

1. No painel de navegação à esquerda, em Soluções, expanda **Descoberta Eletrônica** e escolha **Padrão**.

1. No topo da página Descoberta Eletrônica (Standard), selecione **+ Criar um caso**.

1. Na janela Novo processo, insira um nome para o Processo, **SC900 Processo Teste**. Depois, selecione **Salvar** na parte inferior da página.

1. Agora, o processo deve aparecer na lista.

1. Como você criou o processo e tem privilégios de Administrador de Descoberta Eletrônica, é possível começar a trabalhar nele.  

1. Mantenha essa guia do navegador aberta, pois você vai usá-la na tarefa seguinte.

### Tarefa 3

Agora que criou um caso de Descoberta Eletrônica (Standard), você pode começar a trabalhar nele.  Nesta tarefa, você criará uma retenção de Descoberta Eletrônica para o caso criado.  Especificamente, você criará uma retenção para a caixa de correio do Exchange pertencente a Alice Pena.

1. Abra a guia Descoberta Eletrônica (Standard) no navegador.

1. Na página Descoberta Eletrônica (Standard), selecione o caso criado na guia anterior, **Caso de teste SC900**.

1. Na Página Inicial do processo, selecione a guia **Retenção** e depois **+Criar**.

1. No campo do nome, insira **Retenção teste** e selecione **Avançar**.

1. Na página Escolher localizações, selecione a opção de alternância ao lado de **Caixas de correio do Exchange** para definir o status como **Ativado**.  

1. Agora, selecione **Escolher usuários, grupos ou equipes**.  Na caixa de pesquisa, insira **Adele** e pressione o enter no teclado. Nos resultados da pesquisa, selecione **Alice Pena** e **Concluído**.

1. Na página Escolher localizações, selecione **Avançar**.  Por uma questão de conveniência para o laboratório, nenhuma outra localização vai ser incluída nesta retenção.

1. A página Condições de consulta permite que você crie uma retenção, com base em palavras-chave ou condições específicas atendidas. Selecione **+ Adicionar condição** para ver as opções disponíveis.  Selecione **Avançar**. Quando não tiver nenhuma condição, a retenção preserva todo o conteúdo da localização especificada.

1. Verifique as configurações e selecione **Enviar**; isso pode levar um minuto. Depois, selecione **Concluído**.  A Retenção teste deve aparecer na lista.  Se você não a encontrar de imediato, selecione **Atualizar**

1. Mantenha essa guia do navegador aberta, pois você vai usá-la na tarefa seguinte.

### Tarefa 4

Com uma retenção estabelecida, você criará uma consulta de pesquisa.  Após a conclusão da pesquisa, a Descoberta Eletrônica dá suporte a ações, como a exportação e o download dos resultados para investigação futura.   Observação:  As pesquisas associadas a um caso da Descoberta Eletrônica (Standard) não são listadas na página Pesquisar conteúdo do portal de conformidade do Microsoft Purview. Essas pesquisas são listadas apenas na página Pesquisas do caso da Descoberta Eletrônica (Standard) associado.

1. Abra a guia Caso de Teste SC900 no navegador.

1. Na página Caso de Teste de SC900, selecione **Pesquisas**.

1. Na página Pesquisa, selecione **+ Nova Pesquisa**.

1. No campo de Nome, insira **Retenção Teste – Pesquisa de Vendas** e depois selecione **Avançar** na parte inferior da página.

1. Na página Escolher locais, selecione **locais em espera** e desmarque **Adicionar Conteúdo do Aplicativo para usuários locais**, pois seu ambiente de laboratório não tem usuários locais e, em seguida, selecione **Avançar**.

1. A página Consultar condições permite criar uma pesquisa com base em Palavras-chave ou Condições atendidas. No campo de palavra-chave, insira **Vendas** e selecione **Avançar**.

1. Verifique as configurações e selecione **Enviar**; isso pode levar um minuto. Depois, selecione **Concluído**.  A pesquisa deve aparecer na lista.  Se você não a encontrar de imediato, selecione **Atualizar**

1. Na janela Pesquisas, selecione a pesquisa criada, **Retenção Teste – Pesquisa de Vendas**.  Uma janela será aberta com a guia Resumo selecionada.  Quando a pesquisa for concluída, o status indicará isso.  Você verá uma guia Estatísticas da pesquisa (se não encontrá-la, a pesquisa ainda poderá estar em execução e poderá levar alguns minutos para ser concluída).  Selecione **Estatísticas da pesquisa** e selecione o menu suspenso próximo de Pesquisar conteúdo.  Também é possível encontrar mais informações para o Relatório de condições e as Localizações principais.  

1. Na parte inferior da página, selecione **Ações**.  Observe as opções disponíveis que incluem opções de exportação (as opções de exportação não podem ser selecionadas na plataforma do laboratório fornecida pelo hoster do laboratório autorizado, mas estão disponíveis em um ambiente de produção e são consideradas parte do fluxo de trabalho padrão). Selecione **Fechar**.

1. Saia do serviço e feche todas as janelas abertas do navegador.

### Revisão

Neste laboratório, você acompanhará as etapas necessárias para começar a usar a Descoberta Eletrônica (Standard), incluindo a configuração das permissões de funções para a Descoberta Eletrônica e a criação de um caso da Descoberta Eletrônica.  Com o caso criado, você acompanhou os elementos do fluxo de trabalho da Descoberta Eletrônica (Standard) criando uma retenção de Descoberta Eletrônica e uma consulta de pesquisa.
