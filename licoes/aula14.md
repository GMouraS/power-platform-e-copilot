# 📘 Registro de Aprendizado – Aula 14

**👤 Nome:** Gabriel Moura  
**🎯 Tema da Aula:** Utilizando Variáveis no Microsoft Copilot Studio

---

## 📝 Resumo da Aula
> Aprofundamos o conceito de variáveis no Copilot Studio, entendendo que elas são essenciais para armazenar contexto e dados ao longo de uma conversa. Exploramos os tipos de variáveis: Variáveis de Tópico (restritas a um tópico), Variáveis Globais (acessíveis em todo o agente), e Variáveis de Sistema (predefinidas pelo Studio, como `Activity.Text` ou `User.DisplayName`). Demonstramos como referenciar variáveis de sistema em mensagens, como variáveis de tópico são criadas automaticamente ao capturar respostas de perguntas, e como usar o nó de "Gerenciamento de variáveis" para definir, analisar ou limpar valores, inclusive aplicando funções Power FX para manipulação de dados. Enfatizamos a importância de encerrar tópicos para evitar problemas de contexto e mostramos como a aplicação de funções via gerenciamento de variáveis melhora a manutenção do fluxo.

---

## 🔍 Conceitos ou Ferramentas Apresentadas
- **Variáveis:** Elementos que armazenam informações (texto, números, booleanos, etc.) utilizadas pelo agente para manter o contexto da conversa, capturar dados do usuário e manipular informações.
- **Tipos de Variáveis:**
    - **Variáveis de Tópico (`Topic`):** Variáveis criadas dentro de um tópico específico. Seu escopo é limitado a esse tópico e não são acessíveis diretamente em outros tópicos (a menos que sejam configuradas para receber/retornar valores).
    - **Variáveis Globais (`Global`):** Variáveis acessíveis de qualquer tópico dentro do agente. Úteis para informações que precisam persistir ou ser compartilhadas amplamente. Podem carregar valores entre sessões.
    - **Variáveis de Sistema:** Variáveis predefinidas pelo Copilot Studio que fornecem informações sobre o usuário, o canal, a atividade, o ambiente, etc. (ex: `Activity.Text`, `User.DisplayName`, `Channel.ID`). São referenciadas usando o prefixo correspondente (`Activity.`, `User.`, etc.).
    - **Variáveis de Ambiente:** Variáveis relacionadas ao ambiente/solução (menos comuns no dia a dia do desenvolvimento do tópico).
- **Referenciar Variáveis:** Utilizar o nome da variável (com o prefixo apropriado, ex: `User.FirstName`, `Topic.VarSaborPizza`, `Global.MinhaVariavelGlobal`) em nós como "Enviar uma mensagem" para exibir seu valor.
- **Criação Automática de Variáveis de Tópico:** Ao usar o nó "Fazer uma pergunta" e escolher onde salvar a resposta do usuário, o Studio cria automaticamente uma nova variável de tópico para armazenar essa resposta.
- **Painel de Variáveis:** Seção na interface do designer de tópicos que lista todas as variáveis usadas nesse tópico (tópico, global, ambiente) e permite gerenciá-las (renomear, alterar escopo, configurar recebimento/retorno).
- **Escopo Limitado:** Refere-se ao escopo padrão das variáveis de tópico, restrito ao tópico atual.
- **Receber valores de outros tópicos / Retornar valores aos tópicos originais:** Flags em variáveis de tópico que permitem a troca de informações com outros tópicos quando há redirecionamento.
- **Tornar Global:** Opção para converter uma variável de tópico em uma variável global.
- **Nó "Gerenciamento de variáveis":**
    - **Definir valor de uma variável:** Atribuir um valor (fixo ou dinâmico, usando funções Power FX) a uma variável.
    - **Analisar valor:** Extrair um tipo de dado específico de uma variável (ex: converter string para número) ou copiar o valor para outra variável.
    - **Limpar valor(es):** Remover o valor de uma variável ou limpar todas as variáveis.
- **Power FX em Variáveis:** Utilizar funções Power FX no nó "Definir valor de uma variável" para manipular o valor antes de armazená-lo (ex: `Upper()` para converter para maiúsculo).
- **Encerrar o Tópico Atual:** Nó recomendado para finalizar o fluxo de um tópico, liberando o contexto e evitando comportamentos inesperados.

---

## 💡 O que eu aprendi de mais importante
> 1.  Variáveis são o mecanismo fundamental para o agente lembrar informações, personalizar interações e usar dados coletados.
> 2.  Existem diferentes escopos (Tópico vs. Global) que definem a acessibilidade da variável. Variáveis de Sistema fornecem informações contextuais prontas para usar.
> 3.  É uma boa prática usar o nó **"Gerenciamento de variáveis"** para manipular valores de variáveis (especialmente aplicando funções Power FX), em vez de embutir a lógica diretamente em nós de mensagem, para melhorar a manutenibilidade.
> 4.  Sempre **encerrar um tópico** (ou redirecionar para outro) é importante para gerenciar corretamente o fluxo da conversa e o contexto das variáveis.

---

## 🛠 Exercícios ou Atividades Práticas
- **Descrição breve do exercício ou atividade:** Abrir um tópico existente ou criar um novo. No nó "Enviar uma mensagem", adicionar uma variável de sistema (ex: `User.DisplayName` ou `User.FirstName`) para personalizar a mensagem. Adicionar um nó "Fazer uma pergunta" que capture a resposta em uma variável de tópico. Adicionar um nó "Gerenciamento de variáveis" > "Definir valor de uma variável". Selecionar a variável de tópico criada e usar uma fórmula Power FX simples (ex: `Upper(Topic.NomeDaVariavel)`) para modificar seu valor. Adicionar um nó "Enviar uma mensagem" que mostre o valor modificado da variável. Adicionar um nó "Encerrar o tópico atual". Testar o tópico e verificar se o nome do usuário aparece e se a variável é capturada e modificada corretamente. Explorar o painel "Variáveis" para ver as variáveis em uso.
- **Dificuldades encontradas ou insights obtidos:** Lembrar a sintaxe correta para referenciar variáveis (`User.`, `Topic.`). Entender a diferença entre usar Power FX diretamente em um nó de mensagem e usar um nó de "Gerenciamento de variáveis" para aplicar a função. Gerenciar o escopo (tópico vs. global) pode ser confuso inicialmente. A importância de adicionar o nó "Encerrar o tópico atual" se torna clara ao observar o comportamento do agente sem ele.

---

## 📌 Aplicações no Trabalho
> O uso eficaz de variáveis permite construir agentes que:
> - Personalizam a interação chamando o usuário pelo nome ou referenciando informações previamente fornecidas.
> - Coletam dados específicos de cada usuário durante a conversa para processamento ou automação posterior.
> - Adaptam o fluxo da conversa com base nas informações coletadas e na lógica definida pelas variáveis e condições.
> - Preparam dados para serem enviados a sistemas externos (via Power Automate) manipulando seus valores com Power FX.
> Dominar variáveis é fundamental para criar agentes interativos e orientados por dados.

---

## ❓ Dúvidas ou Pontos a Revisar
- Como usar as flags "Receber valores de outros tópicos" e "Retornar valores aos tópicos originais" para passar variáveis entre tópicos.
- Mais exemplos avançados de uso de Power FX no nó "Gerenciamento de variáveis".
- Cenários em que o uso de variáveis globais é mais apropriado.
- Como as variáveis de sistema podem ser usadas em diferentes contextos (não apenas em mensagens).
- O que acontece com as variáveis após o término de uma sessão.
- Tipos de dados das variáveis e como convertê-los usando "Analisar valor".

---