<a name="---"></a><!---
---
Laboratório: Título: 'Explorar o Azure Policy' Roteiro de aprendizagem/Módulo/Unidade: 'Roteiro de aprendizagem: descrever as funcionalidades de conformidade da Microsoft; Módulo 6: descrever as funcionalidades da governança de recursos no Azure; Unidade 2: descrever o Azure Policy'
---
--->

# <a name="lab-explore-azure-policy"></a>Laboratório: Explorar o Azure Policy

Esse laboratório é mapeado para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades de conformidade da Microsoft
- Módulo: descrever as funcionalidades de governança de recursos no Azure
- Unidade: descrever o Azure Policy

## <a name="lab-scenario"></a>Cenário do laboratório

O Azure Policy ajuda a impor padrões organizacionais e a avaliar a conformidade em escala. O Azure Policy avalia os recursos no Azure comparando as propriedades desses recursos com as regras de negócio. Neste laboratório, você criará uma política e verá o impacto dela.  Você também vai explorar por informações de conformidade e correção disponíveis na página da política.

**Tempo estimado**: 15 a 20 minutos

### <a name="task-1"></a>Tarefa 1:

Nesta tarefa, você vai criar uma atribuição de política básica para exigir uma marca em um grupo de recurso.
1.  Abra o Microsoft Edge. Na barra de endereços, insira **portal.azure.com**.

1. Entre com as credenciais de administrador da sua assinatura do Azure (essas credenciais de administrador são diferentes das credenciais de administrador do Microsoft 365).
    1. Na janela Entrar, insira **User1-XXXXXXXX@LODSPRODMSLEARNMCA.onmicrosoft.com** (em que XXXXXXXX é a sua ID de locatário exclusiva fornecida pelo provedor de hospedagem do laboratório) e selecione **Avançar**.

    1. Insira a senha de administrador fornecida pelo provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Se for exibida uma mensagem perguntando se você deseja permanecer conectado, selecione **Sim**.

1. Agora você está no portal do Azure.  Na caixa de pesquisa, na barra azul, na parte superior da página, ao lado de onde está escrito Microsoft Azure, insira **política** e selecione **Política** nos resultados da pesquisa. Isso abrirá a home page da Política, que fornece uma exibição do painel.  O escopo da exibição Painel é a assinatura do Azure fornecida pelo ALH (hoster do laboratório autorizado). Você verá uma política listada. Essa é uma política criada pelo ALH para uso da assinatura do Azure.

1. Do lado esquerdo do painel de navegação, em Criação, selecione **Atribuições**.

1. Na parte superior da página, selecione **Atribuir política**. O assistente para Atribuir política será aberto para orientar o administrador no processo de atribuição de uma política.

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

### <a name="task-2"></a>Tarefa 2:

Nesta tarefa, você verá o impacto da atribuição de política do Azure com a tentativa de criar um grupo de recursos no Azure sem marca.

1. Abra a guia do navegador Página Inicial – Microsoft Azure.

1. No topo da página, abaixo de Serviços do Azure, selecione **Grupos de recursos**.

1. No canto superior esquerdo da página, selecione **+ Criar**.

1. Na guia Informações Básicas da página Criar um grupo de recursos, mantenha o campo Assinatura como está.

1. No campo Grupo de recursos, insira **SC900-Labs**.

1. Deixe todas as configurações de Região como padrão e selecione **Avançar: Marcas**.

1. Deixe os campos do Nome e do Valor vazios.  NÃO PREENCHA, e selecione **Revisar + criar**.

1. Você verá uma mensagem indicando a aprovação na validação (o nome e o valor da marca não são campos obrigatórios no assistente). Selecione **Criar**.

1. Você verá a mensagem "Falha ao criar o grupo de recursos" na parte superior da tela. Selecione **Exibir detalhes de erro**. A condição que faz parte da política do Azure não foi atendida, ou seja, a criação do grupo de recursos foi bloqueada por não conformidade. Observação: Caso você não veja uma mensagem de falha e o grupo de recursos seja criado, é porque a política ainda não entrou em vigor.  Acesse a página Política da política criada na tarefa anterior. Quando a política entrar em vigor, você verá que o recurso está fora de conformidade.  A página de detalhes inclui a mensagem de não conformidade.

1. O resumo do erro mostra o tipo de erro, “O recurso ‘SC900-Labs’ não foi permitido pela política.  Feche essa janela selecionando o **X** no canto superior esquerdo da tela.

1. Na janela Criar um grupo de recursos, selecione **Anterior**.

1. Você está novamente na página Marcas para Criar um grupo de recursos.  No campo Nome, insira Ambiente e, no campo Valor, insira **SC900-Labs**. Depois, selecione **Avançar: Examinar + Criar >** .

1. Verifique a marca e selecione **Criar**.

1. No campo Nome, insira **Ambiente** e, no campo Valor, insira **Laboratórios** (esse valor pode ser qualquer coisa, a política apenas exige um valor de marca) e selecione **Avançar: Revisar + Criar >** e **Criar**.

1. Você verá o grupo de recursos listado.  

1. Selecione **Página Inicial** na parte superior da navegação estrutural para voltar à home page do Azure.

1. Mantenha a guia do navegador aberta, pois você precisará dela para a próxima tarefa.

### <a name="task-3-optional"></a>Tarefa 3 (opcional)

Nesta tarefa, você percorrerá as etapas usadas para corrigir um grupo de recursos fora de conformidade. OBSERVAÇÃO: a assinatura do Azure usada para o laboratório enfrentará um atraso maior do que o normal para atualizar o status de conformidade de um grupo de recursos corrigido.

1. Na home page do Azure, selecione **política**. Isso abrirá a home page da Política, que fornece uma exibição do painel.  O escopo da exibição Painel é a assinatura do Azure fornecida pelo hoster do laboratório autorizado.  

1. Você verá a política criada anteriormente. Selecione-a.

1. No topo da página, em Essentials, encontramos o nome, a descrição e outras informações essenciais.  Observe que a política é exibida como fora de conformidade.  Selecione a política para obter mais informações sobre o motivo de a política não estar em conformidade. Aqui você pode ver que um recurso listado como resourgegroup1 está fora de conformidade.  Este é um exemplo de um grupo de recursos que foi criado, anterior à criação da política. Selecione **Detalhes** para obter mais informações.  Aqui você pode ver a mensagem de conformidade indicando que uma marca de ambiente é obrigatória.  Selecione o **X** no canto superior direito para fechar a janela.

1. Selecione **resourcegroup1** e, na parte superior da página, **Exibir Recurso**.
    1. Ao lado de Marcas, selecione **editar**
    1. Posicione o cursor do mouse no campo Marca e selecione **Ambiente**.
    1. Posicione o cursor do mouse no campo Valor, selecione **Laboratórios** e escolha **Salvar**.

1. Agora, volte à página da política.  Posicione e o cursor do mouse na caixa de pesquisa azul na parte superior da página e selecione **Política**.

1. À esquerda no painel de navegação, selecione **Conformidade**.  Assim como na página de visão geral, aqui é possível exibir o estado de conformidade das políticas e/ou iniciativas listadas.  OBSERVAÇÃO: embora você tenha adicionado a marca ao grupo de recursos, levará tempo para que o status seja atualizado.  As assinaturas do Azure usadas para fins de laboratório podem enfrentar atrasos mais longos do que o normal. Se você quiser aguardar o status de conformidade para que esse recurso seja atualizado, não encerre o laboratório. Dependendo do ambiente de laboratório, a atualização pode levar uma hora ou mais.  

### <a name="review"></a>Revisão

Neste laboratório, você passou pelo processo de criação de uma atribuição de política do Azure e pôde ver o impacto dessa política.
