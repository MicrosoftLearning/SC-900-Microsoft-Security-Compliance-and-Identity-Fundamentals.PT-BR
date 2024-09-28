<!---
---
Demonstração: Título: "Acesso condicional do Azure AD" Roteiro de aprendizagem/módulo/unidade: "Roteiro de aprendizagem: descrever as funcionalidades do Microsoft Entra; Módulo 3: descrever as funcionalidades de gerenciamento de acesso do Microsoft Entra ID; Unidade 2: descrever o acesso condicional"
---
--->

# Demonstração: acesso condicional do Microsoft Entra

Essa demonstração é mapeada para o seguinte conteúdo do Learn:

- Roteiro de aprendizagem: Descrever as funcionalidades do Microsoft Entra
- Módulo: descrever as funcionalidades de gerenciamento de acesso do Microsoft Entra ID
- Unidade: Descrever o acesso condicional

## Cenário de demonstração

Nesta demonstração, você verá as várias opções disponíveis para uma política de acesso condicional.

1. Volte para a guia aberta do navegador intitulada "Página Inicial-Centro de administração do Microsoft Entra".  Se você fechou anteriormente essa guia do navegador, abra o Microsoft Edge e faça logon em **[entra.microsoft.com](https://entra.microsoft.com)** com suas credenciais de administrador do Microsoft 365.

1. No painel de navegação esquerdo, expanda **Proteção** e selecione **Acesso condicional**.

1. A página de visão geral do acesso condicional é exibida.  Aqui você verá informações sobre o resumo da política, as novidades e os alertas gerais.  No painel de navegação esquerdo da janela Acesso Condicional, selecione **Políticas**.

1. A tela Políticas de acesso condicional é exibida. Todas as políticas de acesso condicional existentes são listadas aqui. Para mostrar as configurações associadas ao acesso condicional, selecione **+ Nova política**.

1. No campo **Nome**, insira um nome para a política.

1. Observe que você tem várias opções em **Atribuições**.  Como as políticas de acesso condicional são como instruções if/then, as configurações de atribuições são como as instruções "if".
    1. **Usuários** – passe o mouse sobre o ícone de informações próximo a "Usuários" e destaque que é aqui que você as identidades no diretório ao qual a política se aplica, incluindo usuários, grupos e entidades de serviço. Selecione **0 usuários e grupos selecionados**.  Agora você verá a opção Incluir ou Excluir usuários ou grupos. Selecione e ressalte as configurações disponíveis para a guia **Incluir** e, em seguida, selecione e fale com as configurações disponíveis para a guia **Excluir**.
    1. **Recursos de destino** – selecione **Recursos de destino**.  Aqui você controla o acesso com base em todo ou parte do tráfego de acesso à rede, aplicativos de nuvem ou ações.  Expanda o campo abaixo de onde diz para selecionar ao que essa política se aplica.  Aqui, você pode selecionar se a política se aplica a aplicativos de nuvem, ações do usuário ou contexto de autenticação.  
        1. Selecione **Aplicativos de nuvem** e, em seguida, na guia Incluir, selecione a opção **Selecionar aplicativos** e, em seguida, abaixo de onde diz **Selecionar**, selecione **Nenhum**, e uma janela será aberta para selecionar um ou mais dos aplicativos para os quais a política será aplicada.
        1. Feche a janela Selecionar aplicativos de nuvem selecionando o **X** no canto superior direito da janela.
        1. Como o tempo permite, você pode optar por percorrer as outras opções (ações do usuário e contexto de autenticação) para ver as opções de configuração para cada uma.
    1. **Rede** – passe o mouse sobre o ícone de informações ao lado de onde está escrito "Rede".  Enfatize que os locais de rede são determinados pelo intervalo de endereços IP ou pelas coordenadas de GPS das quais o usuário está entrando.  Selecione **Não configurado** para ver as opções disponíveis.
    1. **Condições** – passe o mouse sobre o ícone de informações próximo a "Condições" e destaque que isso define condições que definem quando a política será aplicada. Por exemplo, "local. Selecione **0 condição selecionada**. Fale com os diferentes "sinais" listados.   Selecione algumas das opções selecionando primeiro o ícone de informações para definir o que é e, em seguida, selecionando **Não configurado** para o item específico para mostrar as várias opções.
        1. **Risco do usuário** — um risco do usuário representa a probabilidade de que determinada identidade ou conta seja comprometida. Esses riscos são calculados offline usando as fontes de inteligência de ameaças internas e externas da Microsoft.
        1. **Risco de entrada** — um risco de entrada representa a probabilidade de uma determinada solicitação de autenticação não estar autorizada pelo proprietário da identidade. Exemplos podem incluir se o logon for de um endereço IP anônimo ou viagem atípica, etc.
        1. **Risco interno** – o risco interno, configurado na proteção adaptativa, avalia o risco com base nas atividades arriscadas relacionadas a dados de um usuário.
        1. **Plataforma de dispositivo** — plataforma na qual o usuário está entrando. Por exemplo, "iOS".
        1. **Localização** — localização (determinada usando o intervalo de endereços IP) da qual o usuário está entrando
        1. **Aplicativos clientes** — software que o usuário está usando para acessar o aplicativo na nuvem. Por exemplo, "navegador"
        1. **Filtrar por dispositivos** – Ao criar políticas de acesso condicional, os administradores podem direcionar ou excluir dispositivos específicos no ambiente. Os administradores podem direcionar dispositivos específicos usando os operadores e as propriedades com suporte para filtros de dispositivos e as outras condições de atribuição disponíveis nas suas políticas de acesso condicional.

1. **Controles de acesso** – voltando à analogia de que as políticas de acesso condicional são como instruções if/then, os controles de acesso são análogos à instrução "then".
    1. **Concessão** — passe o mouse sobre o ícone de informações próximo a “Concessão” para ver a descrição.  Selecione **0 controles selecionados** para mostrar as diferentes opções.  Fale com alguns desses.  Especificamente, destaque a opção **Exigir autenticação multifator** em Permitir Acesso e como isso pode ser usado para fornecer um controle granular sobre quando exigir a MFA.   Enfatize também que você pode definir vários controles e exigir todos ou apenas um dos controles selecionados.
    1. **Sessão** — passe o mouse sobre o ícone de informações próximo a “Sessão” para ver a descrição.  Ressalte que os controles de sessão permitem uma experiência limitada dentro de um aplicativo na nuvem.  Por exemplo, o usuário pode conseguir acessar o aplicativo de nuvem, mas será impedido de baixar qualquer conteúdo ou imprimi-lo, por exemplo.  Este é um tópico mais complexo, então mantenha-o o mais simples possível.

1. Depois que uma política for configurada, você poderá habilitá-la selecionando **Ativado** e pressionando o botão **Criar** para criar uma política.

1. Selecione o **X** no canto superior direito da página para fechar a política.

1. Feche as guias do navegador abertas.

### Revisão

Nesta demonstração, você mostrou as várias opções disponíveis para uma política de acesso condicional.
