# 📘 Registro de Aprendizado – Aula 15

**👤 Nome:** Gabriel Moura
**🎯 Tema da Aula:** Utilizando e Criando Entidades no Microsoft Copilot Studio

---

## 📝 Resumo da Aula
> Exploramos o conceito e a utilização de Entidades no Microsoft Copilot Studio, que são essenciais para identificar e extrair tipos específicos de informações das entradas do usuário (como idade, e-mail, datas, etc.) para armazená-las em variáveis. Vimos a vasta lista de entidades pré-definidas disponíveis e aprendemos a criar entidades personalizadas de dois tipos: Lista Fechada (para valores de uma lista predefinida) e Expressão Regular (Regex) (para padrões complexos como CPF). Demonstramos em um tópico como configurar nós de pergunta para usar essas entidades (pré-definidas e personalizadas) e como o agente consegue extrair apenas o valor relevante, independentemente da frase completa do usuário.

---

## 🔍 Conceitos ou Ferramentas Apresentadas
- **Entidades (Entities):** Ferramentas de IA no Copilot Studio que reconhecem e extraem tipos específicos de informações (idades, datas, e-mails, cidades, etc.) da linguagem natural do usuário.
- **Entidades Pré-definidas:** Uma extensa coleção de entidades já prontas fornecidas pela Microsoft (ex: `Age`, `Boolean`, `City`, `Email`, `DateTime`, `Money`, `URL`, etc.).
- **Extração de Valor:** A capacidade da entidade de extrair apenas o dado relevante (ex: o número da idade, o endereço de e-mail) da frase completa do usuário.
- **Entidades Personalizadas:** Entidades criadas pelo usuário quando nenhuma entidade pré-definida atende à necessidade. Dois tipos principais:
    - **Lista Fechada (Closed List):** Usada para reconhecer valores de uma lista específica de itens predefinidos (ex: sabores de pizza). Permite adicionar sinônimos para cada item.
    - **Expressão Regular (Regex):** Usada para reconhecer e extrair texto que segue um padrão específico definido por uma expressão regular (ex: formato de CPF, número de telefone).
- **Correspondência Inteligente (Smart Matching):** Opção em entidades de Lista Fechada que permite ao agente reconhecer variações na linguagem natural e erros de ortografia ao tentar corresponder um valor da lista.
- **Nó "Fazer uma pergunta":** Onde a entidade é configurada. Ao definir o tipo de informação a ser identificada na resposta do usuário, seleciona-se a entidade desejada.
- **Variável (Armazenamento da Entidade):** A informação extraída pela entidade é automaticamente armazenada em uma variável. O tipo da variável é inferido com base na entidade (ex: `Age` -> Number, `Email` -> String, Lista Fechada -> Choice).
- **Opções para o usuário (em perguntas com Lista Fechada):** Ao usar uma entidade de Lista Fechada em um nó de pergunta, é possível exibir os itens da lista como botões de múltipla escolha para o usuário.
- **Regex (Regular Expression):** Uma sequência de caracteres que define um padrão de busca. Usada em entidades do tipo Expressão Regular para identificar padrões complexos no texto do usuário.

---

## 💡 O que eu aprendi de mais importante
> 1.  Entidades são cruciais para tornar o agente "inteligente" na compreensão da entrada do usuário, permitindo extrair **dados estruturados** (como números, datas, e-mails) de texto não estruturado.
> 2.  Há uma vasta gama de **entidades pré-definidas** que cobrem muitos casos de uso comuns, o que acelera o desenvolvimento.
> 3.  Quando as entidades pré-definidas não são suficientes, podemos criar **entidades personalizadas** usando Listas Fechadas (para conjuntos de valores específicos) ou Regex (para padrões complexos), o que oferece grande flexibilidade.
> 4.  Configurar a entidade correta em um nó "Fazer uma pergunta" simplifica muito o processo de captura e validação de informações do usuário.

---

## 🛠 Exercícios ou Atividades Práticas
- **Descrição breve do exercício ou atividade:** Explorar a lista de entidades pré-definidas no menu Configurações > Entidades. Criar uma nova entidade personalizada do tipo Lista Fechada (ex: tipos de produto, departamentos da empresa) com alguns itens e sinônimos. Criar uma nova entidade personalizada do tipo Expressão Regular (ex: um padrão para um código de produto específico, um formato de telefone regional). Criar um novo tópico. Adicionar um nó "Fazer uma pergunta" que utilize uma entidade pré-definida (ex: `City` ou `DateTime`). Adicionar outro nó "Fazer uma pergunta" que utilize a entidade personalizada de Lista Fechada, habilitando a opção de exibir as escolhas. Adicionar um terceiro nó "Fazer uma pergunta" que utilize a entidade personalizada de Regex. Em cada pergunta, configurar para salvar a resposta em uma variável. Adicionar um nó "Enviar uma mensagem" após cada pergunta para exibir a variável capturada. Testar o tópico fornecendo respostas em linguagem natural e verificar se o agente extrai apenas o valor correto da entidade.
- **Dificuldades encontradas ou insights obtidos:** Pensar em exemplos relevantes para entidades personalizadas pode exigir familiaridade com o contexto de negócio. Criar e testar expressões regulares pode ser complexo sem conhecimento prévio de Regex. A opção de exibir escolhas para entidades de Lista Fechada é muito útil para guiar o usuário. A extração baseada em entidades pré-definidas funciona de forma robusta mesmo com frases variadas. A interface para criar entidades é intuitiva.

---

## 📌 Aplicações no Trabalho
> O uso de entidades no Copilot Studio permite criar agentes que:
> - Coletam dados de forma precisa e estruturada (idades, datas, valores monetários, etc.) para usar em processos internos ou automações.
> - Validam entradas do usuário contra uma lista predefinida (ex: categorias de produtos, tipos de solicitação).
> - Extraem informações complexas (números de identificação, códigos específicos) que seguem um padrão definido.
> - Tornam a interação mais natural, permitindo que o usuário forneça a informação dentro de uma frase, em vez de exigir um formato exato.
> Isso é fundamental para qualquer agente que precise capturar e processar informações específicas do usuário.

---

## ❓ Dúvidas ou Pontos a Revisar
- Exemplos mais complexos de uso de Expressões Regulares para criar entidades.
- Como as entidades se integram com o AI Builder para extração de informações de documentos (Form Processing).
- O uso de entidades "registradas externamente".
- Como lidar com casos em que a entidade não consegue extrair o valor (ex: o usuário não fornece a informação no formato esperado).
- O impacto da "Correspondência inteligente" em diferentes idiomas e cenários.

---
