### 📘 Registro de Aprendizado – Aula 10

**👤 Nome:** Gabriel Moura
**🎯 Tema da Aula:** Utilizando Fontes de Conhecimento através de Carregamento de Arquivos

---

#### 📝 Resumo da Aula
> Vimos como adicionar um tipo diferente de fonte de conhecimento: o carregamento direto de arquivos ("carga fria"). Demonstramos o processo de upload de um arquivo (`PDF`) para o agente, notando que o processo de indexação para este tipo de fonte tende a ser mais demorado. Exploramos as restrições de formato (principalmente baseado em texto), tamanho (até `512MB`) e rótulos de confidencialidade para arquivos no OneDrive. Testamos um agente que já possuía um arquivo `PDF` indexado (um livro de receitas), verificando como ele extrai informações relevantes e fornece a referência ao arquivo de origem. Utilizamos o mapa de atividades para visualizar qual fonte foi consultada (neste caso, o arquivo) (ver Aula 16).

---

#### 🔍 Conceitos ou Ferramentas Apresentadas
- **Fontes de Conhecimento - Carregamento de Arquivos (Carga Fria):** Capacidade de fazer upload direto de arquivos para o agente indexar e usar como fonte de informação. Chamado de "carga fria" porque os arquivos não atualizam automaticamente se o original mudar.
- **Processo de Upload:** Selecionar a opção "Carregar arquivo" e escolher o documento da máquina local.
- **Formatos Suportados:** Principalmente arquivos baseados em texto (`PDF`, `Word`, etc.). `Imagens, áudio, vídeo e executáveis não são indexados do conteúdo`.
- **Tamanho Máximo do Arquivo:** Limite de `512MB` por arquivo.
- **Restrições de Rótulos de Confidencialidade (OneDrive/SharePoint):** Arquivos com rótulos "Confidencial" ou "Altamente Confidencial" (dependendo da configuração da organização) no OneDrive ou SharePoint `podem não ser utilizáveis` como fonte. Rótulos como "Interno" ou "Restrito" geralmente são permitidos.
- **Tempo de Indexação (Arquivos):** O processo de indexação de arquivos carregados manualmente tende a ser mais lento em comparação com sites SharePoint ou públicos. O status pode ser verificado no painel de Conhecimento.
- **DataSource (Armazenamento de Arquivos):** Os arquivos carregados são armazenados de forma `segura` dentro do ambiente `Dataverse` (DataSource) associado à solução do agente (ver Aula 2, Aula 7).
- **Teste com Arquivo Indexado:** Fazer perguntas ao agente cujo conteúdo pode ser encontrado no arquivo carregado.
- **Mapa de Atividades / Rastreamento:** Ferramenta de depuração que mostra o passo a passo da consulta do agente, incluindo **quais fontes de conhecimento foram pesquisadas** e de onde a resposta foi finalmente extraída (ver Aula 16).
- **Varrimento de Fontes:** O agente pesquisa em todas as fontes de conhecimento configuradas para encontrar a melhor resposta.
- **Conhecimento Geral versus Fontes Específicas:** Se desabilitado o conhecimento geral, o agente se limita às fontes configuradas. Se habilitado e nenhuma informação for encontrada nas fontes específicas, ele recorrerá ao conhecimento geral da IA (ver Aula 4).

---

#### 💡 O que eu aprendi de mais importante
> 1.  Carregar arquivos diretamente é útil para adicionar fontes de conhecimento específicas (como manuais, relatórios, etc.) que não estão em sites SharePoint ou públicos.
> 2.  Este método de fonte de conhecimento exige atenção às **restrições de formato (texto)**, **tamanho** e **rótulos de confidencialidade** de dados.
> 3.  A indexação de arquivos carregados pode levar tempo, e o status deve ser monitorado.
> 4.  O **Mapa de Atividades** é uma ferramenta poderosa para diagnosticar o comportamento do agente, mostrando quais fontes foram consultadas e de onde veio a resposta.
> 5.  O agente pesquisa em **todas** as fontes de conhecimento configuradas (arquivos, SharePoint, sites públicos) e recorre ao conhecimento geral da IA apenas se não encontrar informações nas fontes específicas (e se essa opção estiver habilitada).

---

#### 🛠 Exercícios ou Atividades Práticas
- **Descrição breve do exercício ou atividade:** Obter um arquivo baseado em texto (ex: um `PDF` simples, um documento Word) com tamanho menor que `512MB` e sem rótulos de confidencialidade restritivos (se aplicável). Acessar a opção "Adicionar conhecimento" no Copilot Studio e selecionar "Carregar arquivo". Fazer o upload do arquivo. Acompanhar o status da indexação no painel de Conhecimento até que esteja "Pronto". No painel de teste do agente, fazer perguntas cujo conteúdo esteja no arquivo carregado e verificar se o agente responde corretamente, fornecendo a referência ao arquivo. Usar o mapa de atividades para confirmar que o arquivo foi a fonte consultada.
- **Dificuldades encontradas ou insights obtidos:**
    - **Problema:** O tempo de indexação pode ser longo. **Insight:** Paciência é necessária, especialmente para arquivos maiores.
    - **Problema:** Lidar com as restrições de confidencialidade pode ser relevante em ambientes corporativos. **Insight:** Verifique as políticas de DLP da organização.

---

#### 📌 Aplicações no Trabalho
> O carregamento de arquivos como fonte de conhecimento é valioso para:
> - Disponibilizar informações de **documentos internos** que não estão em formato de site ou SharePoint (ex: `PDFs` de políticas antigas, manuais específicos, relatórios).
> - Criar agentes baseados em **bases de conhecimento** offline ou documentos de referência.
> - Fornecer acesso a **livros de receitas**, guias de treinamento ou qualquer outro material textual que possa ser transformado em `PDF` ou documento e carregado.
> Permite que o agente responda a perguntas usando conteúdo que talvez não esteja acessível por outros métodos de fonte de conhecimento, ampliando o leque de informações que o agente pode fornecer.

---

#### ❓ Dúvidas ou Pontos a Revisar
- Quais são as estratégias para otimizar o tempo de indexação de arquivos carregados?
- Como gerenciar e atualizar arquivos carregados (o processo de "carga fria" exige re-upload)?
- Quais são os limites na quantidade total ou no tamanho combinado de arquivos que podem ser carregados?
- Como o agente lida com a extração de informações de diferentes formatos de arquivo (`PDF`, `Word`, etc.) e a qualidade da extração?
- Quais são mais exemplos de como usar o mapa de atividades para depurar problemas de busca em fontes de conhecimento?
---