### 📘 Registro de Aprendizado – Aula 12

**👤 Nome:** Gabriel Moura
**🎯 Tema da Aula:** Estrutura e Criação de Tópicos no Copilot Studio

---

#### 📝 Resumo da Aula
> Exploramos os Tópicos, considerados o "motor" dos agentes no Copilot Studio. Aprendemos sobre os tipos de tópicos (Personalizados criados com o agente, de Sistema e Convencionais) e como gerenciá-los (habilitar/desabilitar, copiar, excluir). Focamos na criação de um novo tópico em branco, explorando o designer visual. Configuramos os gatilhos (frases) que disparam o tópico, notando a capacidade de IA de entender similaridades e a recomendação de 5 a 10 frases. Adicionamos nós básicos ao fluxo do tópico (enviar mensagem, fazer pergunta, adicionar condição), utilizamos variáveis para armazenar respostas do usuário e introduzimos o uso de funções Power FX. Testamos o tópico, mostrando como ele é acionado por frases gatilho e como a lógica condicional funciona.

---

#### 🔍 Conceitos ou Ferramentas Apresentadas
- **Tópicos:** Blocos de construção principais de um agente, representando fluxos de conversa ou regras de negócio.
- **Tipos de Tópicos:**
    - **Personalizados:** Criados automaticamente com o agente (Saudação, Obrigado, etc.) ou criados manualmente pelo usuário.
    - **Sistema:** Tópicos padrão essenciais (Início, Fim da Conversa, Escalonar, Fallback, Erro) que não são recomendados para grandes customizações.
    - **Convencionais:** Tópicos customizáveis criados pelo usuário ou a partir de modelos.
- **Status do Tópico:** Habilitado/Desabilitado (permite ativar ou desativar um tópico sem excluí-lo).
- **Gatilho (Trigger):** O evento ou as frases que fazem com que um tópico seja acionado. Pode ser baseado em Frases, Mensagem recebida, Evento, Atividade, etc.
- **Frases Gatilho:** Frases de exemplo que ensinam o agente a reconhecer a intenção do usuário e disparar um tópico. Recomenda-se 5 a 10 frases curtas para o agente começar a aprender a similaridade.
- **Input em Massa (Frases Gatilho):** Possibilidade de adicionar ou substituir frases gatilho de um arquivo `.txt`.
- **Incluir em Várias Correspondências:** Configuração avançada de gatilho que determina se o tópico deve ser sugerido ao usuário quando sua pergunta corresponder a múltiplos tópicos.
- **Designer Visual de Tópicos:** Interface gráfica para construir o fluxo de um tópico adicionando e conectando "nós" (ações ou etapas da conversa).
- **Nós (Nodes):** Etapas individuais em um tópico. Tipos de nós explorados:
    - **Enviar uma mensagem:** Fazer o agente enviar um texto para o usuário.
    - **Fazer uma pergunta:** Fazer uma pergunta ao usuário e capturar a resposta.
    - **Adicionar uma condição (IF/Else):** Criar ramificações lógicas no fluxo baseadas em variáveis ou outras condições.
    - **Gerenciamento de variáveis:** Definir, analisar ou limpar o valor de variáveis.
    - **Gerenciamento de Tópico:** Redirecionar para outro tópico, encerrar tópico, etc.
    - **Encerrar a conversa:** Finalizar a interação com o usuário.
    - **Adicionar uma ação:** Chamar automações (Power Automate), prompts ou habilidades.
    - **Avançado:** Opções como gerar respostas regenerativas, requisições HTTP, telemetria, autenticação.
- **Variáveis:** Containers para armazenar informações capturadas do usuário (ex: resposta a uma pergunta) ou definidas pelo sistema/fluxo.
- **Identificar (em Perguntas):** Opção para especificar o tipo de informação que se espera na resposta do usuário (entidade pré-definida como Idade, Cidade, E-mail; ou a resposta inteira do usuário).
- **Entidades (Entities):** Tipos pré-definidos de informações que o agente pode reconhecer e extrair do texto do usuário.
- **Power FX:** Linguagem de fórmula utilizada para manipulação de dados e lógica, por exemplo, em nós de mensagem ou condições.
- **Mapa de Atividades (no Teste):** Ferramenta de depuração que mostra o caminho percorrido pelo agente no fluxo do tópico durante o teste.

---

#### 💡 O que eu aprendi de mais importante
> 1.  Tópicos são essenciais para definir o comportamento do agente, guiando a conversa e executando ações.
> 2.  A configuração de **frases gatilho** é o método principal para "ensinar" o agente a reconhecer a intenção do usuário e iniciar o tópico correto.
> 3.  O designer visual facilita a construção da lógica da conversa usando **nós** que representam mensagens, perguntas, condições e ações.
> 4.  **Variáveis** são cruciais para capturar e usar informações fornecidas pelo usuário ao longo do tópico.
> 5.  A integração com **Power FX** e **Power Automate (Ações)** expande enormemente as capacidades do agente, permitindo lógica complexa e automação de tarefas externas.

---

#### 🛠 Exercícios ou Atividades Práticas
- **Descrição breve do exercício ou atividade:** Criar um novo tópico "em branco". Dar um título e adicionar uma descrição. Definir pelo menos 5 frases gatilho relevantes para o tema do tópico. Adicionar um nó "Enviar uma mensagem" de boas-vindas. Adicionar um nó "Fazer uma pergunta" para coletar alguma informação do usuário, salvando a resposta em uma variável. Adicionar um nó "Enviar uma mensagem" que utilize o valor da variável na resposta (opcionalmente, usando uma função Power FX simples como `Upper`). Adicionar um nó "Adicionar uma condição" baseada no valor da variável capturada, criando caminhos diferentes para a conversa. Salvar o tópico. Testar o tópico no painel de teste, usando diferentes frases gatilho e fornecendo respostas que sigam os caminhos condicionais definidos.
- **Dificuldades encontradas ou insights obtidos:** Pensar em frases gatilho variadas pode exigir criatividade. Conectar os nós corretamente no designer visual é importante. O uso de variáveis e a referência a elas em mensagens ou condições requer atenção. A integração inicial com Power FX pode parecer complexa, mas exemplos simples ajudam a entender o potencial. O mapa de atividades é muito útil para entender por que um tópico foi disparado ou qual caminho condicional foi seguido.

---

#### 📌 Aplicações no Trabalho
> O domínio da criação de tópicos permite construir agentes que podem:
> - Responder a perguntas frequentes de forma estruturada.
> - Coletar informações do usuário (feedback, detalhes de um problema) e armazená-las ou usá-las em automações.
> - Guiar o usuário por processos passo a passo (ex: solicitação de um serviço, preenchimento de um formulário).
> - Implementar lógicas de negócio simples diretamente na conversa (ex: verificar status, calcular algo rápido).
> - Interagir com outros sistemas através das Ações do Power Automate acionadas pelo tópico.
> É a base para automatizar interações e processos conversacionais.

---

#### ❓ Dúvidas ou Pontos a Revisar
- Aprofundar o uso de diferentes tipos de gatilho (Eventos, Atividades, etc.) além de Frases.
- Explorar todos os tipos de nós disponíveis no designer, especialmente "Adicionar uma ação" (Power Automate) e "Avançado".
- O uso mais complexo de Entidades pré-definidas e a criação de Entidades personalizadas.
- O uso avançado de Variáveis e seus diferentes tipos/escopos.
- Como gerenciar a transição entre tópicos e o uso de "Gerenciamento de Tópico".
- Exemplos mais elaborados de uso de Power FX em tópicos.
- Como os tópicos de Sistema (Fallback, Escalonar, etc.) funcionam e quando customizá-los.
