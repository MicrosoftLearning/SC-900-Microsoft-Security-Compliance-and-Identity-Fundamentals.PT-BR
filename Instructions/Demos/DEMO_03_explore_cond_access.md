<a name="---"></a><!---
---
Demonstração: Título: 'Acesso condicional do Azure AD' Roteiro de aprendizagem/Módulo/Unidade: 'Roteiro de aprendizagem: descrever as funcionalidades do Azure AD (Active Directory), parte do Microsoft Entra; Módulo 3: descrever as funcionalidades de gerenciamento de acesso do Azure AD; Unidade 2: descrever o acesso condicional no Azure AD'
---
--->

# <a name="demo-azure-ad-conditional-access"></a>Demonstração: acesso condicional do Azure AD

Essa demonstração é mapeada para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: descrever as funcionalidades do Azure AD (Azure Active Directory), parte do Microsoft Entra
- Módulo: descrever as funcionalidades de gerenciamento de acesso do Azure AD
- Unidade: descrever o acesso condicional no Azure AD

## <a name="demo-scenario"></a>Cenário da demonstração

Nesta demonstração, você verá as várias opções disponíveis para uma política de acesso condicional.

1. Vá para a guia **Contoso – Microsoft Azure** aberta no seu navegador. Se você fechou a guia anteriormente, abra uma página do navegador e, na barra de endereços, insira portal.azure.com e selecione Azure Active Directory. Você deve estar conectado como administrador no portal do Azure; caso contrário, entre novamente.

1. No painel de navegação esquerdo, selecione **Segurança**.

1. No painel de navegação esquerdo, selecione **Acesso condicional**.

1. A tela Políticas de acesso condicional é exibida. Todas as políticas de acesso condicional existentes são listadas aqui. Para mostrar as configurações associadas ao acesso condicional, selecione **+ Nova política**.

1. No campo **Nome**, insira um nome para a política.

1. Observe que você tem várias opções em **Atribuições**.  Como as políticas de acesso condicional são como declarações se/então, as configurações de atribuições são como declarações “se”.
    1. **Usuários e grupos** — passe o mouse sobre o ícone de informações próximo a “Usuários e grupos” e destaque que é aqui que você define os usuários e grupos no diretório ao qual a política se aplica. Selecione **0 usuários e grupos selecionados**.  Agora você verá a opção Incluir ou Excluir usuários ou grupos. Selecione e destaque as configurações disponíveis para a guia **Incluir** e, em seguida, selecione e fale sobre as configurações disponíveis para a guia **Excluir**.
    1. **Ações ou aplicativos de nuvem** — passe o mouse sobre o ícone de informação próximo a “Ações ou aplicativos de nuvem” e destaque que é aqui que você define os aplicativos usados ou as ações executadas pelo usuário para a política de acesso condicional.  Selecione **Nenhum aplicativo de nuvem, ação ou contexto de autenticação selecionado**.
        1. Selecione a seta suspensa na caixa abaixo de onde está escrito **Selecionar a que esta política se aplica** e observe as opções.  Deixe a configuração padrão – Aplicativos de nuvem.
        1. Selecione e destaque as configurações disponíveis para a guia Incluir. Na guia **Incluir**, escolha **Selecionar aplicativos**.  Observe a janela que é aberta, em que você pode selecionar um aplicativo de uma lista.  Não selecione nada. Feche esta janela selecionando o **X** no canto superior direito da janela. Volte para escolher **Nenhum** para remover o erro.
        1. Depois, selecione e fale sobre as configurações disponíveis para a **guia Excluir**.  Mais uma vez, aqui você pode selecionar aplicativos específicos para excluir.
    1. **Condições** — passe o mouse sobre o ícone de informações próximo a “Condições” e destaque que isso define quando a política se aplicará. Selecione **0 condições selecionadas**. Fale sobre os “sinais” diferentes listados.   Selecione algumas opções, selecionando primeiro o ícone de informações para definir o que é e depois selecione **Não configurado** para o item específico para exibir as várias opções.
        1. **Risco do usuário** — um risco do usuário representa a probabilidade de que determinada identidade ou conta seja comprometida. Esses riscos são calculados offline usando as fontes de inteligência de ameaças internas e externas da Microsoft.
        1. **Risco de entrada** — um risco de entrada representa a probabilidade de uma determinada solicitação de autenticação não estar autorizada pelo proprietário da identidade. Alguns exemplos são credenciais com origem de endereço IP anônimo ou viagem atípica etc.
        1. **Plataforma de dispositivo** — plataforma na qual o usuário está entrando. Por exemplo, iOS.
        1. **Localização** — localização (determinada usando o intervalo de endereços IP) da qual o usuário está entrando
        1. **Aplicativos clientes** — software que o usuário está usando para acessar o aplicativo na nuvem. Por exemplo, Navegador
        1. **Filtrar por dispositivos** – Ao criar políticas de acesso condicional, os administradores podem direcionar ou excluir dispositivos específicos no ambiente. Os administradores podem direcionar dispositivos específicos usando os operadores e as propriedades com suporte para filtros de dispositivos e as outras condições de atribuição disponíveis nas suas políticas de acesso condicional.

1. **Controles de acesso** – voltando à analogia de que as políticas de acesso condicional são como declarações se/então, os controles de acesso são análogos à declaração “então”.
    1. **Concessão** — passe o mouse sobre o ícone de informações próximo a “Concessão” para ver a descrição.  Selecione **0 controles selecionados** para exibir as várias opções.  Fale sobre algumas delas.  Especificamente, destaque a opção **Exigir autenticação multifator** em Permitir Acesso e como isso pode ser usado para fornecer um controle granular sobre quando exigir a MFA.   Também destaque que você pode definir vários controles e exigir todos ou apenas um dos controles selecionados.
    1. **Sessão** — passe o mouse sobre o ícone de informações próximo a “Sessão” para ver a descrição.  Destaque que os controles de sessão permitem uma experiência limitada em um aplicativo de nuvem.  Por exemplo, o usuário pode conseguir acessar o aplicativo de nuvem, mas será impedido de baixar qualquer conteúdo ou imprimi-lo, por exemplo.  Este é um tópico mais complexo, portanto, mantenha-o simples.

1. Depois de configurar uma política, você pode habilitá-la selecionando **Ativado**. Depois, pressione o botão **Criar** para criar uma política.

1. Selecione o **X** no canto superior direito da página para fechar a política e selecione Microsoft Azure na barra azul na parte superior da página para voltar à home page do portal do Azure.

1. Deixe esta página do navegador aberta para a próxima demonstração.

### <a name="review"></a>Revisão

Nesta demonstração, você mostrou as várias opções disponíveis para uma política de acesso condicional.
