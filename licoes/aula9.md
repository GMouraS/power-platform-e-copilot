# 📘 Registro de Aprendizado – Aula 9

**👤 Nome:** Gabriel Moura
**🎯 Tema da Aula:** Utilizando Fontes de Conhecimento de Sites Públicos

---

## 📝 Resumo da Aula
> Aprendemos a adicionar sites públicos como fontes de conhecimento para o nosso agente no Microsoft Copilot Studio. Detalhamos a restrição de profundidade da URL (máximo dois níveis) ao adicionar sites públicos. Adicionamos exemplos como a documentação de funções DAX da Microsoft e a página da Seleção Brasileira na Wikipédia. Observamos como o agente, ao ser questionado, consulta essas novas fontes (juntamente com as já existentes, como SharePoint) e fornece respostas com referências. Enfrentamos alguns bugs temporários na interface de teste durante a demonstração, mas a funcionalidade básica foi mostrada.

---

## 🔍 Conceitos ou Ferramentas Apresentadas
- **Fontes de Conhecimento - Sites Públicos:** Capacidade de o agente buscar informações em URLs de sites acessíveis publicamente.
- **Restrição de Profundidade da URL:** Sites públicos adicionados como fonte não podem ter URLs com mais de dois níveis de profundidade (barras após o domínio principal). Ex: `site.com/nivel1/nivel2` é aceito; `site.com/nivel1/nivel2/nivel3` não.
- **Propriedade do Site:** Opção ao adicionar um site público para indicar se a organização é proprietária do site. Habilitar isso pode influenciar resultados de busca, possivelmente usando o Bing Search API para sites verificados.
- **Múltiplas Fontes de Conhecimento:** O agente pode consultar e mesclar informações de diferentes tipos de fontes configuradas (SharePoint, Sites Públicos, etc.) para responder a uma pergunta.
- **Teste com Múltiplas Fontes:** No painel de teste, podemos observar (idealmente via mapa de atividades/depuração) qual fonte foi consultada para responder a cada pergunta.
- **Referências Cruzadas:** O agente fornece links para a fonte específica (seja SharePoint ou site público) de onde a informação foi extraída.
- **Limitação na Quantidade de Sites Públicos:** Existe um limite não especificado na documentação apresentada, mas mencionado na aula (aparentemente, até 5 sites públicos podem ser adicionados por agente).

---

## 💡 O que eu aprendi de mais importante
> 1.  É possível expandir o conhecimento do agente para incluir informações da web pública, o que é útil para dados gerais ou documentação pública relevante.
> 2.  A adição de sites públicos como fonte de conhecimento tem uma limitação técnica importante quanto à **estrutura da URL (profundidade)**.
> 3.  O agente é capaz de consultar e sintetizar informações de **múltiplas fontes** configuradas (internas como SharePoint e externas como sites públicos) para fornecer uma resposta abrangente.
> 4.  Assim como no SharePoint, o agente fornece **referências** diretas para os sites públicos consultados, permitindo ao usuário verificar a fonte.

---

## 🛠 Exercícios ou Atividades Práticas
- **Descrição breve do exercício ou atividade:** Adicionar pelo menos um site público como fonte de conhecimento ao agente criado, certificando-se de que a URL respeita a limitação de profundidade (menos de 3 barras após o domínio). Tentar adicionar um URL com mais de dois níveis para ver a mensagem de erro. Adicionar um segundo site público. Testar o agente com perguntas que possam ser respondidas usando o conteúdo desses sites. Observar (se possível, sem bugs) quais fontes são consultadas para cada pergunta.
- **Dificuldades encontradas ou insights obtidos:** Lembrar da restrição de profundidade da URL ao copiar links. A interface de teste pode apresentar bugs temporários que dificultam a visualização completa do processo de busca e resposta. É interessante ver como o agente combina informações de diferentes fontes. A limitação na quantidade de sites públicos (embora não detalhada na aula/documentação mostrada) é um ponto a considerar no planejamento.

---

## 📌 Aplicações no Trabalho
> A capacidade de usar sites públicos permite que o agente:
> - Responda perguntas sobre produtos ou serviços da própria empresa, usando o site institucional como fonte.
> - Forneça informações sobre documentação técnica pública de softwares ou ferramentas utilizadas na organização.
> - Acesse FAQs públicas ou bases de conhecimento externas relevantes para o suporte ou operações.
> Combinado com fontes internas (SharePoint), um agente pode oferecer um ponto de acesso único para informações relevantes, sejam elas públicas ou privadas da empresa.

---

## ❓ Dúvidas ou Pontos a Revisar
- O limite exato na quantidade de sites públicos que podem ser adicionados.
- Como a opção "Propriedade do site" influencia os resultados de busca.
- Como o agente prioriza ou escolhe entre múltiplas fontes se a informação estiver disponível em mais de uma.
- O impacto da qualidade do conteúdo em sites públicos (ex: formatação complexa, JavaScript pesado) na capacidade de indexação e resposta do agente.
- Como lidar com bugs temporários na interface de teste (reiniciar, trocar de navegador, aguardar).
