### 📘 Registro de Aprendizado – Aula 13

**👤 Nome:** Gabriel Moura
**🎯 Tema da Aula:** O Tópico de Sistema "Conversation Boost" (Fallback)

---

#### 📝 Resumo da Aula
> Nesta aula, exploramos o tópico de sistema "Conversation Boost" (anteriormente conhecido como `Fallback`), que atua como o mecanismo de fallback do agente quando a intenção do usuário é desconhecida (ou seja, quando nenhuma frase gatilho de outros tópicos é reconhecida). Entendemos que este tópico é o principal ponto de integração com as fontes de conhecimento configuradas. Detalhamos a estrutura deste tópico, focando no nó de "Resposta generativa", onde a busca nas fontes de conhecimento ocorre. Vimos como configurar as fontes a serem pesquisadas (limitando a pesquisa a fontes específicas se desejado) e como ajustar a moderação do conteúdo/temperatura. Testamos o tópico fazendo perguntas que não correspondem a outros tópicos, observando como o agente recorre ao Conversation Boost para buscar respostas nas fontes configuradas.

---

#### 🔍 Conceitos ou Ferramentas Apresentadas
- **Tópico de Sistema "Conversation Boost" (Fallback):** O tópico acionado automaticamente quando o agente não consegue identificar a intenção do usuário (ou seja, quando nenhuma frase gatilho de outros tópicos corresponde). Ele é o "plano B" para tentar responder usando as fontes de conhecimento. Anteriormente era chamado de `Fallback`.
- **Intenção Desconhecida:** O estado que aciona o tópico Conversation Boost. Ocorre quando a entrada do usuário não é reconhecida por nenhum gatilho de tópico existente.
- **Gatilho "Intenção Desconhecida":** O tipo de gatilho configurado por padrão no tópico Conversation Boost. É um gatilho especial que não usa frases, mas sim a ausência de reconhecimento de outros gatilhos.
- **Nó "Resposta Generativa":** O principal nó dentro do tópico Conversation Boost (e disponível em outros tópicos) que permite ao agente gerar respostas usando as fontes de conhecimento configuradas e capacidades de IA.
- **Variável `Activity.Text`:** Variável interna que armazena o texto digitado pelo usuário. É usada pelo nó de Resposta Generativa para saber o que pesquisar nas fontes.
- **Fontes de Dados (Configuração da Resposta Generativa):** Permite especificar quais fontes de conhecimento (SharePoint, Sites Públicos, Arquivos, etc.) o nó de Resposta Generativa deve consultar. Por padrão, consulta todas as fontes configuradas, mas pode ser limitado.
- **Pesquisar somente em fontes de conhecimento selecionadas:** Flag dentro da configuração da Resposta Generativa que permite limitar a busca a um subconjunto das fontes configuradas.
- **Dados Clássicos:** Termo usado na configuração da Resposta Generativa que se refere à capacidade de usar o conhecimento geral da IA (a flag "Permitir que a IA use seus próprios conhecimentos gerais" configurada na Visão Geral - ver Aula 4).
- **Moderação do Conteúdo (Nível):** Configuração na Resposta Generativa que ajusta o quão criativa ou precisa deve ser a resposta da IA. Níveis baixos podem levar a **alucinações** (informações incorretas). Níveis altos visam maior precisão.
- **Instruções (na Resposta Generativa):** Permite dar instruções específicas à IA sobre como formatar ou elaborar a resposta generativa (pode usar variáveis e funções).
- **Mensagens de Latência:** Configuração avançada relacionada ao tempo de resposta.
- **Salvar resposta do bot como:** Opção para armazenar o texto gerado pela Resposta Generativa em uma variável.

---

#### 💡 O que eu aprendi de mais importante
> 1.  O tópico **`Conversation Boost`** é o ponto central para que o agente utilize suas fontes de conhecimento e a IA generativa para responder perguntas que **não foram explicitamente mapeadas em outros tópicos**.
> 2.  A **Resposta Generativa** é o nó chave dentro deste tópico (e em outros) que executa a busca nas fontes e sintetiza a resposta.
> 3.  Podemos **controlar** quais fontes de conhecimento são consultadas pelo nó de Resposta Generativa, inclusive limitando a busca a fontes específicas.
> 4.  A configuração da **Moderação do Conteúdo** na Resposta Generativa é importante para equilibrar entre a quantidade de respostas e a precisão.

---

#### 🛠 Exercícios ou Atividades Práticas
- **Descrição breve do exercício ou atividade:** Acessar o tópico de sistema "Conversation Boost" (via "Tópicos" > "Sistemas"). Abrir o editor do tópico para visualizar sua estrutura padrão. Clicar no nó de "Resposta generativa" e em "Editar" para explorar suas configurações, incluindo as fontes de dados e o nível de moderação. Opcionalmente, tentar limitar a busca a apenas uma fonte específica. Salvar as configurações (se alteradas). No painel de teste, fazer perguntas que não correspondam a nenhum outro tópico definido e observar como o Conversation Boost é acionado (verificando no mapa de atividades, se funcionando) e como ele usa as fontes de conhecimento para responder.
- **Dificuldades encontradas ou insights obtidos:**
    - **Insight:** Entender que o gatilho "Intenção Desconhecida" é diferente dos gatilhos baseados em frases.
    - **Insight:** O nó de Resposta Generativa tem várias configurações importantes que influenciam o comportamento da busca e da resposta da IA.
    - **Insight:** A capacidade de limitar as fontes consultadas em um nó de Resposta Generativa abre possibilidades para lógica mais refinada em outros tópicos.
    - **Problema:** Bugs temporários na interface de teste podem dificultar a visualização do mapa de atividades e do rastreamento. **Insight:** Reiniciar o navegador ou aguardar pode ajudar.

---

#### 📌 Aplicações no Trabalho
> O tópico Conversation Boost é vital para a funcionalidade de qualquer agente baseado em conhecimento. Ele permite que o agente:
> - Atue como um **buscador inteligente** sobre o conteúdo das fontes de conhecimento da organização, mesmo para perguntas não previstas em tópicos específicos.
> - Forneça respostas úteis e relevantes de forma automática, reduzindo a necessidade de criar manualmente tópicos para cada pergunta possível.
> - Sirva como o **mecanismo principal** para agentes cujo propósito é principalmente buscar e apresentar informações de documentos e sites.
> Gerenciar e otimizar este tópico é chave para a eficácia geral do agente em lidar com uma ampla gama de perguntas dos usuários.

---

#### ❓ Dúvidas ou Pontos a Revisar
- Como otimizar o texto das "Instruções" dentro do nó de Resposta Generativa para melhorar a qualidade e o estilo das respostas generativas?
- Qual o impacto prático de diferentes níveis de "Moderação do conteúdo" e como escolher o nível adequado?
- Quais são os cenários em que seria útil limitar as fontes de conhecimento em um nó de Resposta Generativa (ex: ter um tópico específico que só busca em uma fonte, enquanto o Conversation Boost busca em todas)?
- Como o agente lida com a incerteza quando a busca em fontes de conhecimento não retorna um resultado claro ou relevante?
- Qual é o status e possíveis evoluções da funcionalidade "Fonte oficial" em conjunto com a Resposta Generativa (ver Aula 11)?
---