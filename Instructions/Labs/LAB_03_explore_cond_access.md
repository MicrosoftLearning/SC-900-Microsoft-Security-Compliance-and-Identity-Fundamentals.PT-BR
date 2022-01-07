---
lab:
    title: 'Explorar o gerenciamento de acesso no Azure AD com Condicional'
    module: 'Módulo 2 Lição 3: Descrever as funcionalidades das soluções de gerenciamento de acesso e identidade da Microsoft: Explorar os recursos de gerenciamento de acesso do Azure AD'
---


# Laboratório: Explorar o gerenciamento de acesso no Azure AD com Condicional

## Cenário do laboratório
Neste laboratório, você explorará o acesso condicional do MFA, da perspectiva de um administrador e de um usuário.  Como administrador, você criará uma política que exigirá que um usuário passe por autenticação de vários fatores ao acessar um aplicativo de gerenciamento do Microsoft Azure baseado em nuvem.  Da perspectiva do usuário, você verá o impacto da política de acesso condicional, incluindo o processo de registro para o MFA.

**Tempo estimado**: 10 a 15 minutos

#### Tarefa 1: Nesta tarefa você, como administrador, irá redefinir a senha do usuário Debra Berger.  Esta etapa é necessária para que você possa inicialmente fazer logon como usuário nas tarefas seguintes.

1. Abra o Microsoft Edge.  Na barra de endereço, digite **portal.azure.com**.

2. Entre com suas credenciais de administrador.
    1. Na janela de login, digite **admin@WWLxZZZZZZ.onmicrosoft.com** (ZZZZZZ é a sua ID de titular exclusiva fornecida pelo provedor de hospedagem de laboratório), depois selecione **Avançar**.
    1. Digite a senha de administrador que deve ser fornecida pelo provedor de hospedagem de laboratório. Selecione **Entrar**.
    1. Se você receber um aviso para permanecer conectado, escolha **Sim**.

3. Selecione **Azure Active Directory**.  

4. No painel de navegação esquerdo selecione **Usuários**.

5. Escolha **Debra Berger** da lista de usuários.

6. Selecione **Redefinir senha** na parte superior da página. Como você não fez logon anteriormente como Debra Berger, você não sabe a senha dela e precisará redefini-la.

7. Quando a janela de redefinição de senha abrir, selecione **Redefinir senha**.  IMPORTANTE, anote a nova senha, pois você precisará dela em alguma outra tarefa para poder entrar como usuário.

8. Selecione o **X**, no canto superior direito da página, para fechar a janela de redefinição de senha.

9. Selecione o **X**, no canto superior direito da página, para fechar a janela Usuários.

10. Mantenha essa janela aberta.


#### Tarefa 2:  Nesta tarefa, você percorrerá o processo de criação de uma política de acesso condicional no Azure AD.

1. Abra a guia do navegador, denominada Contoso - Microsoft Azure.   Se você fechou anteriormente a guia do navegador, abra o Microsoft Edge e, na barra de endereços, digite portal.azure.com, entre com suas credenciais de administrador e escolha Azure Active Directory.  

2. No painel de navegação esquerdo, selecione **Segurança**.

3. No painel de navegação esquerdo, selecione **Acesso condicional**.

4. A tela Políticas de acesso condicional é exibida. Todas as políticas de acesso condicional existentes são listadas aqui. Escolha**Nova política**.

5. No campo Nome, digite **Política de Teste do MFA**.

6. Em Usuários e grupos, selecione **0 usuários e grupos escolhidos**.

7. Agora você verá a opção de Incluir ou Excluir usuários ou grupos.  Garanta que **Incluir** esteja selecionado (sublinhado).

8. Escolha a opção **Selecionar usuários e grupos** e **Usuários e grupos**.  A janela para Selecionar usuários e grupos é aberta.  

9. Na barra de Pesquisa, digite **Debra**.  Escolha **Debra Berger** abaixo da barra de pesquisa e pressione o botão **Selecionar** na parte inferior da página.  Observe que uma prática comum é atribuir a política a usuários em um grupo.  Para fins de conveniência com este laboratório, atribuiremos a política a um usuário específico. 

10. Em aplicativos ou ações na Nuvem, escolha **Nenhum aplicativo em nuvem ou ações selecionadas**.

11. Agora você verá a opção de Incluir ou Excluir aplicativos em nuvem ou ações do usuário.  Garanta que **Aplicativos em nuvem** esteja destacado e **Incluir** esteja selecionado (sublinhado), depois selecione **Selecionar aplicativos**.  A janela para Selecionar aplicativos de nuvem é aberta.

12. Na barra de pesquisa, digite **Azure**.  Nos resultados da pesquisa que aparecem abaixo da caixa de pesquisa, selecione **Microsoft Azure Management**, e depois pressione **Selecionar** na parte inferior da página.  Observe o aviso.  

13. Em Condições, selecione **0 condições selecionadas**.  Observe as diferentes opções que você pode configurar.  Por meio da política, você pode controlar o acesso do usuário com base em sinais de condições como risco, plataforma do dispositivo, localização, aplicativos cliente ou estado do dispositivo.  Por exemplo, você pode incluir uma condição para que a política se aplique a qualquer local, exceto locais selecionados ou confiáveis, como a rede da sua sede.  Para esta política, não estabeleça nenhuma condição.

14. Agora você definirá os controles de acesso.  Em Concessão, selecione **0 controles escolhidos**.

15. A janela Concessão é aberta.  Garanta que **Conceder acesso** esteja selecionado e depois escolha **Exigir autenticação de vários fatores**.  Na seção Para vários controles, deixe o padrão **Exigir todos os controles selecionados**.  Pressione **Selecionar** na parte inferior da página.

16. Na parte inferior da página, em Habilitar política, selecione **Ativado**, e depois pressione o **Botão Criar**.

17. Após alguns segundos, a política do MFA Pilot deve aparecer na lista de políticas de acesso condicional (se necessário, escolha **Atualizar** na parte superior da página).

18. Saia do Azure e feche as janelas do navegador.

#### Tarefa 3: Nesta tarefa você verá o impacto da política de acesso condicional, na perspectiva do usuário, Debra Berger. Você começará entrando primeiro em um aplicativo que não está incluído na política de acesso condicional.  Em seguida, você repetirá o processo para um aplicativo incluído na política de acesso condicional.  Lembre-se de que a política exige que o usuário passe pelo MFA ao acessar um aplicativo de gerenciamento do Microsoft Azure.  Para usar o MFA, o usuário deve primeiro registrar o método de autenticação que será usado para o MFA, por exemplo, um código enviado para um dispositivo móvel ou um aplicativo autenticador.

1. Abra o Microsoft Edge.  Na barra de endereço do navegador, digite **https://login.microsoftonline.com/**

1. Faça login como Debra Burger,
    1. Na janela de login, digite **DebraB@WWLxZZZZZZ.onmicrosoft.com** (ZZZZZZ é a sua ID de titular exclusiva fornecida pelo provedor de hospedagem de laboratório) e depois selecione **Avançar**.
    1. Digite a senha que você anotou na tarefa anterior. Selecione **Entrar**.
    1. Como a senha fornecida quando você, como administrador, redefine a senha, ela é temporária, você precisa atualizar sua senha (isso não faz parte do MFA).  Digite a senha atual e, depois, para os campos nova senha e confirmar senha, digite **SC900-Lab**.
    1. Se você receber um aviso para permanecer conectado, selecione **Sim**

1. Você deve estar conectado à sua conta do Microsoft 365.  O MFA não era necessário para este aplicativo, pois não faz parte da política.

1. Agora você tentará entrar em um aplicativo que atenda aos critérios para o MFA.  Abra o Microsoft Edge e na barra de endereço, digite https://portal.azure.com.

1. Você verá uma janela indicando Mais informações necessárias.  Selecione **Avançar**.  Isso iniciará o processo de registro do MFA, pois esta é a primeira vez que você está acessando o aplicativo em nuvem que foi identificado na política de acesso condicional.  Este processo de registro é necessário apenas uma vez.   Uma alternativa para o usuário passar pelo processo de registro é fazer com que o administrador configure o método de autenticação a ser usado.

1. Na janela Mantenha sua conta segura, você tem a opção de escolher o método a ser usado para MFA.  O Microsoft Authenticator é uma opção. Por conveniência neste exercício de laboratório, você escolherá um método diferente.  Selecione **Quero configurar um método diferente**.  Na janela pop-up Escolha um método diferente, selecione a **seta suspensa**, **Telefone** e depois **Confirmar**.

1. Na janela aberta, certifique-se de que seu país esteja selecionado e, em seguida, digite o número do telefone celular que deseja usar e selecione, verifique se **Envie-me um código por mensagem** está selecionado, depois pressione **Avançar**.  A tela exibirá "Verificado por SMS. Seu telefone foi registrado com sucesso".  Selecione **Avançar**, depois **Concluído**.  O processo de registro único está concluído.

1. Você provavelmente receberá uma mensagem indicando que o tempo limite de logon expirou.  Basta digitar a senha **SC900-Lab** e escolher **Entrar**.

1. Você verá uma janela solicitando que você digite o código que foi enviado para o seu telefone.  Digite o código e escolha **Avançar**.  Esta é a experiência que você, como Gerhart, experimentará sempre que acessar um aplicativo de nuvem do Microsoft Azure Management, como o Portal do Azure, de acordo com a política do MFA.

1. Você verá uma janela solicitando que você digite o código que foi enviado para o seu telefone.  Digite o código e selecione o botão **Verificar**.  Quando solicitado a permanecer conectado, escolha **Não**.

1. Agora você deve conseguir acessar o portal do Azure.  O portal do Azure é um aplicativo de gerenciamento do Microsoft Azure, portanto, requer autenticação de vários fatores, de acordo com a política de acesso condicional que foi criada.  

1. Saia escolhendo o ícone do usuário próximo ao endereço de email no canto superior direito da tela e selecionando Sair. Em seguida, feche todas as janelas do navegador.

#### Revisão
Neste laboratório, você passou pelo processo de configuração de uma política de acesso condicional que exige que os usuários passem por MFA ao acessar o aplicativo de nuvem Microsoft Azure Management.  Então, como usuário, você passou pelo processo de registro para o MFA e viu o impacto da política de acesso condicional que exigia que você usasse o MFA ao acessar o portal do Azure.
