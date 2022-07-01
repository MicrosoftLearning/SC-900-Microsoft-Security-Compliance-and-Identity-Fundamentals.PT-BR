---
Demo:
  title: Microsoft Defender para Nuvem
  module: 'Module 3 Lesson 2: Describe the capabilities of Microsoft security solutions: Describe security management capabilities of Azure'
ms.openlocfilehash: ff5145e967445c12dacd90ea50002fe0c3042efb
ms.sourcegitcommit: b8b861a8c884a56f094213e47a59be48ba898ca1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "146741898"
---
# <a name="demo-microsoft-defender-for-cloud"></a>Demonstração: Microsoft Defender para Nuvem

## <a name="demo-scenario"></a>Cenário da demonstração

Nesta demonstração, você verá o Microsoft Defender para Nuvem e mostrará como o Azure Secure Score pode ser usado para melhorar a postura de segurança de uma organização.  OBSERVAÇÃO: Esse passo a passo de demonstração pressupõe que o apresentador tenha permissões no nível de administrador para a assinatura do Azure por meio de um passe do Azure.  Uma assinatura do Azure, como uma Assinatura do Cloudslice, gerenciada pelo Hoster do Laboratório Autorizado, limita o acesso e a funcionalidade. Devido a isso, algumas etapas abaixo podem não estar disponíveis ou não mostrar nenhuma informação.

### <a name="demo-setup"></a>Configuração de demonstração

Nesta tarefa de instalação, você fará uma configuração básica do Microsoft Defender para Nuvem a fim de preparar a assinatura e habilitar e atribuir uma política padrão. Faça isso antes da demonstração para a classe. 

1. Abra a guia do navegador, **Página Inicial – Microsoft Azure**.  Se você fechou a guia anteriormente, abra uma página do navegador e, na barra de endereços, insira portal.azure.com e entre novamente.

1. Na caixa de pesquisa, na barra azul na parte superior da página ao lado de onde diz Microsoft Azure, insira **Microsoft Defender para Nuvem** e selecione **Microsoft Defender para Nuvem** nos resultados da pesquisa.

1. Se esta for a primeira vez que você entra no Microsoft Defender para Nuvem com sua assinatura, você pode acessar a página de introdução e pode ser solicitado a atualizar.  Role até a parte inferior da página e selecione **Pular**.  Você será direcionado à página Visão Geral.
    1. Na parte superior, você verá uma caixa de informações azul claro que indica: "Preparando sua assinatura. Isso pode levar alguns minutos...”.
    1. Quando a assinatura estiver pronta, será exibida uma nova caixa de informações que diz: "Uma assinatura não tem a política padrão atribuída. Para examinar a lista de assinaturas, abra a página Política de Segurança".  Selecione a seta para a direita no final da frase.
        1. Isso direcionará você para a página Configurações do ambiente. Selecione **Passe do Azure – Patrocínio**. 
        1. No painel de navegação esquerdo, clique em **Política de segurança**.
        1. Na página principal, em “Iniciativa padrão”, selecione **Atribuir política**.
        1. Na parte inferior da página, selecione **Examinar + criar**.
        1. Na parte inferior dessa página, clique em **Criar**.
        1. Na parte superior da página, abaixo de Microsoft Azure, selecione **Microsoft Defender para Nuvem** na trilha a fim de retornar à página de visão geral.

### <a name="demo-task"></a>Tarefa de demonstração

Nesta tarefa de demonstração, você fará um passo a passo de alto nível de alguns dos recursos do Microsoft Defender para Nuvem.

1. As informações na parte superior da página de visão geral do Microsoft Defender para Nuvem incluem o número de assinaturas do Azure, o número de recursos avaliados, o número de recomendações ativas e quaisquer alertas de segurança.  No corpo principal da página, há cartões que representam Secure Score, Conformidade regulatória, Insights e muito mais.  

1. Na parte superior da página, selecione **Recursos avaliados**.  (Observe que isso equivale a selecionar Inventário no painel de navegação esquerdo da página inicial da Central de Segurança).
    1. Essa ação leva você para a página **Inventário** que mostra sua assinatura do Azure Pass.  Selecione **Azure Pass – Sponsorship**.
    1. A página Resource Health fornece uma lista de recomendações.  Na lista disponível, selecione **Deve haver mais de um proprietário atribuído à sua assinatura**.
    1. Selecione a seta suspensa ao lado de Etapas de correção. Observe como as etapas de correção detalhadas são fornecidas junto com a opção de ação.  
    1. Selecione **Microsoft Defender para Nuvem** no canto superior esquerdo da tela para retornar à página de visão geral do Microsoft Defender para Nuvem.

1. Na parte superior da página, selecione **Recomendações ativas**.  (Observe que isso equivale a selecionar Recomendações no painel de navegação esquerdo da página inicial do Microsoft Defender para Nuvem).
    1. A página de recomendações mostra o painel do Secure Score.
    1. Abaixo do painel do Secure Score, há uma lista de controles. Cada controle de segurança representa um risco de segurança que deve ser mitigado e também inclui informações sobre a pontuação máxima associada a esse controle, a pontuação atual, o aumento potencial da pontuação e o status da integridade do recurso.  
    1. Selecione um dos controles, por exemplo **Habilitar MFA**.  Selecione um dos subitens, por exemplo **A MFA deve ser habilitada em contas com permissões de proprietário em sua assinatura**.  Na página que é aberta, você verá uma descrição, etapas de correção e recursos afetados. Feche a página selecionando o **X** no canto superior direito da tela.
    1. Feche a página de recomendações clicando no **X** no canto superior direito da tela para voltar à página de visão geral.

1. Você está de volta à página de visão geral do Microsoft Defender para Nuvem.  Na página principal, selecione **Conformidade regulatória**. (Observe que isso equivale a selecionar Recomendações no painel de navegação esquerdo da página inicial do Microsoft Defender para Nuvem).
    1. A página de conformidade regulatória fornece uma lista de controles de conformidade.  Em cada controle, está um conjunto de avaliações baseadas no parâmetro de comparação de segurança do Azure, que fornece recomendações sobre como você pode proteger suas soluções de nuvem no Azure.
    1. Selecione **IM. Gerenciamento de Identidades** e selecione **IM.6 Usar controles de autenticação forte**.  A lista mostra as ações de responsabilidade do cliente que podem ser tomadas para melhorar a postura de conformidade.
    1. Selecione o **X** no canto superior direito da tela para fechar a página e retornar à página de conformidade regulatória.
    1. Selecione o **X** no canto de superior direito da tela para voltar à página de visão geral.

1. Lembre-se de que o Microsoft Defender para Nuvem é oferecido em dois modos: sem recursos de segurança aprimorados (gratuitos) e com recursos de segurança aprimorados que estão disponíveis por meio dos planos do Microsoft Defender para Nuvem. Nesta tarefa, você descobre como habilitar/desabilitar os vários planos do Microsoft Defender para Nuvem.
    1. Na página de visão geral do Microsoft Defender para Nuvem, selecione as **Configurações de ambiente** no painel de navegação esquerdo.
    1. Selecione o sinal maior que **>** ao lado de onde está o Grupo Raiz do Locatário para expandi-lo (não selecione Grupo Raiz do Locatário diretamente, pois isso direcionará você para uma página diferente) e, em seguida, selecione **Azure Pass — Patrocínio**
    1. Na página Planos do Defender, observe como você pode selecionar Habilitar todos ou selecionar planos individuais do Defender. Deixe as configurações como estão com todos os planos definidos como desligados.
    1. Selecione o **X** no canto de superior direito da tela para voltar à página Configurações do ambiente.
    1. Selecione o **X** no canto de superior direito da tela para voltar à página de visão geral.

1. Retorne à página inicial do portal do Azure selecionando **Página Inicial** no canto superior esquerdo da página.  Mantenha esta guia do navegador disponível para voltar a ela em uma demonstração posterior.

## <a name="review"></a>Revisão

Nesta demonstração, você viu o Microsoft Defender para Nuvem e mostrou como o Azure Secure Score pode ser usado para melhorar a postura de segurança de uma organização.
