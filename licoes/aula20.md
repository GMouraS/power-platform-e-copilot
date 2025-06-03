# 📘 Registro de Aprendizado – Aula [Número]

**👤 Nome:** Gabriel Moura
**🎯 Tema da Aula:** Gerenciando Permissões (Run Only Users) de Ações no Copilot Studio

---

## 📝 Resumo da Aula
> Nesta aula, abordamos uma configuração crucial para fluxos do Power Automate (Ações) utilizados no Microsoft Copilot Studio: o gerenciamento de permissões "Run Only Users". Entendemos por que fluxos que interagem com recursos (como arquivos Excel no SharePoint) podem falhar para usuários do agente que não têm acesso direto a esses recursos. Aprendemos a configurar o fluxo para sempre usar a conexão do proprietário (quem configurou a permissão de execução), garantindo sua execução bem-sucedida para todos os usuários do agente, independentemente de suas permissões no recurso final.

---

## 🔍 Conceitos ou Ferramentas Apresentadas
- **Ações (Actions):** Fluxos do Power Automate que são chamados e executados por um agente do Copilot Studio.
- **Permissões Run Only (Executar somente usuários):** Configuração de um fluxo do Power Automate que define quais usuários podem executar o fluxo e, crucialmente, quais credenciais (conexões) serão usadas quando eles o fizerem.
- **Fluxos em Soluções:** Fluxos criados dentro do contexto de uma solução (como os criados a partir do Copilot Studio) possuem opções avançadas de permissão "Run Only Users".
- **Conexões (Connections):** Links que um fluxo do Power Automate usa para se autenticar e interagir com outros serviços (ex: Excel Online, SharePoint, Outlook).
- **"Provided by run-only user" (Fornecido pelo usuário que executa):** Configuração padrão de conexão no "Run Only Users". Usa as credenciais da pessoa que *acionou* o fluxo (o usuário final do agente). Se o usuário não tiver acesso ao recurso, o fluxo falhará nesta etapa.
- **"Use this connection" (Usar esta conexão):** Configuração alternativa de conexão no "Run Only Users". Força o fluxo a usar as credenciais de uma conexão pré-definida (geralmente a do proprietário do fluxo) sempre que o fluxo for acionado por qualquer usuário.
- **Credenciais:** As informações de login e permissão de um usuário para acessar sistemas ou dados.

---

## 💡 O que eu aprendi de mais importante
> 1.  Fluxos do Power Automate (Ações) utilizados no Copilot Studio podem falhar para usuários do agente se eles não tiverem as mesmas permissões que o criador do fluxo nos sistemas que o fluxo acessa (ex: SharePoint, Excel).
> 2.  A configuração **"Run Only Users"** é essencial para garantir que as automações funcionem para **todos** que usam o agente, independentemente de suas permissões nos sistemas externos.
> 3.  Mudar a configuração de uma conexão para **"Use this connection"** no "Run Only Users" força o fluxo a rodar com as credenciais de uma conta específica (tipicamente a do proprietário), resolvendo problemas de permissão para outros usuários.
> 4.  Essa configuração é crucial para ações que criam, modificam ou leem dados em nome do agente em sistemas onde os usuários finais podem não ter acesso direto.

---

## 🛠 Exercícios ou Atividades Práticas
 Configure as permissões "Run Only Users" para o fluxo do Power Automate criado na aula anterior (registro de reclamações) para garantir que ele funcione para outros usuários.

 **Pré-requisito:** Ter criado o fluxo `Registrar Reclamacao Copilot` (ou similar) que adiciona uma linha em uma tabela Excel no SharePoint/OneDrive e está integrado a um tópico no Copilot Studio.

 **Passos:**
 1.  No Microsoft Copilot Studio, navegar até a seção **Ações**.
 2.  Localizar o fluxo do Power Automate que você deseja configurar (`Registrar Reclamacao Copilot`).
 3.  Clicar no nome do fluxo para abrir seus detalhes no portal do Power Automate (ou acessar o fluxo diretamente pelo portal do Power Automate se souber onde ele está).
 4.  No menu superior ou na página de detalhes do fluxo, encontrar e clicar na opção **"Executar somente usuários"** (ou "Run Only Users", ou "Gerenciar permissões Run Only").
 5.  Na seção "Conexões", você verá as conexões que o fluxo utiliza (ex: Excel Online, SharePoint). Por padrão, elas estarão configuradas como "Fornecido pelo usuário que executa".
 6.  Para as conexões onde você não quer que as credenciais do usuário final sejam usadas (ex: a conexão do Excel/SharePoint que salva os dados):
     *   Selecionar a opção **"Usar esta conexão"**.
     *   Certificar-se de que a conexão listada abaixo é a que você deseja usar (geralmente a sua, como proprietário do fluxo).
 7.  (Opcional) Configurar a opção de "Usar esta conexão" para outras conexões, se houver, que possam causar problemas de permissão para outros usuários.
 8.  Clicar em **"Salvar"** no topo da página "Executar somente usuários".
 9.  (Opcional, para verificar mentalmente) Pensar em um usuário hipotético na sua organização que não tem acesso ao arquivo Excel ou site SharePoint onde o fluxo salva os dados. Entender que, sem essa configuração, o fluxo falharia para ele, mas com a configuração "Usar esta conexão", o fluxo usará suas credenciais (que têm acesso) e funcionará corretamente para ele.
 10. (Opcional) Retornar ao Copilot Studio e testar o agente no painel de teste novamente. Embora para o seu usuário o comportamento não mude (já que você tem acesso), a configuração foi feita para beneficiar outros usuários.

 **Dificuldades encontradas ou insights obtidos:**
 - Encontrar a opção "Executar somente usuários" no portal do Power Automate, dependendo da versão da interface.
 - Identificar quais conexões dentro do fluxo podem causar problemas de permissão para outros usuários.
 - Entender que testar com a própria conta não revela o problema de permissão, mas a configuração é crucial para o uso compartilhado.
 - A configuração precisa ser feita por conexão, em cada fluxo que será utilizado por outros usuários.

---

## 📌 Aplicações no Trabalho
> A configuração de "Run Only Users" é **fundamental** para implantar agentes com automações em ambientes corporativos. Ela permite:
> - **Garantir que as ações do agente funcionem** para qualquer usuário na organização, mesmo que eles não tenham permissão direta aos sistemas de backend que o fluxo utiliza.
> - **Implementar cenários de automação** onde o agente atua em nome de um processo ou serviço (usando a conexão do proprietário ou de uma conta de serviço) sem exigir que todos os usuários finais tenham acesso a esses sistemas.
> - **Evitar falhas de fluxo** generalizadas e problemas de suporte relacionados a permissões quando o agente é compartilhado.
> - **Manter a segurança** dos sistemas de backend, pois as permissões de execução do fluxo são centralizadas e não exigem a distribuição de acesso direto a todos os usuários do agente.

---

## ❓ Dúvidas ou Pontos a Revisar
- Cenários mais complexos com múltiplos conectores e como configurar suas permissões Run Only.
- O uso de contas de serviço dedicadas para executar fluxos em vez das credenciais do proprietário.
- Como essa configuração se aplica a diferentes tipos de autenticação de conectores.
- O impacto dessa configuração no log de auditoria ou no registro de quem "executou" a ação (se aparece o nome do usuário final ou o nome da conta usada na conexão).
- Como gerenciar essas permissões em fluxos que estão em soluções e são movidos entre ambientes.
