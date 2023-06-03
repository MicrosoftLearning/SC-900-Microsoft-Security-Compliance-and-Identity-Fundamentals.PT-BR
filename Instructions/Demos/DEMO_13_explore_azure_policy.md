<a name="---"></a><!---
---
Demonstração: Título: 'Azure Policy' Roteiro de aprendizagem/Módulo/Unidade: 'Roteiro de aprendizagem: descrever as funcionalidades de conformidade da Microsoft; Módulo 6: descrever as funcionalidades da governança de recursos no Azure; Unidade 2: descrever o Azure Policy'
---
--->

# <a name="demo-azure-policy"></a>Demonstração: Azure Policy

Essa demonstração é mapeada para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades de conformidade da Microsoft
- Módulo: descrever as funcionalidades de governança de recursos no Azure
- Unidade: descrever o Azure Policy

## <a name="demo-scenario"></a>Cenário da demonstração

Nesta demonstração, você verá o processo de configuração de uma política do Azure e o impacto dela.

### <a name="demo-part-1"></a>Demonstração parte 1

Criar uma política para exigir uma marcação em um grupo de recursos (mostra as etapas para criar uma política de um modelo)

1. Abra o Microsoft Edge. Na barra de endereços, insira **portal.azure.com**.  Você já deverá estar conectado, caso contrário, entre com suas credenciais de administrador.

1. Na caixa de pesquisa, na barra azul, na parte superior da página, ao lado de onde está escrito Microsoft Azure, insira **política** e selecione **Política** nos resultados da pesquisa.

1. Agora você está na visão geral da página Política. Observe as informações disponíveis no painel.

1. No painel de navegação à esquerda, em Criação, selecione **Atribuições**.  Você observará que uma atribuição de política já existe. Selecione **Padrão ASC**.  Analise o campo de descrição. OBSERVAÇÃO: o campo de descrição referencia a Central de Segurança do Azure, que foi renomeada como Microsoft Defender para Nuvem.  Retorne à página Atribuições de política selecionando o **X** no canto superior direito da página.

1. Na parte superior da página, selecione **Atribuir política**. O assistente de Atribuir política será aberto para guiar o administrador no processo de atribuição de política.

1. Comece na guia Informações Básicas.
    1. Para o Escopo, mantenha a configuração padrão. Nesse caso, o escopo da política é a assinatura do Azure fornecida pelo ALH (hoster do laboratório autorizado).
    1. Em Definição de Política, selecione as **reticências**.  Uma lista de definições de política disponíveis será exibida.  Na barra de pesquisa, insira **Exigir uma marca**. A partir dos resultados da pesquisa, selecione **Exigir marca em grupo de recursos** (pode ser necessário rolar a página) e depois **Selecionar**.  Observação: o objetivo dessa política é Negar a criação de qualquer novo grupo de recursos que não atenda ao requisito.  
    1. Observe o nome de atribuição padrão.  Mantenha o nome como está.
    1. Verifique se a opção Imposição de política está definida como **Habilitada** e selecione **Avançar**.

1. Agora você está na guia Parâmetros. No campo Nome da marca, insira **Ambiente** e selecione **Avançar**.

1. Na guia Correção, mantenha as configurações padrão como estão e selecione **Avançar**.

1. Agora você está na guia Mensagens de não conformidade. No campo da mensagem de não conformidade, insira **Uma marca de ambiente é obrigatória** e selecione **Avançar**. Observação: essa mensagem aparece por conta da não conformidade dos grupos de recursos criados antes da atribuição da política, já que eles não têm uma marca de Ambiente.  

1. Revise a atribuição de política e selecione **Criar**.  Se você não encontrar a política de imediato, selecione **Atualizar**. Observação: pode levar até 30 minutos para que a política entre em vigor, mas geralmente isso é muito mais rápido.

1. Saia da página Atribuições de política selecionando o **X** no canto superior direito da tela.

1. Agora você está na home page dos serviços do Azure.  Mantenha essa página aberta, pois você precisará dela para a próxima tarefa.

### <a name="demo-part-2"></a>Demonstração parte 2

Nesta tarefa, você verá o impacto da atribuição de política do Azure com a tentativa de criar um grupo de recursos no Azure sem marca.

1. Abra a guia do navegador Página Inicial – Microsoft Azure.

1. No topo da página, abaixo de Serviços do Azure, selecione **Grupos de recursos**.

1. No canto superior esquerdo da página, selecione **+ Criar**.

1. Na guia Informações Básicas da página Criar um grupo de recursos, mantenha o campo Assinatura como está.

1. No campo Grupo de recursos, insira **SC900-Labs**.

1. Deixe todas as configurações de Região como padrão e selecione **Avançar: Marcas**.

1. Deixe os campos do Nome e do Valor vazios.  NÃO PREENCHA, e selecione **Revisar + criar**.

1. Você verá uma mensagem indicando a aprovação na validação (o nome e o valor da marca não são campos obrigatórios no assistente). Selecione **Criar**.

1. Você verá a mensagem "Falha ao criar o grupo de recursos" na parte superior da tela. Selecione **Exibir detalhes do erro**. A condição que faz parte da política do Azure não foi atendida, ou seja, a criação do grupo de recursos foi bloqueada por não conformidade. Observação: Caso você não veja uma mensagem de falha e o grupo de recursos seja criado, é porque a política ainda não entrou em vigor.  Acesse a página Política da política criada na tarefa anterior. Quando a política entrar em vigor, você verá que o recurso está fora de conformidade.  A página de detalhes inclui a mensagem de não conformidade.

1. O resumo do erro mostra o tipo de erro, “O recurso ‘SC900-Labs’ não foi permitido pela política.  Feche essa janela selecionando o **X** no canto superior esquerdo da tela.

1. Na janela Criar um grupo de recursos, selecione **Anterior**.

1. Você está novamente na página Marcas para Criar um grupo de recursos.  No campo Nome, insira Ambiente e, no campo Valor, insira **SC900-Labs**. Depois, selecione **Avançar: Examinar + Criar >** .

1. Verifique a marca e selecione **Criar**.

1. No campo Nome, insira **Ambiente** e, no campo Valor, insira **Laboratórios** (esse valor pode ser qualquer coisa, a política apenas exige um valor de marca) e selecione **Avançar: Revisar + Criar >** e **Criar**.

1. Você verá o grupo de recursos listado.  

1. Indique aos aprendizes que, se um grupo de recursos tiver sido criado antes da política, esse grupo de recursos agora será exibido como fora de conformidade com essa atribuição de política e precisará ser corrigido com a aplicação da marca Ambiente.  Há um grupo de recursos pré-existente rotulado ResourceGroup1 que não está em conformidade e pode ser corrigido, mas o tempo para o status ser atualizado, após a correção, é maior do que o normal para o ambiente de laboratório.

### <a name="review"></a>Revisão

Nesta demonstração, você mostrou o processo de configuração de uma política do Azure e o impacto dela.
