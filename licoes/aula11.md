### 📘 Registro de Aprendizado – Aula 11

**👤 Nome:** Gabriel Moura
**🎯 Tema da Aula:** Configurando Fontes de Conhecimento Oficiais

---

#### 📝 Resumo da Aula
> Nesta aula, aprendemos a designar uma ou mais fontes de conhecimento como "oficiais" dentro do Microsoft Copilot Studio (Copilot Studio). Demonstramos como fazer isso para uma fonte SharePoint existente. Explicamos que ao marcar uma fonte como oficial, o agente pode adicionar um disclaimer em suas respostas indicando que a informação provém de uma fonte autorizada. Vimos que esta configuração atualiza automaticamente as instruções do agente com um texto padrão (em `inglês`) e como esse disclaimer aparece junto à resposta no painel de teste. Enfatizamos a importância de usar essa funcionalidade para destacar fontes primárias de informação dentro da organização.

---

#### 🔍 Conceitos ou Ferramentas Apresentadas
- **Fontes Oficiais (Official Sources):** Uma funcionalidade (atualmente em `versão preliminar`) que permite marcar uma ou mais fontes de conhecimento configuradas como sendo fontes autorizadas ou primárias de informação.
- **Designar Fonte Oficial:** Opção disponível no menu de três pontos ao lado de cada fonte de conhecimento listada no painel de Conhecimento.
- **Atualizar Instruções do Agente:** Ao marcar uma fonte como oficial, o sistema oferece a opção de adicionar automaticamente um texto padrão (em `inglês`) às instruções gerais do agente, indicando seu comportamento em relação a fontes oficiais. Essa é uma configuração de `versão preliminar`.
- **Disclaimer (Baseado em fonte oficial):** Uma mensagem (atualmente em `inglês`) que aparece junto à resposta do agente no painel de teste (e presumivelmente para o usuário final, dependendo da publicação) quando a resposta é extraída de uma fonte oficial marcada.
- **Fonte da Verdade:** Termo utilizado para descrever a(s) fonte(s) de conhecimento considerada(s) `mais confiável(is) e autorizada(s)` dentro de uma organização.
- **Múltiplas Fontes Oficiais:** É possível marcar mais de uma fonte de conhecimento como oficial.

---

#### 💡 O que eu aprendi de mais importante
> 1.  Podemos conferir um status diferenciado a certas fontes de conhecimento, marcando-as como **"oficiais"**, para indicar sua autoridade ou confiabilidade.
> 2.  **Marcar uma fonte como oficial é um recurso em `versão preliminar` e pode afetar as instruções gerais do agente, adicionando um texto padrão relacionado a fontes oficiais.**
> 3.  Respostas baseadas em fontes oficiais marcadas podem exibir um **disclaimer** que valida a informação como vinda de uma fonte autorizada.
> 4.  Esta funcionalidade é útil para guiar o usuário final sobre a procedência da informação, especialmente quando o agente consulta múltiplas fontes com diferentes níveis de confiabilidade.

---

#### 🛠 Exercícios ou Atividades Práticas
- **Descrição breve do exercício ou atividade:** Acessar o painel de Conhecimento do agente que possui fontes configuradas (SharePoint, Sites Públicos, Arquivos). Selecionar uma das fontes que consideraria "oficial" (ex: a fonte SharePoint com dados internos críticos). Clicar no menu de três pontos ao lado dessa fonte e selecionar "Fonte oficial". Escolher a opção de "Atualizar as instruções do Agent" (lembrando que é versão preliminar). Ir para a Visão Geral do agente e verificar se o texto padrão foi adicionado às instruções. Testar o agente com uma pergunta que será respondida por essa fonte oficial e verificar se o disclaimer aparece junto à resposta. Opcionalmente, marcar outra fonte como oficial e testar novamente.
- **Dificuldades encontradas ou insights obtidos:**
    - **Insight:** O texto adicionado às instruções padrão do agente está em inglês, o que pode ser um ponto a considerar se o agente for em outro idioma. O disclaimer de fonte oficial também aparece em inglês (atualmente).
    - **Insight:** A funcionalidade em versão preliminar indica que pode mudar no futuro.
    - **Insight:** É interessante ver como o agente interage com a instrução adicionada e exibe o disclaimer.
    - **Insight:** A escolha de qual fonte é "oficial" é uma decisão de negócio/conteúdo.

---

#### 📌 Aplicações no Trabalho
> Designar fontes oficiais é importante para:
> - **Aumentar a confiança do usuário:** Ao indicar que uma resposta vem de uma fonte "oficial da empresa", o usuário tende a confiar mais na informação.
> - **Priorizar fontes de informação:** Embora não explicitado se isso altera o comportamento de busca, logicamente as fontes oficiais devem ser as "fontes da verdade" preferenciais.
> - **Gerenciamento de conhecimento:** Ajuda a organizar e certificar quais são os repositórios de informação primários para o agente.
> - **Conformidade:** Em alguns contextos, pode ser importante para conformidade ou auditoria destacar que a informação vem de uma fonte aprovada/oficial.

---

#### ❓ Dúvidas ou Pontos a Revisar
- É possível traduzir o texto padrão das instruções e do disclaimer para outros idiomas (como português)?
- Marcar uma fonte como oficial realmente altera a prioridade ou o algoritmo de busca do agente?
- Qual o impacto de ter múltiplas fontes oficiais – o disclaimer aparece se a resposta for de *qualquer* fonte oficial?
- Qual é o status futuro dessa funcionalidade (se sairá de versão preliminar e quais mudanças podem ocorrer)?
- Quais são exemplos práticos de texto de instruções personalizado relacionado a fontes oficiais?
---