### 📘 Registro de Aprendizado – Aula 8

**👤 Nome:** Gabriel Moura
**🎯 Tema da Aula:** Utilizando Fontes de Conhecimento do SharePoint

---

#### 📝 Resumo da Aula
> Aprendemos a utilizar fontes de conhecimento baseadas em sites do SharePoint para que nosso agente no Microsoft Copilot Studio (Copilot Studio) possa responder perguntas com base no conteúdo desses sites. Atualizamos o ícone do agente e desabilitamos o conhecimento geral da IA para focar exclusivamente nas fontes fornecidas. Adicionamos um site SharePoint como fonte, observamos o status de indexação e testamos fazendo perguntas sobre o conteúdo da página. Verificamos como o agente extrai informações, resume e fornece **referências diretas** para a fonte original.

---

#### 🔍 Conceitos ou Ferramentas Apresentadas
- **Ícone do Agente:** Imagem personalizada (`PNG`, máx. `30KB`) para representar o agente. Pode ser atualizado no designer.
- **Permitir que a IA use seus próprios conhecimentos gerais:** Flag que controla se o agente pode buscar informações além das fontes configuradas (usando conhecimento da OpenAI/GPT). Desabilitamos para forçar o uso exclusivo das fontes específicas (ver Aula 4).
- **Adicionar Conhecimento:** Opção para conectar o agente a diferentes fontes de informação.
- **SharePoint (como Fonte de Conhecimento):** Permite que o agente indexe o conteúdo de sites do SharePoint e use-o para responder perguntas.
- **URL do Site SharePoint:** O endereço base do site SharePoint a ser usado como fonte (sem níveis de profundidade excessivos como em URLs públicos).
- **Enriquecimento de Conteúdo (no SharePoint):** A importância de ter conteúdo textual relevante e bem estruturado nas páginas do SharePoint para otimizar a indexação pelo agente. Formatos suportados incluem `texto e documentos (PDF, Word)`, mas `não imagens`.
- **Status de Indexação:** Indica se a fonte de conhecimento (SharePoint) foi processada pelo agente e está pronta para uso ("Pronto"). O tempo de indexação depende do tamanho do site.
- **Autenticação (para SharePoint):** A fonte SharePoint só estará disponível para usuários finais do agente que tiverem as permissões de acesso adequadas ao site SharePoint original. O agente **verifica as permissões do usuário**.
- **Teste do Agente (com Fontes):** Utilizar o painel de teste para fazer perguntas e verificar se o agente consegue recuperar informações das fontes de conhecimento configuradas.
- **Modo de Depuração / Rastreamento da Sessão:** Ferramenta visual no painel de teste que mostra o fluxo lógico que o agente seguiu para responder, incluindo qual fonte foi consultada. Pode ser `desativado para melhor performance` (ver Aula 16).
- **Referências:** Ao usar fontes de conhecimento, o agente não apenas responde, mas também fornece links diretos para a(s) página(s) específica(s) onde a informação foi encontrada.

---

#### 💡 O que eu aprendi de mais importante
> 1.  Configurar fontes de conhecimento como sites SharePoint permite que o agente responda a perguntas baseadas em **conteúdo específico da organização**.
> 2.  É **crucial desabilitar** o conhecimento geral da IA para garantir que o agente se restrinja às fontes fornecidas, mantendo o foco e a precisão das respostas dentro do contexto desejado.
> 3.  A qualidade do conteúdo na fonte (principalmente texto) impacta diretamente a capacidade do agente de extrair informações relevantes. Documentos dentro do SharePoint (PDF, Word) também são indexados.
> 4.  A **segurança** é mantida: o agente respeita as permissões de acesso do usuário final ao site SharePoint, garantindo que apenas quem tem acesso à fonte original receba a informação.
> 5.  A capacidade de o agente fornecer **referências** diretas à fonte original aumenta a confiança na resposta e permite que o usuário aprofunde a informação.

---

#### 🛠 Exercícios ou Atividades Práticas
- **Descrição breve do exercício ou atividade:** Adicionar um ícone personalizado (`PNG` até `30KB`) ao agente criado na aula anterior. Desabilitar a opção "Permitir que a IA use seus próprios conhecimentos gerais". Adicionar um site SharePoint (ao qual tenho acesso) como fonte de conhecimento, observando o status de indexação. No painel de teste, fazer perguntas sobre o conteúdo do site SharePoint adicionado (ex: sobre pessoas, processos, informações contidas nas páginas) e verificar se o agente responde corretamente, extrai informações relevantes e fornece referências. Opcionalmente, ativar/desativar o modo de depuração.
- **Dificuldades encontradas ou insights obtidos:**
    - **Problema:** Encontrar ou criar um ícone PNG no tamanho correto pode exigir o uso de ferramentas de edição de imagem. **Insight:** Planeje o ícone com antecedência.
    - **Problema:** A indexação de sites SharePoint pode levar algum tempo. **Insight:** Para sites grandes, pode ser um processo demorado.
    - **Problema:** Problemas temporários (como o bug no navegador na aula) podem dificultar o teste imediato. **Insight:** Reiniciar o navegador ou aguardar pode resolver.
    - **Insight:** É importante garantir que o site SharePoint usado como fonte tenha conteúdo textual significativo para que o agente tenha algo a indexar.

---

#### 📌 Aplicações no Trabalho
> A utilização de fontes de conhecimento do SharePoint é uma das aplicações mais poderosas do Copilot Studio para o ambiente corporativo. Posso criar agentes que respondam a perguntas sobre:
> - **Políticas e procedimentos internos:** Baseando o agente em sites ou documentos do SharePoint contendo manuais e guias.
> - **Informações de RH:** FAQ sobre benefícios, processos de admissão/demissão, etc., baseados em páginas do SharePoint.
> - **Conhecimento técnico ou de produto:** Indexando wikis, bases de conhecimento ou documentação técnica armazenada no SharePoint.
> - **Dados de projetos ou equipes:** Respondendo perguntas sobre status de projetos ou informações de equipe armazenadas em sites SharePoint dedicados.
> Isso transforma o Copilot Studio em um assistente inteligente que acessa e sumariza o conhecimento distribuído na organização de forma segura e eficiente.

---

#### ❓ Dúvidas ou Pontos a Revisar
- Quais são os diferentes tipos de fontes de conhecimento (Sites Públicos, Arquivos, Dataverse, Conectores) e quando cada um é mais adequado para diferentes cenários de uso?
- Como gerenciar múltiplas fontes de conhecimento e o comportamento do agente quando a informação está presente em várias fontes?
- Qual é o impacto de diferentes níveis de permissão no SharePoint no que o agente consegue responder para diferentes usuários?
- Como otimizar o conteúdo no SharePoint para melhorar a qualidade das respostas do agente?
- Quais são os limites na quantidade de fontes de conhecimento ou no tamanho total do conteúdo indexado?
---