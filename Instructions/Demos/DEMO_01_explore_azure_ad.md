---
Demo:
  title: Configurações de usuário do Azure Active Directory
  module: 'Module 2 Lesson 1: Describe the capabilities of Microsoft Identity and access management solutions: Explore the services and identity types of Azure AD'
ms.openlocfilehash: eb1ffc50ce90922dced58726c39879edfc74fb5b
ms.sourcegitcommit: 25998048c2e354ea23d6f497205e8a062d34ac80
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "144557176"
---
# <a name="demo-azure-active-directory-user-settings"></a>Demonstração: Configurações de usuário do Azure Active Directory

## <a name="demo-scenario"></a>Cenário da demonstração

Nesta demonstração, você acessará o Azure Active Directory e passará pelas várias configurações de um usuário existente.

1. Vá para a guia **Página Inicial – Microsoft Azure** aberta no seu navegador.  Se você fechou a guia anteriormente, abra o Microsoft Edge e, na barra de endereços, insira portal.azure.com e entre com as mesmas credenciais de administrador do seu locatário do Microsoft 365.

1. A página de aterrissagem do portal do Azure exibe os serviços do Azure. Selecione **Azure Active Directory**. Se não estiver imediatamente visível, na caixa de pesquisa ao lado de onde diz Microsoft Azure, insira Azure Active Directory.  Você também pode querer mostrar como acessar por meio do ícone Mostrar menu do portal (as três linhas horizontais também conhecidas como ícone de hambúrguer, na barra azul, na parte superior da página) à esquerda de onde está escrito Microsoft Azure.

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
