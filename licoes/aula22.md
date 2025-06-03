### 📘 Registro de Aprendizado – Aula 22

**👤 Nome:** Gabriel Moura
**🎯 Tema da Aula:** Fazendo Requisições HTTP via Power Automate (Ações)

---

#### 📝 Resumo da Aula
> Exploramos como realizar chamadas de API utilizando um fluxo do Power Automate como "Ação" no Microsoft Copilot Studio (Copilot Studio). Diferentemente da requisição HTTP direta no Copilot Studio, o Power Automate oferece mais flexibilidade para cenários complexos (`como gerar tokens de autenticação`). Recriamos a funcionalidade de consulta de CEP, mas desta vez usando o conector HTTP premium do Power Automate. Configuramos o fluxo para receber o CEP como input, construir a URL da API, fazer a chamada `GET`, analisar a resposta `JSON` e retornar dados específicos (estado, cidade, endereço) para o agente. Integramos esse fluxo a um tópico no Copilot Studio, passando o CEP do usuário para o fluxo e exibindo os outputs retornados. Desabilitamos o tópico anterior de consulta de CEP para evitar conflitos e testamos a nova automação, verificando sua execução no Power Automate e o retorno dos dados no chat do agente.

---

#### 🔍 Conceitos ou Ferramentas Apresentadas
- **Ações (Actions) com Power Automate:** Reafirmação de que fluxos do Power Automate são utilizados como ações no Copilot Studio para realizar tarefas, incluindo chamadas de API (ver Aula 19).
- **Vantagens do Power Automate para APIs:** Oferece mais opções e etapas para cenários complexos de API (`ex: gerar token, múltiplos passos de autenticação ou processamento`) que `não são possíveis com a requisição HTTP direta no Copilot Studio`.
- **Conector HTTP (Premium):** Um conector no Power Automate que permite realizar requisições HTTP. É um conector `premium`, exigindo uma `licença Power Automate Premium`.
- **Gatilho "Executar um fluxo do Copilot Studio":** Usado novamente no fluxo do Power Automate para receber o input do CEP do agente (ver Aula 19).
- **Analisar JSON (Parse JSON):** Ação no Power Automate utilizada para interpretar a estrutura de uma resposta `JSON` recebida de uma API, permitindo acessar seus campos individualmente. Requer um `esquema JSON` (gerado a partir de dados de exemplo).
- **Esquema JSON (JSON Schema):** Uma representação formal da estrutura de um documento `JSON`, utilizada pela ação "Analisar JSON" para entender como extrair os dados.
- **Ação "Responder ao Copilot Studio":** Usada para retornar os dados processados (estado, cidade, endereço) do fluxo Power Automate de volta para o agente, definindo saídas com base nos campos do `JSON` analisado.
- **Outputs da Ação (no Power Automate):** Os dados que o fluxo envia de volta para o agente (estado, cidade, endereço), que se tornam variáveis no Copilot Studio.
- **Entrada no Tópico (Variável):** A variável do Copilot Studio que contém o CEP digitado pelo usuário, que é mapeada para o input do fluxo Power Automate.
- **Saídas da Ação (no Copilot Studio):** As saídas definidas no fluxo Power Automate aparecem como variáveis no Copilot Studio após adicionar a ação no tópico, permitindo usá-las (ex: em nós de mensagem).
- **Conector Premium:** Conectores no Power Automate marcados com um diamante, que exigem uma licença paga (Power Automate Premium ou licença que inclua esse direito). O conector HTTP é premium.
- **Gerenciar Permissões Run Only:** Reafirmação de que essa configuração é crucial para fluxos que interagem com recursos que exigem autenticação (ver Aula 20), embora no caso de um fluxo que *apenas* usa o conector HTTP (sem interagir com SharePoint/Excel), essa configuração de conexão específica pode não ser necessária da mesma forma, pois a autenticação da API é tratada *dentro* do fluxo.
- **Conflito de Tópicos:** Ter múltiplos tópicos com frases gatilho semelhantes pode causar comportamento inesperado no agente. Desabilitar tópicos duplicados evita esse conflito.

---

#### 💡 O que eu aprendi de mais importante
> 1.  Usar o Power Automate para chamadas de API oferece `maior flexibilidade e controle` do que o nó "Enviar solicitação HTTP" direto no Copilot Studio, sendo `ideal para APIs que requerem múltiplas etapas de autenticação, tratamento complexo de dados, ou que envolvam outros conectores`.
> 2.  O conector HTTP no Power Automate é `premium`, o que implica em `custos de licenciamento adicionais` (Power Automate Premium).
> 3.  A ação **"Analisar JSON"** no Power Automate é fundamental para extrair dados de respostas de API com estrutura `JSON`, tornando-os acessíveis como variáveis no fluxo.
> 4.  A integração entre Copilot Studio e Power Automate é fluida, com inputs do agente se tornando entradas do fluxo e outputs do fluxo se tornando variáveis no agente.
> 5.  É importante **gerenciar tópicos com gatilhos sobrepostos** para evitar que o agente se confunda e acione o tópico errado.

---

#### 🛠 Exercícios ou Atividades Práticas
- **Descrição breve do exercício ou atividade:** Crie um fluxo do Power Automate que realize uma consulta a uma API pública utilizando o conector HTTP premium. Integre este fluxo a um tópico no Copilot Studio e teste sua execução.

    **Pré-requisito:**
    *   Ter uma licença que inclua o uso de conectores premium do Power Automate (ex: Power Automate Premium).
    *   Ter um endpoint de API pública `GET` que retorne `JSON` (ex: Brasil API CEP).
    *   Ter um exemplo da resposta `JSON` dessa API.

    **Passos:**

    **Parte 1: Criar o Fluxo do Power Automate (Ação) com Conector HTTP**
    1.  No Microsoft Copilot Studio, navegar até a seção **Ações**.
    2.  Clicar em **"Adicionar uma ação"** e depois em **"Novo fluxo do Power Automate"**.
    3.  **Renomear** o fluxo (ex: `Consulta CEP HTTP PA`).
    4.  No gatilho **"Executar um fluxo do Copilot Studio"**:
        *   Clicar em **"Adicionar um input"**.
        *   Selecionar **"Texto"** e nomear o input como `CEP`.
    5.  Adicionar uma nova etapa (`+ Novo passo`): Buscar pelo conector **"HTTP"**.
    6.  Selecionar a ação **"HTTP"**.
    7.  Configurar a ação HTTP:
        *   Em "Método", selecionar **"GET"**.
        *   Em "URI", construir a URL concatenando o endpoint base com o input do gatilho `CEP` (ex: `https://brasilapi.com.br/api/cep/v1/@{triggerBody()['CEP']}`). A expressão para o input de texto do gatilho é `triggerBody()['NomeDoInput']`.
    8.  Adicionar uma nova etapa (`+ Novo passo`): Buscar pela ação **"Analisar JSON"** (Parse JSON).
    9.  Configurar a ação "Analisar JSON":
        *   Em "Conteúdo", selecionar o **`Corpo`** (`Body`) da etapa HTTP (usando conteúdo dinâmico).
        *   Em "Esquema", clicar em **"Usar conteúdo de exemplo para gerar esquema"**. Colar um exemplo real da resposta `JSON` da API de CEP e clicar em **"Concluído"**.
    10. No retorno **"Responder ao Copilot Studio"**:
        *   Adicionar saídas para os campos que você deseja retornar (ex: "Texto" para "Estado", "Cidade", "Endereco").
        *   Mapear as saídas para os campos extraídos da ação "Analisar JSON" (usando conteúdo dinâmico, ex: `Estado` -> `state`, `Cidade` -> `city`, `Endereco` -> `street` do conteúdo analisado).
    11. Clicar em **"Salvar"** no topo do designer do Power Automate.

    **Parte 2: Integrar o Fluxo no Tópico do Copilot Studio**
    1.  Voltar ao Microsoft Copilot Studio. O novo fluxo deve aparecer na lista de Ações (pode precisar de atualização).
    2.  (Opcional) Criar um **Novo Tópico em branco** para a consulta de CEP, ou editar o tópico anterior (Certifique-se de que não haja conflito de gatilhos com o tópico anterior). Se usar o tópico anterior, **desabilitar** o tópico que fazia a requisição HTTP direta (ver Aula 21).
    3.  Adicionar **Frases gatilho** para o tópico (ex: "Consultar CEP via automação").
    4.  Adicionar um nó `+` e selecionar **"Fazer uma pergunta"** para capturar o CEP, salvando em uma variável (ex: `varCEP`).
    5.  Adicionar um nó `+` e selecionar **"Adicionar uma ação"**.
        *   Selecionar o fluxo do Power Automate criado (`Consulta CEP HTTP PA`).
        *   Mapear o input do fluxo: Input `CEP` do fluxo com a variável `varCEP` do Copilot Studio.
        *   Note que as saídas definidas no fluxo ("Estado", "Cidade", "Endereco") aparecem como variáveis no Copilot Studio.
    6.  Adicionar um nó `+` e selecionar **"Enviar uma mensagem"**.
        *   Digitar a mensagem exibindo os resultados, usando as variáveis de saída do fluxo (ex: `Estado: {Estado}, Cidade: {Cidade}, Endereço: {Endereco}`).
    7.  Adicionar um nó `+` e selecionar **"Gerenciamento de tópico"** -> **"Encerrar o tópico atual"**.
    8.  Clicar em **"Salvar"**.

    **Parte 3: Testar a Automação e Verificar a Execução**
    1.  No painel de **Teste** do Copilot Studio, dar um **Reload**.
    2.  Digitar uma frase gatilho para acionar o novo tópico.
    3.  Quando o agente perguntar o CEP, digitar um **CEP válido**.
    4.  Observar a resposta do agente.
    5.  Navegar até o portal do Power Automate, ir em **"Meus fluxos"**, localizar o fluxo `Consulta CEP HTTP PA`.
    6.  Verificar o **Histórico de execuções**. Deve haver uma execução recente com status "Sucesso". Clicar nela para ver os detalhes (inputs, outputs, status de cada ação, incluindo a chamada HTTP e a Análise JSON).

- **Dificuldades encontradas ou insights obtidos:**
    - **Problema:** A sintaxe para referenciar o input do gatilho na URL da ação HTTP no Power Automate pode ser um pouco confusa inicialmente (`triggerBody()['NomeDoInput']`). **Insight:** Pratique com exemplos e use o assistente de conteúdo dinâmico.
    - **Insight:** Gerar e usar corretamente o esquema `JSON` na ação "Analisar JSON" é fundamental.
    - **Insight:** Mapear corretamente as saídas analisadas para as saídas do fluxo "Responder ao Copilot Studio" exige atenção.
    - **Insight:** Garantir que o tópico anterior (se existir) com gatilhos semelhantes está desabilitado para evitar confusão no teste.
    - **Insight:** O histórico de execução do fluxo no Power Automate é essencial para depurar problemas no fluxo em si.

---

#### 📌 Aplicações no Trabalho
> Usar o Power Automate para chamadas de API permite:
> - **Conectar o agente a sistemas complexos** que exigem autenticação multi-passo ou processamento de dados antes ou depois da chamada API.
> - **Utilizar qualquer um dos mais de 1000 conectores** disponíveis no Power Automate em conjunto com chamadas HTTP (ex: buscar dados de um SQL, processar e enviar para uma API).
> - **Realizar operações que modificam dados** (`POST`, `PUT`, `DELETE`) em APIs externas de forma mais robusta.
> - **Centralizar a lógica de integração** em fluxos do Power Automate, tornando o agente mais focado na conversa.

---

#### ❓ Dúvidas ou Pontos a Revisar
- Como usar o conector HTTP para chamadas `POST` e passar dados no corpo da requisição?
- Como realizar o tratamento de erros em chamadas HTTP no Power Automate (usando blocos Try/Catch/Finally ou configurações de "run after")?
- Como gerenciar autenticação de API mais complexa (`OAuth`, chaves em cabeçalhos/corpo) dentro do Power Automate?
- Quais são as diferenças e cenários ideais para usar a requisição HTTP direta no Copilot Studio versus o conector HTTP no Power Automate (ver Aula 21)?
- Qual é o licenciamento detalhado do conector HTTP premium?
---