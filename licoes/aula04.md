### 📘 Registro de Aprendizado – Aula 4

**👤 Nome:** Gabriel Moura
**🎯 Tema da Aula:** Criação e Exploração do Designer do Microsoft Copilot Studio

---

#### 📝 Resumo da Aula
> Nesta aula, demos os primeiros passos na criação de um agente (copiloto) no Microsoft Copilot Studio. Focamos em explorar o processo de configuração inicial, incluindo a definição de idioma, nome, descrição, instruções e prompts iniciais. Além disso, navegamos pela interface do designer para entender as diferentes seções (Visão Geral, Conhecimento, Tópicos, Ações, Análise, Canais de Publicação) e as funcionalidades básicas disponíveis para construir e gerenciar o copiloto. Publicamos o agente pela primeira vez para ver o status mudar.

---

#### 🔍 Conceitos ou Ferramentas Apresentadas
- **Microsoft Copilot Studio:** A ferramenta principal utilizada para criar, configurar e gerenciar agentes de conversação (copilotos).
- **Agente/Copiloto:** O assistente virtual que está sendo criado e configurado.
- **Configurações Iniciais:** O processo de definir idioma, nome, descrição, instruções e prompts iniciais ao criar um novo agente.
- **Instruções:** Define a "personalidade", tom de fala e comportamento geral do agente. Pode usar variáveis e funções `Power FX`.
- **Prompts Iniciais:** Sugestões de perguntas que aparecem para o usuário na primeira interação com o agente.
- **Fontes de Conhecimento:** Locais onde o agente busca informações para responder perguntas. Inclui:
    - SharePoint
    - Sites Públicos (com restrição de profundidade de URL)
    - DataSource
    - Carregamento de Arquivos ("arquivos frios", como PDFs de texto, com limite de tamanho e restrições de formato/confidencialidade).
    - Conectores Avançados (Microsoft Fabric, Azure Data Lake, Git Wiki, SQL, Confluence, CSV, GitHub, Jira, Oracle, etc. Alguns podem estar indisponíveis ou exigir licenciamento específico).
- **Solução:** Repositório onde o agente e seus componentes podem ser armazenados (configuração avançada) (ver Aula 7).
- **Nome do Esquema:** Acrônimo/prefixo para elementos do agente dentro de uma solução (configuração avançada) (ver Aula 7).
- **Designer:** A interface visual principal dentro do Copilot Studio para construir e configurar o agente.
- **Power FX:** Linguagem de fórmula mencionada como utilizável nas instruções do agente para personalização avançada (ver Aula 2, Aula 14).
- **Ações:** Automações (fluxos do Power Automate) que o agente pode executar de forma explicitamente, geralmente após um tópico ser acionado (ver Aula 19).
- **Gatilhos / Agentes Autônomos:** Fluxos do Power Automate que o agente pode decidir acionar automaticamente com base no contexto da conversa e instruções (recurso em versão preliminar e com status de disponibilidade variável).
- **Conhecimento Geral (IA Generativa):** Capacidade do agente de usar conhecimentos amplos, além das fontes configuradas (integrado com GPT/OpenAI). Pode ser habilitado ou desabilitado.
- **Tópicos:** Fluxos de conversa pré-definidos. Podem ser tópicos de **Sistema** (padrão, não recomendado grandes alterações) ou **Convencionais** (customizáveis, como Saudação, Obrigado, etc.) (ver Aula 12).
- **Status do Agente:** Indica se o agente está publicado e disponível para uso.
- **Canais de Publicação:** Plataformas onde o agente pode ser disponibilizado para os usuários (Teams, M365, Sites, Mobile Apps, Facebook, Skype, Telegram, Twilio, Line, GroupMe, Direct Line, Email, WhatsApp futuro, Hub de Engajamento) (ver Aula 17).
- **Hub de Engajamento:** Permite transferir a sessão de chat para um agente humano ou outro serviço (ex: Salesforce, Service Now).
- **Análise:** Painel com métricas de desempenho do agente (sessões, participação, pontuação, erros) após a publicação.
- **Configurações (Menu):** Opções detalhadas para ajustar o agente (IA Generativa, Moderação de Conteúdo/Temperatura, Recursos Premium, Segurança, Autenticação, Entidades, Skills, Voz, Idiomas, etc.).
- **Temperatura (IA Generativa):** Parâmetro na configuração de IA que afeta a criatividade versus precisão das respostas (mais alto = mais preciso/menos alucinação, mais baixo = mais criativo/mais alucinação).
- **Teste:** Painel lateral dentro do designer para testar as respostas e o comportamento do agente em tempo real (ver Aula 16).
- **Compartilhar Agente:** Opção para dar a outras pessoas permissão de Visualizador ou Editor no projeto do agente.

---

#### 💡 O que eu aprendi de mais importante
> 1.  A criação de um agente começa com configurações básicas (idioma, nome, instruções) e a definição de onde ele buscará informações (Fontes de Conhecimento).
> 2.  O Designer é o painel central onde se configura praticamente tudo no agente, desde tópicos de conversa até integrações com automações.
> 3.  Podemos controlar se o agente usa apenas as fontes de conhecimento que fornecemos ou também o conhecimento geral de IA, o que é crucial para garantir respostas relevantes e precisas.
> 4.  A integração com o Power Automate (via Ações e Gatilhos/Agentes Autônomos) permite que o agente não apenas responda, mas também *aja* em nome do usuário.

---

#### 🛠 Exercícios ou Atividades Práticas
- **Descrição breve do exercício ou atividade:** Criar um novo agente do zero, preenchendo suas configurações iniciais como nome, descrição, instruções e adicionando uma fonte de conhecimento baseada em um site público. Explorar as diferentes abas e menus do designer (Visão Geral, Conhecimento, Tópicos, Ações, Análise, Canais, Configurações, Teste) para entender a estrutura da ferramenta. Publicar o agente pela primeira vez.
- **Dificuldades encontradas ou insights obtidos:**
    - **Problema:** URLs de sites públicos têm limitação de profundidade. **Insight:** URLs de sites públicos têm profundidade máxima de 2 níveis.
    - **Problema:** Arquivos carregados diretamente ("frios") não atualizam automaticamente. **Insight:** É necessário re-upload se o arquivo original na máquina mudar.
    - **Problema:** Algumas funcionalidades podem ser preliminares ou indisponíveis. **Insight:** Funções como Gatilhos/Agentes Autônomos dependem do ambiente/idioma selecionado.
    - **Insight:** Testar o agente e observar como ele usa (ou não usa, se desabilitado) o conhecimento geral de IA demonstra a importância dessa configuração.

---

#### 📌 Aplicações no Trabalho
> O conhecimento adquirido nesta aula é fundamental para iniciar a construção de copilotos que podem:
> - Automatizar respostas a perguntas comuns em áreas como RH, TI, e processos internos, liberando tempo da equipe.
> - Facilitar o acesso a informações e documentos da empresa ao usar SharePoint ou arquivos como fontes de conhecimento.
> - Servir como um ponto de entrada inicial para suporte, podendo inclusive direcionar para agentes humanos ou outros sistemas via Hub de Engajamento ou Ações.
> - Estar disponível diretamente nas plataformas já utilizadas no dia a dia, como o Microsoft Teams.

---

#### ❓ Dúvidas ou Pontos a Revisar
- Como controlar exatamente quais prompts iniciais aparecem para o usuário (o "truquezinho" mencionado) (ver Aula 18)?
- Como entender em mais detalhes as configurações avançadas, como Solutions e Scheme Name (ver Aula 7)?
- Como aprofundar o uso e a configuração das Ações e Gatilhos/Agentes Autônomos, especialmente considerando o status preliminar?
- Como configurar e usar as opções de Segurança e Autenticação em maior profundidade?
- Como configurar e publicar o agente em canais específicos, como o Teams (ver Aula 17)?
- Como analisar os dados e insights disponíveis no painel de Análise após o agente estar em uso?
- Qual o impacto prático da configuração de "Temperatura" na Moderação de Conteúdo?
---