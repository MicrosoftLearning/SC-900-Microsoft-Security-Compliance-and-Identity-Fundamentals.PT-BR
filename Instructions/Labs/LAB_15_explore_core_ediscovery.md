---
lab:
  title: Explorar a Descoberta Eletrônica
  module: Describe the data compliance solutions of Microsoft Purview
---

# Laboratório: Explorar a Descoberta Eletrônica

Esse laboratório é mapeado para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: Descrever as funcionalidades do Microsoft Priva e do Microsoft Purview
- Módulo: descrever as soluções de conformidade de dados do Microsoft Purview
- Unidade: descrever a Descoberta Eletrônica

## Cenário do laboratório

Neste laboratório, você acompanhará as etapas necessárias para configurar a Descoberta Eletrônica, incluindo a configuração de permissões de função, a criação de um caso de Descoberta Eletrônica, a criação de uma retenção de Descoberta Eletrônica e a criação de uma consulta de pesquisa.  Observação: o licenciamento para Descoberta Eletrônica (Standard) requer a assinatura apropriada da organização e o licenciamento por usuário. Se você não sabe quais licenças dão suporte à Descoberta Eletrônica (Standard), visite [Introdução à Descoberta Eletrônica (Standard) no Microsoft Purview](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery?view=o365-worldwide).

**Tempo estimado**: 45 minutos

### Tarefa 1

Para acessar a Descoberta Eletrônica (Standard) ou ser adicionado como membro de um caso da Descoberta Eletrônica, um usuário deve receber as permissões apropriadas. Nesta etapa, você, como administrador global, adicionará usuários específicos como membros do grupo de funções do Gerente de Descoberta Eletrônica.

1. Abra a guia do navegador na home page do Microsoft Purview.  Se você a fechou anteriormente, abra uma nova guia do navegador e insira **https://admin.microsoft.com** . Entre com as credenciais de administrador para o locatário do Microsoft 365 fornecido pelo hoster de laboratório autorizado (ALH).

1. No painel de navegação à esquerda do Centro de administração do Microsoft 365, selecione **Mostrar tudo** e depois **Conformidade**.  Uma nova página inicial do portal do Microsoft Purview será aberta em uma nova página do navegador.  

1. No painel de navegação à esquerda, selecione **Configurações**, expanda **Funções e escopos** e selecione **Grupos de funções**.

1. No campo de pesquisa, na parte superior direita da página, insira **Descoberta Eletrônica** e pressione ENTER no teclado.  Selecione **Gerenciador de Descoberta Eletrônica**.

1. Selecione **Editar**. Para a finalidade deste laboratório, você se definirá como administrador do MOD, Gerenciador e administrador da Descoberta Eletrônica.  Na prática, você atribui usuários específicos a funções específicas.
    1. A página “Gerenciar o Gerente de Descoberta Eletrônica” permite adicionar usuários à função de Gerente de Descoberta Eletrônica.
    1. Clique em **Selecionar usuário**. Pesquise e selecione **Administrador MOD**, pressione **Selecionar** na parte inferior da página e clique em **Avançar**.
    1. Na página “Gerenciar o Administrador de Descoberta Eletrônica”, selecione **Escolher usuários**. Pesquise e selecione **Administrador MOD**, pressione **Selecionar** na parte inferior da página, clique em **Avançar** e, depois, **Salvar**.
    1. Na página “Você atualizou com sucesso o grupo de funções”, selecione **Concluído**.

1. Mantenha essa guia do navegador aberta, pois você vai usá-la na próxima tarefa.

### Tarefa 2

Nesta tarefa, como Administrador da Descoberta Eletrônica (o administrador MOD é um administrador da Descoberta Eletrônica), você vai criar um caso para começar a usar a Descoberta Eletrônica (Standard).

1. Você ainda deve estar na página de funções do portal de conformidade. Se você fechou a guia do navegador da tarefa anterior, abra uma nova guia e insira **compliance.microsoft.com** para acessar o portal do Microsoft Purview.

1. No painel de navegação à esquerda, em Soluções, expanda **Descoberta Eletrônica** e escolha **Casos Padrão**.

1. No topo da página Descoberta Eletrônica (Standard), selecione **+ Criar um caso**.

1. Na janela Novo caso, insira um Nome do caso, **Caso de teste SC900** e selecione **Salvar** na parte inferior da página.

1. O caso agora deve aparecer na lista.

1. Como criador do caso e porque você tem privilégios de Administrador de Descoberta Eletrônica, você pode começar a trabalhar com ele.  

1. Mantenha essa guia do navegador aberta, pois você vai usá-la na tarefa seguinte.

### Tarefa 3

Agora que criou um caso de Descoberta Eletrônica (Standard), você pode começar a trabalhar nele.  Nesta tarefa, você criará uma retenção de Descoberta Eletrônica para o caso criado.  Especificamente, você criará uma retenção para a caixa de correio do Exchange pertencente a Alice Pena.

1. Abra a guia Descoberta Eletrônica (Standard) no navegador.

1. Na página Descoberta Eletrônica (Standard), selecione o caso criado na guia anterior, **Caso de teste SC900**.

1. Na Página inicial do caso, selecione a guia **Manter** e selecione **+Criar**.

1. No campo do nome, insira **Retenção teste** e selecione **Avançar**.

1. Na página Escolher localizações, selecione a opção de alternância ao lado de **Caixas de correio do Exchange** para definir o status como **Ativado**.  

1. Agora, selecione **Escolher usuários, grupos ou equipes**.  Na caixa de pesquisa, digite **Adele** e pressione Enter no teclado. Nos resultados da pesquisa, selecione **Alice Pena** e **Concluído**.

1. Na página Escolher locais, selecione **Avançar**.  Por uma questão de conveniência, para o laboratório, nenhuma outra localização será incluída nesta retenção.

1. A página Condições de consulta permite que você crie um bloqueio para itens com base em uma consulta que você pode criar.  Você pode optar por usar o Construtor de Consultas para criar uma consulta ou, para usuários mais avançados, pode usar o editor KQL. Para este exercício, você deseja que o bloqueio preserve todo o conteúdo no local especificado para o usuário especificado, portanto, você não criará uma consulta.

1. Revise suas configurações e selecione **Enviar**, isso pode levar um minuto e, em seguida, selecione **Concluído**.  A retenção de teste deve aparecer na lista.  Se você não encontrá-la de imediato, selecione **Atualizar**.

1. Mantenha essa guia do navegador aberta, pois você vai usá-la na tarefa seguinte.

### Tarefa 4

Com uma retenção estabelecida, você criará uma consulta de pesquisa.  Após a conclusão da pesquisa, a Descoberta Eletrônica dá suporte a ações, como a exportação e o download dos resultados para investigação futura.   Observação: as pesquisas associadas a um caso da Descoberta Eletrônica (Standard) não são listadas na página de pesquisa de conteúdo do portal do Microsoft Purview. Essas pesquisas são listadas apenas na página Pesquisas do caso da Descoberta Eletrônica (Standard) associado.

1. Abra a guia Caso de Teste SC900 no navegador.

1. Na página Caso de Teste de SC900, selecione **Pesquisas**.

1. Na página Pesquisar, selecione **+ Nova pesquisa**.

1. No campo Nome, insira **Retenção de Teste – Pesquisa de Vendas** e selecione **Avançar** na parte inferior da página.

1. Na página Escolher locais, selecione **locais em espera** e desmarque **Adicionar Conteúdo do Aplicativo para usuários locais**, pois seu ambiente de laboratório não tem usuários locais e, em seguida, selecione **Avançar**.

1. A página Condições de consulta permite que você crie uma pesquisa, com base em palavras-chave ou condições específicas que são satisfeitas. No campo palavra-chave, digite **Vendas** e selecione **Avançar**.

1. Revise suas configurações e selecione **Enviar**, isso pode levar um minuto e, em seguida, selecione **Concluído**.  A pesquisa deve aparecer na lista.  Se você não encontrá-la de imediato, selecione **Atualizar**.

1. Na janela Pesquisas, selecione a pesquisa criada, **Retenção Teste – Pesquisa de Vendas**.  Uma janela que é aberta com a guia Resumo selecionada.  Quando a pesquisa for concluída, o status indicará isso.  Você verá uma guia Estatísticas da pesquisa (se não encontrá-la, a pesquisa ainda poderá estar em execução e poderá levar alguns minutos para ser concluída).  Selecione a guia **Estatísticas de pesquisa** e selecione o menu suspenso próximo de Pesquisar conteúdo.  Você também pode exibir mais informações sobre o relatório de condição e os principais locais.  

1. Na parte inferior dessa página, clique em **Ações**.  Observe as opções disponíveis que incluem opções de exportação (as opções de exportação não podem ser selecionadas na plataforma do laboratório fornecida pelo hoster do laboratório autorizado, mas estão disponíveis em um ambiente de produção e são consideradas parte do fluxo de trabalho padrão). Selecione **Fechar**.

1. Saia do serviço e feche todas as janelas abertas do navegador.

### Revisão

Neste laboratório, você acompanhará as etapas necessárias para começar a usar a Descoberta Eletrônica (Standard), incluindo a configuração das permissões de funções para a Descoberta Eletrônica e a criação de um caso da Descoberta Eletrônica.  Com o caso criado, você acompanhou os elementos do fluxo de trabalho da Descoberta Eletrônica (Standard) criando uma retenção de Descoberta Eletrônica e uma consulta de pesquisa.
