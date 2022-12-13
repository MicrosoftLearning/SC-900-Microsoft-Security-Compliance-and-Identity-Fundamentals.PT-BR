<a name="---"></a><!---
---
Laboratório: Título: 'Explorar o Microsoft Defender para Nuvem' Roteiro de Aprendizagem/Módulo/Unidade: 'Roteiro de aprendizagem: descrever as funcionalidades das soluções de segurança da Microsoft; Módulo 2: descrever as funcionalidades do gerenciamento de segurança do Azure; Unidade 3: descrever o Microsoft Defender para Nuvem'
---
--->

# <a name="lab-explore-microsoft-defender-for-cloud"></a>Laboratório: Explorar o Microsoft Defender para Nuvem

Esse laboratório é mapeado para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades da solução de segurança da Microsoft
- Módulo: descrever os recursos de gerenciamento de segurança do Azure
- Unidade: descrever o Microsoft Defender para Nuvem

## <a name="lab-scenario"></a>Cenário do laboratório

Neste laboratório, você vai explorar o Microsoft Defender para Nuvem.  OBSERVAÇÃO: a assinatura do Azure fornecida pelo ALH (Hoster do Laboratório Autorizado) limita o acesso e poderá enfrentar atrasos mais longos do que o normal.

**Tempo estimado**: 30 minutos

### <a name="task-1"></a>Tarefa 1:

Nesta tarefa, você fará um passo a passo de alto nível de algumas das funcionalidades do Microsoft Defender para Nuvem

1. Abra o Microsoft Edge. Na barra de endereços, insira **portal.azure.com**.
1. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira o nome de usuário fornecido pelo provedor de hospedagem do laboratório e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**.

1. Na barra de pesquisa azul, insira **Microsoft Defender para Nuvem** e, na lista de resultados, selecione **Microsoft Defender para Nuvem**.

1. Se esta for a primeira vez que você entra no Microsoft Defender para Nuvem com sua assinatura, você poderá chegar à página Introdução e precisar fazer a atualização.  Role a página até a parte inferior e selecione **Lembrar-me mais tarde** (ou **Ignorar**).  Você será direcionado à página Visão geral.

1. Na página Visão geral do Microsoft Defender para Nuvem, observe as informações disponíveis na página (se você observar 0 recursos avaliados e recomendações ativas, atualize a página do navegador. Isso pode levar alguns minutos).  As informações na parte superior da página incluem o número de assinaturas do Azure, o número de Recursos avaliados, o número de recomendações ativas e outros alertas de segurança.  No corpo principal da página, há cartões que representam a Postura de segurança, a Conformidade regulatória, os Insights, entre outros.  Observação: a iniciativa de política padrão do Microsoft Defender para Nuvem, que normalmente precisará ser atribuída pelo administrador, já foi atribuída como parte da configuração da assinatura do Azure. No entanto, a classificação de segurança será mostrada como 0%, pois pode haver um atraso de até 24 horas para o Azure refletir uma classificação inicial.

1. Na parte superior da página, selecione **Recursos avaliados**.  (Observe que isso equivale a selecionar Inventário no painel de navegação esquerdo da página inicial da Central de Segurança).
    1. Isso levará você à página **Inventário** que lista os recursos atuais. Selecione o recurso de máquina virtual, **sc900-winwm**. Esse recurso está associado à máquina virtual usada no laboratório anterior.
    1. A página Integridade do recurso da VM fornece uma lista de recomendações.  Na lista disponível, selecione qualquer item que mostre o status **não íntegro**.
    1. Observe a descrição detalhada.  Selecione a seta suspensa ao lado de Etapas de correção. Observe como as instruções de correção (ou links para instruções) são fornecidas com a opção de executar uma ação.  Saia da janela sem executar nenhuma ação.
    1. Volte à página de visão geral do Microsoft Defender para Nuvem selecionando **Microsoft Defender para Cloud | Visão geral** na parte superior da página, acima de Integridade do recurso.

1. No painel de navegação à esquerda, selecione **Recomendações**.  (Observe que isso equivale a selecionar Recomendações ativas na parte superior da página de visão geral do Microsoft Defender para Nuvem).
    1. Verifique se a guia **Todas as recomendações** está selecionada (sublinhada).  Observe a exibição do painel que mostra Recomendações ativas por gravidade, Integridade do recurso, entre outros.
    1. Observe que alguns itens são mostrados como recursos não íntegros, conforme descrito pela barra vermelha à direita do item de linha.  Na lista, selecione **O Microsoft Defender para Resource Manager deve ser habilitado**.  Na página que será aberta, você verá uma descrição, as etapas de correção e os recursos afetados. Feche a página selecionando o **X** no canto superior direito da tela.
    1. Feche a página de recomendações clicando no **X** no canto superior direito da tela para voltar à página de visão geral.

1. No painel de navegação principal à esquerda, selecione **Conformidade regulatória**. A página de conformidade regulatória fornece uma lista de controles de conformidade com base no parâmetro de comparação de segurança da nuvem da Microsoft (verifique se a guia Parâmetro de comparação de segurança da nuvem da Microsoft está selecionada/sublinhada). Em cada domínio de controle há um subconjunto de controles e, para cada controle, há uma ou mais avaliações. Cada avaliação fornece informações, incluindo descrição, correção e recursos afetados.
    1. Vamos explorar uma das áreas de domínios de controle. Selecione (expanda) **NS. Segurança de Rede**. Uma lista de controles relacionados à segurança de rede é exibida.
    1. Selecione **NS-10. O Microsoft Defender para DNS deve ser habilitado**. Observe a lista de avaliações automatizadas (que incluem avaliações automatizadas para a AWS) e como cada item de linha de avaliação fornece informações, incluindo o tipo de recurso, os recursos com falha e as estações de conformidade. Selecione as avaliações listadas.  Aqui você verá informações, incluindo uma descrição, as etapas de correção e os recursos afetados.
    1. Selecione o **X** no canto superior direito da tela para fechar a página.
    1. Selecione **Visão geral** no painel de navegação à esquerda para voltar à página Visão geral do Microsoft Defender para Nuvem.
    1. Mantenha aberta a página de visão geral do Microsoft Defender para Nuvem, pois você a usará na próxima tarefa.

### <a name="task-2"></a>Tarefa 2:

Lembre-se de que o Microsoft Defender para Nuvem é oferecido em dois modos: sem recursos de segurança aprimorada (gratuitos) e com recursos de segurança aprimorada que estão disponíveis por meio dos planos do Microsoft Defender para Nuvem. Nesta tarefa, você descobrirá como habilitar/desabilitar os vários planos do Microsoft Defender para Nuvem.

1. Na página de visão geral do Microsoft Defender para Nuvem, selecione as **Configurações de ambiente** no painel de navegação esquerdo.
1. Selecione a caixa **Expandir tudo** e escolha a **Assinatura MOC – lodXXXXXXXX** listada ao lado do ícone de chave amarela.
1. Na página Planos do Defender, observe como você pode selecionar Habilitar todos ou selecionar planos individuais do Defender. 
    1. Verifique se o status do CSPM está definido como **Ativado**, caso contrário, defina-o agora.  
    1. Habilite o plano para servidores.  Selecione **Ativado** para o item de linha Servidores e escolha **Salvar** na parte superior da página.
1. Feche todas as guias abertas do navegador.

### <a name="review"></a>Revisão

Neste laboratório, você explorou o Microsoft Defender para Nuvem.
