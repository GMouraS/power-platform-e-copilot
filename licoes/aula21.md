# 📘 Registro de Aprendizado – Aula 21

**👤 Nome:** Gabriel Moura
**🎯 Tema da Aula:** Fazendo Requisições HTTP (Chamadas de API) no Copilot Studio

---

## 📝 Resumo da Aula
> Aprendemos a realizar requisições a APIs externas diretamente do Microsoft Copilot Studio, sem a necessidade do Power Automate. Utilizamos a Brasil API como exemplo para consultar informações de um CEP. Para garantir que o CEP inserido pelo usuário (que pode conter traços) seja formatado corretamente para a API (apenas números), criamos uma entidade personalizada usando Expressão Regular (Regex). Em seguida, criamos um tópico que coleta o CEP do usuário, formata a URL da API concatenando o endpoint com o CEP (utilizando a função Power FX `Concat`), envia a requisição HTTP, processa a resposta JSON (obtendo o esquema a partir de um exemplo), armazena em uma variável do tipo Record e exibe as informações extraídas (cidade, estado, endereço) para o usuário.

---

## 🔍 Conceitos ou Ferramentas Apresentadas
- **Requisições HTTP / Chamadas de API:** A capacidade de o agente enviar solicitações (GET, POST, etc.) a serviços web externos (APIs) para enviar ou receber dados.
- **Brasil API:** Um exemplo de API pública brasileira utilizada na aula para consulta de CEPs.
- **Endpoint:** O URL específico de um recurso em uma API (ex: `/api/cep/v1/{cep}`).
- **Entidades Personalizadas (Custom Entities):** Permitem definir tipos de dados específicos que o agente deve reconhecer e extrair do input do usuário.
- **Expressão Regular (Regex):** Uma sequência de caracteres que define um padrão de busca. Utilizada para criar uma entidade personalizada que extrai apenas os dígitos numéricos de um CEP, removendo o traço.
- **Entidade `CEP Brasil` (exemplo):** Entidade personalizada criada com Regex para capturar CEPs no formato brasileiro (com ou sem traço) e extrair apenas os números.
- **Nó "Fazer uma pergunta":** Usado para coletar o CEP do usuário, associando-o à entidade personalizada `CEP Brasil` para garantir o formato correto na variável.
- **Variável (ex: `varCep`):** Variável do tipo texto (string) ou correspondente à entidade personalizada, usada para armazenar o CEP capturado do usuário.
- **Nó "Gerenciamento de variáveis - Definir valor de uma variável":** Usado para manipular o valor de variáveis, por exemplo, formatando strings ou realizando cálculos.
- **Power FX - Função `Concat`:** Função utilizada para concatenar (juntar) strings. Usada na aula para construir a URL completa da API concatenando o endpoint base com a variável que contém o CEP (após a entidade ter removido o traço).
- **Nó "Avançado - Enviar solicitação HTTP":** Permite configurar e enviar uma requisição HTTP a um URL especificado.
- **Método HTTP:** O tipo de operação HTTP (GET, POST, PUT, DELETE). `GET` é usado para buscar dados de uma API.
- **URL da Solicitação:** A URL completa da API a ser chamada, construída dinamicamente na aula usando a variável formatada com Power FX.
- **Tipo de Resposta:** O formato dos dados esperados na resposta da API (ex: JSON).
- **Dados de Exemplo (JSON):** Fornecer um exemplo da estrutura JSON esperada na resposta da API permite que o Copilot Studio crie automaticamente o "esquema" da resposta e mapeie os dados em variáveis estruturadas.
- **Obter esquema do JSON (Exemplo):** Ferramenta para colar um exemplo de resposta JSON e gerar o esquema para mapeamento em variáveis.
- **Variável do Tipo Record:** Uma variável estruturada que armazena dados JSON, com propriedades aninhadas acessíveis usando notação de ponto (ex: `varResultado.city`).
- **Nó "Enviar uma mensagem":** Usado para exibir os dados extraídos da resposta da API para o usuário, referenciando as propriedades da variável do tipo Record.

---

## 💡 O que eu aprendi de mais importante
> 1.  O Copilot Studio pode interagir diretamente com APIs externas usando o nó **"Enviar solicitação HTTP"**, sem a necessidade de um fluxo do Power Automate para chamadas simples.
> 2.  **Entidades personalizadas com Regex** são essenciais para validar e formatar o input do usuário de acordo com os requisitos da API (ex: remover traços de CEPs).
> 3.  **Power FX** é necessário para construir dinamicamente a URL da API, concatenando o endpoint base com os dados fornecidos pelo usuário (como o CEP).
> 4.  Fornecer um **exemplo da resposta JSON** da API é crucial para que o Copilot Studio entenda a estrutura dos dados e os mapeie corretamente em uma variável (tipo Record) para uso posterior (ex: exibir as informações).
> 5.  A capacidade de consultar APIs diretamente abre um vasto leque de possibilidades para o agente, permitindo que ele acesse e use dados em tempo real de sistemas externos.

---

## 🛠 Exercícios ou Atividades Práticas
 Crie um tópico para consultar informações de um CEP utilizando uma API pública. Use uma entidade Regex para formatar o input e uma requisição HTTP para chamar a API.

 **Pré-requisito:** Conhecer o endpoint de uma API pública de consulta de CEP que retorne JSON (ex: Brasil API - `https://brasilapi.com.br/api/cep/v1/{cep}`). Ter um exemplo da resposta JSON dessa API.

 **Passos:**

 **Parte 1: Criar Entidade Regex para CEP**
 1.  Navegar até a seção **Entidades** (no menu lateral) ou clicar em "Entidades" no menu superior.
 2.  Clicar em **"+ Nova entidade"** e selecionar **"Expressão Regex"**.
 3.  Nomear a entidade (ex: `CEP_Numeros`).
 4.  Inserir a expressão Regex para extrair apenas dígitos numéricos (ex: `\d+`).
 5.  Clicar em **"Salvar"**.

 **Parte 2: Criar o Tópico de Consulta de CEP**
 1.  Navegar até a seção **Tópicos**.
 2.  Clicar em **"Novo Tópico"** e selecionar **"Do zero"**.
 3.  Dar um **Título** ao tópico (ex: "Consulta de CEP").
 4.  Adicionar pelo menos 5 frases gatilho relevantes (ex: "Consultar CEP", "Verificar endereço por CEP", "Qual o endereço do CEP").
 5.  Adicionar um nó **"+"** e selecionar **"Fazer uma pergunta"**.
     *   Definir o texto da pergunta (ex: "Por favor, digite o CEP que deseja consultar:").
     *   Em "Identificar", selecionar a entidade **`CEP_Numeros`** (ou o nome que você deu na Parte 1).
     *   Salvar a resposta em uma **variável** (ex: `varCEP_Input`).
 6.  Adicionar um nó **"+"** e selecionar **"Gerenciamento de variáveis"** - **"Definir valor de uma variável"**.
     *   Clicar no ícone `{x}` para criar uma **nova variável** (ex: `varCEP_URL`). Esta variável armazenará a URL completa.
     *   Na caixa de fórmula, usar a função `Concat` para construir a URL:
         *   Inserir o endpoint base da API entre aspas duplas (ex: `"https://brasilapi.com.br/api/cep/v1/"`).
         *   Adicionar uma vírgula.
         *   Inserir a variável com o CEP (a que você capturou na pergunta, ex: `varCEP_Input`).
         *   Exemplo completo da fórmula: `Concat("https://brasilapi.com.br/api/cep/v1/", varCEP_Input)`
 7.  Adicionar um nó **"+"** e selecionar **"Avançado"** - **"Enviar solicitação HTTP"**.
     *   Em "URL da solicitação", clicar no ícone de variável `{x}` e selecionar a variável **`varCEP_URL`**.
     *   Em "Método HTTP", selecionar **"GET"**.
     *   Em "Tipo de resposta", selecionar **"JSON"**.
     *   Em "Dados de exemplo", clicar em **"Obter esquema do JSON (Exemplo)"**. Colar um exemplo real da resposta JSON da API de CEP e clicar em **"Confirmar"**. Note que uma variável do tipo Record é criada automaticamente (ex: `varResultado`).
     *   (Opcional) Renomear a variável do tipo Record se necessário.
 8.  Adicionar um nó **"+"** e selecionar **"Enviar uma mensagem"**.
     *   Digitar um texto introdutório (ex: "Informações do CEP:").
     *   Na mesma caixa de texto, adicionar as propriedades da variável Record usando a notação de ponto (ex: `Cidade: {varResultado.city}`, `Estado: {varResultado.state}`, `Endereço: {varResultado.street}`). Lembre-se que os nomes das propriedades (city, state, street) devem corresponder exatamente ao JSON de exemplo.
 9.  Adicionar um nó **"+"** e selecionar **"Gerenciamento de tópico"** - **"Encerrar o tópico atual"**.
 10. Clicar em **"Salvar"**.

 **Parte 3: Testar a Requisição HTTP**
 1.  No painel de **Teste**, dar um **Reload**.
 2.  Digitar uma frase gatilho para acionar o tópico de Consulta de CEP.
 3.  Quando o agente perguntar o CEP, digitar um **CEP válido** (com ou sem traço).
 4.  Observar a resposta do agente. Ele deve exibir as informações de Cidade, Estado e Endereço obtidas da API.
 5.  Testar com diferentes CEPs válidos.
 6.  (Opcional) Usar o mapa de atividades para ver o fluxo passando pelo nó "Enviar solicitação HTTP".

 **Dificuldades encontradas ou insights obtidos:**
 - Criar a expressão Regex correta para a entidade.
 - A sintaxe do Power FX (função `Concat`) para construir a URL dinâmica.
 - Obter e fornecer um exemplo **válido e completo** da resposta JSON da API para gerar o esquema corretamente.
 - Referenciar as propriedades corretas da variável Record (os nomes devem ser idênticos aos do JSON).
 - Debugar falhas na requisição HTTP (códigos de status, erros na URL). Testar a URL diretamente no navegador ou em ferramentas como Postman pode ajudar.
 - Descobrir que um CEP digitado no teste estava incorreto ou inexistente e causou uma falha na API, o que exigiu testar com um CEP válido.

---

## 📌 Aplicações no Trabalho
> A capacidade de fazer requisições HTTP diretamente permite que o agente:
> - **Acesse e exiba dados em tempo real** de sistemas que expõem APIs (ex: sistemas de inventário, status de pedidos, cotações, informações de produtos).
> - **Integre-se com serviços externos** que não possuem conectores prontos no Power Automate ou que precisam de interações mais diretas.
> - **Automatize a busca por informações** que estão disponíveis via web services.
> - **Construa interações mais dinâmicas** e baseadas em dados externos.

---

## ❓ Dúvidas ou Pontos a Revisar
- Como lidar com diferentes métodos HTTP (POST, PUT, DELETE) e passar dados no corpo da requisição.
- Como configurar cabeçalhos HTTP personalizados (Headers) para autenticação ou outros fins.
- Tratamento de erros nas respostas da API (códigos de status HTTP como 404, 500) e como comunicar isso ao usuário no agente.
- Lidar com respostas JSON mais complexas ou aninhadas e extrair dados de arrays.
- Alternativas para construir URLs dinâmicas ou manipular strings complexas no Power FX.
- Quando usar "Enviar solicitação HTTP" vs. "Adicionar uma ação" (Power Automate) para interagir com sistemas externos.
