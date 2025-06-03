### 📘 Registro de Aprendizado – Aula 26

**👤 Nome:** Gabriel Moura
**🎯 Tema da Aula:** Redirecionamento de Tópicos e Feedback do Usuário

---

#### 📝 Resumo da Aula
> Nesta aula, exploramos o conceito crucial de redirecionamento de tópicos no Microsoft Copilot Studio (Copilot Studio), que permite que o agente mantenha a continuidade da conversa e não encerre de forma reativa. Demonstramos como substituir a etapa de encerramento de um tópico existente (`Consulta de CEP`) pelo nó "Acessar outro tópico", redirecionando a interação para o tópico de sistema **"Fim da Conversa"**. Este tópico, com seu gatilho de redirecionamento, permite coletar feedback do usuário (NPS) antes de finalizar a interação. Observamos a importância da publicação para que as mudanças se reflitam nos canais e, devido a um bug temporário na visualização de Adaptive Cards no painel de teste, a demonstração foi realizada com um tópico sem card ou diretamente no Microsoft Teams.

---

#### 🔍 Conceitos ou Ferramentas Apresentadas
- **Redirecionamento de Tópicos:** Mecanismo que permite ao agente transferir o controle da conversa de um tópico para outro, garantindo fluidez e continuidade na interação.
- **Nó "Acessar outro tópico":** Uma ação de gerenciamento de tópicos no designer do Copilot Studio que permite redirecionar a conversa para qualquer outro tópico existente no agente.
- **Tópico de Sistema "Fim da Conversa":** Um tópico padrão do sistema cujo gatilho principal é um redirecionamento. Ele é projetado para finalizar a interação de forma estruturada, geralmente coletando feedback do usuário (como uma pesquisa `NPS` - Net Promoter Score) e oferecendo opções de ajuda adicional.
- **NPS (Net Promoter Score):** Uma métrica de satisfação do cliente, geralmente coletada através de uma pergunta de 1 a 10 ou 1 a 5, como implementado no tópico "Fim da Conversa".
- **Tópico de Sistema "Escalonar":** Um tópico de sistema que lida com situações onde o agente não consegue resolver a dúvida do usuário, geralmente redirecionando para um recurso humano ou um sistema de suporte (pode ser um gatilho de redirecionamento no "Fim da Conversa").
- **Nó "Gerenciamento de Tópicos":** Categoria de nós que inclui opções para controlar o fluxo da conversa entre tópicos, como "Redirecionar para outro tópico", "Encerrar todos os tópicos", "Transferir conversa" e "Encerrar o tópico atual".
- **Publicação do Agente:** O processo de tornar as alterações do agente disponíveis para os usuários nos canais configurados. Pode haver um pequeno atraso (`delay`) na propagação das novas versões para os ambientes de teste ou produção (ver Aula 17).
- **Bug de Visualização de Adaptive Card:** Um problema temporário ou inconsistência no ambiente de teste do Copilot Studio que pode impedir a correta renderização de Adaptive Cards complexos após certas modificações, exigindo o uso de um tópico mais simples ou testes diretos no Teams (ver Aula 23).
- **Microsoft Teams:** Um dos canais de publicação do agente, onde as interações são realizadas em ambiente real (ver Aula 17, Aula 18).

---

#### 💡 O que eu aprendi de mais importante
> 1.  O **redirecionamento de tópicos** é essencial para criar agentes que oferecem uma experiência de usuário contínua e não fragmentada, permitindo que a conversa flua entre diferentes funcionalidades do agente.
> 2.  O nó **"Acessar outro tópico"** é a ferramenta para implementar esse redirecionamento, transferindo o controle para qualquer outro tópico do agente.
> 3.  O tópico de sistema **"Fim da Conversa"** é um recurso valioso para coletar **feedback do usuário** e medir a satisfação com o atendimento do agente, o que é crucial para melhorias contínuas.
> 4.  Problemas de visualização (como o bug do Adaptive Card no painel de teste) podem ocorrer, mas o uso de tópicos mais simples ou testes diretos no Teams pode ser uma alternativa para verificar a funcionalidade.

---

#### 🛠 Exercícios ou Atividades Práticas
- **Descrição breve do exercício ou atividade:** Modificar um tópico existente (ex: "Consulta de CEP" da Aula 21 ou 22) para que, em vez de encerrar o tópico diretamente, ele redirecione para o tópico de sistema "Fim da Conversa". Testar a interação no painel de teste ou no Microsoft Teams para observar a transição para o tópico de feedback.

    **Passos:**
    1.  Abrir um tópico existente no Microsoft Copilot Studio (ex: "Consulta de CEP").
    2.  Localizar o nó que encerra o tópico atualmente (geralmente "Encerrar o tópico atual").
    3.  **Remover** este nó.
    4.  Adicionar um novo nó (`+`) no lugar, e selecionar **"Gerenciamento de tópicos"** -> **"Acessar outro tópico"**.
    5.  Na lista de tópicos, selecionar o tópico de sistema **"Fim da Conversa"**.
    6.  **Salvar** o tópico.
    7.  (Opcional, se o tópico modificado usar Adaptive Cards e estiver enfrentando o bug de visualização): Desabilitar temporariamente o tópico que usa Adaptive Cards (se houver um tópico duplicado sem card) e habilitar um tópico mais simples (como o de "Consulta de CEP" que faz requisição HTTP direta, se esse não estiver causando problemas de visualização).
    8.  **Publicar** o agente para que as mudanças se reflitam nos canais (ver Aula 17).
    9.  **Testar a automação:**
        *   **No painel de Teste:** Digitar uma frase gatilho para o tópico modificado (ex: "Consultar CEP").
        *   **No Teams:** Se preferir, desinstalar e reinstalar o agente no Teams (ver Aula 18) e interagir com ele.
    10. Observar como, após a resposta principal do tópico, o agente redireciona para o tópico "Fim da Conversa", perguntando sobre a satisfação e oferecendo opções de feedback.

- **Dificuldades encontradas ou insights obtidos:**
    - **Problema:** O bug de visualização do Adaptive Card no painel de teste pode dificultar a depuração imediata. **Insight:** É necessário alternar para um tópico mais simples ou testar diretamente no Teams para contornar essa limitação.
    - **Insight:** O atraso na propagação da publicação do agente (mesmo que alguns minutos) pode exigir paciência antes de testar a nova versão.
    - **Insight:** A transição para o tópico "Fim da Conversa" é fluida e permite uma coleta de feedback valiosa para a melhoria contínua do agente.

---

#### 📌 Aplicações no Trabalho
> O conhecimento sobre redirecionamento de tópicos é fundamental para criar agentes de alto desempenho que:
> - **Mantêm o usuário engajado:** Evitando que a conversa pare abruptamente, oferecendo sempre um próximo passo relevante.
> - **Simplificam o fluxo de conversa:** Reutilizando tópicos de sistema ou customizados para etapas comuns (ex: escalonar para humano, coletar feedback, perguntar se há mais dúvidas).
> - **Melhoram a satisfação do usuário:** Ao coletar feedback proativamente, demonstrando que a experiência do usuário é valorizada.
> - **Fornecem dados para tomada de decisão:** Os feedbacks coletados podem ser usados para identificar áreas de melhoria no agente.

---

#### ❓ Dúvidas ou Pontos a Revisar
- Como gerenciar o comportamento do agente quando múltiplos tópicos podem ser acionados por uma mesma frase (ambiguidade)?
- Quais são os cenários mais comuns em que o tópico "Escalonar" é utilizado e como customizá-lo para diferentes necessidades de negócio?
- É possível passar variáveis de um tópico para outro durante um redirecionamento (ver Aula 14)?
- Como personalizar a experiência do tópico "Fim da Conversa" além das opções padrão (ex: customizar as perguntas de NPS, enviar o feedback para um sistema externo)?
- Quais são as melhores práticas para desenhar fluxos de tópicos que utilizam múltiplos redirecionamentos de forma eficiente?
---