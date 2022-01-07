---
lab:
    title: 'Explorar o Microsoft Defender for Cloud'
    module: 'Módulo 3 – Lição 2: Descrever as funcionalidades das soluções de segurança da Microsoft Descrever os recursos de gerenciamento de segurança do Azure'
---

# Laboratório: Explorar o Microsoft Defender for Cloud

## Cenário do laboratório
Neste laboratório, vamos explorar o Microsoft Defender for Cloud e aprender como o Azure Secure Score pode ser usado para melhorar a postura de segurança da sua organização.

**Tempo estimado**: 30 minutos

#### Tarefa 1: Nesta tarefa, vamos fazer um breve tour pelo Microsoft Defender for Cloud.
1.	Abra o Microsoft Edge. Na barra de endereço, digite **portal.azure.com**.

1. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (onde ZZZZZZ é sua ID de locatário exclusiva fornecida por seu provedor de hospedagem de laboratório) e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida por seu provedor de hospedagem de laboratório. Selecione **Entrar**.
    1. Se você receber um aviso para permanecer conectado, selecione **Sim**.

1. No canto superior esquerdo da tela, ao lado de onde está escrito Microsoft Azure, selecione o ícone de menu Mostrar portal (as três linhas horizontais também chamadas de ícone de hambúrguer) e, em seguida, À esquerda no painel de navegação, em Favoritos, selecione **Microsoft Defender for Cloud**.  Se não estiver listado em favoritos, na caixa de pesquisa, insira **Microsoft Defender for Cloud** e, na lista de resultados, selecione **Microsoft Defender for Cloud**.

1. Observe as informações disponíveis na página de visão geral do Microsoft Defender for Cloud.  

1. Você pode ver uma caixa de informações azul na parte superior da página indicando que você pode estar vendo informações limitadas.  Selecione **clique aqui**.
    1. Para garantir que seu locatário tenha uma visibilidade ampla, atribua as funções necessárias.  Selecione **Administrador de Segurança** e depois **Obter acesso** na parte inferior da página.
    1. É provável que apareça a mensagem O grupo de gerenciamento raiz não existe.  Pela descrição, o sistema vai criar um grupo para você.  Pode levar até 15 minutos para ser concluído (mas geralmente acaba antes).  Ao obter acesso, selecione **Microsoft Defender for Cloud** no canto superior esquerdo da página, acima de Obter permissões, e atualize a página de visão geral do Microsoft Defender for Cloud.

1. As informações na parte superior da página incluem o número de assinaturas do Azure, o número de Recursos avaliados, o número de recomendações ativas e outros alertas de segurança.  No corpo principal da página, há cartões que representam Secure Score, Conformidade regulatória, Insights, Azure Defender e muito mais.  

1. Na parte superior da página, selecione **Recursos avaliados**.  (Observe que isso equivale a selecionar Inventário À esquerda no painel de navegação da página inicial do Microsoft Defender for Cloud).
    1. Essa ação leva você para a página **Inventário** que mostra sua assinatura do Azure Pass.  Selecione **Azure Pass – Sponsorship**.
    1. A página Resource Health fornece uma lista de recomendações.  Na lista disponível, selecione **Deve haver mais de um proprietário atribuído à sua assinatura**.
    1. Selecione a seta suspensa ao lado de Etapas de correção. Observe como as etapas de correção detalhadas são fornecidas junto com a opção de ação.  
    1. Selecione **Microsoft Defender for Cloud** no canto superior esquerdo da tela para retornar à página de visão geral do Microsoft Defender for Cloud.

1. Na parte superior da página, selecione **Recomendações ativas**.  (Observe que isso equivale a selecionar Recomendações À esquerda no painel de navegação da página inicial do Microsoft Defender for Cloud).
    1. A página de recomendações mostra o painel do Secure Score.
    1. Abaixo do painel do Secure Score, há uma lista de controles. Cada controle de segurança representa um risco de segurança que deve ser mitigado e também inclui informações sobre a pontuação máxima associada a esse controle, a pontuação atual, o aumento potencial da pontuação e o status da integridade do recurso.  
    1. Selecione um dos controles, por exemplo **Habilitar MFA**.  Selecione um dos subitens, por exemplo **A MFA deve ser habilitada em contas com permissões de proprietário em sua assinatura**.  Na página que é aberta, você verá uma descrição, etapas de correção e recursos afetados. Feche a página selecionando o **X** no canto superior direito da tela.
    1. Feche a página de recomendações clicando no **X** no canto superior direito da tela para voltar à página de visão geral.

1. Na página principal, selecione **Conformidade regulatória**. A página de conformidade regulatória fornece uma lista de controles de conformidade.  Em cada controle, tem um conjunto de avaliações com base no Azure Security Benchmark, com recomendações para você proteger suas soluções de nuvem no Azure.
    1. Selecione **IM. Identity Management**, depois selecione **IM-6 Usar controles de autenticação fortes**.  A lista mostra as ações de responsabilidade do cliente que podem ser tomadas para melhorar a postura de conformidade.
    1. Selecione o **X** no canto superior direito da tela para fechar a página e voltar à página de visão geral do Microsoft Defender for Cloud. 
    1. Deixe a página de visão geral do Microsoft Defender for Cloud aberta; vamos usá-la na próxima tarefa.


#### Tarefa 2: Nesta tarefa, vamos navegar pela Classificação de segurança do Azure e explorar recomendações que podem melhorar sua classificação de segurança. 

1. Na página de visão geral do Microsoft Defender for Cloud, selecione o cartão **Classificação de Segurança**.
1. Selecione **Azure Pass – Sponsorship**.  Observe a sua classificação de segurança.
1. Na página de recomendações, selecione **Implementar práticas recomendadas de segurança** para expandir a lista. Observe que ele mostra o status de integridade do recurso em vermelho.
1. Selecione o item **Deve haver mais de um proprietário atribuído à sua assinatura**, que mostra o status do resource health em vermelho. 
1. Abaixo de onde diz **Recursos afetados**, certifique-se de que Recursos não íntegros esteja selecionado/sublinhado e, em seguida, selecione a assinatura do Azure listada.
1. No topo da página Controle de acesso (IAM), selecione **+ Adicionar** e depois **Adicionar atribuição de função** no menu suspenso.
    1. No lado esquerdo da página, selecione **Proprietário** (este deve ser o primeiro item listado) para que a linha seja destacada em cinza e selecione **Avançar** na parte inferior da página.
    1. Ao lado de onde diz Membros, selecione **+ Selecionar membros**. 
    1. Na janela Selecionar membros que se abre no lado direito da tela, selecione **Alex Wilber** e pressione **Selecionar** na parte inferior da página.  
    1. Na página Adicionar atribuição de função, verifique se Alex Wilber está listado como membro e selecione **Avançar** seguido de **Revisar + atribuir**.
    1. Pode levar até 24 horas para atualizar o status. Depois, sua classificação de segurança também vai ser atualizada, já que todos os itens do grupo Gerenciar acesso e permissões serão atendidos.
    1. No canto superior esquerdo da página, acima de Azure Pass, selecione **Microsoft Defender for Cloud** e depois Visão Geral para voltar à página de visão geral do Microsoft Defender for Cloud.
1. Deixe essa página aberta para a próxima tarefa.


#### Tarefa 3:  Lembre-se de que o Microsoft Defender for Cloud é oferecido em dois modos: sem recursos de segurança aprimorados (grátis) e com recursos de segurança aprimorados que estão disponíveis por meio dos planos do Microsoft Defender for Cloud. Nesta tarefa, você descobrirá como habilitar/desabilitar os vários planos do Microsoft Defender for Cloud.

1.	Na página de visão geral do Microsoft Defender for Cloud, selecione as **Configurações de ambiente** no painel de navegação esquerdo.
1. Selecione o sinal maior que **>** ao lado de onde está escrito Grupo raiz do locatário para expandi-lo (não selecione Grupo raiz do locatário diretamente, porque isso o direcionará para uma página diferente) e, em seguida, selecione **Azure Pass - Sponsorship**
1.	Na página de planos do Defender, observe como você pode selecionar Habilitar todos ou selecionar planos individuais do Defender. Deixe as configurações como estão com todos os planos desativados.
1.	Agora pode fechar a guia do navegador para sair do portal do Azure.


#### Revisão
Neste laboratório, exploramos o Microsoft Defender for Cloud e aprendemos como o Microsoft Defender for Cloud pode ser usado para melhorar a postura de segurança da sua organização.
