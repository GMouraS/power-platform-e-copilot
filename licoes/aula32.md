### 📘 Registro de Aprendizado – Aula 32

**👤 Nome:** Gabriel Moura
**🎯 Tema da Aula:** Integração do Microsoft Copilot Studio com Power Apps

---

#### 📝 Resumo da Aula
> Nesta aula, exploramos a integração do Microsoft Copilot Studio (Copilot Studio) com o Power Apps, especificamente como um agente do Copilot Studio pode atuar como o "cérebro" de um copiloto embutido dentro de uma aplicação Power Apps. Demonstramos o processo de criar um Power App Canvas simples, conectar-se a uma lista do SharePoint e, crucialmente, configurar o "Copiloto do aplicativo" nas configurações do Power App. Isso permitiu selecionar um agente específico do Copilot Studio para fornecer a inteligência de conversação, transformando o Power App em um aplicativo com capacidades de IA interativas. Observamos que esta é uma funcionalidade `premium` e como o agente selecionado fornece as respostas e executa os tópicos por trás de uma interface de copiloto genérica.

---

#### 🔍 Conceitos ou Ferramentas Apresentadas
- **Microsoft Copilot Studio (Copilot Studio):** Ferramenta para criar e gerenciar agentes de conversação (ver Aula 2).
- **Power Apps:** Plataforma da Microsoft Power Platform para criar aplicações de negócio personalizadas (ver Aula 2).
- **Copiloto no Power Apps (Copilot in app):** Uma funcionalidade (atualmente em `versão preliminar`) que permite integrar um agente do Copilot Studio diretamente em um aplicativo Power Apps. Este agente atua como um assistente de IA dentro do contexto do aplicativo.
- **Recurso Premium:** Funcionalidades marcadas com um ícone de diamante no Power Apps ou Copilot Studio, indicando que exigem uma licença premium para uso. A funcionalidade "Copiloto no Power Apps" é um recurso `premium`.
- **Power Apps Maker Portal:** O ambiente de desenvolvimento do Power Apps, onde é possível criar, editar e gerenciar aplicativos. Inclui uma guia dedicada a "Agentes" que lista os copilotos criados no Copilot Studio.
- **Aplicativo Canvas (Canvas App):** Um tipo de aplicativo no Power Apps que permite aos criadores desenvolver uma interface de usuário altamente personalizada a partir de uma tela em branco.
- **SharePoint List:** Uma fonte de dados comum utilizada no Power Apps para armazenar e gerenciar informações (ver Aula 8).
- **Galeria Vertical (Vertical Gallery):** Um componente do Power Apps usado para exibir coleções de dados (ex: itens de uma lista SharePoint) em um formato de lista.
- **Integração de Agente (Configurações do Power App):** A opção dentro das "Configurações" de um Power App onde se pode selecionar qual agente do Copilot Studio será o "cérebro" do copiloto do aplicativo.
- **Publicação do Power App:** O processo de disponibilizar o aplicativo para ser usado pelos usuários (ver Aula 17).
- **Interface de Copiloto Genérica:** O botão e painel de chat que aparecem no canto superior direito do Power App quando a funcionalidade de copiloto é ativada. Por trás dessa interface, o agente do Copilot Studio selecionado é quem responde e executa as ações.
- **Orquestração de Inteligência:** O conceito de que o Power App atua como a interface de usuário, enquanto o agente do Copilot Studio fornece a inteligência de conversação e o acesso aos tópicos e automações (ver Aula 27).

---

#### 💡 O que eu aprendi de mais importante
> 1.  É possível integrar um agente do Copilot Studio em um Power App, permitindo que a inteligência de conversação do agente seja utilizada diretamente dentro da aplicação.
> 2.  O Power App atua como a **"capa" ou interface** do usuário, enquanto o agente do Copilot Studio selecionado nas configurações do Power App se torna o **"cérebro"** que processa as conversas e executa as lógicas.
> 3.  Esta integração é um **recurso `premium`**, o que implica em considerações de licenciamento para sua utilização.
> 4.  A combinação de Power Apps (para `input` e interface) e Copilot Studio (para `output` e inteligência de conversação) abre um **vasto mar de possibilidades** para soluções de negócio integradas e inteligentes.

---

#### 🛠 Exercícios ou Atividades Práticas
- **Descrição breve do exercício ou atividade:** Criar um aplicativo Power Apps simples com uma galeria de dados e, em seguida, integrar um agente existente do Microsoft Copilot Studio para que ele funcione como o copiloto do aplicativo.

    **Pré-requisito:**
    *   Ter acesso ao Power Apps Maker Portal.
    *   Ter um agente criado no Copilot Studio com tópicos funcionais (ex: o agente "Tina" com tópicos de "Consulta de CEP" e "Pedir Pizza" das aulas anteriores).
    *   Ter uma lista do SharePoint (ex: "Lista IBGE" com "Código IBGE" e "Município") para usar como fonte de dados no Power App.

    **Passos:**

    **Parte 1: Criar um Power App Canvas Simples**
    1.  Acessar o Power Apps Maker Portal.
    2.  Clicar em **"Criar"** no menu lateral.
    3.  Selecionar **"Aplicativo em branco"** e depois **"Aplicativo Canvas em branco"**.
    4.  Escolher o formato **"Tablet"** e dar um nome ao aplicativo (ex: "Aplicativo Copiloto Aula").
    5.  No designer do Power Apps, adicionar uma **"Fonte de Dados"** (ícone de cilindro no menu lateral).
    6.  Selecionar **"SharePoint"**, escolher a conexão, o site (ex: seu site SharePoint) e a lista (ex: "Lista IBGE").
    7.  Inserir um componente **"Galeria vertical"** na tela.
    8.  Conectar a galeria à "Lista IBGE" como fonte de dados.
    9.  Ajustar o layout da galeria para exibir o `Código IBGE` e o `Município` (ex: no título e subtítulo da galeria).

    **Parte 2: Integrar o Agente do Copilot Studio**
    1.  No Power Apps Designer, clicar nos três pontos (`...`) no menu lateral esquerdo e selecionar **"Configurações"**.
    2.  Na aba "Geral", procurar pela seção **"Copiloto"** (ou "Copiloto do aplicativo").
    3.  Ativar a opção de copiloto.
    4.  No dropdown, selecionar o agente do Copilot Studio desejado (ex: "Tina").
    5.  **Fechar** o painel de configurações.
    6.  **Salvar** o aplicativo.
    7.  **Publicar** o aplicativo.

    **Parte 3: Testar a Integração no Power App**
    1.  Voltar para a lista de aplicativos no Power Apps Maker Portal.
    2.  **Executar (Play)** o aplicativo recém-publicado.
    3.  A primeira vez, o aplicativo pode solicitar permissões de conexão (ex: SharePoint). Concedê-las.
    4.  No canto superior direito da interface do aplicativo em execução, localizar e clicar no botão do **Copiloto**.
    5.  O painel do copiloto será exibido. Interagir com ele usando frases que acionem tópicos do agente do Copilot Studio que foi integrado (ex: "Olá", "Consultar CEP", "Pedir pizza").
    6.  Observar como o copiloto no Power App utiliza a inteligência e os tópicos do agente do Copilot Studio para responder e interagir.

- **Dificuldades encontradas ou insights obtidos:**
    - **Problema:** A integração é um recurso `premium`. **Insight:** O licenciamento premium é necessário para utilizar essa funcionalidade.
    - **Insight:** A funcionalidade de "Criar Agente" diretamente no Power Apps Maker Portal (em "Criar" -> "Crie seu Agente") redireciona para o Copilot Studio, reforçando a integração da Power Platform.
    - **Insight:** O botão do copiloto no aplicativo (`UI`) é genérico, mas a inteligência por trás dele é fornecida pelo agente específico do Copilot Studio que foi configurado.
    - **Insight:** A combinação de um Power App para entrada e visualização de dados e um agente do Copilot Studio para consultas e automações é uma arquitetura poderosa para soluções de negócio.
    - **Problema:** Pode haver um pequeno atraso na propagação das configurações do copiloto após a publicação do Power App. **Insight:** Paciência ou um `reload` do aplicativo podem ser necessários.

---

#### 📌 Aplicações no Trabalho
> A integração do Microsoft Copilot Studio com Power Apps é altamente aplicável no ambiente de trabalho, permitindo:
> - **Aplicativos Mais Inteligentes:** Adicionar uma camada de inteligência conversacional a aplicativos de negócios existentes ou novos, tornando-os mais intuitivos e eficientes.
> - **Experiência do Usuário Aprimorada:** Usuários podem fazer perguntas em linguagem natural e obter respostas ou executar ações sem navegar por menus complexos do aplicativo.
> - **Automação Integrada:** Combinar a interface de um Power App (para `input` de dados) com a inteligência do agente (para `output` de informações ou orquestração de `workflows`) que interagem com sistemas de backend.
> - **Self-Service Avançado:** Criar aplicativos que capacitam os usuários a encontrar informações, solucionar problemas ou iniciar processos por conta própria, reduzindo a carga sobre equipes de suporte.

---

#### ❓ Dúvidas ou Pontos a Revisar
- Quais são os detalhes de licenciamento específicos para o uso do "Copiloto no Power Apps"?
- Quais são as opções de personalização da interface de usuário do copiloto dentro do Power App (ex: cor, posição, texto de boas-vindas)?
- Como passar o contexto ou dados específicos do Power App para o agente do Copilot Studio e vice-versa?
- Quais são os cenários de integração mais complexos, como usar o copiloto para interagir com os dados exibidos na galeria do Power App?
- Como o "layout personalizado" que a Microsoft menciona ao conectar um copiloto impacta o aplicativo?
---