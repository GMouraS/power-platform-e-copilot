### 📘 Registro de Aprendizado – Aula 24

**👤 Nome:** Gabriel Moura
**🎯 Tema da Aula:** Enriquecendo Adaptive Cards com Dados Dinâmicos (Power FX)

---

#### 📝 Resumo da Aula
> Nesta aula, aprendemos a transformar Adaptive Cards estáticos em elementos dinâmicos, exibindo informações provenientes de variáveis do agente. A chave para isso é a transição do modo de edição `JSON` para o modo **Fórmula** no editor de Adaptive Cards do Microsoft Copilot Studio. Demonstramos como referenciar variáveis de tópico e globais diretamente no `JSON` do card usando a sintaxe `Power FX` (operador `&` e notação de ponto), permitindo que dados como "Estado", "Cidade" e "Endereço" (obtidos de uma API de CEP, como na aula anterior) sejam automaticamente preenchidos. Enfatizamos que, ao usar o modo Fórmula, a visualização prévia do card não está disponível no designer, mas a funcionalidade é mantida durante a execução. O teste confirmou a exibição personalizada das informações.

---

#### 🔍 Conceitos ou Ferramentas Apresentadas
- **Adaptive Cards (Cards Adaptativos):** Uma forma de UI declarativa que permite criar interfaces ricas e interativas diretamente no chat do agente (ver Aula 23).
- **Modo de Edição `JSON` (Adaptive Card):** O modo padrão no editor de Adaptive Cards no Copilot Studio onde o card é definido por seu código `JSON` estático. Não permite referenciar variáveis dinâmicas diretamente.
- **Modo de Edição Fórmula (Adaptive Card):** Um modo de edição avançado para Adaptive Cards no Copilot Studio que permite injetar dados dinâmicos de variáveis usando expressões `Power FX` no `JSON` do card. A interface visual de design do card não está disponível neste modo.
- **`Power FX`:** Linguagem de fórmula de baixo código usada na Microsoft Power Platform, semelhante às funções do Microsoft Excel, que permite manipulação de dados e lógica (ver Aula 2, Aula 14).
- **Operador de Concatenação (`&`):** Um operador `Power FX` utilizado para juntar (concatenar) strings. Essencial para combinar texto estático com valores de variáveis em Adaptive Cards.
- **Variáveis de Tópico (`Topic`):** Variáveis com escopo limitado ao tópico atual, acessadas usando `Topic.NomeDaVariavel` (ver Aula 14).
- **Variáveis Globais (`Global`):** Variáveis acessíveis de qualquer tópico dentro do agente, acessadas usando `Global.NomeDaVariavel` (ver Aula 14).
- **Referência de Variáveis em Adaptive Cards:** A sintaxe para incluir o valor de uma variável em um card no modo Fórmula, como `& Topic.Estado` ou `& Global.MinhaVariavel`.
- **Validação em Tempo Real:** O editor de `Power FX` verifica a sintaxe das expressões em tempo real, indicando erros (com coloração vermelha) ou sucesso (verde).
- **Preenchimento Dinâmico:** A capacidade de um Adaptive Card de exibir informações que variam com base nos dados de uma conversa ou em resultados de ações (como chamadas de API).
- **Brasil API:** Exemplo de API pública usada em aulas anteriores para consulta de CEP, cujos resultados são usados para preencher dinamicamente o card (ver Aula 21, Aula 22).

---

#### 💡 O que eu aprendi de mais importante
> 1.  É possível exibir dados dinâmicos de variáveis em Adaptive Cards no Copilot Studio, permitindo criar interfaces de usuário **personalizadas e ricas em dados**.
> 2.  Para injetar dados dinâmicos, é **obrigatório** mudar o editor do Adaptive Card para o modo **Fórmula**, o que desabilita a visualização gráfica no designer.
> 3.  A injeção de variáveis em Adaptive Cards é feita utilizando a sintaxe `Power FX`, como `& Topic.NomeDaVariavel`, para concatenar texto estático com valores de variáveis.
> 4.  A capacidade de exibir informações dinâmicas de APIs diretamente em cards amplia significativamente o potencial de personalização e utilidade dos agentes.

---

#### 🛠 Exercícios ou Atividades Práticas
- **Descrição breve do exercício ou atividade:** Transformar o Adaptive Card estático de consulta de CEP (criado na aula anterior) em um card dinâmico, que exiba as informações de Estado, Cidade e Endereço obtidas da API.

    **Pré-requisito:** Ter o tópico de consulta de CEP com um Adaptive Card estático e que já esteja capturando as informações de Estado, Cidade e Endereço em variáveis (sejam elas de um `Record` de resposta HTTP ou de saídas de um fluxo Power Automate) (ver Aula 21, Aula 22, Aula 23).

    **Passos:**
    1.  Abrir o tópico de **Consulta de CEP** no Microsoft Copilot Studio.
    2.  Clicar no nó **"Perguntar com um cartão adaptável"** que contém o card estático.
    3.  No editor de Adaptive Card, mudar a opção de **"JSON"** para **"Fórmula"**.
    4.  Localizar os elementos de `Text Block` onde as informações de Estado, Cidade e Endereço deveriam aparecer (ex: onde estava "Estado:").
    5.  Modificar o `text` de cada `Text Block` para incluir a referência à variável, utilizando o operador `&` para concatenar o texto estático com o valor da variável. Certifique-se de que a variável já existe no tópico (ex: `varResultado.state` se for um `Record` da requisição HTTP, ou `Estado` se for uma saída de um fluxo Power Automate).
        *   Exemplo para Estado: `"Estado: " & Topic.varResultado.state` (ajuste o nome da variável conforme o seu tópico).
        *   Exemplo para Cidade: `"Cidade: " & Topic.varResultado.city`
        *   Exemplo para Endereço: `"Endereço: " & Topic.varResultado.street`
    6.  Observar a coloração verde no editor de fórmula, indicando que a sintaxe `Power FX` está correta.
    7.  Clicar em **"Salvar"** no topo do designer do tópico.
    8.  No painel de **Teste**, dar um **Reload**.
    9.  Acionar o tópico de Consulta de CEP e fornecer um CEP válido (ex: `07060101`).
    10. Observar a resposta do agente: um Adaptive Card deve aparecer com as informações de Estado, Cidade e Endereço **preenchidas dinamicamente** com os dados da API.

- **Dificuldades encontradas ou insights obtidos:**
    - **Problema:** A ausência da visualização prévia no modo Fórmula pode ser desafiadora inicialmente para o design. **Insight:** O design deve ser feito no Adaptive Card Designer e depois adaptado para o modo Fórmula.
    - **Problema:** A sintaxe `Power FX` para referenciar variáveis e usar o operador `&` exige precisão. **Insight:** Pequenos erros de digitação ou formatação podem causar falhas.
    - **Insight:** O validador em tempo real do editor de `Power FX` (indicando erros em vermelho) é extremamente útil para depuração.
    - **Insight:** A funcionalidade de exibir dados dinâmicos é um salto qualitativo para a interface do agente.

---

#### 📌 Aplicações no Trabalho
> A capacidade de enriquecer Adaptive Cards com dados dinâmicos é fundamental para criar agentes que oferecem uma experiência de usuário superior, permitindo:
> - **Exibir resultados de consultas** de forma visualmente atraente (ex: status de pedido, cotações, informações de produtos).
> - **Personalizar a interação** apresentando informações específicas do usuário (ex: dados do perfil, histórico).
> - **Criar dashboards ou resumos interativos** diretamente no chat, usando dados de sistemas externos.
> - **Melhorar a legibilidade** e a compreensão de informações complexas que seriam difíceis de apresentar em texto simples.

---

#### ❓ Dúvidas ou Pontos a Revisar
- Quais são os cenários mais complexos de uso de `Power FX` para manipular dados antes de exibi-los em um Adaptive Card?
- Quais são outros elementos de Adaptive Cards que podem ser preenchidos dinamicamente além de `Text Block` (ex: imagens, `Input.Text`)?
- Como lidar com cenários onde uma variável referenciada em um Adaptive Card pode estar vazia ou nula?
- Como a "Edição Fórmula" se relaciona com a criação de `JSON` dinâmico (com arrays ou objetos aninhados)?
- Quais são as melhores práticas para o design de Adaptive Cards quando a visualização prévia não está disponível no editor?
---