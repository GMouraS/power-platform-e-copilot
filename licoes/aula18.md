### 📘 Registro de Aprendizado – Aula 18

**👤 Nome:** Gabriel Moura
**🎯 Tema da Aula:** Configurando e Utilizando Prompts Iniciais no Teams

---

#### 📝 Resumo da Aula
> Aprendemos a configurar os prompts iniciais do agente no Microsoft Copilot Studio (Copilot Studio) para sugerir perguntas aos usuários, facilitando a interação inicial no Teams e Microsoft 365 Copilot. Descobrimos que, para que esses prompts iniciais apareçam de forma proeminente, é necessário **desabilitar o tópico de sistema "Iniciar Conversa"**. Demonstramos como desinstalar o agente do Teams (para limpar o teste anterior), desabilitar o tópico "Iniciar Conversa", publicar o agente novamente e, finalmente, adicioná-lo de novo ao Teams para ver os prompts iniciais configurados aparecendo na tela de boas-vindas. Exploramos também as opções de disponibilidade no Teams (chat, reunião, canal) e como removê-las se necessário.

---

#### 🔍 Conceitos ou Ferramentas Apresentadas
- **Prompts Iniciais (Suggest ways to start conversations):** Sugestões de perguntas ou tópicos que aparecem para o usuário quando ele inicia uma conversa com o agente pela primeira vez no Teams ou Microsoft 365 Copilot. Configurados na seção "Prompts iniciais" na Visão Geral.
- **Limite de Prompts Iniciais:** Pode-se adicionar até `6 prompts iniciais` (divididos em blocos de 2, 4 ou 6).
- **Tópico de Sistema "Iniciar Conversa" (Conversation start):** O tópico padrão que é acionado na primeira interação do usuário com o agente, enviando uma mensagem de boas-vindas (ver Aula 12, Aula 17).
- **Conflito de Comportamento:** O tópico "Iniciar Conversa" e os Prompts Iniciais competem pela primeira interação. Para que os Prompts Iniciais apareçam de forma clara na tela de boas-vindas, é necessário **desabilitar** o tópico "Iniciar Conversa". `(Este é o "truque" principal)`
- **Desinstalar Agente do Teams:** Processo para remover uma instância do agente já adicionada no Teams (clicar com o botão direito no chat do agente e selecionar "Desinstalar"). Necessário durante o teste para ver as mudanças de publicação refletidas.
- **Desabilitar Tópico de Sistema:** Acessar a seção "Tópicos", ir para "Sistema" e mudar o status do tópico "Iniciar Conversa" para desabilitado.
- **Publicação Após Modificação:** `Qualquer alteração importante` (como desabilitar um tópico de sistema) requer uma `nova publicação` do agente para que a mudança reflita nos canais.
- **Propagação das Configurações no Teams:** Mudanças visuais (ícone, descrições) e de configuração (opções de disponibilidade) podem levar algum tempo para aparecerem no cliente Teams após a publicação.
- **Opções de Disponibilidade no Teams (Revisão):** Configurações (em Canais -> Teams e Microsoft 365 -> Editar detalhes) para permitir ou não que o agente seja adicionado a chats de grupo/reunião ou canais de equipe. Podem ser desabilitadas e requerem nova publicação para efeito (ver Aula 17).
- **Tela de Boas-Vindas no Teams:** A interface que aparece ao adicionar o agente pela primeira vez, mostrando o nome, ícone, descrições e, crucialmente (se configurado corretamente), os prompts iniciais sugeridos.
- **Botão "Ver Prompts" (View Prompts):** Opção na tela de boas-vindas do Teams que exibe a lista completa de prompts iniciais configurados.

---

#### 💡 O que eu aprendi de mais importante
> 1.  Os **prompts iniciais** são uma ótima forma de guiar o usuário e apresentar as capacidades do agente logo na primeira interação no Teams/Microsoft 365 Copilot.
> 2.  Para que os prompts iniciais apareçam de forma proeminente, é **obrigatório desabilitar o tópico de sistema "Iniciar Conversa"**. Esta é a **dica** ou **truque** para que funcione corretamente.
> 3.  Mudanças na configuração do agente (incluindo desabilitar tópicos de sistema) requerem uma **nova publicação** para serem aplicadas nos canais.
> 4.  A **desinstalação e re-adição** do agente no Teams durante a fase de teste é útil para garantir que as últimas configurações publicadas estejam sendo carregadas corretamente.
> 5.  Detalhes visuais e algumas configurações no Teams podem levar **algum tempo para serem propagados** após a publicação.

---

#### 🛠 Exercícios ou Atividades Práticas
- **Descrição breve do exercício ou atividade:** Acessar a seção "Prompts iniciais" na Visão Geral e configurar pelo menos 2 prompts com título e texto. Acessar a seção "Tópicos", ir para "Sistema" e desabilitar o tópico "Iniciar Conversa". Publicar o agente. No Microsoft Teams, desinstalar qualquer versão anterior do agente. Retornar à seção "Canais" no Copilot Studio, clicar em "Teams e Microsoft 365" e usar "Ver agente no Teams" para adicionar o agente novamente. Observar se os prompts iniciais aparecem na tela de boas-vindas. Clicar em um dos prompts sugeridos para iniciar a conversa com esse tema. Opcionalmente, editar os detalhes do Teams (descrições, ícone), publicar novamente e notar o tempo de propagação das mudanças no Teams.
- **Dificuldades encontradas ou insights obtidos:**
    - **Problema:** Lembrar de desinstalar e adicionar novamente o agente no Teams após cada publicação relevante durante o teste. **Insight:** Esse passo é crucial para ver as mudanças refletidas.
    - **Insight:** Identificar e desabilitar o tópico correto nos tópicos de sistema é essencial.
    - **Insight:** Perceber que a propagação das mudanças visuais não é instantânea.
    - **Insight:** A interação via prompts sugeridos torna a primeira experiência do usuário mais amigável.
    - **Insight:** O botão "Ver Prompts" é útil se muitos prompts estiverem configurados.

---

#### 📌 Aplicações no Trabalho
> Configurar prompts iniciais é essencial para agentes que serão utilizados por um público mais amplo no Teams ou Microsoft 365 Copilot. Isso permite:
> - **Educar o usuário** sobre o que o agente pode fazer.
> - **Facilitar o início da conversa** e guiar o usuário para os tópicos mais relevantes.
> - **Reduzir a curva de aprendizado** para novos usuários.
> - **Garantir que a primeira impressão** do agente seja positiva e útil, mostrando suas principais funcionalidades de cara.
> A desabilitação do tópico "Iniciar Conversa" é uma configuração técnica crítica para alcançar esse objetivo.

---

#### ❓ Dúvidas ou Pontos a Revisar
- O que acontece se o tópico "Iniciar Conversa" não for desabilitado quando prompts iniciais são configurados?
- Quais são os cenários em que seria útil *manter* o tópico "Iniciar Conversa" habilitado em vez de desabilitá-lo?
- Como personalizar o texto padrão adicionado às instruções do agente ao marcar fontes como oficiais (ver Aula 11)?
- Quais são mais detalhes sobre as opções de disponibilidade no Teams e suas implicações de segurança?
- Qual é o processo para customizar o tópico "Iniciar Conversa" caso eu queira usá-lo em vez de desabilitá-lo?
---