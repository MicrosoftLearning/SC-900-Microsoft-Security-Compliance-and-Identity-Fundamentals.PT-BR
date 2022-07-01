---
Demo:
  title: Configurações de usuário do Azure Active Directory
  module: 'Module 2 Lesson 1: Describe the capabilities of Microsoft Identity and access management solutions: Explore the services and identity types of Azure AD'
ms.openlocfilehash: 061dfa556f7e4e00d63c938b52097e0b641fed4f
ms.sourcegitcommit: b8b861a8c884a56f094213e47a59be48ba898ca1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "146741886"
---
# <a name="demo-azure-active-directory-user-settings"></a>Demonstração: Configurações de usuário do Azure Active Directory

## <a name="demo-scenario"></a>Cenário da demonstração

Nesta demonstração, você acessará o Azure Active Directory e passará pelas várias configurações de um usuário existente.  Nota ao apresentador:  Esta demonstração acessa o Azure AD por meio do locatário do Microsoft 365. Uma opção alternativa que pode ser mostrada aos alunos é o acesso ao Azure AD por meio do portal do Azure. A intenção de percorrer o portal do Microsoft 365 é mostrar que o Microsoft 365 inclui o acesso ao Azure AD.

1. Abra o Microsoft Edge.

1. Na barra de endereços, insira **admin.microsoft.com** para acessar o Centro de administração do Microsoft 365.

1. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é sua ID de locatário exclusiva fornecida pelo provedor de hospedagem de laboratório) e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem de laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**.

1. À esquerda no painel de navegação do Centro de administração do Microsoft 365, selecione **Mostrar todos**.

1. Em Centros de administração, selecione **Azure Active Directory** (talvez seja necessário rolar a tela).  Uma nova página do navegador abre a página Meu painel do Centro de administração do Azure Active Directory. Na janela principal do painel, você verá diversos blocos, incluindo o de identidade da organização (Contoso, o locatário e a edição do Azure AD), um bloco para usuários e grupos, entre outros.

1. No painel de navegação esquerdo, selecione **Usuários**. Observe que seu locatário já está configurado com usuários.

1. Na lista de usuários, selecione **Adele Vence**.

1. Observe que no painel de navegação esquerdo, **Perfil** está selecionado.  Mostre/fale sobre as informações exibidas na página de perfil.

1. No painel de navegação esquerdo, selecione **Funções atribuídas**.  Este usuário não possui funções administrativas atribuídas.  Na parte superior da página, selecione **+ Adicionar atribuições** para exibir os tipos de funções administrativas disponíveis.  Não adicione nada, apenas feche a página selecionando o **X** no canto superior direito da página.

1. No painel de navegação esquerdo, selecione **Grupos**.  Fale sobre o fato de que este usuário é membro de vários grupos.  Aqui, você pode falar sobre os tipos de grupos.  Para adicionar este usuário a outros grupos, você simplesmente selecionaria **+ Adicionar associações**.  Não adicione novos grupos, apenas fale sobre como é fácil adicionar um usuário a grupos existentes. Feche a janela de grupos selecionando o **X** no canto superior direito da página.

1. No painel de navegação esquerdo, selecione **Licenças**. Observe que este usuário recebeu licenças do Microsoft 365 E5 e licença do EMS.  Para adicionar uma licença, selecione **+ Atribuições** na parte superior da janela principal.  Mostre as licenças para este usuário. NÃO altere nada.  Feche esta janela selecionando o **X** no canto superior direito da página.

1. No painel de navegação esquerdo, selecione **Dispositivos**.  Nada aparece, mas você pode dizer que se este usuário tivesse dispositivos atribuídos, é aqui que apareceriam.

1. No painel de navegação esquerdo, selecione **Atribuições de função do Azure**.  Destacar que:
    1. Isso é diferente da guia de funções atribuídas mostrada anteriormente, pois a guia anterior é para controle de acesso baseado em função no Azure Active Directory (enfatize o Active Directory).
    1. Nesta guia, você pode exibir as atribuições de função atribuídas a usuários para recursos do Azure. Por exemplo, se você criasse um Grupo de Recursos do Azure e atribuísse a Adele uma função específica, como proprietário ou colaborador do grupo de recursos, você veria essa função listada aqui. Isso faz parte do Azure RBAC (controle de acesso baseado em função do Azure). Essa atribuição de função é gerenciada como parte desse recurso específico.

1. No painel de navegação esquerdo, selecione **Métodos de autenticação**.  Destaque a descrição que diz: 'Aqui, você pode definir os números de telefone e endereços de email que os usuários usam para realizar a autenticação multifator e redefinição de senha self-service de um usuário'. Se um usuário estiver configurado para SSPR ou precisar usar MFA e você, como administrador, preencher isso, esse usuário já estará registrado e não terá que passar pelas etapas de registro para SSPR ou MFA.  É comum que o usuário se registre em vez de o administrador ter de fazer isso.

1. No painel de navegação esquerdo, selecione **Entradas**.  Aqui, você pode ver a atividade de entrada deste usuário.  Talvez você não veja nada para este usuário, pois ele ainda não entrou.

1. Selecione o **X** no canto superior direito da página. Isso o leva de volta à lista de usuários.  Antes de fechar a lista de usuários, você pode realçar que a MFA é exibida na parte superior da página.  Selecione **Autenticação Multifator**.  Uma nova janela do navegador é aberta.  Aqui você pode selecionar MFA em massa para os usuários.  Essa é uma maneira de habilitar MFA para os usuários.  Na verdade, mostraremos mais sobre MFA no contexto do acesso condicional, que fornece um controle mais granular da MFA.  Feche a guia do navegador da autenticação multifator.

1. Selecione o **X** no canto superior direito da página. Isso o leva de volta à página principal do locatário da Contoso.

### <a name="review"></a>Revisão

Nesta demonstração, você mostrou as configurações de um usuário existente, incluindo grupos aos quais o usuário pode ser atribuído, a disponibilidade de funções e a atribuição de licenças de usuário.
