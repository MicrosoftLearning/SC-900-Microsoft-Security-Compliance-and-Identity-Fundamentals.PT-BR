<!---
---
Demonstração: Título: "Explorar configurações de usuário do Microsoft Entra ID" Roteiro de aprendizagem/módulo/unidade: "Roteiro de aprendizagem: descrever os recursos do Microsoft Entra; Módulo 1: descrever os tipos de função e identidade do Microsoft Entra ID; Unidade 3: descrever os tipos de identidade do Microsoft Entra"
---
--->

# Demonstração: configurações de usuário do Microsoft Entra ID

Essa demonstração é mapeada para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descreva as funcionalidades do Microsoft Entra.
- Módulo: descreva os tipos de função e identidade do Microsoft Entra ID.
- Unidade: descreva os tipos de identidades.

## Cenário da demonstração

Nesta demonstração, você acessará o Microsoft Entra ID e acompanhará as várias configurações de um usuário existente.

1. Abra o Microsoft Edge.

1. Na barra de endereços, insira **admin.microsoft.com** para acessar o Centro de administração do Microsoft 365.

1. Entre com suas credenciais de administrador.
    1. Na janela Entrar, insira **admin@WWLxZZZZZZ.onmicrosoft.com** (em que ZZZZZZ é a sua ID de locatário exclusiva fornecida pelo provedor de hospedagem do laboratório) e selecione **Avançar**.
    1. Insira a senha de administrador que deve ser fornecida pelo provedor de hospedagem do laboratório. Selecione **Entrar**.
    1. Quando solicitado a permanecer conectado, selecione **Sim**.

1. À esquerda no painel de navegação do Centro de administração do Microsoft 365, selecione **Mostrar todos**.

1. Em Centros de administração, selecione **Identidade** (talvez seja necessário rolar para baixo).  Uma nova página do navegador é aberta para a página de visão geral do Centro de administração do Microsoft Entra. Aqui você verá informações básicas sobre o seu locatário da Contoso. Se você rolar para baixo na janela principal, também verá informações sobre alertas, meu feed, destaques de recursos e muito mais.  
    1. Observação ao apresentador/instrutor: você também pode acessar o Centro de administração do Microsoft Entra diretamente acessando **[entra.microsoft.com](https://entra.microsoft.com)** .

1. No painel de navegação à esquerda, expanda **Usuários** e selecione **Todos os usuários**.  Na página de usuários, você pode ver opções de navegação adicionais e a lista de usuários. O seu locatário já está configurado com usuários.

1. Na lista de usuários, selecione **Adele Vence**.

1. Observe que, no painel de navegação esquerdo, a **Visão geral** é realçada em cinza claro.  Mostre/fale sobre as informações exibidas na página de visão geral.  Selecione a guia **Monitoramento** na parte superior da página, que mostra as entradas do usuário (nenhuma entrada será exibida, a menos que você tenha se conectado anteriormente como Adele Vance).  Em seguida, selecione **Propriedades** para ver todas as propriedades do objeto de usuário Adele Vance.

1. No painel de navegação esquerdo, selecione **Funções atribuídas**.  Este usuário não tem nenhuma função administrativa atribuída.  Na parte superior da página, selecione **+ Adicionar atribuições** e, na página de adicionar atribuições, expanda o campo de função Pesquisa em Selecionar função para ver uma listagem dos tipos de funções administrativas disponíveis.  Não adicione nada, apenas feche a página selecionando o **X** no canto superior direito da página.

1. No painel de navegação esquerdo, selecione **Grupos**.  Fale sobre o fato de que este usuário é membro de vários grupos.  Aqui, você pode falar sobre os tipos de grupos.  Para adicionar este usuário a outros grupos, selecione **+ Adicionar associações**.  Não adicione novos grupos, apenas fale sobre como é fácil adicionar um usuário aos grupos existentes. Feche a janela Selecionar grupos selecionando o **X** no canto superior direito da página.

1. No painel de navegação esquerdo selecione **Licenças**. Observe que este usuário recebeu licenças do Microsoft 365 E5 e licença do EMS.  Para adicionar uma licença, selecione **+ Atribuições** na parte superior da janela principal.  Mostre as licenças para este usuário. NÃO altere nada.  Feche esta janela selecionando o **X** no canto superior direito da página.

1. No painel de navegação à esquerda, selecione **Dispositivos**.  Nada aparece, mas você pode dizer que se este usuário tivesse dispositivos atribuídos, é aqui que apareceriam.

1. No painel de navegação esquerdo, selecione **Atribuições de função do Azure**.  Destacar que:
    1. Isso é diferente da guia de funções atribuídas mostrada anteriormente, pois a guia anterior é para controle de acesso baseado em função no Microsoft Entra.
    1. Embora nada esteja listado aqui, esta é a guia em que você seria capaz de exibir atribuições de função, atribuídas à Adele, para recursos do Azure. Por exemplo, se você criasse um Grupo de Recursos do Azure e atribuísse a Adele uma função específica, como proprietário ou colaborador do grupo de recursos, você veria essa função listada aqui. Isso faz parte do Azure RBAC (controle de acesso baseado em função do Azure). Essa atribuição de função é adicionada e gerenciada como parte desse recurso específico.

1. No painel de navegação esquerdo, selecione **Métodos de autenticação**.  Destaque a descrição que diz: 'Aqui, você pode definir os números de telefone e endereços de email que os usuários usam para realizar a autenticação multifator e redefinição de senha self-service de um usuário'. Se um usuário estiver configurado para a SSPR ou precisar usar a MFA e você, como administrador, preencher isso, esse usuário já estará registrado e não precisará passar pelas etapas de registro para a SSPR ou a MFA.  É comum que um usuário se registre em vez de um administrador precisar fazer isso.

1. Selecione o **X** no canto superior direito da página. Isso o leva de volta à lista de usuários.

1. Selecione o **X** no canto superior direito da página. Isso retorna você para a página principal do Centro de administração do Microsoft Entra.

1. Mantenha essa guia do navegador aberta; vamos usá-la na próxima demonstração.

### Revisão

Nesta demonstração, você mostrou as configurações de um usuário existente, incluindo os grupos aos quais o usuário pode ser atribuído, a disponibilidade de funções e a atribuição de licenças de usuário.
