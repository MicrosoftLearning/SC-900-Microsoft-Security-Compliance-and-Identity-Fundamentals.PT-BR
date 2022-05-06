---
Demo:
  title: Redefinição de senha de autoatendimento do Azure Active Directory
  module: 'Module 2 Lesson 2: Describe the capabilities of Microsoft Identity and access management solutions: Describe the different authentication methods of Azure AD'
ms.openlocfilehash: 819439157f86ba4a28255cf876e239f3960df8f4
ms.sourcegitcommit: 25998048c2e354ea23d6f497205e8a062d34ac80
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "144557213"
---
# <a name="demo-azure-active-directory-self-service-password-reset-sspr"></a>Demonstração: Redefinição de senha self-service (SSPR) do Azure Active Directory

## <a name="demo-scenario"></a>Cenário da demonstração

Nesta demonstração, você verá as várias configurações associadas à habilitação da redefinição de senha self-service.

1. Vá para a guia Contoso – Microsoft Azure aberta no seu navegador. Se você fechou a guia anteriormente, abra uma página do navegador e, na barra de endereços, insira portal.azure.com e selecione Azure Active Directory. Você deve estar conectado como administrador no portal do Azure; caso contrário, entre novamente.

1. No painel de navegação esquerdo, selecione Redefinição de senha.

1. A guia de propriedades é realçada.  Na janela Propriedades, observe que o SSPR pode ser habilitado para Nenhum, Selecionar ou Todos.
    1. Coloque o cursor sobre o ícone de informações próximo a “Redefinição de senha self-service habilitada” e destaque que você pode escolher “Selecionado” para restringir a redefinição de senha a um grupo limitado de usuários, em vez de selecionar Nenhum ou Todos.
    1. Coloque o cursor sobre o ícone de informações próximo a “selecionar grupo” e destaque que é aqui que você identifica o grupo de usuários que têm permissão para redefinir as próprias senhas.   Você deve incluir usuários no grupo. Não é possível selecionar usuários individualmente.  Além disso, se você alterar o grupo, o grupo selecionado substituirá o grupo listado atualmente.  Portanto, é recomendável que você simplesmente adicione usuários ao grupo SSPR.
    1. Observe a caixa de informações em azul-claro e a destaque aos alunos. Essas configurações se aplicam apenas aos usuários finais em sua organização. Os administradores estão sempre habilitados para a redefinição de senha por autoatendimento e devem usar dois métodos de autenticação para redefinir a própria senha.

1. No painel de navegação esquerdo da Redefinição de senha, selecione Métodos de autenticação.
    1. Coloque o cursor sobre o ícone de informações ao lado de “Número de métodos necessários para redefinir”.  Destaque o fato de que isso define o número de métodos alternativos de identificação que um usuário nesse diretório deve ter para redefinir a senha.   Não altere a configuração.
    1. Destaque os diferentes “métodos disponíveis para os usuários”, incluindo o ponto de que o SSPR é compatível com perguntas de segurança. Selecione Perguntas de segurança para exibir as opções de uso de perguntas de segurança. Depois de falar sobre as opções, volte e selecione Perguntas de segurança para remover a marca de seleção.

1. No painel de navegação esquerdo da Redefinição de senha, selecione Registro.
    1. Passe o mouse sobre o ícone de informações ao lado de “Exigir que os usuários se registrem ao entrar”.   Destaque isso para os usuários.  
    1. Passe o mouse sobre o ícone de informações ao lado de “Número de dias antes que o usuário seja solicitado a reconfirmar as informações de autenticação”.   Destaque isso para os usuários.  

1. No painel de navegação esquerdo da Redefinição de senha, selecione Notificações.  Destaque as duas configurações. Passe o mouse sobre o ícone de informações para ver a descrição.

1. Observe como o painel de navegação de redefinição de senha também inclui opções para exibir logs de auditoria e Uso e insights.

1. Selecione o X no canto superior direito da página. Isso o leva de volta à página principal do locatário da Contoso.

1. Deixe esta página do navegador aberta para a próxima demonstração.

### <a name="review"></a>Revisão

Nesta demonstração, você mostrou as configurações associadas à redefinição de senha self-service.
