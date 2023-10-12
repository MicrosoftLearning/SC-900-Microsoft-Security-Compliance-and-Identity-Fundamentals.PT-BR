<!---
---
Laboratório: Título: 'Explorar a autenticação do Microsoft Azure AD com redefinição de senha self-service' Roteiro de Aprendizagem/Módulo/Unidade: 'Roteiro de Aprendizagem: descrever as capacidades do Azure Active Directory (Azure AD), parte do Microsoft Entra; Módulo 2: descrever as capacidades de autenticação do Microsoft Azure AD; Unidade 4: descrever a senha self-service'
---
--->

# Laboratório: redefinição de senha self-service do Microsoft Entra

Esse laboratório é mapeado para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as capacidades do Microsoft Entra
- Módulo: descrever as capacidades de autenticação do Microsoft Entra ID
- Unidade: descrever a redefinição de senha self-service

## Cenário do laboratório

Neste laboratório, você, como administrador, percorrerá o processo de adição de um usuário ao grupo de segurança SSPR, que já está configurado no seu locatário do Microsoft 365. Com a SSPR habilitada, você assumirá a função de um usuário e passará pelo processo de registro da SSPR e pela redefinição da senha.  Por fim, você, como administrador, poderá ver os registros de auditoria, dados de uso e insights para o SSPR.

**Tempo estimado**: 15 a 20 minutos

### Tarefa 1:

Nesta tarefa, você, como administrador, percorrerá algumas das definições de configuração disponíveis para o SSPR.

1. Abra o navegador Microsoft Edge. Na barra de endereços, insira **https://entra.microsoft.com** e entre com as credenciais de administrador do Microsoft 365 fornecidas pelo seu hoster de laboratório autorizado (ALH).
    1. Na Janela de Entrada, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é a ID de Locatário exclusiva fornecida pelo ALH) e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**.

1. No painel de navegação à esquerda, expanda a opção **Proteção** e selecione **Redefinição de senha**.  

1. As propriedades para reconfiguração de senha de autoatendimento são exibidas. Selecione o ícone de informações no local no qual está escrito **Redefinição de senha self-service habilitada** para exibir a descrição. Certifique-se de que **Selecionado** esteja destacado em azul. Agora, coloque o cursor sobre o ícone de informações próximo ao local no qual está escrito **Selecionar grupo** e observe que ele diz: "Define o grupo de usuários que têm permissão para redefinir suas próprias senhas." Você deve incluir usuários no grupo. Não é possível selecionar usuários individualmente. Observe que já existe um grupo listado: SSPRSecurityGroupUsers (esse grupo foi pré-configurado como parte do seu locatário do Microsoft 365). Por último, observe a caixa de informações azul, "Estas configurações se aplicam apenas a usuários finais em sua organização. Os administradores estão sempre habilitados para redefinir a senha de autoatendimento e são obrigados a usar dois métodos de autenticação para redefinir a senha."

1. No painel de navegação esquerdo de Redefinição de senha, selecione **Métodos de Autenticação**.

1. Em Número de métodos necessários para a redefinição, selecione **1**. Observe a caixa de informações na tela.

1. Observe os diferentes métodos disponíveis para os usuários.  **Email** e **Telefone celular (apenas SMS)** já devem estar marcados; se não estiverem, selecione-os.

1. No painel de navegação esquerdo de Redefinição de senha, selecione **Registro**.  

1. Confirme se a configuração de Exigir que os usuários se registrem ao fazer logon está definida como **Sim**.  Mantenha o Número de dias antes que os usuários precisem confirmar novamente as informações de autenticação como o padrão de 180.   Observe a caixa de informações na página.

1. No painel de navegação esquerdo de Redefinição de senha, selecione **Notificações**.  

1. Confirme se a configuração Notificar usuários sobre redefinições de senha está definida como **Sim**.  Mantenha a configuração de Notificar todos os administradores quando outros administradores redefinirem suas senhas definida como Não.

1. Observe como o painel de navegação de redefinição de senha também inclui opções para exibir logs de auditoria e Uso e insights.

1. Feche a janela de redefinição de senha selecionando o **X** no canto superior direito da janela. Isso o leva de volta ao centro de administração Microsoft Entra.

1. Mantenha a janela do Microsoft Entra aberta.

### Tarefa 2:

Nesta tarefa, você, como administrador, adicionará o usuário criado no exercício de laboratório anterior ao grupo de segurança SSPR.

1. Abra a guia do navegador da página inicial do Centro de Administração Microsoft Entra **[entra.microsoft.com](https://entra.microsoft.com)** . Se necessário, expanda **Identidade**.

1. No painel de navegação à esquerda, em "Identidade", expanda **Grupos** e selecione **Todos os grupos**.

1. Uma lista de grupos existentes é exibida. No campo de grupos de Pesquisa, digite **SSPR** e nos resultados de pesquisa selecione **SSPRSecurityGroupUsers**.  Você será direcionado para a opção de configuração para este grupo.

1. No painel de navegação esquerdo, selecione **Membros**.

1. Na parte superior da página, selecione **+ Adicionar membros**.  

1. Na caixa Pesquisar, insira **Sara Perez**.  Uma vez que o usuário, **Sara Perez**, aparecer abaixo da caixa de pesquisa, selecione-o e pressione **Selecionar** na parte inferior da página.  Que será retornado à página de membros.  Selecione **Atualizar** na parte superior da página. Agora você deverá ver a usuária Sara Perez listada como membro do grupo de segurança SSPR.

1. Saia de todas as guias do navegador clicando no ícone do usuário ao lado do endereço de email, no canto superior direito da tela. Em seguida, feche todas as janelas do navegador.

### Tarefa 3

Nesta tarefa, você, como usuária Sara Perez, passará pelo processo de registro da redefinição de senha self-service.  Esta tarefa requer que você tenha acesso a um dispositivo móvel onde possa receber mensagens de texto ou uma conta de email pessoal que você possa acessar

1. Abra o Microsoft Edge e, na barra de endereços, insira **https://login.microsoft.com** .

1. Entre como Sara Perez.

1. Um pop-up indicando que Mais informações são necessárias é exibido.  Isso ocorre porque, como membro do grupo SSPRSecurityGroupUsers, a configuração exige que seus membros se registrem ao entrar.  Selecione o botão **Avançar**.  Observação:  Uma alternativa para que os próprios usuários façam o registro é que os administradores configurem diretamente os métodos de autenticação ao adicionar um usuário. Isso exige que os administradores conheçam e definam os números de telefone e endereços de email que os usuários usam para realizar a redefinição de senha de autoatendimento e para redefinir a senha de um usuário.

1. A página “Mantenha sua conta segura” se abre.  A janela que aparece é para o método de autenticação por telefone, se você não tiver um dispositivo móvel habilitado para receber mensagens de texto, passe para a próxima etapa.  Você precisará inserir um número de telefone. Garanta que a opção **Envie-me um código por mensagem** esteja ativada.   Digite o número de telefone que pode receber um código e selecione o botão **Avançar**.  Uma nova janela será aberta, indicando que um código foi enviado para o telefone que você informou.  Digite o código recebido e selecione **Avançar**. Uma janela se abre indicando Sucesso e mostrando seu método de logon Padrão.  Selecione **Concluído**.  
    1. Como alternativa, você pode configurar outro método, conforme mostrado no canto inferior esquerdo da janela.  Se você optar por configurar outro método, selecione **Quero configurar um método diferente**, uma janela pop-up será exibida perguntando "Qual método deseja usar?"  No menu suspenso, escolha seu método preferido, **Email**, e selecione o botão **Confirmar**.  Digite o email que deseja usar e selecione **Avançar**.  Uma nova janela será aberta, indicando que um código foi enviado para o email que você informou.  Acesse o email que você informou para obter o código.  Digite o código recebido e selecione **Avançar**. Uma janela se abre indicando Sucesso e mostrando seu método de logon Padrão.  Selecione **Concluído**.

1. Agora você pode concluir a entrada. Se você perceber que o tempo de entrada expirou, basta digitar a senha novamente.

1. Saia de todas as guias do navegador clicando no ícone do usuário ao lado do endereço de email, no canto superior direito da tela. Em seguida, feche todas as janelas do navegador.

### Tarefa 4 (opcional)

Nesta tarefa, você, como usuária Sara Perez, passará pelo processo de redefinição da senha

1. Abra o Microsoft Edge.

1. Na barra de endereços, insira **https://login.microsoftonline.com** .

1. Entre como Sara Perez, inserindo seu email **sara@WWLxZZZZ.onmicrosoft.com** (em que ZZZZZZ é sua ID de Locatário exclusivo fornecida pelo provedor de hospedagem de laboratório) e selecione o botão **Avançar**. Em vez disso, você vê a janela Escolha uma conta aberta; se for o caso, selecione a conta para Sara Perez.

1. Na janela Digitar senha, selecione **Esqueci minha senha**.

1. A janela para Voltar para a sua conta se abre.   Verifique se o email de Sara Perez, sara@WWLxZZZZ.onmicrosoft.com, é mostrado na caixa de email ou nome de usuário.  Se não, digite-o.  

1. Na caixa vazia, digite os caracteres exibidos na imagem ou as palavras do áudio. Depois de inseri-los, selecione **Avançar**.

1. A tela mostra Voltar para sua conta e mostra etapa de Verificação 1 > escolha uma nova senha. Deixe a configuração padrão **Enviar mensagem de texto para meu celular**.  Você precisará inserir o número do seu celular.  Depois de inseri-lo, selecione o **botão de Texto**.  Se, durante o registro, você selecionar Email, a janela Voltar para sua conta indicará que você receberá um email com um código de verificação no seu endereço de email alternativo.  Selecione **Email**.

1. Insira o código de verificação e clique em **Avançar**.

1. Na próxima tela, você precisará inserir a nova senha e confirmá-la.  Digite-os agora e selecione o botão **Concluir**.

1. Você verá uma mensagem na tela informando que a sua senha foi redefinida.  Selecione **clicar aqui** para entrar com sua nova senha.

1. Na caixa Escolher uma informação de conta, selecione **sara@WWLxZZZZZZ.onmicrosoft.com** , digite sua nova senha e selecione o botão **Entrar**.  Se for exibida uma mensagem perguntando se deseja permanecer conectado. selecione **Não**.

1. Agora você deve estar no portal do Office.

1. Saia selecionando o ícone do usuário próximo ao endereço de email no canto superior direito da tela e selecionando **Sair**. Em seguida, feche todas as janelas do navegador

### Tarefa 5 (opcional)

Nesta tarefa, você, como administrador, verá resumidamente os registros de auditoria e os dados de Uso e Insights associados à redefinição de senha

1. Abra o Microsoft Edge.

1. Na barra de endereços, insira **https://entra.microsoft.com** e entre com as credenciais de administrador do Microsoft 365 fornecidas pelo seu hoster de laboratório autorizado (ALH).

1. Você está no centro de administração Microsoft Entra.  No painel de navegação à esquerda, expanda a opção **Proteção** e selecione **Redefinição de senha**.

1. No painel de navegação esquerdo, selecione **Logs de Auditoria**.  Observe as informações e os filtros disponíveis.  Observe também que você pode baixar os logs.  

1. Selecione **Baixar**.  Observe que você pode formatar o download como CSV ou JSON.  Selecione o **X** no canto superior direito da tela para fechar a janela.

1. No painel de navegação esquerdo, selecione **Usos e Insight**.

1. Observe as informações disponíveis que pertencem ao registro.  Pode levar algum tempo para atualizar esses dados mesmo depois de uma atualização, ele pode ainda não mostrar o registro ou os dados de uso da tarefa anterior.

1. Na parte superior da página, selecione **Uso** para ver o número de redefinições de senha de autoatendimento e desbloqueios de conta por método.  Pode levar algum tempo para atualizar esses dados mesmo depois de uma atualização, ele pode ainda não mostrar os dados de uso da tarefa anterior.

1. Feche as guias do navegador abertas.

### Revisão

Neste laboratório, você, como administrador, percorreu o processo de ativação da redefinição de senha de autoatendimento. Com a SSPR habilitada, você assumirá a função de um usuário para passar pelo processo de registro da SSPR e pela redefinição da senha.  Por fim, você, como administrador, aprendeu onde acessar os registros de auditoria, dados de uso e insights para o SSPR.
