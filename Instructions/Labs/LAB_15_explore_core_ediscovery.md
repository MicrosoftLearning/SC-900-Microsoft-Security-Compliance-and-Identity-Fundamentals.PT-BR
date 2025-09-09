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

Neste laboratório, você acompanhará as etapas necessárias para configurar a Descoberta Eletrônica, incluindo a configuração de permissões de função, a criação de um caso de Descoberta Eletrônica, a criação de uma retenção de Descoberta Eletrônica e a criação de uma consulta de pesquisa.  Observação:  O licenciamento para Descoberta Eletrônica requer a assinatura organizacional apropriada e licenciamento por usuário. Se você não sabe quais licenças dão suporte à Descoberta Eletrônica, visite [Introdução à Descoberta Eletrônica no Microsoft Purview](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery?view=o365-worldwide).

**Tempo estimado**: 45 minutos

### Tarefa 1

Para acessar a Descoberta Eletrônica ou ser adicionado como membro de um caso de Descoberta Eletrônica, um usuário deve receber as permissões apropriadas. Nesta etapa, você, como administrador global, adicionará usuários específicos como membros do grupo de funções do Gerente de Descoberta Eletrônica.

1. Você deve estar na home page do portal do Microsoft Purview.  Se você a fechou anteriormente, abra uma nova guia do navegador e insira **https://purivew.microsoft.com** .

1. No painel de navegação à esquerda, selecione **Configurações**, expanda **Funções e escopos** e selecione **Grupos de funções**.

1. No campo de pesquisa, na parte superior direita da página, insira **Descoberta Eletrônica** e pressione ENTER no teclado.  Selecione **Gerenciador de Descoberta Eletrônica**.

1. Selecione **Editar**. Para a finalidade deste laboratório, você se definirá como administrador do MOD, Gerenciador e administrador da Descoberta Eletrônica.  Na prática, você atribui usuários específicos a funções específicas.
    1. A página “Gerenciar o Gerente de Descoberta Eletrônica” permite adicionar usuários à função de Gerente de Descoberta Eletrônica.
    1. Clique em **Selecionar usuário**. Pesquise e selecione **Administrador MOD**, pressione **Selecionar** na parte inferior da página e clique em **Avançar**.
    1. Na página “Gerenciar o Administrador de Descoberta Eletrônica”, selecione **Escolher usuários**. Pesquise e selecione **Administrador MOD**, pressione **Selecionar** na parte inferior da página, clique em **Avançar** e, depois, **Salvar**.
    1. Na página “Você atualizou com sucesso o grupo de funções”, selecione **Concluído**.

1. Retorne à home page do Microsoft Purview selecionando **Página Inicial** no painel de navegação esquerdo.

1. Mantenha essa guia do navegador aberta, pois você vai usá-la na próxima tarefa.

### Tarefa 2

Nesta tarefa, como Administrador da Descoberta Eletrônica (o administrador MOD é um administrador da Descoberta Eletrônica), você vai criar um caso para começar a usar a Descoberta Eletrônica.

1. Você deve estar na home page do portal do Microsoft Purview.

1. No painel de navegação à esquerda, em Soluções, expanda **Descoberta Eletrônica** e escolha **Casos**.

1. Na página Casos, selecione **Criar caso**.

1. Na janela Novo caso, insira o nome para o caso, **SC900 Test Case** e , em seguida, selecione **Criar**.

1. O caso agora deve aparecer na lista.

1. Como criador do caso e porque você tem privilégios de Administrador de Descoberta Eletrônica, você pode começar a trabalhar com ele.  

1. Mantenha essa guia do navegador aberta, pois você vai usá-la na tarefa seguinte.

### Tarefa 3

Com um caso criado, você pode começar a trabalhar com ele.  Isso inclui a criação de uma consulta de pesquisa para localizar dados e conteúdo relevantes para seu caso, a aplicação de uma política de retenção, a criação de um conjunto de revisão e a exportação de dados. Nesta tarefa, você irá explorar algumas dessas opções.

1. Abra a guia Caso de Teste SC900 no navegador.

1. Na página SC900 Test Case, selecione  **Criar uma pesquisa**.

1. No campo nome, insira **SC900 Test Case** e selecione **Criar**.

1. Escolha **Adicionar fontes**. Observe as opções de filtro e as configurações padrão. Na caixa de pesquisa, insira **Pradeep** e pressione o enter no teclado. Nos resultados da pesquisa, selecione **Pradeep Gupta** e, em seguida, selecione **Salvar e fechar**. O Construtor de Condições permite criar uma consulta de pesquisa com base em palavras-chave ou condições específicas que sejam atendidas. No campo de palavras-chave, insira **Vendas**. A partir daqui, você pode selecionar para **Executar a consulta**.  Isso pode levar vários minutos.

1. Com os resultados da consulta retornados na forma de estatísticas, você pode exportar resultados.  Selecione **Exportar** para exibir as opções disponíveis e selecione **Cancelar** (as opções de exportação não podem ser selecionadas na plataforma do laboratório fornecida pelo hoster autorizado, mas estão disponíveis em um ambiente de produção e são consideradas parte do fluxo de trabalho).

1. Você pode adicionar a um conjunto de revisão para processamento adicional.  Selecione **Adicionar a um conjunto de revisão**. Insira um nome para o novo conjunto de revisão, **`SC900-review-set`**, mantenha as configurações padrão e selecione **Adicionar ao conjunto de revisão**.  Ela pode levar alguns minutos para ser concluída.  Agora você pode revisar e tomar ações a partir do conjunto de revisão, incluindo marcar itens, consultar o conjunto de revisão, executar análises e mais.  Explore as várias opções.

1. Você também pode criar políticas de retenção para preservar o conteúdo relevante para seu caso. Selecione **Manter políticas** e, em seguida, **Nova política**.  Insira um nome de política, **`SC900-hold`**, e selecione **Criar**.  Como na pesquisa, você precisa adicionar fontes de dados para a retenção e pode adicionar palavras-chave e condições para usar na política de retenção e, em seguida, você pode selecionar **Aplicar retenção**.  As ações que você pode executar em uma política de retenção incluem tentar novamente, desativar uma política e excluir uma política de retenção.

1. Saia do serviço e feche todas as janelas abertas do navegador.

### Revisão

Neste laboratório, acompanhamos as etapas necessárias de introdução à Descoberta Eletrônica, incluindo a configuração das permissões de funções para a Descoberta Eletrônica e a criação de um processo de Descoberta Eletrônica.  Com o caso criado, você explorou as opções disponíveis como parte do fluxo de trabalho da Descoberta Eletrônica, incluindo uma pesquisa de Descoberta Eletrônica, uma política de retenção, adicionar resultados da pesquisa a um conjunto de revisão e exportar resultados.
