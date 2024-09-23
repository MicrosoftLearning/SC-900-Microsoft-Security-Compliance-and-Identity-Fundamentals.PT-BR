<!---
---
Demonstração: Título: "Explorar o fluxo de trabalho da Descoberta Eletrônica" Roteiro de aprendizagem/Módulo/Unidade: "Roteiro de aprendizagem: Descrever as funcionalidades do Microsoft Priva e do Microsoft Purview; Módulo 3: descrever as soluções de conformidade de dados do Microsoft Purview; Unidade 2: Descrever a Descoberta Eletrônica"
---
--->

# Demonstração: explorar o fluxo de trabalho da Descoberta Eletrônica (Standard)

Essa demonstração é mapeada para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: Descrever as funcionalidades do Microsoft Priva e do Microsoft Purview
- Módulo: Descrever as soluções de conformidade de dados do Microsoft Purview
- Unidade: Descrever a Descoberta Eletrônica

## Cenário de demonstração

Nesta demonstração, você acompanhará as etapas necessárias para configurar a Descoberta Eletrônica, incluindo a configuração de permissões de função, a criação de um caso de Descoberta Eletrônica, a criação de uma retenção de Descoberta Eletrônica e a criação de uma consulta de pesquisa.  OBSERVAÇÃO: no portal do Microsoft Purview, as atualizações na interface do usuário estão sendo lançadas gradualmente. Alguns locatários de laboratório/demonstração talvez ainda não mostrar a interface do usuário mais recente, portanto, todas as etapas do laboratório são mostradas usando a interface do usuário clássica de Descoberta Eletrônica.

### Demonstração parte 1

Para acessar a Descoberta Eletrônica (Standard) ou ser adicionado como membro de um caso da Descoberta Eletrônica, um usuário deve receber as permissões apropriadas. Nesta parte da demonstração, você, como administrador global, percorrerá o processo de adição de usuários específicos como membros do grupo de funções do Gerente de Descoberta Eletrônica.

1. Abra a guia do navegador no **Microsoft Purview**. Se a tiver fechado previamente, abra uma guia do navegador e, na barra de endereços, insira **https://purview.microsoft.com**. Para acessar o novo portal do Microsoft Purview, marque a caixa ao lado de onde diz **"Eu concordo com os termos de divulgação de fluxo de dados e Políticas de Privacidade"** e escolha **Introdução**.  
1. No painel de navegação à esquerda, clique em **Configurações**
1. No painel de navegação que abriu, selecione **Funções e escopo** para expandir a opção e, em seguida, selecione **Grupos de funções**.
1. Na caixa de pesquisa no lado direito da tela, pesquise o termo **Descoberta Eletrônica**.  Selecione **Gerenciador de Descoberta Eletrônica**.
    1. Selecione **Editar**.
    1. Selecione **Escolher usuários**.
    1. Procure por Administrador do MOD, marque a caixa ao lado de **Administrador do MOD** e clique no botão **Selecionar** na parte inferior da página.
    1. Clique em **Avançar**, **Salvar** e, por fim, em **Concluído**.

1. Mantenha essa guia do navegador aberta.

### Demonstração parte 2

Nesta parte, você criará um caso para começar a usar a Descoberta Eletrônica (Padrão).

1. No painel de navegação à esquerda, clique em **Soluções**, **Descoberta Eletrônica** e **Casos padrão**.

1. No topo da página Descoberta Eletrônica (Standard), selecione **+ Criar um caso**.

1. Na janela Novo caso, insira um Nome do caso, **Caso de teste SC900** e selecione **Salvar** na parte inferior da página.

1. O caso agora deve aparecer na lista.

1. Como criador do caso e porque você tem privilégios de Administrador de Descoberta Eletrônica, você pode começar a trabalhar com ele.  

1. Mantenha essa guia do navegador aberta.

### Demonstração parte 3

Agora que criou um caso de Descoberta Eletrônica (Standard), você pode começar a trabalhar nele.  Nesta parte, você criará uma retenção de Descoberta Eletrônica para o caso criado.  Especificamente, você criará uma retenção para a caixa de correio do Exchange pertencente a Alice Pena.

1. Na página Descoberta Eletrônica (Standard), selecione o caso criado – **Caso de teste SC900**.

1. Na página inicial do caso, selecione a guia **Manter** e selecione **+Criar**.

1. No campo do nome, insira **Retenção teste** e selecione **Avançar**.

1. Na página Escolher localizações, selecione a opção de alternância ao lado de **Caixas de correio do Exchange** para definir o status como **Ativado**.  

1. Agora, selecione **Escolher usuários, grupos ou equipes**.  Na caixa de pesquisa, digite **Adele** e pressione Enter no teclado. Nos resultados da pesquisa, selecione **Alice Pena** e **Concluído**.

1. Na página Escolher locais, selecione **Avançar**.  Por uma questão de conveniência, para a demonstração, nenhuma outra localização será incluída nesta retenção.

1. A página Condições de consulta permite que você crie uma retenção, com base em palavras-chave ou condições específicas atendidas. Selecione **+ Adicionar condição** para ver as opções disponíveis.  Selecione **Avançar**. Sem nenhuma condição, a retenção preservará todo o conteúdo no local especificado.

1. Revise suas configurações e selecione **Enviar**, isso pode levar um minuto e, em seguida, selecione **Concluído**.  A retenção de teste deve aparecer na lista.  Se você não encontrá-la de imediato, selecione **Atualizar**.

1. Mantenha essa guia do navegador aberta.

### Demonstração parte 4

Com uma retenção estabelecida, você criará uma consulta de pesquisa.  Após a conclusão da pesquisa, a Descoberta Eletrônica dá suporte a ações, como a exportação e o download dos resultados para investigação futura.   Observação: as pesquisas associadas a um caso da Descoberta Eletrônica (Standard) não são listadas na página Pesquisa de conteúdo do portal de conformidade do Microsoft Purview. Essas pesquisas são listadas apenas na página Pesquisas do caso da Descoberta Eletrônica (Standard) associado.

1. Na página Caso de Teste de SC900, selecione **Pesquisas**.

1. Na página Pesquisar, selecione **+ Nova pesquisa**.

1. No campo Nome, insira **Retenção de Teste – Pesquisa de Vendas** e selecione **Avançar** na parte inferior da página.

1. Na página Escolher locais, selecione **locais em espera** e desmarque **Adicionar Conteúdo do Aplicativo para usuários locais**, pois seu ambiente de laboratório não tem usuários locais e, em seguida, selecione **Avançar**.

1. A página Condições de consulta permite que você crie uma pesquisa, com base em palavras-chave ou condições específicas que são satisfeitas. No campo palavra-chave, digite **Vendas** e selecione **Avançar**.

1. Revise suas configurações e selecione **Enviar**, isso pode levar um minuto e, em seguida, selecione **Concluído**.  A pesquisa deve aparecer na lista.  Se você não encontrá-la de imediato, selecione **Atualizar**.

1. Na janela Pesquisas, selecione a pesquisa criada, **Retenção Teste – Pesquisa de Vendas**.  Uma janela que é aberta com a guia Resumo selecionada.  Quando a pesquisa for concluída, o status indicará isso.  Você verá uma guia Estatísticas da pesquisa (se não encontrá-la, a pesquisa ainda poderá estar em execução e poderá levar alguns minutos para ser concluída).  Selecione a guia **Estatísticas de pesquisa** e selecione o menu suspenso próximo de Pesquisar conteúdo.  Você também pode exibir mais informações sobre o relatório de condição e os principais locais.  

1. Na parte inferior dessa página, clique em **Ações**.  Observe as opções disponíveis que incluem opções de exportação. Selecione **Fechar**.

1. Feche todas as guias abertas do navegador.

### Revisão

Nesta demonstração, você acompanhará as etapas necessárias para começar a usar a Descoberta Eletrônica (Standard), incluindo a configuração das permissões de funções para a Descoberta Eletrônica e a criação de um caso da Descoberta Eletrônica.  Com o caso criado, você acompanhou os elementos do fluxo de trabalho da Descoberta Eletrônica (Standard) criando uma retenção de Descoberta Eletrônica e uma consulta de pesquisa.
