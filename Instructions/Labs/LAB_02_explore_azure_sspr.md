<a name="---"></a><!---
---
Laboratório: Título: 'Explorar a autenticação do Azure AD com a redefinição de senha self-service' Roteiro de aprendizagem/Módulo/Unidade: 'Roteiro de aprendizagem: descrever as funcionalidades do Azure AD (Active Directory), parte do Microsoft Entra; Módulo 2: descrever as funcionalidades de autenticação do Azure AD; Unidade 4: descrever a redefinição de senha self-service no Azure AD'
---
--->

# <a name="lab-explore-azure-ad-authentication-with-self-service-password-reset"></a>Laboratório: Explorar a autenticação do Azure AD com redefinição de senha de autoatendimento

Esse laboratório é mapeado para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades do Azure AD (Azure Active Directory), parte do Microsoft Entra
- Módulo: descrever as funcionalidades de autenticação do Azure AD
- Unidade: descrever a redefinição de senha self-service no Azure AD

## <a name="lab-scenario"></a>Cenário do laboratório

Neste laboratório, você, como administrador, percorrerá o processo de ativação da redefinição de senha de autoatendimento. Com a SSPR habilitada, você assumirá a função de um usuário e passará pelo processo de registro da SSPR e pela redefinição da senha.  Por fim, você, como administrador, poderá ver os registros de auditoria, dados de uso e insights para o SSPR.

**Tempo estimado**: 15 a 20 minutos

### <a name="task-1"></a>Tarefa 1:

Nesta tarefa, você, como administrador, adicionará um usuário existente, Adele Vance, ao grupo de usuários de segurança do SSPR.  Além disso, você também precisará redefinir a senha do usuário para se conectar pela primeira vez, como usuário, e se registrar na SSPR.

1. Abra o Microsoft Edge.

2. Na barra de endereços, insira **portal.azure.com** e entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é a sua ID de locatário exclusiva fornecida pelo provedor de hospedagem do laboratório) e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**.

3. Selecione **Azure Active Directory**.  

4. No painel de navegação esquerdo, selecione **Grupos**.

5. Uma lista de grupos existentes é exibida. No campo de grupos de Pesquisa, digite **SSPR** e nos resultados de pesquisa selecione **SSPRSecurityGroupUsers**.  Você será direcionado para a opção de configuração para este grupo.

6. No painel de navegação esquerdo, selecione **Membros**.

7. Na parte superior da página, selecione **+ Adicionar membros**.  

8. Na caixa de pesquisa, digite **Adele**.  Assim que o usuário, **Adele Vance**, aparecer abaixo da caixa de pesquisa, selecione-o e clique em **Selecionar** no fim da página.

9. Feche a janela SSPRSecurityUsers, selecionando o **X** no canto superior direito da tela,

10. Selecione **Contoso** no canto superior esquerdo da tela, logo acima de Grupos, para voltar para a página do Contoso Azure Active Directory.

11. No painel de navegação esquerdo selecione **Usuários**.

12. Selecione **Adele Vance** na lista de usuários.

13. Selecione **Redefinir senha** na parte superior da página. Como você não fez logon anteriormente como Alice Pena, precisa redefinir a senha

14. Quando a janela de redefinição de senha abrir, selecione **Redefinir senha**.  IMPORTANTE: anote a nova senha, pois você precisará dela em uma tarefa posterior, para entrar como o usuário.

15. Selecione o **X**, no canto superior direito da página, para fechar a janela de redefinição de senha.

16. Selecione o **X**, no canto superior direito da página, para fechar a janela Adele Vance.

17. Selecione o **X**, no canto superior direito da página, para fechar a janela Usuários.

18. Mantenha a janela Visão geral do Contoso aberta, pois você vai usá-la na tarefa seguinte.

### <a name="task-2"></a>Tarefa 2:

Nesta tarefa, você, como administrador, aprenderá como configurar a redefinição de senha para usuários, incluindo a configuração dos tipos de métodos de autenticação que devem ser usados

1. Vá para a guia Contoso – Microsoft Azure aberta no seu navegador. Se você fechou a guia anteriormente, abra uma página do navegador e, na barra de endereços, insira portal.azure.com e selecione Azure Active Directory.  Você deve estar conectado como administrador no portal do Azure; caso contrário, entre novamente.

1. No painel de navegação esquerdo, selecione **Redefinição de senha**.  

1. As propriedades para reconfiguração de senha de autoatendimento são exibidas.  Verifique se a opção **Redefinição por autoatendimento** está **selecionada** para o grupo listado, o **SSPRSecurityGroupUsers**.  Posicione o cursor sobre o ícone de informações ao lado de "selecionar grupo" e observe que ele indica "Define o grupo de usuários que tem permissão para redefinir as respectivas senhas". Você deve incluir usuários no grupo. Não é possível selecionar usuários individualmente.  Além disso, se você alterar o grupo, o grupo selecionado substituirá o grupo listado atualmente.  Portanto, é recomendável que você adicione os usuários ao grupo da SSPR.  Por último, observe a caixa de informações azul, "Estas configurações se aplicam apenas a usuários finais em sua organização. Os administradores estão sempre habilitados para redefinir a senha de autoatendimento e são obrigados a usar dois métodos de autenticação para redefinir a senha."

1. No painel de navegação esquerdo de Redefinição de senha, selecione **Métodos de Autenticação**.

1. Em Número de métodos necessários para a redefinição, selecione **1**. Observe a caixa de informações na tela.

1. Observe os diferentes métodos disponíveis para os usuários.  **Email** e **Telefone celular (apenas SMS)** já devem estar marcados; se não estiverem, selecione-os.

1. No painel de navegação esquerdo de Redefinição de senha, selecione **Registro**.  

1. Confirme se a configuração de Exigir que os usuários se registrem ao fazer logon está definida como **Sim**.  Mantenha o Número de dias antes que os usuários precisem confirmar novamente as informações de autenticação como o padrão de 180.   Observe a caixa de informações na página.

1. No painel de navegação esquerdo de Redefinição de senha, selecione **Notificações**.  

1. Confirme se a configuração Notificar usuários sobre redefinições de senha está definida como **Sim**.  Mantenha a configuração de Notificar todos os administradores quando outros administradores redefinirem suas senhas definida como Não.

1. Observe como o painel de navegação de redefinição de senha também inclui opções para exibir logs de auditoria e Uso e insights.

1. **Saia** de todas as guias do navegador clicando no ícone do usuário ao lado do endereço de email, no canto superior direito da tela. Em seguida, feche todas as janelas do navegador.

### <a name="task-3"></a>Tarefa 3

Nesta tarefa, você, como usuário Adele Vance, passará pelo processo de registro para redefinição de senha de autoatendimento.  Esta tarefa requer que você tenha acesso a um dispositivo móvel onde possa receber mensagens de texto ou uma conta de email pessoal que você possa acessar

1. Abra o Microsoft Edge.

2. Na barra de endereços, insira **login.microsoftonline.com**.

3. Faça logon como Adele Vance,
    1. Na janela Entrar, insira **AdeleV@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é a sua ID de locatário exclusiva fornecida pelo provedor de hospedagem do laboratório) e selecione **Avançar**.
    1. Digite a senha que você anotou na tarefa anterior. Selecione **Entrar**.
    1. Se você receber um aviso para permanecer conectado, selecione **Sim**


4. Como esta é a sua primeira entrada como Alice Pena, você precisa redefinir sua senha.  Coloque sua senha antiga.  Para sua nova senha, insira **SC900-Lab**. Digite **SC-900-Lab** no campo de confirmação de senha.  Selecione **Entrar**.  Observação: estamos usando essa senha apenas para a conveniência do laboratório. Como prática recomendada, você deve digitar uma senha mais segura.

5. Um pop-up indicando que Mais informações são necessárias é exibido.  Isso ocorre porque, como membro do grupo SSPRSecurityGroupUsers, a configuração exige que seus membros se registrem ao entrar.  Selecione o botão **Avançar**.  Observação:  Uma alternativa para que os próprios usuários façam o registro é que os administradores configurem diretamente os métodos de autenticação ao adicionar um usuário. Isso exige que os administradores conheçam e definam os números de telefone e endereços de email que os usuários usam para realizar a redefinição de senha de autoatendimento e para redefinir a senha de um usuário.

6. A página “Mantenha sua conta segura” se abre.  A janela que aparece é para o método de autenticação por telefone, se você não tiver um dispositivo móvel habilitado para receber mensagens de texto, passe para a próxima etapa.  Você precisará inserir um número de telefone. Garanta que a opção **Envie-me um código por mensagem** esteja ativada.   Digite o número de telefone que pode receber um código e selecione o botão **Avançar**.  Uma nova janela será aberta, indicando que um código foi enviado para o telefone que você informou.  Digite o código recebido e selecione **Avançar**. Uma janela se abre indicando Sucesso e mostrando seu método de logon Padrão.  Selecione **Concluído**.  

7. Pule esta etapa se você conseguiu configurar o SSPR com o número do telefone celular.  Como alternativa, você pode configurar outro método, conforme mostrado no canto inferior esquerdo da janela.  Se você optar por configurar outro método, selecione **Quero configurar um método diferente**, uma janela pop-up será exibida perguntando "Qual método deseja usar?"  No menu suspenso, escolha seu método preferido, **Email**, e selecione o botão **Confirmar**.  Digite o email que deseja usar e selecione **Avançar**.  Uma nova janela será aberta, indicando que um código foi enviado para o email que você informou.  Acesse o email que você informou para obter o código.  Digite o código recebido e selecione **Avançar**. Uma janela se abre indicando Sucesso e mostrando seu método de logon Padrão.  Selecione **Concluído**.

8. Agora você pode concluir a entrada.  Você está na página de aterrissagem do portal do Azure.  Se o tempo de logon vencer, basta inserir novamente a senha, SC900-Lab.

9. Saia do portal do Azure e feche a janela do navegador.

### <a name="task-4-optional"></a>Tarefa 4 (opcional)

Nesta tarefa, você, usando o usuário Alice Pena, passará pelo processo de redefinição de senha

1. Abra o Microsoft Edge.

2. Na barra de endereços, insira **login.microsoftonline.com**.

3. Faça logon como Adele Vance, digitando seu email **AdeleV@WWLxZZZZ.onmicrosoft.com** (ZZZZZZ é a sua ID de titular exclusiva fornecida pelo provedor de hospedagem de laboratório) e selecione o botão **Avançar**. Você pode, em vez disso, ver a janela Escolher uma conta aberta; em caso afirmativo, selecione a conta de Adele Vance.

4. Na janela Digitar senha, selecione **Esqueci minha senha**.

5. A janela para Voltar para a sua conta se abre.   Verifique se o email para Adele Vance, AdeleV@WWLxZZZZ.onmicrosoft.com, é mostrado na caixa email ou nome de usuário.  Se não, digite-o.  

6. Na caixa vazia, digite os caracteres exibidos na imagem ou as palavras do áudio. Depois de inseri-los, selecione **Avançar**.

7. A tela mostra Voltar para sua conta e mostra etapa de Verificação 1 > escolha uma nova senha. Deixe a configuração padrão **Enviar mensagem de texto para meu celular**.  Você precisará inserir o número do seu celular.  Depois de inseri-lo, selecione o **botão de Texto**.  Se, durante o registro, você selecionar Email, a janela Voltar para sua conta indicará que você receberá um email com um código de verificação no seu endereço de email alternativo.  Selecione **Email**.

8. Insira o código de verificação e clique em **Avançar**.

9. Na próxima tela, você precisará inserir a nova senha e confirmá-la.  Digite-os agora e selecione o botão **Concluir**.

10. Você verá uma mensagem na tela informando que a sua senha foi redefinida.  Selecione **clicar aqui** para entrar com sua nova senha.

11. Na caixa Escolher uma informação de conta, selecione **AdeleV@WWLxZZZZZZ.onmicrosoft.com** , digite sua nova senha e selecione o botão **Entrar**.  Se for exibida uma mensagem perguntando se deseja permanecer conectado. selecione **Não**.

12. Agora você deve estar no portal do Office.

13. Saia selecionando o ícone do usuário próximo ao endereço de email no canto superior direito da tela e selecionando **Sair**. Em seguida, feche todas as janelas do navegador

### <a name="task-5-optional"></a>Tarefa 5 (opcional)

Nesta tarefa, você, como administrador, verá resumidamente os registros de auditoria e os dados de Uso e Insights associados à redefinição de senha

1. Abra o Microsoft Edge.

2. Na barra de endereços, insira **portal.azure.com**

3. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é a sua ID de locatário exclusiva fornecida pelo provedor de hospedagem do laboratório) e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**.

4. Selecione **Azure Active Directory**.  

5. No painel de navegação esquerdo, selecione **Redefinição de senha**.

6. No painel de navegação esquerdo, selecione **Logs de Auditoria**.  Observe as informações e os filtros disponíveis.  Observe também que você pode baixar os logs.  

7. Selecione **Baixar**.  Observe que você pode formatar o download como CSV ou JSON.  Selecione o **X** no canto superior direito da tela para fechar a janela.

8. No painel de navegação esquerdo, selecione **Usos e Insight**.

9. Observe as informações disponíveis que pertencem ao registro.  Pode levar algum tempo para atualizar esses dados mesmo depois de uma atualização, ele pode ainda não mostrar o registro ou os dados de uso da tarefa anterior.

10. Na parte superior da página, selecione **Uso** para ver o número de redefinições de senha de autoatendimento e desbloqueios de conta por método.  Pode levar algum tempo para atualizar esses dados mesmo depois de uma atualização, ele pode ainda não mostrar os dados de uso da tarefa anterior.

11. Feche as guias do navegador abertas.

### <a name="review"></a>Revisão

Neste laboratório, você, como administrador, percorreu o processo de ativação da redefinição de senha de autoatendimento. Com a SSPR habilitada, você assumirá a função de um usuário para passar pelo processo de registro da SSPR e pela redefinição da senha.  Por fim, você, como administrador, aprendeu onde acessar os registros de auditoria, dados de uso e insights para o SSPR.
