<!---
---
Demonstração: Título: 'Microsoft Defender para Nuvem' Roteiro de Aprendizagem/Módulo/Unidade: 'Roteiro de Aprendizagem: descrever as capacidades das soluções de segurança da Microsoft; Módulo 2: descrever as capacidades de gerenciamento de segurança do Azure; Unidade 3: descrever o gerenciamento da postura de segurança na nuvem'
---
--->

# Demonstração: Microsoft Defender para Nuvem

Essa demonstração é mapeada para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades das soluções de segurança da Microsoft
- Módulo: descrever os recursos de gerenciamento de segurança do Azure
- Unidade: descrever o gerenciamento da postura de segurança na nuvem

## Cenário de demonstração

Nesta demonstração, você verá o Microsoft Defender para Nuvem e mostrará como ele pode ser usado para aprimorar a postura de segurança de uma organização.  OBSERVAÇÃO: a assinatura do Azure gerenciada pelo AH (Hoster do Laboratório Autorizado) pode limitar o acesso e enfrentar atrasos mais longos do que o normal.

### Demonstração parte 1

Nesta tarefa de demonstração, você fará um passo a passo de alto nível de algumas das funcionalidades do Microsoft Defender para Nuvem.

1. Abra a guia do navegador **Página Inicial – Microsoft Azure**.  Se tiver fechado previamente a guia, abra uma página do navegador e, na barra de endereços, insira **https://portal.azure.com** . Entre com as credenciais do Azure fornecidas pelo hoster de laboratório autorizado (ALH).  Isso o levará você à página inicial dos serviços do Azure.

1. Na barra de pesquisa azul, insira **Microsoft Defender para Nuvem** e, na lista de resultados, selecione **Microsoft Defender para Nuvem**.

1. Se esta for a primeira vez que você entra no Microsoft Defender para Nuvem com sua assinatura, você poderá chegar à página Introdução e precisar fazer a atualização.  Role a página até a parte inferior e selecione **Pular**.  Você será direcionado à página Visão geral. Observe as informações disponíveis na página Visão Geral do Microsoft Defender para Nuvem.  As informações na parte superior da página incluem o número de assinaturas do Azure, o número de recursos avaliados, o número de recomendações ativas e todos os alertas de segurança.  No corpo principal da página, há cartões que representam a Postura de segurança, a Conformidade regulatória, os Insights, entre outros.  Todas as assinaturas têm o CSPM básico habilitado por padrão, o que permite uma pontuação segura.  
    1. Se o valor da pontuação segura for mostrado como 0%, é porque pode haver um atraso de até 24 horas para que o Azure reflita uma pontuação inicial.  
    1. Também é importante chamar a atenção para o fato de que o Defender para Nuvem é uma solução multinuvem que pode fornecer ajuda para melhorar sua postura de segurança não apenas com o Azure, mas também com o AWS e o Google Cloud Platform.

1. Em primeiro lugar, você deseja mostrar que o Microsoft Defender para Nuvem usa o Microsoft Cloud Security Benchmark como uma iniciativa de política padrão.  No painel de navegação à esquerda, selecione **Configurações do ambiente**. Na janela principal, selecione **Expandir tudo**.  A exibição expandida mostrará sua assinatura em texto azul.  Selecione a assinatura **MOC Subscription--lodXXXXXX**.

1. No painel de navegação à esquerda, selecione a **Política de segurança**, que está listada nas configurações de política. Se a iniciativa padrão não for atribuída, selecione **Atribuir política**.
    1. Observe que, na guia noções básicas, a definição da iniciativa é parâmetro de comparação de segurança da nuvem da Microsoft.  Essa opção está esmaecida porque é a iniciativa padrão e tudo o que estamos fazendo aqui é atribuí-la.
    1. Selecione **Revisar + criar** e **Criar**. Se desejar, você poderá percorrer os parâmetros configurados para as diferentes guias antes de selecionar a opção que será examinada e criada.
    1. Essa é uma etapa importante para garantir que você possa ver as recomendações de segurança com base no Microsoft Cloud Security Benchmark.  

1. Observe também que existem padrões regulamentares e do setor que você deve adicionar e que estão prontos para uso. Se os listados forem mostrados como preteridos, selecione **Adicionar mais padrões** para ver uma lista completa.  Selecione um na lista e adicione-o manualmente selecionando **Analisar + criar** e, em seguida, **Criar**.  Você será adicionado à lista de regulamentações padrão e do setor.

1. Selecione **Visão geral**.  No corpo principal da página, há cartões que representam a Postura de segurança, a Conformidade regulatória, os Insights, entre outros.  Todas as assinaturas têm o CSPM básico habilitado, o que fornece uma pontuação segura. O valor é mostrado como 0% porque pode haver um atraso de até 24 horas para que o Azure reflita uma pontuação inicial.  Embora a pontuação de segurança atualmente mostre 0%, chame a atenção para o fato de que o Defender para Nuvem é uma solução multinuvem que pode fornecer ajuda para melhorar sua postura de segurança não apenas com o Azure, mas também com o AWS e o Google Cloud Platform.

1. Na parte superior da página, selecione **Recursos avaliados**.  (Observe que isso equivale a selecionar Inventário no painel de navegação esquerdo da página inicial da Central de Segurança).
    1. Isso levará você à página **Inventário** que lista os recursos atuais. Selecione o recurso de máquina virtual, **sc900-winwm**. Esse recurso está associado à máquina virtual que você usou no laboratório/demostração anterior.
    1. A página Integridade do recurso da VM fornece uma lista de recomendações.  Na lista disponível, selecione qualquer item que mostre o status **não íntegro**.
    1. Observe a descrição detalhada.  Selecione a seta suspensa ao lado de Etapas de correção. Observe como as instruções de correção (ou links para instruções) são fornecidas com a opção de executar uma ação.  Saia da janela sem executar nenhuma ação.
    1. Volte à página de visão geral do Microsoft Defender para Nuvem selecionando **Microsoft Defender para Cloud | Visão geral** na parte superior da página, acima de Integridade do recurso.

1. No painel de navegação à esquerda, selecione **Recomendações**.  (Observe que isso equivale a selecionar Recomendações ativas na parte superior da página de visão geral do Microsoft Defender para Nuvem).
    1. Verifique se a guia **Todas as recomendações** está selecionada (sublinhada).  Observe a exibição do painel que mostra Recomendações ativas por gravidade, Integridade do recurso, entre outros.
    1. Observe que alguns itens são mostrados como recursos não íntegros, conforme descrito pela barra vermelha à direita do item de linha.  Na lista, selecione qualquer recurso não íntegro.  Na página que será aberta, você verá uma descrição, as etapas de correção e os recursos afetados. Saia desta página, selecionando o **X** no canto superior direito da tela.
    1. Saia da página de recomendações selecionando o **X** no canto superior direito da tela para retornar à página de visão geral.

1. No painel de navegação principal à esquerda, selecione **Conformidade regulatória**.  **OBSERVAÇÃO**: se você vir que não existe assinatura para calcular a conformidade, é porque pode haver um atraso de até 24 horas para que as informações apareçam. Mova para a Tarefa 2.  Se você vir as informações, prossiga com as etapas a seguir.
    1. A página de conformidade regulatória fornece uma lista de controles de conformidade com base no parâmetro de comparação de segurança da nuvem da Microsoft (verifique se a guia Parâmetro de comparação de segurança da nuvem da Microsoft está selecionada/sublinhada). Em cada domínio de controle há um subconjunto de controles e, para cada controle, há uma ou mais avaliações. Cada avaliação fornece informações, incluindo descrição, correção e recursos afetados.
    1. Vamos explorar uma das áreas de domínios de controle. Selecione (expanda) **NS. Segurança de Rede**. Uma lista de controles relacionados à segurança de rede é exibida.
    1. Selecione **NS-10. O Microsoft Defender para DNS deve ser habilitado**. Observe a lista de avaliações automatizadas (que incluem avaliações automatizadas para a AWS) e como cada item de linha de avaliação fornece informações, incluindo o tipo de recurso, os recursos com falha e as estações de conformidade. Selecione as avaliações listadas.  Aqui você verá informações, incluindo uma descrição, as etapas de correção e os recursos afetados.
    1. Selecione o **X** no canto superior direito da tela para fechar a página.
    1. Selecione **Visão geral** no painel de navegação à esquerda para voltar à página Visão geral do Microsoft Defender para Nuvem.
    1. Mantenha aberta a página de visão geral do Microsoft Defender para Nuvem, pois você a usará na próxima tarefa.

### Demonstração parte 2

Lembre-se de que o Microsoft Defender para Nuvem é oferecido em dois modos: sem recursos de segurança aprimorada (gratuitos) e com recursos de segurança aprimorada que estão disponíveis por meio dos planos do Microsoft Defender para Nuvem. Nesta tarefa, você descobrirá como habilitar/desabilitar os vários planos do Microsoft Defender para Nuvem.

1. Na página de visão geral do Microsoft Defender para Nuvem, selecione as **Configurações de ambiente** no painel de navegação esquerdo.
1. Selecione a caixa **Expandir tudo** e escolha a **Assinatura MOC – lodXXXXXXXX** listada ao lado do ícone de chave amarela.
1. Na página Planos do Defender, observe como você pode selecionar Habilitar todos ou selecionar planos individuais do Defender. 
    1. Verifique se o status do CSPM está definido como **Ativado**, caso contrário, defina-o agora.  
    1. Habilite o plano para servidores.  Selecione **Ativado** para o item de linha Servidores e escolha **Salvar** na parte superior da página.
1. Mantenha a guia Azure aberta em seu navegador para a próxima demonstração do Azure.

## Revisão

Nessa demonstração, você fez um passo a passo de alto nível do Microsoft Defender para Nuvem e mostrou como o Azure Secure Score pode ser utilizado para melhorar a postura de segurança de uma organização.
