### 📘 Registro de Aprendizado – Aula 33

**👤 Nome:** Gabriel Moura
**🎯 Tema da Aula:** Mensagens de Latência e Feedback ao Usuário no Microsoft Copilot Studio

---

#### 📝 Resumo da Aula
> Nesta aula, abordamos as **mensagens de latência** no Microsoft Copilot Studio (Copilot Studio), um recurso crucial para melhorar a experiência do usuário durante operações que podem demorar (consultas a `APIs`, chamadas a `Power Automate`). Explicamos como configurar essas mensagens diretamente nas propriedades de nós específicos (ex: "Enviar solicitação HTTP", "Adicionar uma ação"). Demonstramos a possibilidade de adicionar **múltiplas frases** (inclusive com variáveis e funções `Power FX`) que o agente randomizará e exibirá ao usuário enquanto aguarda a conclusão da operação. Isso evita que o usuário pense que o agente travou e proporciona um feedback proativo. Testes com diferentes tópicos (requisição HTTP direta e Power Automate) ilustraram a funcionalidade, destacando que fluxos com maior `delay` de processamento são ideais para observar a latência.

---

#### 🔍 Conceitos ou Ferramentas Apresentadas
- **Mensagens de Latência (Latency Messages):** Pequenas mensagens ou frases configuradas nas propriedades de certos nós do Copilot Studio que são exibidas ao usuário enquanto o agente aguarda a conclusão de uma operação demorada (ex: chamada de `API`, execução de um fluxo `Power Automate`).
- **Nós com Propriedades de Latência:**
    - **"Enviar solicitação HTTP":** Nó usado para fazer chamadas diretas a `APIs` (ver Aula 21).
    - **"Adicionar uma ação":** Nó usado para invocar fluxos do Power Automate (ver Aula 19, Aula 22).
- **Finalidade da Mensagem de Latência:** Evitar que o usuário pense que o agente travou durante um `delay` (atraso) de processamento, informando-o proativamente que a operação está em andamento.
- **Configuração de Mensagem de Latência:** Acessada nas "Propriedades" do nó específico. Permite adicionar uma ou mais frases.
- **Randomização de Frases:** Se múltiplas frases de latência forem configuradas, o agente escolherá uma delas aleatoriamente para exibir ao usuário, tornando a interação menos repetitiva.
- **Variáveis e Funções em Mensagens de Latência:** É possível incluir variáveis de tópico ou sistema (ex: `User.FirstName`) e funções `Power FX` nas frases de latência para personalizá-las (ex: `"Aguarde, " & User.FirstName & ", estou verificando o CEP informado."`).
- **Comparações de Desempenho:** Operações que envolvem chamadas a serviços externos (como `APIs` ou Power Automate) geralmente têm um `delay` maior, sendo ideais para testar e observar as mensagens de latência. Requisições HTTP diretas a `APIs` muito rápidas podem não exibir a mensagem.
- **Conversas de Voz:** Em conversas de voz, a mensagem de latência pode ser enviada repetidas vezes até a conclusão da operação, para manter o usuário informado.

---

#### 💡 O que eu aprendi de mais importante
> 1.  **Mensagens de latência** são um recurso simples, mas **poderoso**, para melhorar a experiência do usuário, fornecendo feedback proativo durante operações demoradas do agente.
> 2.  É possível configurar **múltiplas frases** de latência, que serão randomizadas, e **personalizá-las com variáveis e `Power FX`**, evitando a repetição e tornando a interação mais natural.
> 3.  Essas mensagens são configuradas diretamente nas **propriedades de nós específicos** que realizam operações externas (HTTP, Power Automate), eliminando a necessidade de criar passos extras no fluxo do tópico.
> 4.  A funcionalidade é mais perceptível em fluxos que naturalmente possuem um **pequeno `delay`** de processamento, como aqueles que envolvem a chamada ao Power Automate.

---

#### 🛠 Exercícios ou Atividades Práticas
- **Descrição breve do exercício ou atividade:** Configurar mensagens de latência em um tópico existente que realiza uma operação com `delay` (ex: consulta de CEP via Power Automate) e testar a exibição dessas mensagens.

    **Pré-requisito:**
    *   Ter um tópico de consulta de CEP que utiliza um fluxo do Power Automate para a requisição HTTP (ver Aula 22), pois tende a ter um `delay` mais perceptível.
    *   (Opcional) Ter configurado o tópico de consulta de CEP via requisição HTTP direta (ver Aula 21) para comparar o `delay`.

    **Passos:**
    1.  No Microsoft Copilot Studio, navegar até o tópico de **Consulta de CEP** que utiliza o Power Automate (ex: `Consulta CEP HTTP PA`).
    2.  Localizar o nó **"Adicionar uma ação"** que chama o fluxo Power Automate.
    3.  Clicar no nó e, no painel de propriedades à direita, rolar até **"Propriedades"** e expandir "Mensagens de latência".
    4.  Ativar a opção **"Enviar uma mensagem de latência"**.
    5.  Adicionar pelo menos três frases de latência, variando o texto e, em uma delas, incluindo uma variável de sistema (ex: `User.FirstName`):
        *   "Espere um momento, estou verificando."
        *   "Aguarde, `User.FirstName`, estou verificando o CEP informado."
        *   "Peraí, vou checar para você!"
    6.  **Salvar** o tópico.
    7.  No painel de **Teste** do Copilot Studio, dar um **Reload**.
    8.  Digitar uma frase para acionar o tópico (ex: "Consultar CEP").
    9.  Inserir um CEP válido.
    10. Observar as mensagens de latência que aparecem enquanto o agente processa a solicitação (elas devem aparecer no chat do agente).
    11. Repetir o teste algumas vezes para ver diferentes frases sendo exibidas.
    12. (Opcional) Tentar configurar as mensagens de latência no tópico de consulta de CEP via requisição HTTP direta e observar se elas são exibidas, dado que essa API é muito rápida.

- **Dificuldades encontradas ou insights obtidos:**
    - **Problema:** A visualização das mensagens de latência pode ser difícil se a operação for muito rápida. **Insight:** Usar fluxos com inerente `delay` (como Power Automate) ou APIs com maior tempo de resposta ajuda a observar o comportamento.
    - **Insight:** A randomização das frases torna a interação mais dinâmica e menos robótica.
    - **Insight:** A inclusão de variáveis nas mensagens de latência é um toque de personalização que melhora a experiência do usuário.

---

#### 📌 Aplicações no Trabalho
> As mensagens de latência são importantes para:
> - **Melhorar a Experiência do Usuário:** Reduzir a frustração e a incerteza do usuário ao aguardar uma resposta, comunicando proativamente que o agente está trabalhando.
> - **Evitar Abandono da Conversa:** Impedir que usuários encerrem a sessão por pensarem que o agente travou ou não está respondendo.
> - **Humanizar a Interação:** Frases variadas e personalizadas podem dar uma sensação de que o agente está "pensando" ou "buscando", tornando a experiência mais natural.
> - **Indicação de Processamento:** Dar ao usuário uma indicação visual de que a solicitação está sendo processada, mesmo que não haja um feedback imediato.

---

#### ❓ Dúvidas ou Pontos a Revisar
- Quais são os limites de caracteres ou o número máximo de frases de latência que podem ser configuradas por nó?
- Como as mensagens de latência interagem com outras mensagens de feedback (ex: "Digitando..." no Teams)?
- Quais são os cenários em que o uso de mensagens de latência é mais crítico?
- É possível configurar um `timeout` para a operação, caso a latência seja muito longa e a operação falhe?
- Como o `delay` de processamento de diferentes tipos de conectores do Power Automate pode influenciar a necessidade de mensagens de latência?
---