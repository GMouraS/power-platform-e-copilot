### 📘 Registro de Aprendizado – Aula 29

**👤 Nome:** Gabriel Moura
**🎯 Tema da Aula:** Ações Disparadas pelo Agente (Agent-Triggered Actions) no Microsoft Copilot Studio

---

#### 📝 Resumo da Aula
> Nesta aula, exploramos um recurso avançado do Microsoft Copilot Studio (Copilot Studio): a capacidade de um agente chamar autonomamente uma automação (Ação do Power Automate) **sem a necessidade de um tópico dedicado** para essa finalidade. Demonstramos como adicionar um fluxo Power Automate existente como uma "Ação disparada pelo agente", fornecendo instruções em linguagem natural para guiar a inteligência artificial do agente sobre quando executá-la. Testamos a funcionalidade com o fluxo de registro de reclamações (ver Aula 19), observando o agente solicitar inputs, executar a automação e confirmar o registro no SharePoint. Também adicionamos o fluxo de consulta de CEP (ver Aula 21, Aula 22) e verificamos como o agente pode formatar as respostas dinamicamente, mesmo recebendo apenas as variáveis.

---

#### 🔍 Conceitos ou Ferramentas Apresentadas
- **Ações Disparadas pelo Agente (Agent-Triggered Actions):** Uma funcionalidade (em versão preliminar) do Microsoft Copilot Studio que permite que o agente invoque um fluxo do Power Automate de forma autônoma, com base na intenção do usuário e em instruções fornecidas, sem a necessidade de um tópico de conversa pré-definido para aquele fluxo.
- **`Power Automate (Fluxo)`:** Ferramenta da Microsoft Power Platform para criar automações, referida como "Ação" quando integrada ao Copilot Studio (ver Aula 2, Aula 19).
- **Adicionar Fluxo como Ação Disparada pelo Agente:** Processo de vincular um fluxo Power Automate a esta funcionalidade. Seleciona-se o fluxo e fornece-se uma descrição em linguagem natural para o agente.
- **Instruções (para Ação Disparada pelo Agente):** Descrição em texto livre que "ensina" o agente quando uma determinada automação deve ser executada. A IA do Copilot Studio usa essa instrução para deduzir a intenção do usuário.
- **Inputs da Ação:** Parâmetros que o fluxo Power Automate espera receber do agente (ex: nome do usuário, descrição da reclamação, CEP). O agente se encarrega de solicitá-los ao usuário se necessário.
- **Outputs da Ação:** Retornos que o fluxo Power Automate envia de volta ao agente após a execução (ex: mensagem de sucesso, dados do CEP).
- **`user.displayName`:** Variável de sistema do Copilot Studio que fornece o nome de exibição do usuário logado, útil para preencher inputs de automações (ver Aula 14).
- **Mapa de Atividades:** Ferramenta de depuração que visualiza o fluxo de interação do agente, incluindo quando uma Ação Disparada pelo Agente é invocada (ver Aula 16).
- **Implicit Response Formatting:** A capacidade do Copilot Studio de formatar uma resposta inteligivelmente para o usuário mesmo quando o fluxo do Power Automate retorna apenas as variáveis de saída, sem uma mensagem formatada prévia.

---

#### 💡 O que eu aprendi de mais importante
> 1.  O Microsoft Copilot Studio pode **autonomamente acionar automações** do Power Automate (Ações) baseadas em instruções em linguagem natural, **eliminando a necessidade de criar tópicos específicos** para cada automação.
> 2.  Essa funcionalidade aproveita a inteligência artificial do agente para **deduzir a intenção do usuário** e invocar a ação correta, tornando o agente mais flexível e adaptável.
> 3.  O agente é capaz de **gerenciar os inputs necessários** para a automação, solicitando as informações ao usuário quando ausentes.
> 4.  A resposta do agente pode ser **automaticamente formatada** a partir das variáveis de saída do fluxo, o que demonstra a capacidade de geração de linguagem natural do Copilot Studio.

---

#### 🛠 Exercícios ou Atividades Práticas
- **Descrição breve do exercício ou atividade:** Adicionar fluxos do Power Automate existentes como "Ações Disparadas pelo Agente" e testar sua invocação autônoma.

    **Pré-requisito:**
    *   Ter o fluxo `Registrar Reclamacao Copilot` (ver Aula 19).
    *   Ter o fluxo `Consulta CEP HTTP PA` (ou a requisição HTTP direta da Aula 21).

    **Passos:**

    **Parte 1: Adicionar o Fluxo de Registro de Reclamações como Ação Disparada pelo Agente**
    1.  No Microsoft Copilot Studio, navegar até a seção **Ações** (no menu lateral).
    2.  Clicar em **"Adicionar ação"**.
    3.  Na janela pop-up, selecionar o fluxo `Registrar Reclamacao Copilot`.
    4.  Dar um **Nome** para a ação (ex: "Registrar Reclamação").
    5.  No campo **"Instruções"**, digitar a descrição para o agente sobre quando usar esta ação (ex: "Toda vez que o usuário desejar relatar uma reclamação").
    6.  Verificar os inputs esperados (`NomeUsuario`, `DescricaoReclamacao`).
    7.  Clicar em **"Adicionar ação"**.
    8.  Aguardar alguns segundos para que a ação seja adicionada.

    **Parte 2: Testar a Ação de Registro de Reclamações**
    1.  No painel de **Teste** do Copilot Studio, dar um **Reload**.
    2.  Digitar uma frase que corresponda à instrução fornecida (ex: "Eu gostaria de fazer uma reclamação").
    3.  Observar como o agente reconhece a intenção e solicita os inputs (primeiro o nome, depois a reclamação).
    4.  Fornecer o nome (ex: "Pedro Paulo") e a reclamação (ex: "A comida estava fria demais").
    5.  Verificar a resposta do agente (deve ser a mensagem de sucesso do fluxo) e, opcionalmente, verificar a planilha Excel no SharePoint para confirmar o registro.

    **Parte 3: Adicionar o Fluxo de Consulta de CEP como Ação Disparada pelo Agente**
    1.  No Microsoft Copilot Studio, navegar novamente até a seção **Ações**.
    2.  Clicar em **"Adicionar ação"**.
    3.  Na janela pop-up, selecionar o fluxo `Consulta CEP HTTP PA` (ou o tópico de requisição HTTP direta).
    4.  Dar um **Nome** para a ação (ex: "Consultar Endereço por CEP").
    5.  No campo **"Instruções"**, digitar (ex: "Toda vez que o usuário desejar consultar um CEP e correspondência de endereço").
    6.  Verificar os inputs esperados (`CEP`).
    7.  Clicar em **"Adicionar ação"**.

    **Parte 4: Testar a Ação de Consulta de CEP**
    1.  No painel de **Teste** do Copilot Studio, dar um **Reload**.
    2.  Digitar uma frase que acione a nova ação (ex: "Quero consultar um CEP").
    3.  Observar o agente solicitar o CEP.
    4.  Inserir um CEP válido (ex: `07060101`).
    5.  Verificar como o agente processa a solicitação e exibe as informações de endereço. Note como ele pode formatar a resposta, mesmo que o fluxo Power Automate apenas retorne as variáveis.

- **Dificuldades encontradas ou insights obtidos:**
    - **Problema:** A IA do agente pode inicialmente não interpretar corretamente as instruções ou solicitar os inputs em ordem inesperada. **Insight:** Aumentar a clareza e concisão das instruções pode melhorar o desempenho. O teste interativo é fundamental para refinar o comportamento.
    - **Insight:** É impressionante a capacidade da IA em deduzir a intenção e chamar a ação sem um tópico explícito.
    - **Insight:** O agente pode compor respostas de forma inteligente mesmo quando recebe apenas variáveis de saída de uma automação.
    - **Insight:** Esta funcionalidade é um "supra sumo" para desenvolvedores, pois permite focar mais na lógica da automação e menos na criação de tópicos de conversa repetitivos.

---

#### 📌 Aplicações no Trabalho
> As Ações Disparadas pelo Agente são extremamente poderosas para o ambiente de trabalho, permitindo:
> - **Automação Inteligente:** O agente pode iniciar processos de negócio complexos (`registros`, `consultas`, `envio de notificações`) sem que o usuário precise seguir um menu ou tópico pré-definido.
> - **Redução da Complexidade do Agente:** Diminui a necessidade de criar e manter muitos tópicos, tornando o design do agente mais enxuto e escalável.
> - **Experiência de Usuário Aprimorada:** O usuário pode expressar sua intenção em linguagem natural e o agente age proativamente, tornando a interação mais fluida e eficiente.
> - **Flexibilidade e Adaptação:** O agente se torna mais adaptável a diferentes formas de expressar uma mesma necessidade, pois sua IA pode inferir a automação correta.

---

#### ❓ Dúvidas ou Pontos a Revisar
- Quais são os limites na quantidade de Ações Disparadas pelo Agente que podem ser configuradas?
- Como o agente lida com a ambiguidade quando uma intenção do usuário pode corresponder a múltiplas Ações Disparadas pelo Agente ou a um tópico convencional?
- Quais são as melhores práticas para escrever instruções eficazes para as Ações Disparadas pelo Agente?
- Como depurar problemas de execução de Ações Disparadas pelo Agente que falham após o agente ter solicitado todos os inputs?
- Há diferenças de licenciamento ou desempenho entre fluxos chamados via tópico tradicional e fluxos chamados como Ações Disparadas pelo Agente?
---