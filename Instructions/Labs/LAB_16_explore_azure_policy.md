---
lab:
  title: Explorar o Azure Policy
  module: 'Module 4 Lesson 6: Describe the capabilities of Microsoft compliance solutions: Describe Azure Policy'
ms.openlocfilehash: f314612acb21c226e350ce9f6ab026cee2551378
ms.sourcegitcommit: b8b861a8c884a56f094213e47a59be48ba898ca1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "146741910"
---
# <a name="lab-explore-azure-policy"></a>Laboratório: Explorar o Azure Policy

## <a name="lab-scenario"></a>Cenário do laboratório

O Azure Policy ajuda a impor padrões organizacionais e a avaliar a conformidade em escala. O Azure Policy avalia os recursos no Azure comparando as propriedades desses recursos com as regras de negócio. Neste laboratório, vamos começar explorando a página de aterrissagem do Azure Policy. Após essa introdução à página do Azure Policy, vamos criar uma política e verificar o impacto dessa política.

**Tempo estimado**: 20 a 25 minutos

### <a name="task-1"></a>Tarefa 1:

Explorar brevemente a página do Azure Policy.

1. Abra o Microsoft Edge. Na barra de endereços, insira **portal.azure.com**.

1. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é sua ID de locatário exclusiva fornecida pelo provedor de hospedagem de laboratório) e selecione **Avançar**.

    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem de laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**.

1. Agora estamos no Portal do Azure.  Na caixa de pesquisa, na barra azul, na parte superior da página, ao lado de onde está escrito Microsoft Azure, insira **política** e selecione **Política** nos resultados da pesquisa. A página inicial Política será aberta, gerando a exibição do painel.  O escopo das informações que estamos verificando se aplica ao Azure Pass usado por você como parte deste laboratório.   Observe as informações disponíveis no painel.

1. Há um item chamado ASC Default (ASC refere-se ao Central de Segurança do Azure que agora é chamado de Microsoft Defender para Nuvem) cujo escopo é Azure Pass – Sponsorship.   Selecione **Padrão ASC**.

1. No topo da página, em Essentials, encontramos o nome, a descrição e outras informações essenciais.  Leia a descrição (posicione o cursor do mouse sobre a descrição). OBSERVAÇÃO: o campo de descrição faz Central de Segurança do Azure que foi renomeado para Microsoft Defender para Nuvem.

1. Observe que as informações apresentadas no painel são atualizadas de acordo com o item selecionado, o Padrão ASC. Esse padrão de ASC é a definição de iniciativa do Azure Security Benchmark.  Lembre-se de que a definição da inciativa é uma coleta de definições de políticas ajustada para obter um objetivo singular abrangente. As informações podem ser exibidas por grupo, políticas, recursos não compatíveis ou eventos.

1. Saia da página ASC e retorne à página inicial da política selecionando **X** no canto superior direito da janela.

1. Do lado esquerdo do painel de navegação, selecione **Introdução**.  Aqui encontramos diferentes opções, incluindo a opção para procurar políticas internas e atribuir políticas em escala. É possível criar definições de política personalizadas para o seu ambiente, atribuições de política recomendadas e muito mais.

1. À esquerda no painel de navegação, selecione **Conformidade**.  Assim como na página de visão geral, aqui é possível exibir o estado de conformidade das políticas e/ou iniciativas listadas.  Na página Conformidade da Política, também é possível atribuir uma política ou iniciativa (vamos atribuir uma política na próxima tarefa).

1. Do lado esquerdo do painel de navegação, selecione **Correção**.  Esta página apresenta uma lista de políticas que têm recursos não compatíveis.  Selecionando uma política na página de correção, é possível disparar a criação de uma tarefa para corrigir a política.  

1. Do lado esquerdo do painel de navegação, em criação, selecione **Atribuições**.  Aqui, encontramos atribuições atuais de políticas e/ou inciativas e é possível criar atribuições de políticas ou iniciativas.  Vamos voltar a esse tema na próxima tarefa.  

1. Do lado esquerdo do painel de navegação, selecione **Definições**.  Nesta página, selecione **Auditar máquinas com configurações de segurança de senha não seguras**.  Esta é uma definição de iniciativa que inclui diversas políticas.  Para conferir o aspecto de uma definição de política, selecione **Auditar máquinas do Windows cuja senha não tenha uma idade máxima de 70 dias**.  Quando a página abrir, vamos encontrar a real definição da política na estrutura Java Script Object Notation (JSON).   Como podemos ver no texto em vermelho, a definição da política contém elementos que definem o nome de exibição, a descrição, os parâmetros, as regras da política, entre outros. NÃO ALTERE NADA.  

1. Saia da página Definição da política selecionando o **X** no canto superior direito da página.

1. Saia da página Definição da iniciativa selecionando o **X** no canto superior direito da página.

1. Mantenha essa guia (Política – Microsoft Azure) aberta no navegador para a próxima tarefa.

### <a name="task-2"></a>Tarefa 2:

Nesta tarefa, vamos criar uma atribuição de política básica para exigir uma marca em grupos de recursos.

1. Abra a guia do navegador Política – Microsoft Azure.

1. Do lado esquerdo do painel de navegação, em Criação, selecione **Atribuições**.

1. Na parte superior da página, selecione **Atribuir política**.

1. O assistente de Atribuir política será aberto para guiar o administrador no processo de atribuição de política.  Próximo ao campo Definição de política, selecione as **reticências**.  Uma lista de definições de política disponíveis será exibida.  

1. Na barra de pesquisa, insira **Marca**.

1. A partir dos resultados da pesquisa, selecione **Exigir marca em grupo de recursos** (pode ser necessário rolar a página) e depois **Selecionar**.  Observação: o objetivo dessa política é Negar a criação de qualquer novo grupo de recursos que não atenda ao requisito.  

1. Observe o nome de atribuição padrão.  Mantenha o nome como está e selecione **Avançar** na parte inferior da página.

1. No campo Nome da marca, insira **Ambiente** e depois selecione **Avançar**.

1. Deixe as configurações de correção padrão como estão e selecione **Avançar**.

1. Na mensagem de não conformidade, insira **É necessária uma marca de ambiente** e depois selecione **Avançar**. Observação: essa mensagem aparece por conta da não conformidade dos grupos de recursos criados antes da atribuição da política, já que eles não têm uma marca de Ambiente.  Grupos de recursos criados depois da criação da política terão sua criação negada caso não tenham uma marca de ambiente.

1. Verifique a atribuição da política e selecione Criar.  Se você não encontrar a política de imediato, selecione **Atualizar**. Observação: Pode levar até 30 minutos para a política entrar em vigor.

1. Saia da página Atribuições de política selecionando o **X** no canto superior direito da tela.

1. Agora estamos na página inicial de serviços do Azure.  Deixe essa página aberta; vamos precisar para a próxima tarefa.

### <a name="task-3"></a>Tarefa 3

Nesta tarefa, vamos verificar o impacto da atribuição de política do Azure, criando um grupo de recursos no Azure sem marca. Depois, vamos atualizar o grupo de recursos para incluir uma marca.  Observação: Pode levar até 30 minutos para que a política criada na tarefa anterior entre em vigor, mas geralmente é mais rápido.

1. Abra a guia do navegador Página Inicial – Microsoft Azure.

1. No topo da página, abaixo de Serviços do Azure, selecione **Grupos de recursos**.

1. No canto superior esquerdo da página, selecione **+ Criar**.

1. Na guia Básico da página Criar um grupo de recursos, deixe o campo Assinatura como está, Azure Pass - Sponsorship.

1. No campo Grupo de recursos, insira **SC900-Labs**.

1. Deixe todas as configurações de Região como padrão e selecione **Avançar: Marcas**.

1. Deixe os campos do Nome e do Valor vazios.  NÃO PREENCHA, e selecione **Revisar + criar**.

1. Vai aparecer validação aprovada (o nome e o valor da marca não são campos exigidos no assistente), então selecione **Criar**.

1. Uma mensagem de falha será exibida no topo da tela, dizendo “Falha ao criar o grupo de recursos. Exibir detalhes de erro”.  Selecione **Exibir detalhes de erro**. A condição que integra a política do Azure não foi atendida, então a criação do grupo de recursos foi bloqueada por não conformidade.

    Observação: Caso você não veja uma mensagem de falha e o grupo de recursos seja criado, é porque a política ainda não entrou em vigor.  Vá para a página Política para a política criada na tarefa anterior. Quando a política entrar em vigor, o recurso vai aparecer como não compatível.  A página de detalhes inclui a mensagem de não conformidade. Caso você receba o erro, as etapas a seguir demonstram como corrigir a implantação.

1. O resumo do erro mostra o tipo de erro, “O recurso ‘SC900-Labs’ não foi permitido pela política.  Feche essa janela selecionando o **X** no canto superior esquerdo da tela.

1. Na janela Criar um grupo de recursos, selecione **Anterior**.

1. Estamos de volta à página Marcas para Criar um grupo de recursos.  No campo Nome, insira Ambiente e, no campo Valor, insira **SC900-Labs**. Depois, selecione **Avançar: Examinar + Criar >** .

1. Verifique a marca e selecione **Criar**.

1. O grupo de recursos aparecerá listado.  Como a marca foi gerada no grupo de recursos, a condição incluída como parte da política do Azure foi atendida.  O grupo de recursos é compatível com a política.

1. Antes de sair, remova a política do Azure.
    1. No canto superior esquerdo da página, selecione Página Inicial para voltar à página inicial do Azure.

    1. Abaixo de Serviços do Azure, selecione Política do Azure.
    1. No meio da página, encontramos uma lista das atribuições de políticas/iniciativas do Azure.  Selecione as reticências para a atribuição de política Exigir uma marca no grupo de recursos. Depois, selecione Excluir atribuição.
    1. Vai aparecer uma solicitação para confirmar se você deseja excluir a atribuição.  Selecione Sim.

1. Feche todas as guias abertas do navegador.

### <a name="review"></a>Revisão

Neste laboratório, exploramos a página de aterrissagem da política do Azure. Após essa introdução à página da política do Azure, acompanhamos o processo de criação de uma política e verificamos o impacto dessa política.
