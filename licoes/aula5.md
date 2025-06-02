# 📘 Registro de Aprendizado – Aula 5

**👤 Nome:** Gabriel Moura
**🎯 Tema da Aula:** Licenciamento e Gerenciamento de Capacidade no Microsoft Copilot Studio

---

## 📝 Resumo da Aula
> Nesta aula crucial, abordamos os diferentes modelos de licenciamento disponíveis para o Microsoft Copilot Studio, incluindo o "Pague pelo que usar", o "Pacote do Locatário" e a inclusão no "Microsoft 365 Copilot". Detalhamos como a capacidade é consumida (mensagens e sessões) e como diferentes tipos de interações (respostas clássicas, generativas, agentes autônomos, recursos premium) consomem essa capacidade de forma variada. Enfatizamos a importância de consultar a documentação oficial, que é dinâmica e pode mudar.

---

## 🔍 Conceitos ou Ferramentas Apresentadas
- **Licenciamento:** Modelos de custo para utilizar o Microsoft Copilot Studio.
- **Go (Pague pelo que usar):** Modelo de licenciamento baseado no consumo de mensagens. Custo por mensagem (atualmente $0.001/mensagem).
- **Pacote do Locatário:** Licença por locatário/mês ($200/mês) que inclui uma capacidade fixa de mensagens (25.000 mensagens/mês). A capacidade pode ser expandida comprando múltiplos pacotes.
- **Microsoft 365 Copilot:** Licença por usuário/mês ($30/usuário/mês) que concede acesso ao Copilot em várias aplicações M365 e inclui a capacidade de criar e publicar agentes do Copilot Studio para uso dentro do **Teams, SharePoint e Microsoft 365 Copilot** sem custo adicional de mensagens (capacidade "ilimitada" dentro deste escopo).
- **Mensagem:** Unidade de consumo de capacidade no Copilot Studio. A quantidade consumida varia dependendo do tipo de interação.
- **Resposta Clássica:** Resposta gerada por um tópico tradicional (baseado em regras e condições). Consome 1 mensagem de capacidade.
- **Resposta Generativa:** Resposta gerada utilizando as fontes de conhecimento e capacidades de IA (consulta a documentos, knowledge base geral). Consome 2 mensagens de capacidade.
- **Agentes Autônomos (Gatilhos):** Ações automatizadas acionadas de forma autônoma pela IA. Cada ação consome 25 mensagens de capacidade.
- **Microsoft Graph:** Interações com o Microsoft Graph (para dados de usuário, calendário, etc.). Consomem 30 mensagens de capacidade.
- **Ferramentas de IA Generativa Básicas:** Consomem 0.1 mensagem.
- **Mensagens Generativas de Texto Padrão:** Consomem 1.5 mensagens.
- **Recursos Premium de IA Generativa:** Funções de IA que podem melhorar o desempenho ou a concisão das respostas. Consomem 10 mensagens de capacidade. Relacionado à configuração "Recurso Premium" em IA Generativa no Designer.
- **Sessão:** Período de interação contínua com o agente. Uma sessão dura 60 minutos de inatividade. Após 60 minutos, a próxima interação inicia uma nova sessão.
- **Gerenciamento de Capacidade:** Painel ou documentação que detalha o consumo de mensagens pelos diferentes tipos de interações.
- **Excedente:** Ocorre quando a capacidade de mensagens licenciada é ultrapassada. Não bloqueia o ambiente, mas recursos podem ser limitados progressivamente.
- **Documentação Oficial:** Fonte primária e mais atualizada sobre licenciamento e consumo de capacidade.

---

## 💡 O que eu aprendi de mais importante
> 1.  O custo e a forma de implantação de um agente no Copilot Studio dependem diretamente do modelo de licenciamento escolhido. O modelo M365 Copilot ($30/usuário/mês) é vantajoso para uso interno no Teams/SharePoint, pois inclui a capacidade de mensagens sem custo adicional para este escopo.
> 2.  Nem toda "mensagem" consome 1 unidade de capacidade; interações mais complexas (respostas generativas, agentes autônomos, IA premium) consomem mais, o que exige planejamento.
> 3.  É fundamental entender como a capacidade é consumida por diferentes recursos (tópicos clássicos vs. IA generativa vs. automações) para estimar o custo real ou o uso da capacidade licenciada.
> 4.  A documentação oficial sobre licenciamento é **essencial** e deve ser consultada regularmente, pois as informações e os custos (em dólar) podem mudar.

---

## 🛠 Exercícios ou Atividades Práticas
- **Descrição breve do exercício ou atividade:** O exercício prático seria consultar a documentação oficial de licenciamento do Microsoft Copilot Studio (link a ser fornecido/encontrado) para ver os detalhes e comparar os diferentes modelos (Pay as you go, Tenant Pack, M365 Copilot). Tentar localizar a tabela de consumo de mensagens por tipo de interação.
- **Dificuldades encontradas ou insights obtidos:** A documentação pode ser extensa e requer atenção aos detalhes. Os valores em dólar exigem conversão para a moeda local e consideração de possíveis contratos diferenciados da organização. Entender a diferença entre "mensagem clássica", "mensagem generativa" e o consumo dos "agentes autônomos" é crucial para planejar a capacidade.

---

## 📌 Aplicações no Trabalho
> Antes de iniciar um projeto com Copilot Studio, especialmente se for para uso amplo ou externo, é crucial entender o modelo de licenciamento e o consumo esperado de mensagens. Isso permite:
> - **Estimativa de Custo:** Calcular o custo potencial do agente com base no uso esperado e no tipo de interações.
> - **Escolha do Modelo de Licença:** Selecionar o modelo de licenciamento mais adequado e econômico para o cenário de uso (interno M365 vs. externo/qualquer lugar).
> - **Otimização do Design:** Projetar o agente de forma a otimizar o consumo de mensagens, priorizando respostas clássicas onde possível para cenários de alto volume, se a capacidade for limitada.
> - **Planejamento de Capacidade:** Determinar se a capacidade padrão (25.000 mensagens/mês no pacote do locatário) é suficiente ou se pacotes adicionais serão necessários.

---

## ❓ Dúvidas ou Pontos a Revisar
- Como monitorar o consumo de mensagens e a capacidade utilizada em tempo real ou ao longo do tempo.
- Detalhes sobre como os recursos são "bloqueados progressivamente" ao exceder a capacidade.
- O impacto de diferentes contratos de licenciamento corporativo da Microsoft no custo do Copilot Studio.
- Cenários de uso que justificam o modelo "Pay as you go".
- Exemplos práticos de como calcular o consumo para um agente com diferentes tipos de interações.
