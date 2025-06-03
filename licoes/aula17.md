### 📘 Registro de Aprendizado – Aula 17

**👤 Nome:** Gabriel Moura
**🎯 Tema da Aula:** Publicando o Agente e Utilizando no Microsoft Teams

---

#### 📝 Resumo da Aula
> Aprendemos a publicar nosso agente e disponibilizá-lo para uso no Microsoft Teams e no Microsoft 365 Copilot. Demonstramos como habilitar o canal Teams, editar os detalhes de apresentação do agente (ícone, cor, descrições), configurar as opções de disponibilidade (compartilhamento, link direto, loja de aplicativos do Teams) e, finalmente, como adicionar e interagir com o agente diretamente no Teams. Observamos como os diferentes tipos de respostas (geradas por IA versus tópicos manuais) se apresentam e a importância de garantir que o agente esteja publicado com a versão **mais recente**.

---

#### 🔍 Conceitos ou Ferramentas Apresentadas
- **Publicar (Publish):** O processo de disponibilizar a versão **mais recente** do agente para ser utilizada pelos usuários nos canais configurados.
- **Canais:** Seção no Microsoft Copilot Studio (Copilot Studio) onde se configura e gerencia as plataformas em que o agente estará disponível (Teams, Sites, Mobile Apps, etc.).
- **Teams e Microsoft 365:** Um dos canais de publicação, permitindo que o agente seja usado como um aplicativo no Microsoft Teams e integrado ao Microsoft 365 Copilot (se a licença for pertinente).
- **Adicionar Canal / Habilitar Serviço:** Ativar um canal de publicação específico para o agente.
- **Disponibilizar no Microsoft 365 Copilot:** Opção para integrar o agente no chat principal do M365 Copilot (requer licença M365 Copilot).
- **Editar Detalhes:** Opção para personalizar a aparência do agente no canal (ícone `PNG 30KB`, cor, descrição curta, descrição longa, informações do desenvolvedor).
- **Configurações do Teams:** Opções para decidir onde o agente pode ser adicionado no Teams (chats individuais, grupos, reuniões, equipes).
- **Opções de Disponibilidade:** Controles sobre como o agente pode ser encontrado e adicionado pelos usuários no Teams.
    - **Gerenciar Compartilhamento:** Convidar usuários ou grupos específicos (com permissões de visualizador ou editor). Similar ao compartilhamento geral do agente.
    - **Link Direto:** Gerar um URL que permite aos usuários adicionarem o agente diretamente no Teams.
    - **Baixar Arquivo:** Obter um pacote para adicionar o agente à loja de aplicativos do Microsoft 365 (`requer aprovação do administrador do Teams`).
    - **Mostrar na Loja:** Configurar quem pode ver o agente na loja de aplicativos do Teams (apenas colegas, toda a organização - `requer aprovação do administrador do Teams`).
- **Ver Agente no Teams:** Atalho direto no painel de Canais para abrir o Teams e iniciar o processo de adicionar o agente.
- **Processo de Adição no Teams:** Como o usuário final adiciona o agente (clicando no link ou buscando na loja) e a tela de informações (descrição, permissões) antes de adicionar.
- **Interação no Teams:** Como a conversa com o agente aparece no chat do Teams.
- **Tópico Iniciar Conversa:** O tópico padrão que é disparado na primeira interação do usuário com o agente no Teams (ver Aula 18, sobre como desabilitar para usar Prompts Iniciais).
- **Rótulo "Gerado por IA":** Um **indicador visual** que aparece nas respostas geradas pelas fontes de conhecimento via IA generativa, diferenciando-as de respostas de tópicos com lógica manual.
- **Autenticação Microsoft:** Tipo de autenticação selecionado que restringe a publicação do agente principalmente aos canais Teams e M365 para uso interno.
- **Alertas de Segurança/Saúde do Agente:** Notificações no painel de Canais sobre o status de compartilhamento e possíveis riscos de segurança (ex: compartilhado com todos os usuários da organização).

---

#### 💡 O que eu aprendi de mais importante
> 1.  Publicar o agente é um passo separado da criação e salva as alterações para disponibilização nos canais.
> 2.  A publicação no **Teams** é um dos canais mais comuns para uso interno, permitindo que o agente funcione como um aplicativo de chat.
> 3.  É crucial **personalizar a aparência** do agente no Teams (ícone, descrições) para torná-lo reconhecível e útil para os usuários.
> 4.  O controle de **disponibilidade** (compartilhamento com usuários/grupos específicos ou disponibilização na loja via **aprovação do administrador do Teams**) é **fundamental** para gerenciar o acesso ao agente na organização.
> 5.  A experiência do usuário no Teams inclui o tópico "Iniciar Conversa", a interação via chat e indicadores visuais como o rótulo "Gerado por IA" e a indicação de digitação.

---

#### 🛠 Exercícios ou Atividades Práticas
- **Descrição breve do exercício ou atividade:** Publicar a versão mais recente do agente. Acessar a seção "Canais" e clicar em "Teams e Microsoft 365". Habilitar o canal. Editar os detalhes do agente para o Teams, adicionando um ícone (`PNG 30KB`) e descrições curta/longa. Explorar as opções de disponibilidade (compartilhamento, link, loja). Usar a opção "Ver agente no Teams" para abrir o aplicativo Teams e adicionar o agente. Após adicionar, iniciar uma conversa para acionar o tópico "Iniciar Conversa". Fazer perguntas que acionem tópicos manuais e perguntas que usem fontes de conhecimento, observando a resposta e o rótulo "Gerado por IA". Testar o tópico de pizza criado anteriormente no Teams.
- **Dificuldades encontradas ou insights obtidos:**
    - **Problema:** O ícone e outros detalhes visuais podem demorar um pouco para atualizar no Teams. **Insight:** Tenha paciência, a propagação leva tempo.
    - **Problema:** O processo de adição via loja pode exigir interação com a área de TI. **Insight:** Planeje a aprovação com o administrador de TI.
    - **Insight:** Entender as diferentes opções de disponibilidade é importante para controlar quem terá acesso.
    - **Insight:** É interessante ver como o agente se comporta no ambiente real do Teams e a diferença visual entre respostas geradas pela IA e as definidas manualmente.
    - **Problema:** Bugs temporários podem ocorrer no Teams (como na aula) e exigem paciência ou recarga. **Insight:** Reiniciar o Teams ou tentar novamente pode resolver.

---

#### 📌 Aplicações no Trabalho
> Publicar um agente no Teams permite:
> - **Disponibilizar suporte e automação** diretamente na plataforma de colaboração já utilizada pela maioria dos funcionários.
> - **Facilitar o acesso** a informações internas ou processos automatizados sem exigir que o usuário saia do Teams.
> - **Integrar o agente** em fluxos de trabalho de equipe ou reuniões (se configurado).
> - **Testar a usabilidade e o comportamento** do agente em um ambiente de usuário final antes de uma implantação mais ampla.
> É uma forma poderosa de levar as capacidades do Copilot Studio para onde as pessoas já estão trabalhando.

---

#### ❓ Dúvidas ou Pontos a Revisar
- Como funciona o processo de aprovação do administrador do Teams para a disponibilização do agente na loja?
- Como as configurações de autenticação mais avançadas afetam a disponibilidade em diferentes canais?
- Como a integração com o Microsoft 365 Copilot funciona para usuários com essa licença?
- Quais são as melhores práticas para escrever descrições curtas e longas eficazes para o agente no Teams?
- Como monitorar o uso e desempenho do agente uma vez publicado no Teams (via seção Análise, talvez)?
- Qual o impacto das configurações de segurança e governança (Ambientes Gerenciados) na publicação em canais como o Teams?
---