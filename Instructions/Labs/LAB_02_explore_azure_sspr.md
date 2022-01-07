---
lab:
    title: 'Explorar a autenticação do Azure AD com redefinição de senha de autoatendimento'
    module: 'Módulo 2 Lição 2: Descrever as funcionalidades das soluções de gerenciamento de acesso e identidade da Microsoft: Descrever os diferentes métodos de autenticação do Azure AD'
---

# Laboratório: Explorar a autenticação do Azure AD com redefinição de senha de autoatendimento

## Cenário do laboratório

Neste laboratório, você, como administrador, percorrerá o processo de ativação da redefinição de senha de autoatendimento. Com o SSPR habilitado, você assume a função de usuário e passa pelo processo de registro do SSPR e também pela redefinição de sua senha.  Por fim, você, como administrador, poderá ver os registros de auditoria, dados de uso e insights para o SSPR.

**Tempo estimado**: 15 a 20 minutos


#### Tarefa 1:  Nesta tarefa, você, como administrador, adicionará um usuário existente, Adele Vance, ao grupo de usuários de segurança do SSPR.  Além disso, você também precisará redefinir a senha do usuário para poder fazer logon pela primeira vez, como usuário, e registrar-se no SSPR.

1. Abra o Microsoft Edge.

2. Na barra de endereço, digite **portal.azure.com** e faça logon com suas credenciais de administrador.
    1. Na janela de login, digite **admin@WWLxZZZZZZ.onmicrosoft.com** (ZZZZZZ é a sua ID de titular exclusiva fornecida pelo provedor de hospedagem de laboratório), depois selecione **Avançar**.
    1. Digite a senha de administrador que deve ser fornecida pelo provedor de hospedagem de laboratório. Selecione **Entrar**.
    1. Se você receber um aviso para permanecer conectado, escolha **Sim**.

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

13. Selecione **Redefinir senha** na parte superior da página. Como você não fez logon anteriormente como Adele Vance, é necessário redefinir a senha

14. Quando a janela de redefinição de senha abrir, selecione **Redefinir senha**.  IMPORTANTE, anote a nova senha, pois você precisará dela em alguma outra tarefa para poder entrar como usuário.

15. Selecione o **X**, no canto superior direito da página, para fechar a janela de redefinição de senha.

16. Selecione o **X**, no canto superior direito da página, para fechar a janela Adele Vance.

17. Selecione o **X**, no canto superior direito da página, para fechar a janela Usuários.

18. Mantenha a janela Visão geral do Contoso aberta, pois você irá usá-la na tarefa seguinte.

#### Tarefa 2: Nesta tarefa, você, como administrador, aprenderá como configurar a redefinição de senha para usuários, incluindo a configuração dos tipos de métodos de autenticação que devem ser usados.

1. Vá para a guia Contoso - Microsoft Azure que está aberta em seu navegador. Se você fechou a guia anteriormente, abra uma página do navegador e, na barra de endereço, digite portal.azure.com e selecione Azure Active Directory.  Você deve estar conectado como administrador, no portal do Azure; caso contrário, faça logon novamente.

2. No painel de navegação esquerdo, selecione **Redefinição de senha**.  

3. As propriedades para reconfiguração de senha de autoatendimento são exibidas.  Verifique se **Reconfiguração de autoatendimento** está **selecionado** para o grupo que está listado, o **SSPRSecurityUsers**.  Coloque o cursor sobre o ícone de informações próximo a "selecionar grupo" e observe o que ele diz, "Define o grupo de usuários que têm permissão para redefinir suas próprias senhas." Você deve incluir usuários no grupo, não pode escolher usuários individualmente.  Além disso, se você mudar o grupo, o grupo selecionado substitui o grupo listado atualmente.  Portanto, é recomendável que você apenas adicione usuários ao grupo SSPR.  Por último, observe a caixa de informações azul, "Estas configurações se aplicam apenas a usuários finais em sua organização. Os administradores estão sempre habilitados para redefinir a senha de autoatendimento e são obrigados a usar dois métodos de autenticação para redefinir a senha."

5. No painel de navegação esquerdo de Redefinição de senha, selecione **Métodos de Autenticação**.

6. Em Número de métodos necessários para a redefinição, selecione **1**. Observe a caixa de informações na tela.

7. Observe os diferentes métodos disponíveis para os usuários.  **Email** e **Telefone celular (apenas SMS)** já devem estar marcados; se não estiverem, selecione-os.

8. No painel de navegação esquerdo de Redefinição de senha, selecione **Registro**.  

9. Confirme se a configuração de Exigir que os usuários se registrem ao fazer logon está definida como **Sim**.  Mantenha o Número de dias antes que os usuários precisem reconfirmar suas informações de autenticação definido para 180.   Observe a caixa de informações na página.

10. No painel de navegação esquerdo de Redefinição de senha, selecione **Notificações**.  

11. Confirme se a configuração Notificar usuários sobre redefinições de senha está definida como **Sim**.  Mantenha a configuração de Notificar todos os administradores quando outros administradores redefinirem suas senhas definida como Não.

12. Observe como o painel de navegação de redefinição de senha também inclui opções para ver registros de auditoria e Uso e Insights.

13. Clique no ícone do usuário próximo ao endereço de email no canto superior direito da tela para **Sair** de todas as guias do navegador. Em seguida, feche todas as janelas do navegador.


#### Tarefa 3:  Nesta tarefa, você, como usuário Adele Vance, passará pelo processo de registro para redefinição de senha de autoatendimento.  Esta tarefa requer que você tenha acesso a um dispositivo móvel onde possa receber mensagens de texto ou uma conta de email pessoal que você possa acessar.
 
1. Abra o Microsoft Edge.

2. Na barra de endereço, digite **login.microsoftonline.com**.

3. Faça logon como Adele Vance,
    1. Na janela de logon, digite **AdedleV@WWLxZZZZZZ.onmicrosoft.com** (ZZZZZZ é a sua ID de titular exclusiva fornecida pelo provedor de hospedagem de laboratório), depois selecione **Avançar**.
    1. Digite a senha que você anotou na tarefa anterior. Selecione **Entrar**.
    1. Se você receber um aviso para permanecer conectado, selecione **Sim**

4. Como este é seu primeiro logo como Adele Vance, você precisa redefinir sua senha.  Coloque sua senha antiga.  Para sua nova senha, digite **SC900-Lab**. Digite **SC-900-Lab** no campo de confirmação de senha.  Escolha **Entrar**. estamos usando essa senha apenas para a conveniência do laboratório. Como prática recomendada, você deve digitar uma senha mais segura.

5. Um pop-up indicando que Mais informações são necessárias é exibido.  Isso ocorre porque, como membro do grupo SSPRSecurityUsers, a configuração exige que seus membros se registrem ao entrar. Selecione o botão **Avançar**.  Observação:  Uma alternativa para que os próprios usuários façam o registro é que os administradores configurem diretamente os métodos de autenticação ao adicionar um usuário. Isso exige que os administradores conheçam e definam os números de telefone e endereços de email que os usuários usam para realizar a redefinição de senha de autoatendimento e para redefinir a senha de um usuário.

6. A página “Mantenha sua conta segura” se abre.  A janela que aparece é para o método de autenticação por telefone, se você não tiver um dispositivo móvel habilitado para receber mensagens de texto, passe para a próxima etapa.  Insira um número de telefone. Garanta que a opção **Envie-me um código por mensagem** esteja ativada.   Digite o número de telefone que pode receber um código e selecione o botão **Avançar**.  Uma nova janela se abre indicando que um código acabou de ser enviado para o telefone que você informou.  Digite o código recebido e selecione **Avançar**. Uma janela se abre indicando Sucesso e mostrando seu método de logon Padrão.  Selecione **Concluído**.  

7. Pule esta etapa se você conseguiu configurar o SSPR com o número do telefone celular.  Ou então, você pode configurar um método diferente, conforme mostrado no canto inferior esquerdo da janela.  Se você optar por configurar um método diferente, selecione **Quero configurar um método diferente**, uma janela pop-up será exibida perguntando: Qual método gostaria de usar?  No menu suspenso, escolha seu método preferido, **Email** e selecione o botão **Confirmar**.  Digite o email que deseja usar e selecione **Avançar**.  Uma nova janela se abre indicando que um código acabou de ser enviado para o email que você informou.  Acesse o email que você informou para obter o código.  Digite o código recebido e selecione **Avançar**. Uma janela se abre indicando Sucesso e mostrando seu método de logon Padrão.  Selecione **Concluído**.

8. Agora você pode concluir seu logon. Você deve estar na página de aterrissagem do portal do Azure.  Se o tempo de logon expirar, basta inserir novamente a senha, SC900-Lab.

9. Saia do portal do Azure e feche a janela do navegador. 

#### Tarefa 4 (Opcional): Nesta tarefa, você, como usuário Adele Vance, passará pelo processo de redefinição de senha.

1. Abra o Microsoft Edge.

2. Na barra de endereço, digite login.microsoftonline.com.

3. Faça logon como Adele Vance, digitando seu email **AdeleV@WWLxZZZZ.onmicrosoft.com** (ZZZZZZ é a sua ID de titular exclusiva fornecida pelo provedor de hospedagem de laboratório) e selecione o botão **Avançar**. Você pode, em vez disso, ver a janela Escolher uma conta aberta; em caso afirmativo, selecione a conta de Adele Vance.

4. Na janela Digitar senha, selecione **Esqueci minha senha**. 

5. A janela para Voltar para a sua conta se abre.   Verifique se o email para Adele Vance, AdeleV@WWLxZZZZ.onmicrosoft.com, está aparecendo na caixa de email ou de nome de usuário.  Se não, digite-o.  

6. Na caixa vazia, digite os caracteres exibidos na imagem ou as palavras do áudio. Depois de digitá-los, selecione **Avançar**.

7. A tela mostra Voltar para sua conta e mostra etapa de Verificação 1 > escolha uma nova senha. Deixe a configuração padrão **Enviar mensagem de texto para meu celular**.  Você deve digitar o número do seu celular.  Depois de digitá-lo, selecione o botão de **Texto**.  Se, durante o registro, você selecionou email, a janela Voltar para sua conta indicará que Você receberá um email com um código de verificação em seu email alternativo.  Selecione **Email**. 

8. Insira o código de verificação e clique em **Avançar**.

9. Na próxima tela, você deverá digitar a nova senha e confirmá-la.  Digite-os agora e selecione o botão **Concluir**.

10. Você verá uma mensagem na tela informando que sua senha foi redefinida.  Selecione **clicar aqui** para entrar com sua nova senha.

11. Na caixa Escolher uma informação de conta, selecione **AdeleV@WWLxZZZZZZ.onmicrosoft.com**, digite sua nova senha e selecione o botão **Entrar**.  Se você tiver que permanecer conectado, selecione **Não**.

12. Agora você deve estar no portal do Azure.

13. Saia selecionando o ícone do usuário próximo ao endereço de email no canto superior direito da tela e selecionando **Sair**. Em seguida, feche todas as janelas do navegador

#### Tarefa 5 (Opcional):  Nesta tarefa, você, como administrador, verá resumidamente os registros de auditoria e os dados de Uso e Insights associados à redefinição de senha.

1. Abra o Microsoft Edge.

2. Na barra de endereço, digite **portal.azure.com** 

3. Entre com suas credenciais de administrador.
    1. Na janela de login, digite **admin@WWLxZZZZZZ.onmicrosoft.com** (ZZZZZZ é a sua ID de titular exclusiva fornecida pelo provedor de hospedagem de laboratório), depois selecione **Avançar**.
    1. Digite a senha de administrador que deve ser fornecida pelo provedor de hospedagem de laboratório. Selecione **Entrar**.
    1. Se você receber um aviso para permanecer conectado, escolha **Sim**.

4. Selecione **Azure Active Directory**.  

5. No painel de navegação esquerdo, selecione **Redefinição de senha**.

6. No painel de navegação esquerdo, selecione **Logs de Auditoria**.  Observe as informações e os filtros disponíveis.  Observe também que você pode baixar os logs.  

7. Selecione **Baixar**.  Observe que você pode formatar o download como CSV ou JSON.  Selecione o **X** no canto superior direito da tela para fechar a janela.

8. No painel de navegação esquerdo, selecione **Usos e Insight**.

9. Observe as informações disponíveis que pertencem ao registro.  Pode levar algum tempo para atualizar esses dados mesmo depois de uma atualização, ele pode ainda não mostrar o registro ou os dados de uso da tarefa anterior.

10. Na parte superior da página, selecione **Uso** para ver o número de redefinições de senha de autoatendimento e desbloqueios de conta por método.  Pode levar algum tempo para atualizar esses dados mesmo depois de uma atualização, ele pode ainda não mostrar os dados de uso da tarefa anterior.

11. Feche as guias do navegador.


#### Revisão
Neste laboratório, você, como administrador, percorreu o processo de ativação da redefinição de senha de autoatendimento. Com o SSPR ativado, você assume a função de usuário e passa pelo processo de registro do SSPR e também pela redefinição de sua senha.  Por fim, você, como administrador, aprendeu onde acessar os registros de auditoria, dados de uso e insights para o SSPR.
