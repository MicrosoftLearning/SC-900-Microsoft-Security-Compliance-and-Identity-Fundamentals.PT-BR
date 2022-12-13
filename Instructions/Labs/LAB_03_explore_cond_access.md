<a name="---"></a><!---
---
Laboratório: Roteiro de aprendizagem: 'Descrever as funcionalidades do Azure AD (Active Directory), parte do Microsoft Entra' Módulo: 'Descrever as funcionalidades de gerenciamento de acesso do Azure AD' Unidade: 'Descrever o acesso condicional no Azure AD'
---
--->

# <a name="lab-explore-access-management-in-azure-ad-with-conditional-access"></a>Laboratório: Explorar o gerenciamento de acesso no Azure AD com o acesso condicional

Esse laboratório é mapeado para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades do Azure AD (Azure Active Directory), parte do Microsoft Entra
- Módulo: descrever as funcionalidades de gerenciamento de acesso do Azure AD
- Unidade: descrever o acesso condicional no Azure AD

## <a name="lab-scenario"></a>Cenário do laboratório

Neste laboratório, você vai explorar a MFA de acesso condicional, da perspectiva de um administrador e de um usuário.  Como administrador, você criará uma política que exigirá que um usuário passe pela autenticação multifator ao acessar um aplicativo de gerenciamento do Microsoft Azure baseado em nuvem.  Da perspectiva de um usuário, você verá o impacto da política de acesso condicional, incluindo o processo de registro para a MFA.

**Tempo estimado**: 30 minutos

### <a name="task-1"></a>Tarefa 1:

Nesta tarefa você, como administrador, irá redefinir a senha do usuário Debra Berger.  Esta etapa é necessária para que você possa inicialmente fazer logon como usuário nas tarefas seguintes.

1. Abra o Microsoft Edge.  Na barra de endereços, insira **portal.azure.com**.

2. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é a sua ID de locatário exclusiva fornecida pelo provedor de hospedagem do laboratório) e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**.

3. No canto superior esquerdo da tela, ao lado de onde diz Microsoft Azure, selecione o ícone de menu Mostrar portal (as três linhas horizontais também conhecidas como ícone de hambúrguer) e, no painel de navegação esquerdo, em Favoritos, selecione Azure Active Directory. Se ele não estiver listado em favoritos, na caixa de pesquisa, insira Azure Active Directory e, na lista de resultados, selecione **Azure Active Directory**.

4. No painel de navegação esquerdo selecione **Usuários**.

5. Escolha **Debra Berger** da lista de usuários.

6. Selecione **Redefinir senha** na parte superior da página. Como você não fez logon anteriormente como Clara Barbosa, você não sabe a senha dela e precisará redefini-la.

7. Quando a janela de redefinição de senha abrir, selecione **Redefinir senha**.  IMPORTANTE: anote a nova senha, pois você precisará dela em uma tarefa posterior, para entrar como o usuário.

8. Feche a janela de redefinição de senha selecionando o **X** no canto superior direito da página e a janela Clara Barbosa selecionando o **X** no canto superior direito da página.

9. Selecione o **X**, no canto superior direito da página, para fechar a janela Usuários.

10. Agora você está novamente na página **Contoso | Visão geral**.  Mantenha essa janela aberta.

### <a name="task-2"></a>Tarefa 2:

Nesta tarefa, você percorrerá o processo de criação de uma política de acesso condicional no Azure AD.

1. Abra a guia do navegador, denominada Contoso - Microsoft Azure.   Se você fechou anteriormente a guia do navegador, abra o Microsoft Edge e, na barra de endereços, digite portal.azure.com, entre com suas credenciais de administrador e escolha Azure Active Directory.  

2. No painel de navegação esquerdo, selecione **Segurança**.

3. No painel de navegação esquerdo, selecione **Acesso condicional**.

4. A tela Políticas de acesso condicional é exibida. Todas as políticas de acesso condicional existentes são listadas aqui. Selecione **+ Nova política**.

5. No campo Nome, digite **Política de Teste do MFA**.

6. Em Usuários ou identidades de carga de trabalho, selecione **0 usuários ou identidades de carga de trabalho selecionadas**.

7. Agora você verá a opção Incluir ou Excluir usuários ou grupos.  Garanta que **Incluir** esteja selecionado (sublinhado).

8. Escolha a opção **Selecionar usuários e grupos** e **Usuários e grupos**.  A janela para Selecionar usuários e grupos é aberta.  

9. Na barra de Pesquisa, digite **Debra**.  Escolha **Debra Berger** abaixo da barra de pesquisa e pressione o botão **Selecionar** na parte inferior da página.  Observe que uma prática comum é atribuir a política a usuários em um grupo.  Para fins de conveniência neste laboratório, atribuiremos a política a um usuário específico.

10. Em Aplicativos de nuvem ou ações, selecione **Nenhum aplicativo de nuvem, ação ou contexto de autenticação selecionado**.

11. Agora você verá a opção Incluir ou Excluir aplicativos de nuvem ou ações do usuário.  Verifique se a opção **Aplicativos de nuvem** está listada no campo rotulado Selecionar ao que essa política se aplica.  Se ele ainda não estiver listado, selecione-o na lista suspensa. Verifique se a opção **Incluir** está selecionada (sublinhada), escolha **Selecionar aplicativos** e, abaixo de Selecionar, escolha **Nenhum**.  A janela para Selecionar aplicativos de nuvem é aberta.

12. Na barra de pesquisa, digite **Azure**.  Nos resultados da pesquisa que aparecem abaixo da caixa de pesquisa, selecione **Microsoft Azure Management**, e depois pressione **Selecionar** na parte inferior da página.  Observe o aviso.  

13. Em Condições, selecione **0 condições selecionadas**.  Observe as diferentes opções que você pode configurar.  Por meio da política, você pode controlar o acesso do usuário com base em sinais de condições como risco, plataforma do dispositivo, localização, aplicativos cliente ou estado do dispositivo.  Por exemplo, você pode incluir uma condição para que a política se aplique a qualquer local, exceto locais selecionados ou confiáveis, como a rede da sua sede.  Para esta política, não estabeleça nenhuma condição.

14. Agora você definirá os controles de acesso.  Em Concessão, selecione **0 controles escolhidos**.

15. A janela Concessão é aberta.  Verifique se a opção **Permitir acesso** está selecionada e escolha **Exigir a autenticação multifator**. Role a página um pouco para baixo na janela direita e, na seção Para vários controles, mantenha o padrão **Exigir todos os controles selecionados**.  Pressione **Selecionar** na parte inferior da página.

16. Na parte inferior da página, em Habilitar política, selecione **Ativado** e **Criar**.

17. Após alguns segundos, a política do MFA Pilot deve aparecer na lista de políticas de acesso condicional (se necessário, escolha **Atualizar** na parte superior da página).

18. Saia do Azure e feche as janelas do navegador.

### <a name="task-3"></a>Tarefa 3

Nesta tarefa, você verá o impacto da política de acesso condicional da perspectiva do usuário, Clara Barbosa. Você começará entrando em um aplicativo que não está incluído na política de acesso condicional.  Em seguida, você repetirá o processo para um aplicativo incluído na política de acesso condicional.  Lembre-se de que a política exige que o usuário passe pelo MFA ao acessar um aplicativo de gerenciamento do Microsoft Azure.  Para usar o MFA, o usuário deve primeiro registrar o método de autenticação que será usado para o MFA, por exemplo, um código enviado para um dispositivo móvel ou um aplicativo autenticador.

1. Entre como Clara Barbosa. 
    1. Na janela Entrar, insira **DebraB@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é a sua ID de locatário exclusiva fornecida pelo provedor de hospedagem do laboratório) e selecione **Avançar**.
    1. Digite a senha que você anotou na tarefa anterior. Selecione **Entrar**.
    1. Como a senha fornecida quando você, como administrador, a redefiniu é temporária, é preciso atualizar a senha (isso não faz parte da política da MFA). Insira a senha atual e, para a nova senha, insira **SC900-Lab** e **SC900** novamente para confirmar a senha.
    1. Quando solicitado a permanecer conectado, selecione **Sim**.  Você deve estar conectado à sua conta do Microsoft 365. O MFA não era necessário para este aplicativo, pois não faz parte da política.

1. Agora você tentará entrar em um aplicativo que atende aos critérios da MFA. Abra uma nova guia no portal.Microsoft Microsoft Edge e na barra de endereços, insira **portal.azure.com**.

1. Você verá uma janela indicando Mais informações necessárias.  Selecione **Avançar**.  Observação: isso iniciará o processo de registro da MFA, pois esta é a primeira vez que você está acessando o aplicativo em nuvem que foi identificado na política de acesso condicional.  Este processo de registro é necessário apenas uma vez.   Uma alternativa para o usuário passar pelo processo de registro é fazer com que o administrador configure o método de autenticação a ser usado.

1. Na janela Mantenha sua conta segura, você tem a opção de escolher o método a ser usado para MFA.  O Microsoft Authenticator é uma opção. Por conveniência neste exercício do laboratório, você escolherá outro método.  Selecione **Quero configurar um método diferente**.  Na janela pop-up Escolha um método diferente, selecione a **seta suspensa**, **Telefone** e depois **Confirmar**.

1. Na janela aberta, verifique se o seu país está selecionado e insira o número do celular que deseja usar.  Verifique se a opção **Envie-me um código por SMS** está selecionada e pressione **Avançar**.  Você receberá uma mensagem de texto no seu telefone com um código que precisará inserir em Inserir código.  Insira o código recebido e pressione **Avançar**.  Depois de confirmada, a tela exibirá "SMS verificado. Seu telefone foi registrado com sucesso".  Selecione **Avançar**. Em seguida, selecione **Concluído**.  O processo de registro único está concluído.

1. Agora você deve conseguir acessar o portal do Azure.  O portal do Azure é um aplicativo de gerenciamento do Microsoft Azure, portanto, requer autenticação de vários fatores, de acordo com a política de acesso condicional que foi criada.  
    1. Se você receber uma mensagem indicando que a entrada atingiu o tempo limite, insira a senha **SC900-Lab** e escolha **Entrar**. 
    1. Você verá uma janela que exige a verificação da sua identidade.  Selecione Texto =X XXXXXXX para receber um código no seu celular. Insira o código e escolha **Verificar**.
    1. Se for exibida uma mensagem perguntando se deseja permanecer conectado, selecione **Não**.

1. Desconecte-se escolhendo o ícone do usuário ao lado do endereço de email no canto superior direito da tela e selecionando Sair. Em seguida, feche todas as janelas do navegador.

### <a name="review"></a>Revisão

Neste laboratório, você conheceu o processo de configuração de uma política de acesso condicional que exige que os usuários passem pela MFA ao acessar o aplicativo de nuvem de Gerenciamento do Microsoft Azure.  Então, como usuário, você passou pelo processo de registro para o MFA e viu o impacto da política de acesso condicional que exigia que você usasse o MFA ao acessar o portal do Azure.
