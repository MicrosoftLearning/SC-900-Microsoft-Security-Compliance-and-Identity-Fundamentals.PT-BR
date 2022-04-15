---
lab:
  title: Explorar o portal do Microsoft 365 Defender
  module: 'Module 3 Lesson 4: Describe the capabilities of Microsoft security solutions: Describe threat protection with Microsoft 365 Defender'
ms.openlocfilehash: c3b666c86b361f7d33c6ae7f3639b7b015d8fa30
ms.sourcegitcommit: c14538b208890797642cfe5c35abf6bea45364bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/15/2022
ms.locfileid: "142614405"
---
# <a name="lab-explore-the-microsoft-365-defender-portal"></a>Laboratório: Explorar o portal do Microsoft 365 Defender

## <a name="lab-scenario"></a>Cenário do laboratório
Neste laboratório, vamos explorar o portal do Microsoft 365 Defender através do conteúdo exibido na página de aterrissagem. Também vamos explorar as opções do painel de navegação, que fornece um acesso rápido à funcionalidade que integra a solução Extended Detection and Response [Detecção e Resposta Estendidas] (XDR) da Microsoft: O Microsoft Defender para Pontos de Extremidade e o Microsoft Defender para Office 365 (email e colaboração).  Por fim, vamos explorar como o Microsoft Secure Score pode ajudar a melhorar a postura de segurança de uma organização.


**Tempo estimado**: 10 a 15 minutos

#### <a name="task-1--explore-the-microsoft-365-defender-landing-page"></a>Tarefa 1:  Explorar a página de aterrissagem do Microsoft 365 Defender.

1. Abra o Microsoft Edge. Na barra de endereços, insira **admin.microsoft.com**.

1. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é sua ID de locatário exclusiva fornecida pelo provedor de hospedagem de laboratório) e selecione **Avançar**.
   
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem de laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**. Vamos ser direcionados à página Centro de administração do Microsoft 365.

1. À esquerda no painel de navegação do Centro de administração do Microsoft 365, selecione **Segurança**.  Se você não vir Segurança listada, selecione **Mostrar tudo** e, em seguida, selecione **Segurança**.  A página inicial do Portal do Microsoft 365 Defender vai ser aberta no navegador.  

1. Se essa for a primeira vez que você visita o portal do Microsoft 365 Defender, pode ser que apareça uma janela pop-up para fazer um tour rápido.  A realização do tour é recomendada.  Selecione **Fazer um tour rápido**.  Leia a descrição apresentada a cada janela pop-up. Depois, selecione **Avançar**. Continue o tour até o fim e selecione **Concluído**.

1. O lado direito do painel de navegação oferece links/acesso a informações que fazem parte do Extended Detection and Response (solução XDR) da Microsoft, incluindo incidentes e alertas, buscas, central de ações, análise de ameaças, classificação de segurança e muito mais.  Ele também inclui um acesso rápido ao Microsoft Defender para Ponto de Extremidade (links listados em Pontos de extremidade) e Defender para Office 365 (links listados em Email e Colaboração).  Explorar essas opções selecionando alguns links.   Para voltar à página inicial do portal do Microsoft 365 Defender, selecione **Página Inicial** à esquerda no painel de navegação.  Observação: talvez você não encontre muitas informações listadas nessas guias porque não tem dispositivos anexados e pode não haver nenhuma ameaça ou alerta ativo.

1. A página inicial do portal do Microsoft 365 Defender mostra muitos dos cartões comuns necessários às equipes de segurança. A composição dos cartões e dados depende da função do usuário. Role a página para exibir o conjunto padrão de cartões para a sua função de administrador global.

1. Os cartões exibidos podem ser personalizados de acordo com a sua preferência.  Selecione **+Adicionar cartões**. Uma janela será aberta indicando que todos os cartões já estão na sua página inicial.  Feche a janela selecionando o **X** no canto superior direito da tela.

1. Ao selecionar as reticências na parte superior direita de qualquer cartão, encontramos mais ações disponíveis.  

1. Também é possível mover os cartões. Passe o cursor do mouse no título de qualquer cartão até aparecer um sinal de adição no cursor; então, basta selecionar o cartão e movê-lo até o local desejado.

1. Ao selecionar o título de um cartão, encontramos informações adicionais sobre esse tópico. Vamos explorar isso na próxima tarefa.  Mantenha a janela do navegador aberta.

#### <a name="task-2-in-this-task-you-will-explore-how-microsoft-secure-score-can-help-an-organization-improve-its-security-posture"></a>Tarefa 2: Nesta tarefa, vamos explorar como o Microsoft Secure Score pode ajudar a melhorar a postura de segurança de uma organização.

1. Na Página inicial do portal do Microsoft 365 Defender, selecione **Microsoft Secure Score** a partir do título do cartão (o texto vai ficar azul).  Também é possível selecionar **Classificação de segurança** do lado esquerdo do painel de navegação.

1. A página do Microsoft Secure Score abre na guia Visão geral.  O Microsoft Secure Score mede a postura de segurança de uma organização. Essa classificação de segurança é exibida em porcentagem, juntamente com o número de pontos atingidos divididos em categorias. Selecione **Incluir**, ao lado de onde está a sua classificação de segurança.  Uma janela pequena é aberta, permitindo que você inclua a pontuação atingível, a pontuação planejada e a pontuação segura de licença atual na divisão da Pontuação da sua organização.  Selecione **Incluir** novamente para fechar a janela.

1. A página de visão geral também inclui principais ação de melhoria, classificação por comparação, histórico e recursos adicionais.

1. Selecione **Ação de melhoria** na parte superior da página.  Observe, para cada item, as informações disponíveis na tabela, incluindo o impacto da classificação e os pontos atingidos.  

1. Ao selecionar um item da lista, são apresentadas informações detalhadas.  Selecione **Exigir MFA para Funções administrativas**.  Selecione **Editar status & plano de ação**.  Na janela aberta, observe as opções de status disponíveis. Selecione o **X** no canto superior direito para fechar esta janela

1. Na parte inferior da página, selecione **Gerenciar no Microsoft Azure**.  Uma nova guia do navegador vai ser aberta, levando diretamente à página Políticas de Acesso Condicional.  Se você realizou o exercício do laboratório de Acesso condicional, a política deve aparecer listada. Volte à guia Classificação de segurança da Microsoft no seu navegador para retornar à página de ações de melhoria e exigir MFA para funções administrativas. No canto superior direito da janela, selecione o **X** para fechar essa janela e voltar à página de ações de melhoria.

1. Selecione a guia **Histórico** na parte superior da página.  Algumas atividades podem mostrar pontos negativos.  Conforme descrito no campo de atividades, isso pode ocorrer caso um item tenha sido removido por não ser mais relevante.  Selecione um item a partir da tabela do histórico.  Uma página detalhada para o item selecionado é aberta.  Explore as opções disponíveis.  Para sair da página de detalhes e retornar para a página de histórico, selecione o **X** no canto superior direito da página.

1. Na parte superior da página, selecione **Métricas e tendências**.  Observe as informações disponíveis.  No canto superior direito da página, selecione o **ícone de calendário**.  Você pode refinar a visualização, personalizando um intervalo de datas.  Ao selecionar o **ícone de filtro**, é possível filtrar por Identidade, Dispositivos e/ou aplicativos.  Feche a janela e selecione **Página Inicial** do lado esquerdo painel de navegação para voltar à página inicial do Microsoft 365 Defender.

1. Feche a página do navegador.

#### <a name="review"></a>Revisão
Neste laboratório, exploramos o portal do Microsoft 365 Defender através do conteúdo exibido na página de aterrissagem. Vimos as opções do painel de navegação, que oferece um acesso rápido à funcionalidade que integra a solução Extended Detection and Response (XDR) da Microsoft, do Microsoft Defender para Pontos de Extremidade e do Microsoft Defender para Office 365 (email e colaboração).  Por fim, exploramos como o Microsoft Secure Score pode ajudar a melhorar a postura de segurança de uma organização.
