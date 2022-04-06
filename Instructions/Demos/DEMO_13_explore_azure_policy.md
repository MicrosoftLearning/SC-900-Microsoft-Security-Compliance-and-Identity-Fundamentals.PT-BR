---
Demo:
  title: Azure Policy
  module: 'Module 4 Lesson 5: Describe the capabilities of Microsoft compliance solutions: Describe Azure Policy'
ms.openlocfilehash: 898e2d2ae228baf6acbffd7301fcbdf4a6a2dba5
ms.sourcegitcommit: a341c2fc38e9b37dafb792d82e3c948f7ba4a099
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2022
ms.locfileid: "137893764"
---
# <a name="demo-azure-policy"></a>Demonstração: Azure Policy

### <a name="demo-scenario"></a>Cenário da demonstração
Nesta demonstração, você verá o processo de configuração de uma política do Azure e o impacto dela.

#### <a name="demo-part-1-create-a-policy-to-require-a-tag-on-a-resource-group-shows-steps-to-create-a-policy-from-a-template"></a>Demonstração – Parte 1: Criar uma política para exigir uma marcação em um grupo de recursos (mostra as etapas para criar uma política de um modelo)

1. Abra o Microsoft Edge. Na barra de endereços, insira **portal.microsoft.com**.  Você já deve estar conectado, caso contrário, entre com suas credenciais de administrador.

1. Na caixa de pesquisa, na barra azul, na parte superior da página, ao lado de onde está escrito Microsoft Azure, insira **política** e selecione **Política** nos resultados da pesquisa.

1. Agora você está na visão geral da página Política. Observe as informações disponíveis no painel.

1. Do lado esquerdo do painel de navegação, em Criação, selecione **Atribuições**.  Você notará que já existe uma atribuição de política. Selecione **ASC Padrão**.  Analise o campo de descrição. OBSERVAÇÃO: o campo de descrição faz Central de Segurança do Azure que foi renomeado para Microsoft Defender para Nuvem.  Retorne à página Atribuições de política selecionando o **X** no canto superior direito da página.

1. Na parte superior da página, selecione **Atribuir política**.

1. O assistente de Atribuir política será aberto para guiar o administrador no processo de atribuição de política.  Próximo ao campo Definição de política, selecione as **reticências**.  Uma lista de definições de política disponíveis será exibida.  

1. Na barra de pesquisa, insira **Marca**.

1. A partir dos resultados da pesquisa, selecione **Exigir marca em grupo de recursos** (pode ser necessário rolar a página) e depois **Selecionar**.  Observação: o objetivo dessa política é Negar a criação de qualquer novo grupo de recursos que não atenda ao requisito.  

1. Observe o nome de atribuição padrão.  Mantenha o nome como está e selecione **Avançar** na parte inferior da página.

1. No campo Nome da marcação, insira **Ambiente** (os grupos de recursos exigirão uma Marcação de ambiente) e selecione **Avançar**.  

1. Na guia Correção, leia a descrição, mas não altere as configurações. Selecione **Avançar**

1. Na mensagem de não conformidade, insira **É necessária uma marca de ambiente** e depois selecione **Avançar**. Observação: essa mensagem aparece por conta da não conformidade dos grupos de recursos criados antes da atribuição da política, já que eles não têm uma marca de Ambiente.  Grupos de recursos criados depois da criação da política terão sua criação negada caso não tenham uma marca de ambiente.

1. Verifique a atribuição da política e selecione Criar.  Se você não encontrar a política de imediato, selecione **Atualizar**. Observação: Pode levar até 30 minutos para a política entrar em vigor.

1. Saia da página Atribuições de política selecionando o **X** no canto superior direito da tela.

1. Agora estamos na página inicial de serviços do Azure.  Deixe essa página aberta; vamos precisar para a próxima tarefa.

#### <a name="demo-part-2--show-the-impact-of-the-policy-by-creating-a-resource-group-without-a-tag-then-fix-it-to-have-a-tag"></a>Demonstração — Parte 2:  Mostrar o impacto da política criando um grupo de recursos sem uma marcação e, a seguir, corrigir a política para ter uma marcação.

1. Na parte superior da página, em Serviços do Azure, selecione **Grupos de recursos**. Se você não vir a opção listada, insira Grupos de recursos na barra de pesquisa e o selecione de lá.

1. No canto superior esquerdo da página, selecione **+ Criar**.

1. Na guia Básico da página Criar um grupo de recursos, deixe o campo Assinatura como está, Azure Pass - Sponsorship.

1. No campo Grupo de recursos, insira **SC900-Labs**.

1. Deixe todas as configurações de Região como padrão e selecione **Avançar: Marcas**.

1. Deixe os campos do Nome e do Valor vazios.  NÃO PREENCHA, e selecione **Revisar + criar**.

1. Vai aparecer validação aprovada (o nome e o valor da marca não são campos exigidos no assistente), então selecione **Criar**.

1. Uma mensagem de falha será exibida no topo da tela, dizendo “Falha ao criar o grupo de recursos. Exibir detalhes de erro”.  Selecione **Exibir detalhes de erro**. A condição que integra a política do Azure não foi atendida, então a criação do grupo de recursos foi bloqueada por não conformidade. Observação: Caso você não veja uma mensagem de falha e o grupo de recursos seja criado, é porque a política ainda não entrou em vigor.  Vá para a página Política para a política criada na tarefa anterior. Quando a política entrar em vigor, o recurso vai aparecer como não compatível.  A página de detalhes inclui a mensagem de não conformidade.

1. O resumo do erro mostra o tipo de erro, “O recurso ‘SC900-Labs’ não foi permitido pela política.  Feche essa janela selecionando o **X** no canto superior esquerdo da tela.

1. Na janela Criar um grupo de recursos, selecione **<Anterior**.

1. Estamos de volta à página Marcas para Criar um grupo de recursos.  No campo Nome, insira Ambiente e, no campo Valor, insira **SC900-Labs**. Depois, selecione **Avançar: Examinar + Criar >** .

1. Verifique a marca e selecione **Criar**.

1. O grupo de recursos aparecerá listado.  Como a marca foi gerada no grupo de recursos, a condição incluída como parte da política do Azure foi atendida.  O grupo de recursos é compatível com a política.

#### <a name="review"></a>Revisão

Nesta demonstração, você mostrou o processo de configuração de uma política do Azure e o impacto dela.
