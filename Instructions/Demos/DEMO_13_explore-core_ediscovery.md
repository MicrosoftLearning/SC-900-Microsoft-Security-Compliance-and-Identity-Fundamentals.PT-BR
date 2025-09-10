<!---
---
Demonstração: Título: "Explorar a Descoberta Eletrônica" Roteiro de aprendizagem/Módulo/Unidade: "Roteiro de aprendizagem: Descrever as funcionalidades do Microsoft Priva e do Microsoft Purview; Módulo 3: descrever as soluções de conformidade de dados do Microsoft Purview; Unidade 2: Descrever a Descoberta Eletrônica"
---
--->

# Demonstração: Explorar a Descoberta Eletrônica (Standard)

Essa demonstração é mapeada para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades do Microsoft Priva e do Microsoft Purview
- Módulo: descrever as soluções de conformidade de dados do Microsoft Purview
- Unidade: descrever a Descoberta Eletrônica

## Cenário de demonstração

Nesta demonstração, você acompanhará as etapas necessárias para configurar a Descoberta Eletrônica, incluindo a configuração de permissões de função, a criação de um caso de Descoberta Eletrônica, a criação de uma retenção de Descoberta Eletrônica e a criação de uma consulta de pesquisa.  OBSERVAÇÃO: no portal do Microsoft Purview, as atualizações na interface do usuário estão sendo lançadas gradualmente. Alguns locatários de laboratório/demonstração talvez ainda não exibam a interface do usuário mais recente, portanto, todas as etapas do laboratório são mostradas usando a interface do usuário clássica da Descoberta Eletrônica.

### Demonstração parte 1

Para acessar a Descoberta Eletrônica ou ser adicionado como membro de um caso de Descoberta Eletrônica, um usuário deve receber as permissões apropriadas. Nesta parte da demonstração, você, como administrador global, percorrerá o processo de adição de usuários específicos como membros do grupo de funções do Gerente de Descoberta Eletrônica.

1. Abra a guia do navegador no **Microsoft Purview**. Se você o fechou anteriormente, abra uma guia do navegador e, na barra de endereços, insira **https://purview.microsoft.com** e selecione **Introdução**.  
1. No painel de navegação esquerdo, selecione **Configurações**.
1. No painel de navegação que é aberto, selecione **Funções e escopo** para expandir a opção e, em seguida, selecione **Grupos de funções**.
1. Na caixa de pesquisa no lado direito da tela, pesquise o termo **Descoberta Eletrônica**.  Selecione **Gerenciador de Descoberta Eletrônica**.
    1. Selecione **Editar**.
    1. Clique em **Selecionar usuário**.
    1. Procure por Administrador MOD, marque a caixa ao lado de **Administrador MOD** e clique no botão **Selecionar** na parte inferior da página.
    1. Selecione **Avançar**, depois selecione **Salvar** e, finalmente, selecione **Concluído**.

1. Mantenha essa guia do navegador aberta.

### Demonstração parte 2

Nesta parte, como Administrador de Descoberta Eletrônica (o administrador MOD é um Administrador de Descoberta Eletrônica), você vai criar um caso para começar a usar a Descoberta Eletrônica.

1. Você deve estar na home page do portal do Microsoft Purview.

1. No painel de navegação à esquerda, em Soluções, expanda **Descoberta Eletrônica** e escolha **Casos**.

1. Na página Casos, selecione **Criar caso**.

1. Na janela Novo caso, insira o nome para o caso, **SC900 Test Case** e, em seguida, selecione **Criar**.

1. O caso agora deve aparecer na lista.

1. Como criador do caso e porque você tem privilégios de Administrador de Descoberta Eletrônica, você pode começar a trabalhar com ele.  

1. Mantenha essa guia do navegador aberta, pois você vai usá-la na tarefa seguinte.

### Demonstração parte 3

Com um caso criado, você pode começar a trabalhar com ele. Isso inclui a criação de uma consulta de pesquisa para localizar dados e conteúdo relevantes para seu caso, a aplicação de uma política de retenção, a criação de um conjunto de revisão e a exportação de dados. Nesta tarefa, você irá explorar algumas dessas opções. OBSERVAÇÃO: É recomendável que você crie um conjunto de pesquisa e revisão antes da apresentação, para que os resultados do conjunto de pesquisa e revisão estejam prontamente disponíveis durante a demonstração, já que essas ações podem levar vários minutos para serem concluídas.  

1. Abra a guia Caso de Teste SC900 no navegador.

1. Na página SC900 Test Case, selecione  **Criar uma pesquisa**.

1. No campo nome, insira **SC900 Test Case** e selecione **Criar**.

1. Escolha **Adicionar fontes**. Observe as opções de filtro e as configurações padrão. Na caixa de pesquisa, insira **`Pradeep`** e selecione **Pesquisar**. Nos resultados da pesquisa, selecione **Pradeep Gupta** e, em seguida, selecione **Salvar e fechar**. O Construtor de Condições permite criar uma consulta de pesquisa com base em palavras-chave ou condições específicas que sejam atendidas. No campo de palavras-chave, insira **Vendas**. A partir daqui, você pode selecionar para **Executar a consulta** na janela Escolher resultados da pesquisa. Para o locatário do laboratório, somente a exibição de estatísticas dos resultados da pesquisa está disponível. Observe as opções para organizar pelos principais indicadores. Selecione **Executar consulta**.  Isso pode levar vários minutos.

1. Com os resultados da consulta retornados na forma de estatísticas, você pode exportar resultados.  No canto superior direito da tela (ao lado de onde diz Adicionar ao conjunto de revisão), selecione **Exportar** para exibir as opções disponíveis e, em seguida, selecione **Cancelar**.

1. Você pode adicionar a um conjunto de revisão para processamento adicional.  Selecione **Adicionar a um conjunto de revisão**. Insira um nome para o novo conjunto de revisão, **`SC900-review-set`**, mantenha as configurações padrão e selecione **Adicionar ao conjunto de revisão**. Ela pode levar alguns minutos para ser concluída. Assim que os resultados do conjunto de revisão forem apresentados, você poderá explorar as diferentes opções, que incluem Análises, Consulta, Ações, Marcar arquivos e Gerenciar.

1. Você também pode criar políticas de retenção para preservar o conteúdo relevante para seu caso. Na janela Conjunto de revisão, selecione a guia **Retenção**.  Isso levará a você à janela Políticas de retenção. Selecione **Nova política**.  Insira um nome de política, **`SC900-hold`**, e selecione **Criar**.  Como na pesquisa, você precisa adicionar fontes de dados para a retenção e pode adicionar palavras-chave e condições para usar na política de retenção e, em seguida, você pode selecionar **Aplicar retenção**.  As ações que você pode executar em uma política de retenção incluem tentar novamente, desativar uma política e excluir uma política de retenção.

1. Saia do serviço e feche todas as janelas abertas do navegador.

### Revisão

Nesta demonstração, acompanhamos as etapas necessárias de introdução à Descoberta Eletrônica, incluindo a configuração das permissões de funções para a Descoberta Eletrônica e a criação de um processo de Descoberta Eletrônica.  Com o caso criado, você explorou as configurações para criar e exportar resultados de pesquisa, adicionar a um conjunto de revisão e criar uma política de retenção.
