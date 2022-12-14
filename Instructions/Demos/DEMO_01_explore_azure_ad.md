<a name="---"></a><!---
---
Demonstração: Título: 'Explorar as Configurações do Usuário do Azure AD': 'Roteiro de aprendizagem: descrever as funcionalidades do Azure Active Directory (Azure AD), parte do Microsoft Entra; Módulo 1: descrever os serviços básicos e os tipos de identidade de Azure AD; Unidade 4: descrever os tipos de identidade Azure AD'
---
--->

# <a name="demo-azure-ad-user-settings"></a>Demonstração: configurações de usuário do Azure AD

Essa demonstração é mapeada para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades do Azure AD (Azure Active Directory), parte do Microsoft Entra
- Módulo: descrever os serviços básicos e os tipos de identidade do Azure AD
- Unidade: descrever os tipos de Identidade do Azure AD

## <a name="demo-scenario"></a>Cenário da demonstração

Nesta demonstração, você acessará o Azure Active Directory e acompanhará as várias configurações de um usuário existente.  Nota ao apresentador:  Esta demonstração acessa o Azure AD por meio do locatário do Microsoft 365. Uma opção alternativa que pode ser mostrada aos aprendizes é o acesso ao Azure AD por meio do portal do Azure. A intenção de percorrer o portal do Microsoft 365 é mostrar que o Microsoft 365 inclui o acesso ao Azure AD.

1. Abra o Microsoft Edge.

1. Na barra de endereços, insira **admin.microsoft.com** para acessar o Centro de administração do Microsoft 365.

1. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é a sua ID de locatário exclusiva fornecida pelo provedor de hospedagem do laboratório) e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**.

1. À esquerda no painel de navegação do Centro de administração do Microsoft 365, selecione **Mostrar todos**.

1. Em Centros de administração, selecione **Azure Active Directory** (talvez seja necessário rolar a tela).  Uma nova página do navegador abre a página Meu painel do Centro de administração do Azure Active Directory. Na janela principal do painel, você verá diversos blocos, incluindo o de identidade da organização (Contoso, o locatário e a edição do Azure AD), um bloco para usuários e grupos, entre outros.

1. No painel de navegação esquerdo, selecione **Usuários**. Observe que seu locatário já está configurado com usuários.

1. Na lista de usuários, selecione **Adele Vence**.

1. Observe que no painel de navegação esquerdo, **Perfil** está selecionado.  Mostre/fale sobre as informações exibidas na página de perfil.

1. No painel de navegação esquerdo, selecione **Funções atribuídas**.  Este usuário não tem nenhuma função administrativa atribuída.  Na parte superior da página, selecione **+ Adicionar atribuições** para exibir os tipos de funções administrativas disponíveis.  Não adicione nada, apenas feche a página selecionando o **X** no canto superior direito da página.

1. No painel de navegação esquerdo, selecione **Grupos**.  Fale sobre o fato de que este usuário é membro de vários grupos.  Aqui, você pode falar sobre os tipos de grupos.  Para adicionar este usuário a outros grupos, selecione **+ Adicionar associações**.  Não adicione novos grupos, apenas fale sobre como é fácil adicionar um usuário aos grupos existentes. Feche a janela de grupos selecionando o **X** no canto superior direito da página.

1. No painel de navegação esquerdo selecione **Licenças**. Observe que este usuário recebeu licenças do Microsoft 365 E5 e licença do EMS.  Para adicionar uma licença, selecione **+ Atribuições** na parte superior da janela principal.  Mostre as licenças para este usuário. NÃO altere nada.  Feche esta janela selecionando o **X** no canto superior direito da página.

1. No painel de navegação à esquerda, selecione **Dispositivos**.  Nada aparece, mas você pode dizer que se este usuário tivesse dispositivos atribuídos, é aqui que apareceriam.

1. No painel de navegação esquerdo, selecione **Atribuições de função do Azure**.  Destacar que:
    1. Isso é diferente da guia de funções atribuídas mostrada anteriormente, pois a guia anterior é para controle de acesso baseado em função no Azure Active Directory (enfatize o Active Directory).
    1. Nesta guia, você poderá ver as atribuições de função atribuídas aos usuários para recursos do Azure. Por exemplo, se você criasse um Grupo de Recursos do Azure e atribuísse a Adele uma função específica, como proprietário ou colaborador do grupo de recursos, você veria essa função listada aqui. Isso faz parte do Azure RBAC (controle de acesso baseado em função do Azure). Essa atribuição de função é gerenciada como parte desse recurso específico.

1. No painel de navegação esquerdo, selecione **Métodos de autenticação**.  Destaque a descrição que diz: 'Aqui, você pode definir os números de telefone e endereços de email que os usuários usam para realizar a autenticação multifator e redefinição de senha self-service de um usuário'. Se um usuário estiver configurado para a SSPR ou precisar usar a MFA e você, como administrador, preencher isso, esse usuário já estará registrado e não precisará passar pelas etapas de registro para a SSPR ou a MFA.  É comum que um usuário se registre em vez de um administrador precisar fazer isso.

1. No painel de navegação esquerdo, selecione **Entradas**.  Aqui, você pode ver a atividade de entrada deste usuário.  Talvez você não veja nada para este usuário, pois ele ainda não entrou.

1. Selecione o **X** no canto superior direito da página. Isso o leva de volta à lista de usuários.  Antes de fechar a lista de usuários, você pode realçar que a MFA é exibida na parte superior da página.  Selecione **Autenticação Multifator**.  Uma nova janela do navegador é aberta.  Aqui você pode selecionar MFA em massa para os usuários.  Essa é uma maneira de habilitar MFA para os usuários.  Mostraremos mais sobre a MFA no contexto do acesso condicional e como ele fornece um controle mais granular da MFA.  Feche a guia do navegador da autenticação multifator.

1. Selecione o **X** no canto superior direito da página. Isso o leva de volta à página principal do locatário da Contoso.

### <a name="review"></a>Revisão

Nesta demonstração, você mostrou as configurações de um usuário existente, incluindo os grupos aos quais o usuário pode ser atribuído, a disponibilidade de funções e a atribuição de licenças de usuário.
