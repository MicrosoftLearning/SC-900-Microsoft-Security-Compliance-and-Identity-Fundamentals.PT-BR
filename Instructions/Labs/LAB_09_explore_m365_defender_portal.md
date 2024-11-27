---
lab:
  title: Explorar o portal do Microsoft Defender
  module: Describe the threat protection capabilities of Microsoft XDR
---

# Laboratório: Explorar o portal do Microsoft Defender

Esse laboratório é mapeado para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades das soluções de segurança da Microsoft
- Módulo: descrever as funcionalidades de proteção contra ameaças do Microsoft Defender XDR
- Unidade: descrever o portal do Microsoft Defender

## Cenário do laboratório

Neste laboratório, você vai explorar o portal do Microsoft Defender acompanhando o conteúdo exibido na página de aterrissagem. Também vai explorar as opções do painel de navegação que fornece um acesso rápido à funcionalidade que integra a solução XDR (Detecção e Resposta Estendida) da Microsoft: o Microsoft Defender para Pontos de Extremidade e o Microsoft Defender para Office 365 (email e colaboração).  Por fim, você também vai explorar como o Microsoft Secure Score pode ajudar uma organização a aprimorar a postura de segurança.

**Tempo estimado**: 30 minutos

### Tarefa 1

Explorar a página inicial do Microsoft Defender.

1. Abra o Microsoft Edge. Na barra de endereços, insira **admin.microsoft.com**.

1. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é a sua ID de locatário exclusiva fornecida pelo provedor de hospedagem do laboratório) e selecione **Avançar**.
    1. Insira a senha de administrador fornecida pelo provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Dependendo do host do laboratório e se esta for a primeira vez que você está fazendo logon no locatário, pode ser que seja solicitado a concluir o processo de registro de MFA. Se este for o caso, siga as instruções na tela para configurar a MFA.
    1. Depois de entrar, você será levado para a página do Centro de administração do Microsoft 365.

1. À esquerda no painel de navegação do Centro de administração do Microsoft 365, abaixo de Centros de administração, selecione **Segurança**.  Se você não vir Segurança listada, selecione **Mostrar tudo** e, em seguida, selecione **Segurança**.  A página inicial do portal do Microsoft Defender é aberta em uma nova página do navegador.  

1. Se esta for a primeira vez que você visita o portal do Microsoft 365 Defender, você pode obter uma janela pop-up para fazer um tour rápido.  Você pode optar por fazer o breve tour ou fechar a janela.

1. A home page do portal do Microsoft Defender mostra muitos dos cartões comuns de que às equipes de segurança precisam utilizar. A composição de cartões e dados depende da função do usuário. Percorra a página para ver o conjunto padrão de cartões para a sua função de administrador global.

1. Os cartões exibidos podem ser personalizados de acordo com sua preferência.  Selecione **+ Adicionar cartões**. Uma Janela é aberta que exibe todos os cartões que estão disponíveis para adicionar à sua página inicial.  Talvez você já tenha todos os cartões exibidos; nesse caso, você verá a nota " Você já tem todos os cartões em sua página inicial". Clique em **X** no canto superior direito da janela para fechá-la.

1. Selecionar as reticências no canto superior direito de qualquer cartão fornecerá a opção de remover o cartão da página de aterrissagem.  

1. Você também pode mover os cartões. Posicione o cursor do mouse sobre a barra de título de qualquer cartão. Quando um sinal de adição aparecer no cursor, selecione o cartão e mova-o para o local desejado.  

1. Alguns cartões têm botões na parte inferior do cartão que são selecionáveis. O título de alguns cartões serve como um link para a página de seu tópico.  Por exemplo, se você selecionar o título do cartão do Microsoft Secure Score, ele o levará para a página do Microsoft Secure Score.  Você explorará mais sobre o Microsoft Secure Score em uma seção subsequente deste laboratório.

1. Mantenha essa janela do navegador aberta.

### Tarefa 2

Nesta parte do laboratório, você explorará algumas das opções disponíveis no painel de navegação à esquerda do portal do Defender.  Por meio do portal do Microsoft Defender, a Microsoft cumpre a promessa de uma plataforma de operações de segurança unificada. O portal do Microsoft Defender combina proteção, detecção, investigação e resposta a ameaças em toda a sua organização e todos os seus componentes, em um local central.  

1. Explore o painel de navegação à esquerda à vontade.

1. No painel de navegação à esquerda, selecione **Página Inicial** para voltar à home page do portal do Microsoft Defender.

### Tarefa 3

Nesta tarefa, você vai explorar como o Microsoft Secure Score pode ajudar uma organização a aprimorar a postura de segurança.

1. Você deve estar no portal do Microsoft Defender. No painel de navegação à esquerda, expanda **Gerenciamento de Exposição** e clique em **Secure Score**.  Se o Gerenciamento de Exposição não for mostrado em seu locatário, na página inicial do portal do Microsoft Defender, role para baixo até ver o cartão do **Microsoft Secure Score**. Selecione o título do cartão (o texto ficará azul quando você colocar o cursor do mouse sobre o título do cartão).

1. A página do Microsoft Secure Score é aberta na guia Visão geral. O Microsoft Secure Score é uma medida da postura de segurança de uma organização. A classificação de segurança da sua organização é mostrada como um percentual, acompanhado do número de pontos atingidos considerando o total de pontos possíveis e divididos por categoria. Selecione **Incluir**, ao lado de onde está a sua classificação de segurança.  Uma janela pequena é aberta, permitindo que você inclua a pontuação atingível, a pontuação planejada e a pontuação segura de licença atual na divisão da Pontuação da sua organização.  Selecione **Incluir** novamente para fechar a janela.

1. A página de visão geral também inclui as principais ações aprimoradas, pontuação de comparação, histórico e recursos adicionais.

1. Selecione **Ações recomendadas** na parte superior da página.  Observe as informações disponíveis na tabela.  

1. Selecione os primeiros itens da lista e examine as informações disponíveis. Na janela que será aberta, observe as opções de status disponíveis. Selecione a guia **Implementação** para exibir informações relacionadas à implementação. Selecione o **X** no canto superior direito para fechar esta janela.

1. Selecione a guia **Histórico** na parte superior da página.  Para cada atividade listada, há uma breve instrução que fornece contexto.  Selecione um item na tabela do histórico.  No canto superior direito da página de detalhes, em Histórico, selecione **X eventos** (onde X é um número).  A janela do histórico de ações será aberta, mostrando mais informações.  Selecione **Fechar** no canto inferior da página e selecione o **X** no canto superior direito da página de detalhes para retornar para a página Histórico.

1. Na parte superior da página, selecione **Métricas e tendências**.  Observe as informações disponíveis.  Selecione o **ícone de calendário** no canto superior direito da página.  Você pode restringir a exibição a um intervalo de datas personalizado.  A seleção do **ícone de filtro** permite filtrar a exibição por identidade e/ou aplicativos.  Fecha a janela e, no painel de navegação à esquerda, clique em **Página Inicial** para voltar à home page do Microsoft Defender.

1. Feche todas as guias abertas do navegador.

### Revisão

Neste laboratório, você explorou o portal do Microsoft Defender acompanhando o conteúdo exibido na página de aterrissagem, explorou as opções do painel de navegação que fornece acesso rápido à funcionalidade que integra a solução de XDR (Detecção e Resposta Estendida) da Microsoft, o Microsoft Defender para Pontos de Extremidade e o Microsoft Defender para Office 365 (email e colaboração).  Por fim, você também vai explorar como o Microsoft Secure Score pode ajudar uma organização a aprimorar a postura de segurança.
