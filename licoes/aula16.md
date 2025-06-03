### 📘 Registro de Aprendizado – Aula 16

**👤 Nome:** Gabriel Moura
**🎯 Tema da Aula:** Funcionalidades de Teste e Depuração no Microsoft Copilot Studio

---

#### 📝 Resumo da Aula
> Nesta aula, exploramos as ferramentas disponíveis no painel de teste do Microsoft Copilot Studio (Copilot Studio) para depurar e entender o comportamento do nosso agente. Vimos as opções básicas como recarregar o chat e, principalmente, o recurso de rastreamento/mapa de atividades, que visualiza o fluxo que o agente seguiu para responder. Discutimos a evolução e diferença na apresentação dessa funcionalidade dependendo do idioma do agente e a importância desses recursos para identificar e solucionar problemas nos tópicos e nas fontes de conhecimento.

---

#### 🔍 Conceitos ou Ferramentas Apresentadas
- **Painel de Teste:** A área na interface do Copilot Studio onde podemos interagir com o agente em desenvolvimento para verificar suas respostas e comportamento.
- **Botões de Chat (Fechar, Recarregar):** Controles básicos no painel de teste para encerrar a sessão de chat ou limpar a conversa e o contexto atual (`Reload`).
- **Rastrear entre Tópicos (Trace between topics):** Funcionalidade de depuração que, ao ser ativada, move automaticamente o designer visual para o tópico que está sendo executado no chat de teste. `Facilita a visualização do fluxo em tempo real`. (Pode aparecer como um toggle de texto dependendo do idioma/versão).
- **Mapa de Atividades (Debugging Map Icon / Map View):** Um painel visual (apresentado como um ícone de mapa ou como uma view separada no painel de depuração) que mostra um diagrama da jornada do usuário e dos passos que o agente seguiu (`tópicos acionados`, `fontes consultadas`, etc.) de forma `não cíclica`. Substitui ou complementa o "Rastrear entre Tópicos" em algumas configurações/idiomas (como inglês).
- **Visualização de Logs (Logs View):** Uma aba no painel de depuração (dentro do Mapa de Atividades) que apresenta o fluxo da conversa em formato de log textual, incluindo detalhes como nome do tópico acionado, mensagens e a estrutura em `JSON` gerada.
- **Visualização de Revisão (Review View):** Uma aba no painel de depuração que pode fornecer informações adicionais sobre o processo.
- **Visualização de Variáveis (Variables View):** Uma aba no painel de depuração que mostra os valores atuais de todas as variáveis utilizadas na sessão do agente, útil para verificar se as informações estão sendo capturadas e manipuladas corretamente (ver Aula 14).
- **Impacto do Idioma na Interface de Depuração:** Algumas funcionalidades de depuração visual (como o mapa de atividades) podem ter uma apresentação ou disponibilidade diferente dependendo do idioma em que o agente foi criado (ex: mais visível/separado em agentes em inglês).
- **Depuração / Troubleshooting:** O processo de identificar e resolver problemas no comportamento do agente, utilizando ferramentas como o rastreamento/mapa de atividades e a visualização de variáveis/logs.

---

#### 💡 O que eu aprendi de mais importante
> 1.  As ferramentas de **depuração** no painel de teste são **essenciais** para entender como o agente interpreta as entradas do usuário, quais tópicos são acionados e qual caminho ele segue no fluxo.
> 2.  O **rastreamento/mapa de atividades** permite visualizar graficamente a jornada do agente, facilitando a identificação de desvios inesperados ou falhas.
> 3.  Observar o **Mapa de Atividades** ou os **Logs** ajuda a ver quais fontes de conhecimento foram consultadas para uma determinada resposta.
> 4.  A **Visualização de Variáveis** é crucial para verificar se as informações importantes estão sendo capturadas e armazenadas corretamente ao longo da conversa.

---

#### 🛠 Exercícios ou Atividades Práticas
- **Descrição breve do exercício ou atividade:** Utilizar o painel de teste do agente. Ativar a opção "Rastrear entre tópicos" (se disponível no idioma). Fazer perguntas que acionem diferentes tópicos e fontes de conhecimento (ex: sobre DAX, sobre o conteúdo do SharePoint, sobre um arquivo indexado). Observar como a tela do designer se move para o tópico acionada ou como o mapa de atividades se preenche. Fazer uma pergunta que não acione nenhum tópico específico (para testar o fallback) e observar o rastreamento. Clicar no mapa de atividades/ícone de depuração (se disponível) para abrir o painel detalhado e explorar as visualizações de Logs e Variáveis. Desativar o rastreamento/mapa e notar a diferença na performance da interface.
- **Dificuldades encontradas ou insights obtidos:**
    - **Problema:** A apresentação das ferramentas de rastreamento pode variar dependendo do idioma em que o agente foi criado, o que pode causar confusão inicial. **Insight:** É importante estar ciente dessas variações.
    - **Insight:** Manter o rastreamento ativo pode lentificar a interface.
    - **Insight:** O mapa de atividades/logs detalhados fornecem uma riqueza de informações que exigem um pouco de prática para serem totalmente compreendidas.
    - **Insight:** Observar o fallback sendo acionado no rastreamento ajuda a entender seu papel (ver Aula 13).

---

#### 📌 Aplicações no Trabalho
> A habilidade de usar as ferramentas de teste e depuração é diretamente aplicável ao desenvolvimento de qualquer agente no ambiente de trabalho. Permite:
> - **Identificar rapidamente por que o agente não está respondendo** como esperado ou por que um tópico específico não está sendo acionado.
> - **Visualizar o fluxo da conversa** para otimizá-lo ou corrigir lógicas condicionais.
> - **Verificar se as informações do usuário** (capturadas em variáveis) estão sendo processadas corretamente antes de passá-las para automações ou outras etapas.
> - **Diagnosticar problemas com a consulta a fontes de conhecimento**, vendo quais fontes foram de fato pesquisadas.
> - **Troubleshooting eficiente** de agentes em desenvolvimento ou que apresentem bugs.

---

#### ❓ Dúvidas ou Pontos a Revisar
- Quais outros detalhes úteis estão disponíveis nas visualizações de Logs e Revisão no painel de depuração?
- Quais são mais exemplos práticos de como usar as variáveis na visualização de Variáveis para depurar problemas específicos?
- Quais são as diferenças completas na interface e funcionalidades de depuração entre agentes criados em diferentes idiomas?
- Quais são os cenários comuns de troubleshooting e como usar as ferramentas para resolvê-los?
- Existe uma forma de "logar" sessões de usuários reais (em produção) para depuração posterior?
---