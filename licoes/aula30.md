### 📘 Registro de Aprendizado – Aula 30

**👤 Nome:** Gabriel Moura
**🎯 Tema da Aula:** Agentes Autônomos (Autonomous Agents) no Microsoft Copilot Studio

---

#### 📝 Resumo da Aula
> Nesta aula, introduzimos o conceito de Agentes Autônomos no Microsoft Copilot Studio (Copilot Studio), que representa uma mudança substancial na forma de criar automações. O foco principal recaiu sobre a combinação de **instruções claras**, **ações bem elaboradas** e **gatilhos bem definidos**. Demonstramos a criação de um agente de Helpdesk, habilitando a orquestração de agentes autônomos (recurso em `versão preliminar`). Criamos um fluxo do Power Automate (Ação) para registrar chamados em uma lista do SharePoint. Em seguida, configuramos um gatilho de Copilot Studio (`SharePoint - Quando um item é criado`) para reagir à criação do chamado e uma Ação (também do Copilot Studio) para enviar um e-mail de confirmação ao usuário. O teste validou como o agente utiliza a inteligência artificial para orquestrar essas ações de forma autônoma, solicitando os inputs necessários e até formatando e-mails dinamicamente, sem a necessidade de um tópico de conversa explícito para cada automação.

---

#### 🔍 Conceitos ou Ferramentas Apresentadas
- **Agentes Autônomos (Autonomous Agents):** Um paradigma de desenvolvimento de agentes no Microsoft Copilot Studio que permite à inteligência artificial do agente tomar decisões sobre quando executar certas automações ou fluxos de trabalho, baseando-se em instruções em linguagem natural, em vez de depender de tópicos de conversa explicitamente mapeados para cada ação.
- **Orquestração (Orchestration):** A capacidade do agente autônomo de coordenar e encadear diferentes ações e fluxos de trabalho para cumprir uma intenção do usuário, mesmo que não haja um tópico passo a passo definido. Essa funcionalidade precisa ser habilitada nas configurações do agente.
- **Instruções Claras:** Descrições detalhadas fornecidas ao agente sobre seu propósito e sobre quando e como executar determinadas ações. São fundamentais para a IA do agente autônomo.
- **Ações Bem Elaboradas:** Fluxos do Power Automate ou ações nativas do Copilot Studio que são robustas e eficientes, com inputs e outputs bem definidos.
- **Gatilhos (Triggers):** Eventos que iniciam um fluxo de trabalho ou uma resposta do agente. No contexto de agentes autônomos, um gatilho pode ser uma condição específica em um sistema externo (ex: item criado no SharePoint) que o agente monitora.
- **Lista do SharePoint:** Um repositório de dados dentro do SharePoint, utilizado na aula para registrar os chamados do Helpdesk (ver Aula 8).
- **`Power Automate (Fluxo)`:** Ferramenta da Microsoft Power Platform para criar automações, utilizada para interagir com serviços externos como SharePoint e Outlook (ver Aula 2, Aula 19).
- **Ação "Registra um novo chamado no Helpdesk":** Um fluxo do Power Automate configurado para receber inputs (item, problema) do Copilot Studio e criar um item em uma lista do SharePoint.
    - **Gatilho `Executar um fluxo do Copilot Studio`:** O ponto de entrada de um fluxo do Power Automate chamado pelo Copilot Studio (ver Aula 19).
    - **Ação `SharePoint - Criar item`:** Uma ação do conector SharePoint no Power Automate para adicionar uma nova entrada a uma lista.
- **Gatilho de Copilot Studio (`SharePoint - Quando um item é criado`):** Um gatilho configurado diretamente no Copilot Studio que monitora a criação de novos itens em uma lista do SharePoint, permitindo que o agente reaja a esse evento.
- **Ação de Copilot Studio (`Outlook - Enviar um e-mail`):** Uma ação configurada diretamente no Copilot Studio para enviar uma mensagem de e-mail, sem a necessidade de abrir o designer do Power Automate.
    - **Autenticação de Ação:** Ao configurar ações, pode-se escolher a autenticação (`Usuário` ou `Autor`), definindo quem será o remetente da ação (ver Aula 20).
- **Versão Preliminar (Preview):** Indica que uma funcionalidade ainda está em desenvolvimento e pode sofrer alterações ou não estar disponível em todos os ambientes. Os agentes autônomos foram anunciados recentemente (março de 2025 na época da aula).
- **Ajuste Fino (Refinamento de Instruções):** Processo contínuo de aprimoramento das instruções e gatilhos para que a IA do agente interprete e execute as ações de forma mais precisa e eficaz.

---

#### 💡 O que eu aprendi de mais importante
> 1.  Os **Agentes Autônomos** representam uma **mudança de paradigma** no desenvolvimento, permitindo que o agente de IA orquestre e execute ações sem a necessidade de definir tópicos passo a passo para cada automação.
> 2.  O sucesso dos agentes autônomos baseia-se em **três pilares**: `instruções claras`, `ações (fluxos) bem elaboradas` e `gatilhos bem definidos` para o agente saber *o que* fazer e *quando*.
> 3.  É possível criar e integrar **fluxos do Power Automate** e **ações nativas do Copilot Studio** para que o agente autônomo interaja com sistemas externos (SharePoint, Outlook).
> 4.  O agente pode **solicitar inputs** ao usuário quando necessário para completar uma ação e, de forma impressionante, **formatar respostas e e-mails dinamicamente**, mesmo recebendo apenas variáveis.

---

#### 🛠 Exercícios ou Atividades Práticas
- **Descrição breve do exercício ou atividade:** Criar um agente de Helpdesk com a funcionalidade de Agentes Autônomos, que permite abrir chamados em uma lista do SharePoint e enviar confirmações por e-mail, tudo orquestrado pela IA do agente.

    **Pré-requisito:**
    *   Ter uma conta de Helpdesk no SharePoint (site Copilot Studio) com uma lista chamada "Lista Helpdesk" e colunas "Item" e "Problema".

    **Passos:**

    **Parte 1: Criar o Agente de Helpdesk e Habilitar Orquestração**
    1.  No Microsoft Copilot Studio, clicar em **"Criar"** -> **"Novo Agente"**.
    2.  Definir o nome (ex: "Agente Helpdesk").
    3.  Na seção "Instruções", descrever a função: "Você é um agente que ajuda os funcionários a abrir chamados no helpdesk da empresa."
    4.  Criar o agente.
    5.  Após a criação, navegar até **"Configurações"** -> **"Orquestração"** e **habilitar** a funcionalidade de orquestração (se não estiver ativa por padrão).

    **Parte 2: Criar o Fluxo Power Automate para Registrar Chamados**
    1.  No Copilot Studio, navegar até **"Ações"** (no menu lateral).
    2.  Clicar em **"Adicionar uma ação"** e depois em **"Novo fluxo do Power Automate"**.
    3.  **Renomear** o fluxo (ex: `Registra Novo Chamado Helpdesk`).
    4.  No gatilho **"Executar um fluxo do Copilot Studio"**:
        *   Adicionar um input **"Texto"** chamado `Item`.
        *   Adicionar um input **"Texto"** chamado `Problema`.
    5.  Adicionar uma etapa **"SharePoint - Criar item"**:
        *   Configurar o `Endereço do Site` (ex: seu site Copilot Studio).
        *   Configurar o `Nome da Lista` (ex: "Lista Helpdesk").
        *   Mapear o campo `Item` para o input `Item` do gatilho.
        *   Mapear o campo `Problema` para o input `Problema` do gatilho.
    6.  No retorno **"Responder ao Copilot Studio"**:
        *   Adicionar uma saída **"Texto"** chamada `MensagemSucesso`.
        *   Definir o valor como `"Seu chamado foi registrado com sucesso!"`.
    7.  **Salvar** o fluxo no Power Automate.

    **Parte 3: Adicionar o Fluxo como Ação Disparada pelo Agente**
    1.  Voltar ao Copilot Studio, na seção **"Ações"**.
    2.  Clicar em **"Adicionar ação"**.
    3.  Selecionar o fluxo recém-criado (`Registra Novo Chamado Helpdesk`).
    4.  Manter o nome padrão ou renomear.
    5.  No campo **"Descrição para o Agente"** (instruções), digitar: "Registra um novo chamado no helpdesk e grava as informações na lista do SharePoint chamada Lista Helpdesk."
    6.  Clicar em **"Adicionar ação"**.

    **Parte 4: Criar o Gatilho de Copilot Studio (SharePoint)**
    1.  No Copilot Studio, navegar até **"Gatilhos"** (no menu lateral).
    2.  Clicar em **"Adicionar gatilho"**.
    3.  Selecionar **"Quando um item é criado"**.
    4.  **Renomear** o gatilho (ex: `Item Criado no Helpdesk`).
    5.  No campo `Endereço do Site`, informar seu site Copilot Studio.
    6.  No campo `Nome da Lista`, informar "Lista Helpdesk".
    7.  Clicar em **"Criar gatilho"**.

    **Parte 5: Criar a Ação de Copilot Studio (Enviar E-mail)**
    1.  No Copilot Studio, navegar até **"Ações"**.
    2.  Clicar em **"Adicionar ação"**.
    3.  Na janela de busca, digitar "Enviar um e-mail" e selecionar a ação **"Office 365 Outlook - Enviar um e-mail (V2)"**.
    4.  No campo **"Descrição para o Agente"** (instruções), digitar: "Envia um e-mail de confirmação ao usuário toda vez que um item novo for criado na lista do SharePoint chamada Lista Helpdesk."
    5.  Para `Autenticação`, escolher **"Usuário"**.
    6.  Verificar os inputs (Para, Assunto, Corpo).
    7.  Para `Configurações de resposta`, escolher **"Responder com uma mensagem"**.
    8.  Clicar em **"Adicionar ação"**.

    **Parte 6: Ajustar o Gatilho (para enviar e-mail)**
    1.  Navegar novamente até **"Gatilhos"**.
    2.  Clicar no gatilho `Item Criado no Helpdesk`.
    3.  No campo "Ação", onde se escolhe o que fazer quando o gatilho é ativado, selecionar a ação **"Office 365 Outlook - Enviar um e-mail (V2)"**.
    4.  Mapear os inputs do e-mail usando os dados do item criado no SharePoint (conteúdo dinâmico do gatilho `Item Criado no Helpdesk`):
        *   `Para`: Usar a variável do usuário (`User.Email` ou outra forma de obter o e-mail do usuário logado na conversa).
        *   `Assunto`: (ex: `"Chamado Registrado: " & ItemCriadoNoHelpdesk.Item`)
        *   `Corpo`: (ex: `"Olá " & User.DisplayName & "! Seu chamado para o equipamento " & ItemCriadoNoHelpdesk.Item & " com problema: " & ItemCriadoNoHelpdesk.Problema & " foi registrado com sucesso. Atenciosamente, Equipe Helpdesk."`)
    5.  **Salvar** o gatilho.

    **Parte 7: Testar o Agente Autônomo**
    1.  No painel de **Teste**, dar um **Reload**.
    2.  Digitar uma frase como "Abrir um chamado" ou "Tenho um problema".
    3.  Observar como o agente solicita o `Item` (ex: "notebook") e o `Problema` (ex: "Windows não inicia").
    4.  Na primeira interação, autorizar as conexões de SharePoint e Outlook quando solicitado.
    5.  Após a confirmação do agente, verificar:
        *   A lista "Lista Helpdesk" no SharePoint para confirmar o registro do item.
        *   Sua caixa de entrada de e-mail para a confirmação de que um e-mail foi enviado.

- **Dificuldades encontradas ou insights obtidos:**
    - **Problema:** A ferramenta pode apresentar bugs temporários ou inconsistências, como fluxos que não aparecem na lista de ações inicialmente. **Insight:** Recriar o fluxo diretamente a partir do menu "Ações" do Copilot Studio (`+ Nova ação` -> `Novo fluxo do Power Automate`) garante o vínculo correto.
    - **Insight:** A fase de teste inicial exige autorização de conexões para cada serviço, o que é um comportamento esperado.
    - **Insight:** O ajuste fino das "Instruções" para as ações é crucial para que a IA do agente entenda corretamente quando invocar cada automação.
    - **Insight:** É impressionante a capacidade do agente em compor automaticamente e-mails personalizados a partir das variáveis do fluxo, mesmo sem instruções explícitas de formatação no Copilot Studio.

---

#### 📌 Aplicações no Trabalho
> Os Agentes Autônomos são um recurso poderoso para:
> - **Automação de Processos de Negócio:** Permitir que os usuários solicitem ou iniciem processos complexos (ex: abertura de chamados de TI, solicitação de RH, registro de incidentes) de forma totalmente natural e conversacional, com o agente cuidando da orquestração.
> - **Redução da Carga de Trabalho:** Minimizar a necessidade de intervenção humana em tarefas repetitivas, ao mesmo tempo em que oferece uma interface amigável.
> - **Self-Service Aprimorado:** Capacitar os usuários a resolverem suas próprias necessidades sem a necessidade de navegar por menus complexos ou interfaces tradicionais.
> - **Fluxos de Trabalho Dinâmicos:** O agente pode se adaptar a diferentes intenções do usuário e executar as ações apropriadas, tornando a interação mais fluida e eficiente.

---

#### ❓ Dúvidas ou Pontos a Revisar
- Quais são os limites na quantidade de Ações e Gatilhos que podem ser configurados para Agentes Autônomos?
- Como o agente autônomo lida com a ambiguidade quando múltiplas ações ou gatilhos podem ser acionados por uma mesma intenção do usuário?
- Quais são as melhores práticas para refinar as "Instruções" para as ações, a fim de otimizar a precisão da IA?
- Como depurar problemas de execução em Agentes Autônomos quando a orquestração não ocorre como esperado?
- Há diferenças de licenciamento ou desempenho entre as ações criadas via Power Automate e as ações nativas do Copilot Studio (como o envio de e-mail)?
---