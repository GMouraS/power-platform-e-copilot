# 📘 Registro de Aprendizado – Aula [Número]

**👤 Nome:** Gabriel Moura
**🎯 Tema da Aula:** Criando e Integrando Automações (Ações) do Power Automate no Copilot Studio

---

## 📝 Resumo da Aula
> Aprendemos a criar nossa primeira automação utilizando o Power Automate, que no contexto do Copilot Studio é chamada de "Ação". Demonstramos como criar um novo fluxo do Power Automate diretamente da interface do Copilot Studio, configurando-o para receber inputs (nome do usuário, reclamação) do agente e retornar uma resposta. O fluxo criado adiciona uma linha a uma tabela em um arquivo Excel no SharePoint. Integramos essa ação a um novo tópico no Copilot Studio, capturando a reclamação do usuário com um nó "Fazer uma pergunta", passando essa informação e o nome do usuário (variável do sistema) para o fluxo do Power Automate, e exibindo o retorno do fluxo para o usuário. Finalmente, testamos a integração, realizando a conexão necessária pela primeira vez, e verificamos o histórico de execução do fluxo no Power Automate e a atualização na planilha Excel.

---

## 🔍 Conceitos ou Ferramentas Apresentadas
- **Ações (Actions):** É como o Microsoft Copilot Studio se refere às automações criadas no Power Automate que podem ser chamadas pelo agente.
- **Adicionar uma Ação:** Opção no menu de criação de nós dentro de um tópico, ou na seção "Ações" na Visão Geral/Painel lateral, para integrar um fluxo do Power Automate.
- **Novo Fluxo do Power Automate:** Opção para criar um fluxo do zero, sendo redirecionado para o designer do Power Automate, mas já pré-configurado com um gatilho "Executar um fluxo do Copilot Studio" e uma ação "Responder ao Copilot Studio".
- **Gatilho "Executar um fluxo do Copilot Studio":** O ponto de partida do fluxo do Power Automate que recebe inputs do agente.
- **Inputs do Gatilho:** Parâmetros que o agente envia para o fluxo do Power Automate (definidos como texto, número, booleano, etc., no gatilho).
- **Ação "Responder ao Copilot Studio":** O ponto final do fluxo do Power Automate que envia outputs de volta para o agente.
- **Outputs da Ação:** Respostas ou resultados que o fluxo do Power Automate envia de volta para o agente.
- **Conector do Excel (Online) Business / SharePoint:** Conector utilizado no Power Automate para interagir com arquivos Excel armazenados no SharePoint.
- **Ação "Adicionar uma linha em uma tabela":** Ação específica do conector Excel para inserir dados em uma tabela dentro de um arquivo Excel.
- **Tabela no Excel:** É fundamental que os dados no arquivo Excel estejam formatados como Tabela (com nome definido) para que o Power Automate consiga interagir com eles.
- **UTCNow():** Função do Power Automate que retorna a data e hora UTC atual. Utilizada para carimbar a data automaticamente na linha do Excel.
- **Variável de Sistema `user.displayName` (ou similar):** Variável pré-definida no Copilot Studio que contém o nome do usuário logado (ou outras informações do perfil), útil para passar dados do usuário para o fluxo.
- **Variável Customizada (`varReclamação`):** Variável criada no tópico para armazenar a resposta do usuário (a reclamação).
- **Integração da Ação no Tópico:** Adicionar um nó "Adicionar uma ação" no designer do tópico e selecionar o fluxo criado. Mapear as variáveis do Copilot Studio (inputs do fluxo) e utilizar o retorno do fluxo (output) em nós subsequentes (ex: um nó "Enviar uma mensagem").
- **Conexão:** A primeira vez que um fluxo do Power Automate é chamado pelo Copilot Studio, é necessário autorizar a conexão entre o Copilot Studio e os serviços que o fluxo utiliza (neste caso, Excel/SharePoint). Esta autorização é feita pelo usuário que está testando ou usando o agente.
- **Histórico de Execução do Fluxo:** No portal do Power Automate, é possível visualizar o histórico detalhado de cada vez que o fluxo foi executado, incluindo status (Sucesso, Falha) e os inputs/outputs.
- **Gerenciamento de Tópicos - Encerrar Tópico Atual:** Nó adicionado ao final do fluxo do tópico para finalizar a conversa sobre aquele assunto após a automação ser executada e a resposta exibida.

---

## 💡 O que eu aprendi de mais importante
> 1.  A integração entre o Copilot Studio e o Power Automate, chamada de "Ações", é extremamente poderosa, permitindo que o agente não apenas converse, mas também **execute tarefas automatizadas** que interagem com outros sistemas.
> 2.  A criação de um fluxo "para o Copilot Studio" no Power Automate envolve definir **inputs (o que o agente envia)** e **outputs (o que o fluxo devolve)**.
> 3.  Podemos usar **variáveis do agente** (tanto de sistema como capturadas do usuário) para fornecer dados ao fluxo do Power Automate.
> 4.  A **primeira execução de um fluxo** pelo agente requer uma autorização de conexão, mas essa conexão é geralmente persistente para o usuário.
> 5.  É possível **verificar o sucesso** da automação tanto pela resposta do agente quanto pelo histórico de execução do fluxo no portal do Power Automate e pela verificação do sistema de destino (a planilha Excel, neste caso).

---

## 🛠 Exercícios ou Atividades Práticas
 Crie um fluxo do Power Automate que receba dados do Copilot Studio e os registre em uma planilha Excel no SharePoint/OneDrive. Integre este fluxo a um tópico no Copilot Studio e teste a automação.

 **Pré-requisito:**
 *   Ter acesso a um site SharePoint ou OneDrive.
 *   Ter um agente criado no Copilot Studio (preferencialmente dentro de uma solução).

 **Passos:**

 **Parte 1: Preparar o Arquivo Excel no SharePoint/OneDrive**
 1.  No SharePoint ou OneDrive, criar ou navegar até uma pasta (ex: "Dados Copilot").
 2.  Dentro da pasta, criar um novo arquivo **Excel**.
 3.  Adicionar cabeçalhos para as colunas que você deseja preencher (ex: `Data`, `Usuário`, `Reclamação`).
 4.  Selecionar as células com os cabeçalhos e formatá-las como **Tabela** (Menu **Inserir**  **Tabela**).
 5.  No menu "Design da Tabela" (ou similar), dar um **nome** fácil de identificar para a tabela (ex: `TabReclamacoes`). Fechar e salvar o arquivo.

 **Parte 2: Criar o Fluxo do Power Automate (Ação)**
 1.  No Microsoft Copilot Studio, navegar até a seção **Ações** (no menu lateral) ou, dentro de um tópico, adicionar um nó "+" - "Adicionar uma ação".
 2.  Clicar em **"Adicionar uma ação"** e depois em **"Novo fluxo do Power Automate"**. Isso abrirá o portal do Power Automate em uma nova aba com um fluxo base.
 3.  **Renomear** o fluxo (ex: `Registrar Reclamacao Copilot`).
 4.  No gatilho **"Executar um fluxo do Copilot Studio"**:
     *   Clicar em **"Adicionar um input"**.
     *   Selecionar **"Texto"** e nomear o input como `NomeUsuario`.
     *   Clicar em **"Adicionar um input"** novamente.
     *   Selecionar **"Texto"** e nomear o input como `DescricaoReclamacao`.
 5.  Adicionar uma nova etapa (**+ Novo passo**): Buscar pelo conector **"Excel Online (Business)"** (se usando SharePoint) ou **"Excel Online (OneDrive)"** (se usando OneDrive pessoal).
 6.  Selecionar a ação **"Adicionar uma linha em uma tabela"**.
 7.  Configurar a ação "Adicionar uma linha em uma tabela":
     *   Selecionar a **Localização** (SharePoint ou OneDrive group/folder).
     *   Selecionar a **Biblioteca de Documentos** (ex: "Documentos" para SharePoint).
     *   Selecionar o **Arquivo** (navegar até o arquivo Excel criado na Parte 1).
     *   Selecionar a **Tabela** (escolher o nome da tabela, ex: `TabReclamacoes`).
     *   Mapear os campos da tabela usando o **conteúdo dinâmico**:
         *   Campo `Data`: Usar a expressão **`utcNow()`** (vá na aba "Expressão").
         *   Campo `Usuário`: Selecionar o input **`NomeUsuario`** do gatilho.
         *   Campo `Reclamação` (ou nome similar): Selecionar o input **`DescricaoReclamacao`** do gatilho.
 8.  No retorno **"Responder ao Copilot Studio"**:
     *   Clicar em **"Adicionar uma saída"**.
     *   Selecionar **"Texto"** e nomear a saída como `RetornoSucesso`.
     *   Inserir um texto estático na saída (ex: `"Reclamação registrada com sucesso!"`).
 9.  Clicar em **"Salvar"** no topo do designer do Power Automate.

 **Parte 3: Integrar o Fluxo no Tópico do Copilot Studio**
 1.  Voltar ao Microsoft Copilot Studio. Se abriu em outra aba, a lista de Ações deve atualizar automaticamente. Se não, atualize manualmente ou acesse a seção "Ações" no menu lateral. O novo fluxo deve aparecer na lista.
 2.  Criar um **Novo Tópico em branco** (ou editar um existente, ex: o tópico de pizza, adicionando gatilhos relacionados a reclamações).
 3.  Adicionar **Frases gatilho** relevantes para registrar uma reclamação (ex: "Quero reclamar", "Fazer uma reclamação", "Registrar um problema").
 4.  Adicionar um nó **"+"** e selecionar **"Fazer uma pergunta"**.
     *   Definir o texto da pergunta (ex: "Por favor, descreva sua reclamação:").
     *   Em "Identificar", selecionar **"Resposta inteira do usuário"**.
     *   Salvar a resposta em uma **variável** (renomear para algo claro, ex: `varDescricaoReclamacao`).
 5.  Adicionar um nó **"+"** e selecionar **"Adicionar uma ação"**.
     *   Na lista, selecionar o fluxo do Power Automate que você acabou de criar (`Registrar Reclamacao Copilot`).
     *   Mapear os inputs do fluxo usando as variáveis do Copilot Studio:
         *   Input `NomeUsuario`: Clicar no ícone de variável `{x}` e selecionar a variável de sistema **`user.displayName`**.
         *   Input `DescricaoReclamacao`: Clicar no ícone de variável `{x}` e selecionar a variável **`varDescricaoReclamacao`** (a que capturou a resposta do usuário).
 6.  Adicionar um nó **"+"** e selecionar **"Enviar uma mensagem"** após a ação do Power Automate (no caminho de sucesso da ação).
     *   Neste nó, exibir o retorno do fluxo: Clicar no ícone de variável `{x}` e selecionar a saída **`RetornoSucesso`** do seu fluxo Power Automate.
 7.  Adicionar um nó **"+"** e selecionar **"Gerenciamento de tópico"** e depois **"Encerrar o tópico atual"**.
 8.  Clicar em **"Salvar"** no topo do designer do tópico.

 **Parte 4: Testar a Automação**
 1.  No painel de **Teste** do Copilot Studio, dar um **Reload**.
 2.  Digitar uma das **frases gatilho** do tópico de reclamação (ex: "Quero reclamar").
 3.  Responder à pergunta com a descrição da reclamação (ex: "O produto chegou danificado.").
 4.  Na **primeira execução**, o agente solicitará permissão para usar a automação. Clicar em **"Conectar-se"** e autorizar as conexões necessárias (Excel/SharePoint). Clicar em "Enviar" para tentar novamente.
 5.  Observar a resposta do agente (deve ser a mensagem definida na saída do fluxo, ex: "Reclamação registrada com sucesso!").
 6.  Para verificar o sucesso da automação:
     *   Navegar até o portal do Power Automate (utilize o atalho no Copilot Studio se necessário).
     *   Ir na seção **"Meus fluxos"**.
     *   Localizar o fluxo criado (`Registrar Reclamacao Copilot`).
     *   Verificar o **Histórico de execuções**. Deve haver uma execução recente com status **"Sucesso"**. Clicar nela para ver detalhes dos inputs/outputs.
     *   Abrir o arquivo **Excel** no SharePoint/OneDrive criado na Parte 1. Uma nova linha deve ter sido adicionada com a data/hora, seu nome de usuário e a descrição da reclamação.

 **Dificuldades encontradas ou insights obtidos:**
 - Formatar os dados no Excel como Tabela e dar um nome a ela é um passo crucial para o Power Automate.
 - Mapear corretamente os inputs e outputs entre o Copilot Studio e o Power Automate exige atenção ao conteúdo dinâmico e às variáveis.
 - A solicitação de conexão na primeira execução é um comportamento esperado.
 - Verificar o histórico de execução no Power Automate e a atualização no sistema de destino (Excel) são passos fundamentais para confirmar que a automação funcionou.
 - A capacidade de combinar conversa, captura de dados e ação externa em um único fluxo é muito poderosa.
---

## 📌 Aplicações no Trabalho
> Integrar o Power Automate permite que o agente vá muito além de apenas responder perguntas. Ele pode:
> - **Registrar informações** em sistemas (SharePoint Lists, Dataverse, Excel, SQL Server).
> - **Criar ou atualizar itens** (tarefas no Planner, cards no Azure DevOps, registros no Dynamics 365).
> - **Enviar notificações** (e-mails, mensagens no Teams).
> - **Aprovar solicitações**.
> - **Coletar dados de outros sistemas**.
> Essencialmente, permite que o agente participe ativamente dos processos de negócio, transformando conversas em ações concretas.

---

## ❓ Dúvidas ou Pontos a Revisar
- Mais exemplos de como passar diferentes tipos de dados (números, datas, booleanos, arrays) entre Copilot Studio e Power Automate.
- Como lidar com fluxos que falham (tratamento de erros no Power Automate e comunicação com o usuário no Copilot Studio).
- O uso de Outputs no fluxo para retornar dados processados para o agente usar em respostas ou lógica posterior.
- Explorar outros conectores do Power Automate que podem ser úteis para agentes (Outlook, Teams, Dataverse, etc.).
- O licenciamento específico para o uso de fluxos do Power Automate acionados pelo Copilot Studio.
- Melhores práticas para organizar Ações no Power Automate para uso no Copilot Studio.
