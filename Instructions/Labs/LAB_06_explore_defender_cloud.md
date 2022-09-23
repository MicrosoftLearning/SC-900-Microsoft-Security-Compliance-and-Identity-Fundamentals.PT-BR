---
ms.openlocfilehash: eeee584ece9bb3ec4edcba5fa2e76a13dd9459c4
ms.sourcegitcommit: 15658ca1c7bae8a4dbaa33ab6f897070bde521b9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2022
ms.locfileid: "147892600"
---
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

Neste laboratório, vamos explorar o Microsoft Defender para Nuvem e aprender como a Classificação de Segurança do Azure pode ser usada para melhorar a postura de segurança da sua organização.  OBSERVAÇÃO: Esse passo a passo de demonstração pressupõe que o apresentador tenha permissões no nível de administrador para a assinatura do Azure por meio de um passe do Azure.  Uma assinatura do Azure, como uma Assinatura do Cloudslice, gerenciada pelo Hoster do Laboratório Autorizado, limita o acesso e a funcionalidade. Devido a isso, algumas etapas abaixo podem não estar disponíveis ou não mostrar nenhuma informação.

**Tempo estimado**: 30 minutos

### <a name="setup"></a>Instalação

Nesta tarefa, você fará uma configuração básica do Microsoft Defender para Nuvem a fim de preparar a assinatura e habilitar e atribuir uma política padrão.

1. Abra o Microsoft Edge. Na barra de endereços, insira **portal.azure.com**.

1. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é sua ID de locatário exclusiva fornecida pelo provedor de hospedagem de laboratório) e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem de laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**.

1. No canto superior esquerdo da tela, ao lado de onde diz Microsoft Azure, selecione o ícone de menu Mostrar portal (as três linhas horizontais também conhecidas como ícone de hambúrguer) e, no painel de navegação esquerdo, em Favoritos, selecione **Microsoft Defender para Nuvem**.  Se ele não estiver listado em favoritos, na caixa de pesquisa, insira **Microsoft Defender para Nuvem** e, na lista de resultados, selecione **Microsoft Defender para Nuvem**.

1. Se esta for a primeira vez que você entra no Microsoft Defender para Nuvem com sua assinatura, você pode acessar a página de introdução e pode ser solicitado a atualizar.  Role até a parte inferior da página e selecione **Pular**.  Você será direcionado à página Visão Geral.
    1. Na parte superior, você verá uma caixa de informações azul claro que indica: "Preparando sua assinatura. Isso pode levar alguns minutos...”.
    1. Quando a assinatura estiver pronta, será exibida uma nova caixa de informações que diz: "Uma assinatura não tem a política padrão atribuída. Para examinar a lista de assinaturas, abra a página Política de Segurança".  Selecione a seta para a direita no final da frase ou clique em **Configurações do ambiente** no painel de navegação esquerdo.
        1. Isso direcionará você para a página Configurações do ambiente. Selecione **Passe do Azure – Patrocínio**.  Observação:  Se o ambiente do Azure for baseado em uma assinatura do Azure gerenciada pelo Hoster do Laboratório Autorizado, em vez de um Azure Pass, você a verá referenciada. Expanda a opção selecionando o sinal maior que até que não seja mais possível expandir as opções e você veja a assinatura.
        1. No painel de navegação esquerdo, clique em **Política de segurança**.
        1. Na página principal, em “Iniciativa padrão”, selecione **Atribuir política**.
        1. Na parte inferior da página, selecione **Examinar + criar**.
        1. Na parte inferior dessa página, clique em **Criar**.  Isso atribui o Azure Security Benchmark como uma iniciativa de política padrão.  Atualize a tela (pode levar alguns minutos).
        1. Clique no **X** da página de configurações do ambiente para sair dela.  
        1. Na página de serviços do Azure, selecione **Microsoft Defender para Nuvem** a fim de retornar à página de visão geral.

### <a name="task-1"></a>Tarefa 1:

Nesta tarefa, você fará um passo a passo de alto nível de alguns dos recursos do Microsoft Defender para Nuvem.

1. Observe as informações disponíveis na página Visão Geral do Microsoft Defender para Nuvem.  As informações na parte superior da página incluem o número de assinaturas do Azure, o número de Recursos avaliados, o número de recomendações ativas e outros alertas de segurança.  No corpo principal da página, há cartões que representam Secure Score, Conformidade regulatória, Insights e muito mais.

1. Na parte superior da página, selecione **Recursos avaliados**.  (Observe que isso equivale a selecionar Inventário no painel de navegação esquerdo da página inicial da Central de Segurança).
    1. Essa ação leva você para a página **Inventário** que mostra sua assinatura do Azure Pass.  Selecione **Azure Pass – Sponsorship**.
    1. A página Resource Health fornece uma lista de recomendações.  Na lista disponível, selecione **Deve haver mais de um proprietário atribuído à sua assinatura**.
    1. Selecione a seta suspensa ao lado de Etapas de correção. Observe como as etapas de correção detalhadas são fornecidas junto com a opção de ação.  
    1. Selecione **Microsoft Defender para Nuvem** no canto superior esquerdo da tela para retornar à página de visão geral do Microsoft Defender para Nuvem.

1. Na parte superior da página, selecione **Recomendações ativas**.  (Observe que isso equivale a selecionar Recomendações no painel de navegação esquerdo da página inicial do Microsoft Defender para Nuvem).
    1. A página de recomendações mostra o painel do Secure Score.
    1. Abaixo do painel do Secure Score, há uma lista de controles. Cada controle de segurança representa um risco de segurança que deve ser mitigado e também inclui informações sobre a pontuação máxima associada a esse controle, a pontuação atual, o aumento potencial da pontuação e o status da integridade do recurso.  
    1. Selecione um dos controles, como **Implementar práticas recomendadas de segurança**.  Selecione um dos subitens, como **Deve haver mais de um proprietário atribuído à assinatura**.  Na página que é aberta, você verá uma descrição, etapas de correção e recursos afetados. Feche a página selecionando o **X** no canto superior direito da tela.
    1. Feche a página de recomendações clicando no **X** no canto superior direito da tela para voltar à página de visão geral.

1. Na página principal, selecione **Conformidade regulatória**. A página de conformidade regulatória fornece uma lista de controles de conformidade.  Em cada controle, está um conjunto de avaliações baseadas no parâmetro de comparação de segurança do Azure, que fornece recomendações sobre como você pode proteger suas soluções de nuvem no Azure.
    1. Selecione **IM. Gerenciamento de Identidades** e selecione **IM.6 Usar controles de autenticação forte**.  A lista mostra as ações de responsabilidade do cliente que podem ser tomadas para melhorar a postura de conformidade.
    1. Selecione o **X** no canto superior direito da tela para voltar à página Visão Geral do Microsoft Defender para Nuvem.
    1. Mantenha aberta a página de visão geral do Microsoft Defender para Nuvem, você usará na próxima tarefa.

### <a name="task-2"></a>Tarefa 2:

Lembre-se de que o Microsoft Defender para Nuvem é oferecido em dois modos: sem recursos de segurança aprimorados (gratuitos) e com recursos de segurança aprimorados que estão disponíveis por meio dos planos do Microsoft Defender para Nuvem. Nesta tarefa, você descobre como habilitar/desabilitar os vários planos do Microsoft Defender para Nuvem.

1. Na página de visão geral do Microsoft Defender para Nuvem, selecione as **Configurações de ambiente** no painel de navegação esquerdo.
1. Selecione o sinal maior que **>** ao lado de onde está o Grupo Raiz do Locatário para expandi-lo (não selecione Grupo Raiz do Locatário diretamente, pois isso direcionará você para uma página diferente) e, em seguida, selecione **Azure Pass — Patrocínio**
1. Na página Planos do Defender, observe como você pode selecionar Habilitar todos ou selecionar planos individuais do Defender. Deixe as configurações como estão com todos os planos definidos como desligados.
1. Feche todas as guias abertas do navegador.

### <a name="review"></a>Revisão

Neste laboratório, você explorou o Microsoft Defender para Nuvem e aprendeu como a Classificação de Segurança do Azure pode ser usada para melhorar a postura de segurança da sua organização.
