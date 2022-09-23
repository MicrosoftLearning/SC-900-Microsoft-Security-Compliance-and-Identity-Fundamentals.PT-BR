---
ms.openlocfilehash: 8d3268c28c1dc2335f0554caf801abe11b6ae0d2
ms.sourcegitcommit: 15658ca1c7bae8a4dbaa33ab6f897070bde521b9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2022
ms.locfileid: "147892372"
---
<a name="---"></a><!---
---
Laboratório: Título: 'Explore o portal de conformidade e o Gerenciador de Conformidade do Microsoft Purview' Roteiro de Aprendizagem/Módulo/Unidade: 'Roteiro de aprendizagem: descrever as funcionalidades de conformidade da Microsoft; Módulo 2: descrever as funcionalidades do gerenciamento de conformidade no Microsoft Purview; Unidade 2: descrever o portal de conformidade do Microsoft Purview'
---
--->

# <a name="lab-explore-the-microsoft-purview-compliance-portal--compliance-manager"></a>Laboratório: Explorar o portal de conformidade e o Gerenciador de Conformidade do Microsoft Purview

Esse laboratório é mapeado para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades de conformidade da Microsoft
- Módulo: descrever as funcionalidades de gerenciamento de conformidade no Microsoft Purview
- Unidade: descrever o portal de conformidade do Microsoft Purview

## <a name="lab-scenario"></a>Cenário do laboratório

Neste laboratório, você vai explorar a página inicial do portal de conformidade do Microsoft Purview e como os recursos do Gerenciador de Conformidade podem ajudar as organizações a melhorar sua postura de conformidade.

**Tempo estimado**: 15 a 20 minutos

### <a name="task-1"></a>Tarefa 1:

Explorar a página inicial do portal de conformidade do Microsoft Purview e aprender a personalizar a exibição de cartão e o painel de navegação.

1. Abra o Microsoft Edge. Na barra de endereços, insira **admin.microsoft.com**.

1. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é sua ID de locatário exclusiva fornecida pelo provedor de hospedagem de laboratório) e selecione **Avançar**.

    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem de laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**. Vamos ser direcionados à página Centro de administração do Microsoft 365.

1. À esquerda no painel de navegação do Centro de administração do Microsoft 365, selecione **Mostrar todos**.

1. Em Centros de administração, selecione **Conformidade**.  A página inicial do portal de conformidade do Microsoft Purview é aberta em uma nova página do navegador.  
1. A seção de cartão na página inicial apresenta uma visão rápida de como a sua organização está lidando com a sua postura de conformidade, quais soluções estão disponíveis para a sua organização, entre outros.
1. Na janela principal, role a página para exibir diferentes cartões. Os cartões disponíveis na tela inicial e a posição dos cartões podem ser alterados de acordo com a preferência de cada administrador.  
1. Ao colocar o cursor do mouse sobre o título de qualquer cartão, a barra de título vai ficar cinza.  Quando perceber que o cursor assumiu uma forma de cruz, é possível mover o cartão para a localização desejada.
1. Na barra de título de qualquer cartão, também é encontramos reticências que apresentam ações possíveis.  Selecione as reticências no Catálogo de soluções e depois **Remover**.
1. É possível adicionar cartões selecionando **+ Adicionar cartões**.  A janela Adicionar cartões à sua página inicial será aberta.  Posicione o cursor do mouse sobre o Cartão do catálogo de soluções exibido nessa janela e arraste-o até a localização desejada na tela inicial.
1. No painel de navegação esquerdo da página inicial do portal de conformidade do Microsoft Purview, observe que, em Soluções, somente Catálogo é exibido.  Do lado esquerdo do painel de navegação, selecione **Mostrar todos**.  Observe como todas as soluções adicionais aparecem na seção de soluções.  
1. Selecione **Mostrar menos** para ocultar.
1. Como administrador de conformidade, pode haver um conjunto de soluções que você gerencia para nossa organização e, como tal, talvez você queira ter apenas as soluções listadas no painel de navegação que você vê. Para personalizar de acordo com a suas preferências, selecione **Personalizar navegação**.  
1. Na janela rotulada Personalizar o painel de navegação, observe como você pode selecionar os itens que deseja que apareçam no painel de navegação e desmarcar os itens que não deseja ver. Para fins desses laboratórios, mantenha todos os itens selecionados e selecione **Salvar** na parte inferior da janela.  
1. Deixe a guia do navegador aberta.

### <a name="task-2"></a>Tarefa 2:

Aprender sobre a postura de conformidade da sua organização através do Gerenciador de Conformidade.

1. À esquerda no painel de navegação do portal de conformidade do Microsoft Purview, selecione **Gerenciador de Conformidade**.  Também é possível selecionar o Gerenciador de Conformidade a partir da barra de título do cartão Gerenciador de Conformidade.

1. Na página Gerenciador de Conformidade, verifique se a **Visão Geral** está selecionada (sublinhada). Role a página para verificar todas as informações disponíveis na página.  As informações dessa página incluem sua pontuação de conformidade, seus pontos atingidos, e os pontos atingidos gerenciados pela Microsoft.   Você encontrará Ações chave de melhoria, Soluções que afetam a sua pontuação e o detalhamento da pontuação de conformidade por categorias ou avaliações.

1. Na parte superior da página Visão Geral, selecione **Ações de melhoria**.  Essas são ações que podem melhorar a pontuação de conformidade da organização. Observe que, à medida que as ações de melhoria são realizadas, os pontos podem levar até 24 horas para serem atualizados.  Observe os filtros disponíveis.

1. Na lista de ações de melhoria, selecione **Habilitar redefinição de senha self-service**.  Cada ação de melhoria tem uma seção de visão geral junto com uma página de detalhes, onde é possível selecionar implementação, teste, standards relacionados e requisitos regulatórios, e documentos.

1. Saia dessa ação de melhoria selecionando **Ações de melhoria** na trilha na parte superior esquerda da página.  Agora estamos de volta à na página de ações de melhoria.

1. Na parte superior da página, selecione **Soluções**. Nesta página, verificamos como as soluções podem contribuir para a nossa pontuação e as demais oportunidades de melhoria.

1. Na parte superior da página, selecione **Avaliações**. Nesta página, encontramos a Linha de Base de Proteção de Dados.  Esta é uma avaliação padrão oferecida pela Microsoft no Gerenciador de Conformidade para a linha de base de proteção de dados do Microsoft 365.  Essa avaliação da linha de base tem um conjunto de controles para regulamentos e standards para proteção de dados e governança geral de dados. O Gerenciador de Conformidade se torna mais útil conforme você compila e gerencia suas próprias avaliações para atender às necessidades específicas da sua organização.

1. Selecione **Linha de Base de Proteção de Dados**.  Observe as informações disponíveis na guia de progresso.  Você também pode exibir informações em Controles, suas ações de melhoria e as ações da Microsoft.  

1. Na parte superior esquerda da página, acima de Avaliações (navegação estrutural), selecione **Avaliação** para voltar à página de avaliações.  

1. Na parte superior da página, selecione **Modelos de avaliação**.  Esta página lista os modelos disponíveis. É possível criar avaliações para a sua organização usando um modelo existente ou criando um novo modelo.

1. A partir da lista de modelos, selecione **ISO/IEC27001:2013**. Na parte superior direita da página, selecione **+ Criar avaliação**.  Observe que, do lado direita da tela, há apenas duas etapas para criar uma avaliação a partir do modelo.  Selecione Cancelar na parte inferior da página.

1. Feche todas as guias abertas do navegador.

### <a name="review"></a>Revisão

Neste laboratório, você explorou a página inicial do portal de conformidade do Microsoft Purview e como os recursos do Gerenciador de Conformidade podem ajudar as organizações a melhorar sua postura de conformidade.
