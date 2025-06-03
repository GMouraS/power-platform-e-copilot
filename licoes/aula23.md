### 📘 Registro de Aprendizado – Aula 23

**👤 Nome:** Gabriel Moura
**🎯 Tema da Aula:** Introdução a Adaptive Cards (Cards Adaptativos) no Microsoft Copilot Studio

---

#### 📝 Resumo da Aula
> Introduzimos o conceito de Adaptive Cards (Cards Adaptativos) como uma forma de expandir as capacidades visuais de interação do agente no Microsoft Copilot Studio (Copilot Studio), substituindo mensagens de texto simples por elementos mais ricos e interativos. Mostramos como adicionar um nó de "Perguntar com um cartão adaptável" no tópico e exploramos o Adaptive Card Designer para ver exemplos da complexidade e variedade de layouts possíveis (formulários, galerias, itinerários, etc.). Demonstramos como criar um card simples no designer, copiar seu código `JSON` e colar no nó do Copilot Studio. Testamos o tópico com o card, observando que ele aparece na interface do chat, mas notamos que o conteúdo do card está **estático** e não reflete os dados dinâmicos das variáveis do agente (como as retornadas de uma API).

---

#### 🔍 Conceitos ou Ferramentas Apresentadas
- **Adaptive Cards (Cards Adaptativos):** Uma forma de `UI (User Interface) declarativa` que permite que desenvolvedores troquem conteúdo de UI em formato `JSON` de maneira comum e previsível em vários hosts (`Microsoft Teams`, `Outlook`, etc.). Permitem criar interfaces mais ricas e interativas do que mensagens de texto simples.
- **Nó "Perguntar com um cartão adaptável":** Um tipo de nó disponível no designer de tópicos do Copilot Studio que permite incluir um Adaptive Card na conversa com o usuário. Pode ser usado tanto para `exibir informações` quanto para `coletar inputs`.
- **Adaptive Card Designer:** Uma ferramenta web externa ([adaptivecards.io/designer](https://adaptivecards.io/designer)) que fornece um ambiente visual para criar Adaptive Cards. Permite arrastar e soltar elementos, configurar propriedades e ver o `JSON` gerado.
- **Samples (no Adaptive Card Designer):** Exemplos pré-construídos de Adaptive Cards que demonstram o que é possível criar (login forms, agendas, itinerários, formulários, etc.).
- **Payload (JSON):** O código em formato `JSON` que define a estrutura e o conteúdo de um Adaptive Card.
- **Elementos do Card:** Componentes visuais que podem ser adicionados a um Adaptive Card (Text Block, Image, Input.Text, Action.OpenUrl, Action.Submit, etc.).
- **Propriedades do Elemento:** Opções de configuração para cada elemento do card (tamanho da fonte, cor, espaçamento, texto, etc.).
- **Ações no Card:** Botões ou outros elementos interativos que permitem ao usuário realizar uma ação (abrir URL, submeter dados, mostrar outro card). É `necessário para validar o card` no designer do Copilot Studio (mesmo que não vá usar a ação).
- **Colar JSON no Copilot Studio:** A forma de importar um card criado no Adaptive Card Designer para o nó "Perguntar com um cartão adaptável" no Copilot Studio.
- **Edição JSON versus Edição Fórmula:** Duas formas de editar o conteúdo de um card no Copilot Studio. A edição JSON lida com o código estático do card. A edição Fórmula (`a ser vista na próxima aula`) permite usar variáveis do agente.
- **Card Estático:** Um Adaptive Card cujo conteúdo visual (textos, imagens, valores) é fixo e não muda com base nos dados ou variáveis do agente.

---

#### 💡 O que eu aprendi de mais importante
> 1.  Adaptive Cards são uma forma poderosa de criar interfaces de usuário **visualmente ricas e interativas** diretamente no chat do agente, indo além das mensagens de texto simples.
> 2.  O **Adaptive Card Designer** é a ferramenta ideal para criar e pré-visualizar o design de um card.
> 3.  É possível incluir diversos **elementos** e **ações** em um card para exibir informações de forma estruturada ou coletar inputs do usuário de forma mais amigável (como um formulário dentro do chat).
> 4.  Importar um card para o Copilot Studio envolve **copiar o `JSON`** do designer e colar no nó "Perguntar com um cartão adaptável".
> 5.  Ao colar o `JSON`, o card no Copilot Studio é **estático**; seu conteúdo **não muda com base nas variáveis do agente** nesta forma de edição.

---

#### 🛠 Exercícios ou Atividades Práticas
- **Descrição breve do exercício ou atividade:** Explore o Adaptive Card Designer e crie um card simples para ser usado no tópico de consulta de CEP. Adicione-o ao tópico no Copilot Studio.

    **Pré-requisito:** Ter o tópico de consulta de CEP criado (utilizando a requisição HTTP direta ou o fluxo do Power Automate) (ver Aula 21, Aula 22).

    **Passos:**
    1.  Abrir o **Adaptive Card Designer** em uma nova aba do navegador ([adaptivecards.io/designer](https://adaptivecards.io/designer)).
    2.  Em "Select host application", escolher **"Microsoft Teams"**.
    3.  (Opcional) Explorar os **"Samples"** para ver diferentes exemplos de cards e suas funcionalidades (rolar a lista para ver a variedade).
    4.  Clicar em **"New card"** e selecionar **"Blank template"**.
    5.  No painel da esquerda (**Card elements**), arrastar e soltar alguns elementos para a tela de design (ex: um **Text Block** para um título, mais três **Text Block** para Estado, Cidade e Endereço).
    6.  No painel da direita (**Element properties**), selecionar cada elemento adicionado e configurar suas propriedades (ex: mudar o texto do Text Block de título para "Resultado da Consulta de CEP", mudar os textos dos outros Text Blocks para "Estado:", "Cidade:", "Endereço:").
    7.  (Opcional) Adicionar um elemento **Action** (ex: **Action.OpenUrl** ou **Action.Submit** com um título como "Obrigado") para evitar o erro de validação no Copilot Studio (embora o erro possa ser ignorado).
    8.  No painel inferior (**Card payload editor**), copiar o **código `JSON`** gerado para o card.
    9.  Voltar ao Microsoft Copilot Studio e abrir o tópico de **Consulta de CEP**.
    10. **Deletar** o nó **"Enviar uma mensagem"** que exibia o resultado do CEP como texto simples.
    11. Adicionar um nó `+` e selecionar **"Perguntar com um cartão adaptável"**.
    12. Clicar no nó recém-adicionado. Na caixa de texto principal, **colar o código `JSON`** copiado do Adaptive Card Designer.
    13. (Opcional) Clicar no botão **"Open Adaptive Card Designer"** que aparece abaixo da caixa de `JSON` para ver o card dentro do Copilot Studio e fazer pequenas edições.
    14. Clicar no botão **"Salvar"** do tópico (ele pode exibir um aviso de erro sobre a falta de um botão Action, o que é normal se você não adicionou um).
    15. No painel de **Teste**, dar um **Reload**.
    16. Acionar o tópico de Consulta de CEP e fornecer um CEP válido.
    17. Observar a resposta do agente: um Adaptive Card estático com o layout que você criou deve aparecer, mas os campos de Estado, Cidade e Endereço estarão vazios ou com o texto fixo que você digitou no designer.

- **Dificuldades encontradas ou insights obtidos:**
    - **Insight:** A interface do Adaptive Card Designer é visual e fácil de usar, mas criar layouts complexos exige prática.
    - **Insight:** O Copilot Studio exige que o card tenha pelo menos um botão Action para validação, mesmo que você não o use.
    - **Problema:** É frustrante ver o card no chat, mas perceber que ele está estático e não mostra os dados dinâmicos das variáveis do agente. **Insight:** Isso demonstra a limitação de colar o `JSON` puro, que será abordada na próxima aula.
    - **Insight:** A transição do design visual para o código `JSON` é clara no designer.

---

#### 📌 Aplicações no Trabalho
> Utilizar Adaptive Cards permite:
> - **Apresentar informações de forma mais organizada e visualmente agradável** (ex: resultados de consulta, detalhes de um item, resumo de um pedido).
> - **Criar formulários simples** para coletar múltiplos inputs do usuário de uma vez (usando Input.Text, Input.Number, etc. no card).
> - **Incorporar elementos interativos** como botões que podem acionar outras ações ou abrir links.
> - **Padronizar a apresentação** de informações em diferentes canais (Teams, Outlook, etc.).
> Embora nesta aula o card seja estático, a base para criar interfaces ricas está posta.

---

#### ❓ Dúvidas ou Pontos a Revisar
- Como fazer com que o Adaptive Card exiba dados dinâmicos das variáveis do agente (a ser visto na próxima aula)?
- Como usar Adaptive Cards para coletar múltiplos inputs do usuário de uma vez?
- Quais são mais exemplos de elementos e ações de Adaptive Cards e como usá-los no Copilot Studio?
- Qual a diferença entre os tipos de ação (Action.Submit, Action.OpenUrl, etc.) e como eles interagem com o agente?
- Quais são as limitações e compatibilidade de diferentes versões de Adaptive Cards em vários hosts (Teams, Outlook, etc.)?
---