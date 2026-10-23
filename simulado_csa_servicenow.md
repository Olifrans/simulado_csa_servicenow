# Simulado Oficial Completo - ServiceNow Certified System Administrator (CSA)

*Organizado com Gabarito Correto e Respostas Detalhadas (77 Questões)*

## Domínio 1: Database Management & Platform Security (Segurança, ACLs e Tabelas)

### Questão 1

Qual é a ordem de avaliação correta que a ServiceNow utiliza ao processar as regras de controle de acesso (ACLs)?

* \[ \] A) Campo (Field) $\rightarrow$ Linha (Row) $\rightarrow$ Tabela (Table)

* \[x\] **B) Tabela (Table)** $\rightarrow$ **Linha (Row)** $\rightarrow$ **Campo (Field)**

* \[ \] C) Linha (Row) $\rightarrow$ Tabela (Table) $\rightarrow$ Campo (Field)

* \[ \] D) Tabela (Table) $\rightarrow$ Campo (Field) $\rightarrow$ Linha (Row)

> **Resposta Correta: B**
> **Explicação:** A plataforma avalia primeiro o nível da Tabela (Table), depois valida a restrição por registro/linha (Row) e, finalmente, avalia o campo específico (Field). Se o acesso for negado no nível superior, a verificação é interrompida.

### Questão 2

Um administrador do sistema precisa criar uma nova tabela personalizada para armazenar dados de projetos. Qual prefixo é obrigatoriamente utilizado e gerado pela plataforma para tabelas customizadas criadas no escopo global?

* \[ \] A) `sys_`

* \[x\] **B) `u_`**

* \[ \] C) `x_`

* \[ \] D) `custom_`

> **Resposta Correta: B**
> **Explicação:** O prefixo `u_` é atribuído a tabelas criadas por usuários no escopo Global. O prefixo `x_` é reservado para tabelas de aplicações escopadas (*Scoped Applications*).

### Questão 3

Quais são as principais características da role `security_administrator` na plataforma ServiceNow?

* \[ \] A) Permite apenas criar usuários e redefinir senhas no sistema.

* \[x\] **B) É uma role de privilégio elevado (*elevation of privileges*) necessária para modificar ACLs e configurações sensíveis de segurança, sendo concedida apenas temporariamente por sessão.**

* \[ \] C) Concede acesso irrestrito e permanente a todas as tabelas de dados clínicos e financeiros sem necessidade de elevação.

* \[ \] D) Permite gerenciar apenas fluxos de trabalho e integrações via Web Services.

> **Resposta Correta: B**
> **Explicação:** A role `security_administrator` exige uma elevação de privilégio manual na sessão (*Elevate Roles*) para permitir modificações em regras de acesso sensíveis e ACLs.

### Questão 4

O que a funcionalidade/role de Impersonator (`impersonator`) permite que um administrador faça na instância?

* \[ \] A) Criar cópias exatas de instâncias de produção para ambientes de teste.

* \[x\] **B) Assumir temporariamente a identidade de outro usuário para testar o comportamento de ACLs, portais e visibilidade de dados sob a perspectiva daquele usuário.**

* \[ \] C) Apagar registros duplicados de auditoria em massa.

* \[ \] D) Modificar o código-fonte de plugins nativos da plataforma.

> **Resposta Correta: B**
> **Explicação:** A função *Impersonate* permite ver a plataforma exatamente como o usuário selecionado a enxerga, ideal para testes de visibilidade e regras de acesso.

### Questão 5

As tabelas `incident`, `problem` e `change_request` herdam campos e comportamentos de qual tabela principal do framework de ITIL na ServiceNow?

* \[ \] A) `cmdb_ci`

* \[x\] **B) `task`**

* \[ \] C) `sys_object`

* \[ \] D) `kb_knowledge`

> **Resposta Correta: B**
> **Explicação:** A tabela `task` é a tabela pai raiz para todos os processos de trabalho e ITSM (`incident`, `problem`, `change_request`, `sc_task`, etc.).

### Questão 13

O que acontece se uma ACL no nível de Tabela negar o acesso de leitura a um usuário, mas uma ACL no nível de Campo permitir a leitura de um campo específico dessa mesma tabela?

* \[ \] A) O usuário conseguirá visualizar apenas aquele campo específico.

* \[x\] **B) O acesso do usuário será completamente negado, pois a falha na avaliação no nível de tabela interrompe o acesso a todos os campos.**

* \[ \] C) O sistema exibirá uma mensagem de erro fatal na tela.

* \[ \] D) O campo será exibido apenas como leitura (*read-only*).

> **Resposta Correta: B**
> **Explicação:** Para acessar qualquer campo, o usuário deve passar obrigatoriamente primeiro pelas validações de nível de Tabela e de Linha.

### Questão 14

Qual é a finalidade da regra ACL definida com a sintaxe `tabela.*`?

* \[ \] A) Conceder acesso apenas à chave primária (`sys_id`) da tabela.

* \[x\] **B) Aplicar a regra de permissão a todos os campos da tabela que não possuem regras de campo específicas definidas.**

* \[ \] C) Ocultar a tabela de todas as buscas globais.

* \[ \] D) Conceder permissão total de exclusão para todos os administradores.

> **Resposta Correta: B**
> **Explicação:** A sintaxe `tabela.*` funciona como um curinga para os campos da tabela, aplicando-se a todos aqueles que não possuem uma regra de campo individual.

### Questão 15

O que significa a declaração ACL com a sintaxe `tabela.None`?

* \[ \] A) Negar o acesso a todos os registros da tabela.

* \[x\] **B) Definir a permissão de acesso ao registro/tabela como um todo, antes da verificação de campos individuais.**

* \[ \] C) Indicar que nenhum usuário pode alterar o dicionário de dados da tabela.

* \[ \] D) Remover todas as regras de segurança existentes na instância.

> **Resposta Correta: B**
> **Explicação:** `tabela.None` refere-se ao acesso à própria tabela/registro em si. É o primeiro requisito a ser atendido para acessar o registro.

### Questão 16

Qual tabela do sistema é responsável por armazenar as contas de todos os usuários cadastrados na instância ServiceNow?

* \[ \] A) `sys_user_group`

* \[x\] **B) `sys_user`**

* \[ \] C) `sys_user_role`

* \[ \] D) `core_company`

> **Resposta Correta: B**
> **Explicação:** A tabela `sys_user` armazena os registros de usuários (nome, e-mail, departamento, status, etc.).

### Questão 17

Em qual tabela de associação a plataforma armazena quais papéis (*roles*) pertencem diretamente a cada usuário?

* \[ \] A) `sys_user`

* \[ \] B) `sys_user_role`

* \[x\] **C) `sys_user_has_role`**

* \[ \] D) `sys_group_has_role`

> **Resposta Correta: C**
> **Explicação:** A tabela `sys_user_has_role` estabelece a relação muitos-para-muitos (M:N) entre usuários (`sys_user`) e roles (`sys_user_role`).

### Questão 18

Qual é o identificador único universal de 32 caracteres hexadecimais atribuído automaticamente a cada registro criado no banco de dados da ServiceNow?

* \[ \] A) `Pkey`

* \[ \] B) `Record_ID`

* \[x\] **C) `Sys ID` (`sys_id`)**

* \[ \] D) `GUID_Index`

> **Resposta Correta: C**
> **Explicação:** O `sys_id` é a chave primária única de 32 caracteres gerada automaticamente pela plataforma para identificar individualmente qualquer registro.

### Questão 19

O que caracteriza uma tabela criada com o prefixo `x_` na plataforma?

* \[ \] A) É uma tabela de sistema nativa da ServiceNow.

* \[ \] B) É uma tabela temporária de Import Set.

* \[x\] **C) É uma tabela criada dentro do escopo de uma aplicação personalizada (*Scoped Application*).**

* \[ \] D) É uma tabela do módulo de integração legada via SOAP.

> **Resposta Correta: C**
> **Explicação:** O prefixo `x_` (seguido do código do desenvolvedor/empresa) identifica tabelas e artefatos pertencentes a uma aplicação escopada.

### Questão 20

O que é o *Application Scope* (Escopo de Aplicação) e qual seu principal objetivo na plataforma?

* \[ \] A) Definir o limite de usuários simultâneos no sistema.

* \[x\] **B) Fornecer isolamento de dados e código para evitar que modificações em uma aplicação afetem acidentalmente outras aplicações da instância.**

* \[ \] C) Limitar o tamanho dos anexos enviados por e-mail.

* \[ \] D) Medir o tempo de resposta das consultas do banco de dados.

> **Resposta Correta: B**
> **Explicação:** O *Application Scope* protege o código e a estrutura de uma aplicação, impedindo interferências indesejadas de ou para outras aplicações.

### Questão 21

Qual tabela do sistema armazena a lista de todas as opções e escolhas de campos do tipo *Choice List*?

* \[ \] A) `sys_dictionary`

* \[x\] **B) `sys_choice`**

* \[ \] C) `sys_metadata`

* \[ \] D) `sys_ui_list`

> **Resposta Correta: B**
> **Explicação:** As opções exibidas em campos drop-down / choice list são gravadas na tabela `sys_choice`.

### Questão 22

Qual tabela do sistema armazena os metadados dos arquivos anexados aos registros da plataforma?

* \[ \] A) `sys_file`

* \[x\] **B) `sys_attachment`**

* \[ \] C) `sys_upload`

* \[ \] D) `sys_blob`

> **Resposta Correta: B**
> **Explicação:** A tabela `sys_attachment` guarda as informações e metadados de arquivos anexados aos registros.

### Questão 23

Quem tem permissão por padrão para visualizar e acessar diretamente a tabela de logs de auditoria do sistema (`sys_audit`)?

* \[ \] A) Todos os usuários com a role `itil`.

* \[x\] **B) Apenas administradores do sistema (`admin`) com elevação de privilégio.**

* \[ \] C) Qualquer usuário com papel de relatórios (`report_user`).

* \[ \] D) Usuários com a role `knowledge_admin`.

> **Resposta Correta: B**
> **Explicação:** Devido ao grande volume de dados e informações sensíveis, o acesso à tabela `sys_audit` é restrito a administradores.

### Questão 24

O que a configuração *Application Access* na definição de uma tabela permite que o administrador controle?

* \[ \] A) Qual grupo de usuários pode realizar login na instância.

* \[x\] **B) Se scripts e artefatos de outros escopos de aplicação podem ler, criar, atualizar ou excluir registros dessa tabela.**

* \[ \] C) A velocidade da conexão de rede com a tabela.

* \[ \] D) O limite de linhas exibidas em relatórios exportados em PDF.

> **Resposta Correta: B**
> **Explicação:** O *Application Access* governa o acesso entre escopos diferentes no nível de banco de dados.

### Questão 25

Qual ferramenta permite visualizar graficamente a estrutura do banco de dados, incluindo tabelas pai/filha e seus relacionamentos de referência?

* \[ \] A) Dependency Map

* \[x\] **B) Schema Map**

* \[ \] C) Form Builder

* \[ \] D) Workflow Editor

> **Resposta Correta: B**
> **Explicação:** O *Schema Map* exibe o mapa conceitual e gráfico das tabelas e seus relacionamentos no banco de dados da plataforma.

## Domínio 2: Self-Service, Portals & Service Catalog (Automação e Portais)

### Questão 6

Quando um usuário final solicita um produto ou item de catálogo (*Catalog Item*) através do Service Catalog, quais são as tabelas principais e a ordem correta em que os registros são gerados automaticamente?

* \[ \] A) `incident` $\rightarrow$ `problem` $\rightarrow$ `change_request`

* \[x\] **B) `sc_request` (Request)** $\rightarrow$ **`sc_req_item` (Requested Item)** $\rightarrow$ **`sc_task` (Catalog Task)**

* \[ \] C) `task_sla` $\rightarrow$ `sys_email` $\rightarrow$ `sc_task`

* \[ \] D) `cmdb_ci_service` $\rightarrow$ `kb_knowledge` $\rightarrow$ `sc_request`

> **Resposta Correta: B**
> **Explicação:** A ordem hierárquica e de geração é: Requisição Geral (`sc_request`), Item Solicitado (`sc_req_item`) e Tarefa de Atendimento (`sc_task`).

### Questão 7

O que diferencia o acesso e o escopo do Self-Service tradicional em relação ao Employee Center / Employee Portal na ServiceNow?

* \[ \] A) O Self-Service é restrito apenas a desenvolvedores, enquanto o Employee Portal é para usuários comuns.

* \[x\] **B) O Employee Portal unifica múltiplos serviços (RH, TI, Jurídico, Facilities) em uma experiência de portal moderna, enquanto o Self-Service foca nas funcionalidades padrão de navegação de incidentes e base de conhecimento básicas.**

* \[ \] C) Não há diferença técnica; são exatamente a mesma interface com nomes comerciais distintos.

* \[ \] D) O Employee Portal roda fora da plataforma ServiceNow, via integração externa.

> **Resposta Correta: B**
> **Explicação:** O Employee Center substitui portais legados consolidando uma experiência de atendimento multi-departamental unificada.

### Questão 8

Onde os Grupos (`Groups`) de usuários são armazenados estruturalmente na base de dados da plataforma?

* \[ \] A) `sys_user`

* \[x\] **B) `sys_user_group`**

* \[ \] C) `sys_user_has_role`

* \[ \] D) `core_company`

> **Resposta Correta: B**
> **Explicação:** A tabela `sys_user_group` guarda as definições dos grupos de usuários na plataforma.

### Questão 26

Qual tabela armazena especificamente o item individual solicitado (`Requested Item` - RITM) em um pedido do Service Catalog?

* \[ \] A) `sc_request`

* \[x\] **B) `sc_req_item`**

* \[ \] C) `sc_task`

* \[ \] D) `item_option_new`

> **Resposta Correta: B**
> **Explicação:** O registro `RITM` é salvo na tabela `sc_req_item` e representa o produto ou serviço específico selecionado.

### Questão 27

Qual tabela armazena a tarefa individual de trabalho (`Catalog Task` - SCTASK) associada ao atendimento de um pedido no catálogo?

* \[ \] A) `sc_request`

* \[ \] B) `sc_req_item`

* \[x\] **C) `sc_task`**

* \[ \] D) `task_ci`

> **Resposta Correta: C**
> **Explicação:** As tarefas técnicas de atribuição enviadas às equipes de atendimento ficam registradas na tabela `sc_task`.

### Questão 28

O que são os *User Criteria* no contexto do Service Catalog e Knowledge Management?

* \[ \] A) Regras de ordenação alfabética para itens do portal.

* \[x\] **B) Condições configuráveis que definem quais usuários têm permissão para ler, solicitar ou criar itens de catálogo e artigos de conhecimento.**

* \[ \] C) Scripts utilizados para formatar o texto dos artigos.

* \[ \] D) Critérios automáticos para encerramento de chamados inativos.

> **Resposta Correta: B**
> **Explicação:** *User Criteria* definem a elegibilidade de acesso a itens de catálogo e bases de conhecimento com base em papel, departamento, localização, grupo, etc.

### Questão 29

O que são *Widgets* no Service Portal?

* \[ \] A) Plugins instalados no sistema operacional do servidor.

* \[x\] **B) Componentes visuais e reutilizáveis (código HTML/CSS/Client/Server) que compõem as páginas e funcionalidades do portal.**

* \[ \] C) Tabelas temporárias utilizadas para exportar relatórios em Excel.

* \[ \] D) Tipos de variáveis exclusivas do formulário de incidentes.

> **Resposta Correta: B**
> **Explicação:** Os *Widgets* são os blocos de construção das páginas do Service Portal (ex: caixa de busca, lista de solicitações, carrossel de notícias).

### Questão 30

Para que serve o recurso *Branding Editor* no Service Portal?

* \[ \] A) Para criar regras de segurança na base de dados.

* \[x\] **B) Para personalizar visualmente e de forma rápida as cores, logotipos, títulos e temas do portal sem escrever código.**

* \[ \] C) Para alterar a senha dos usuários em lote.

* \[ \] D) Para importar dados de planilhas CSV.

> **Resposta Correta: B**
> **Explicação:** O *Branding Editor* permite ajustar a identidade visual da empresa no portal de maneira amigável e sem código.

### Questão 31

O que um usuário sem roles atribuídas (*End User* / *Unassigned User*) pode realizar por padrão no Employee Center / Portal?

* \[ \] A) Criar regras de controle de acesso (ACLs) e editar scripts.

* \[x\] **B) Pesquisar artigos na Base de Conhecimento, solicitar itens de catálogo e acompanhar o status de suas solicitações.**

* \[ \] C) Visualizar a tabela `sys_audit` e criar novos grupos.

* \[ \] D) Importar planilhas de dados para o CMDB.

> **Resposta Correta: B**
> **Explicação:** Usuários finais usam o portal para autoatendimento: abrir chamados, pedir serviços e ler artigos explicativos.

### Questão 32

Onde ficam armazenadas as variáveis e respostas preenchidas pelo usuário ao enviar um formulário de *Catalog Item*?

* \[ \] A) Na tabela `sys_user_option`.

* \[x\] **B) Associadas ao registro do `sc_req_item` na tabela de variáveis do catálogo (`sc_item_option`).**

* \[ \] C) Na tabela de propriedades do sistema (`sys_properties`).

* \[ \] D) No log de eventos do servidor (`sysevent`).

> **Resposta Correta: B**
> **Explicação:** As variáveis capturadas durante a solicitação pertencem e ficam vinculadas ao *Requested Item* (`sc_req_item`).

### Questão 33

Qual é o principal objetivo do módulo de *Knowledge Management* na plataforma?

* \[ \] A) Monitorar a memória RAM utilizada pela instância.

* \[x\] **B) Criar, revisar, aprovar, publicar e organizar artigos de informação e solução de problemas para usuários e analistas.**

* \[ \] C) Gerenciar as licenças de software compradas pela empresa.

* \[ \] D) Armazenar cópias de segurança do banco de dados.

> **Resposta Correta: B**
> **Explicação:** O *Knowledge Management* gerencia a base de conhecimento corporativa para promover a resolução rápida de dúvidas e incidentes.

### Questão 34

Como o acesso de leitura ou escrita a uma *Knowledge Base* específica é governado?

* \[ \] A) Exclusivamente por scripts no servidor em Java.

* \[x\] **B) Através das listas de verificação *Can Read*, *Cannot Read*, *Can Contribute* e *Cannot Contribute* baseadas em User Criteria.**

* \[ \] C) Apenas por endereço IP do usuário.

* \[ \] D) Todas as bases de conhecimento são públicas por padrão sem opção de restrição.

> **Resposta Correta: B**
> **Explicação:** As permissões de acesso e publicação em cada Knowledge Base são controladas pelas configurações de User Criteria nas abas de acesso.

### Questão 35

Qual ferramenta gráfica do Flow Designer é utilizada para construir gatilhos, ações e fluxos de automação sem a necessidade de codificação?

* \[ \] A) Workflow Classic Engine

* \[x\] **B) Flow Canvas**

* \[ \] C) Schema Visualizer

* \[ \] D) Form Designer

> **Resposta Correta: B**
> **Explicação:** O *Flow Canvas* é a interface visual drag-and-drop do Flow Designer onde os fluxos são modelados.

### Questão 36

Para que serve a funcionalidade *Flow Execution Details* no Flow Designer?

* \[ \] A) Para exportar a licença da plataforma em formato PDF.

* \[x\] **B) Para inspecionar e depurar o estado, entradas, saídas e tempo de execução de cada etapa de um fluxo acionado.**

* \[ \] C) Para alterar a cor dos botões do portal.

* \[ \] D) Para compilar código JavaScript em linguagem C++.

> **Resposta Correta: B**
> **Explicação:** O *Flow Execution Details* é a ferramenta de teste e debug que exibe o histórico detalhado de execução de um fluxo.

## Domínio 3: Instance Configuration, Forms & Client Logic

### Questão 9

Ao customizar e configurar o design de formulários utilizando o Form Builder / Form Designer, qual é a melhor prática recomendada pela ServiceNow para tornar campos obrigatórios (*mandatory*), ocultos (*hidden*) ou somente leitura (*read-only*)?

* \[ \] A) Utilizar sempre Client Scripts customizados em JavaScript puro.

* \[x\] **B) Utilizar preferencialmente UI Policies (Políticas de Interface), pois permitem gerenciar esses estados sem código (low-code) de forma mais segura e performática.**

* \[ \] C) Alterar diretamente o dicionário de dados de cada campo (`sys_dictionary`).

* \[ \] D) Escrever Business Rules síncronas no banco de dados.

> **Resposta Correta: B**
> **Explicação:** UI Policies são recomendadas pela ServiceNow para lógicas dinâmicas de interface sem a necessidade de codificação client-side complexa.

### Questão 10

Qual é a principal diferença de escopo e execução entre Business Rules, Client Scripts e UI Policies?

* \[ \] A) Todas rodam simultaneamente no navegador do usuário (Client-side).

* \[x\] **B) Client Scripts e UI Policies rodam no cliente (browser), enquanto Business Rules rodam no servidor (server-side) em resposta a operações de banco de dados (Insert/Update/Delete/Query).**

* \[ \] C) Business Rules são usadas exclusivamente para mudar a cor de campos nos formulários.

* \[ \] D) UI Policies rodam obrigatoriamente no banco de dados antes da validação das ACLs.

> **Resposta Correta: B**
> **Explicação:** Client Scripts e UI Policies afetam a experiência visual do usuário no navegador; Business Rules executam lógica no servidor ao interagir com o banco de dados.

### Questão 37

Qual é o comportamento de um Client Script do tipo `onLoad`?

* \[ \] A) Executa um script quando o formulário é submetido e salvo.

* \[x\] **B) Executa um script imediatamente quando a página do formulário é carregada no navegador do usuário.**

* \[ \] C) Executa um script quando um valor em um campo específico é alterado.

* \[ \] D) Executa no servidor quando o registro é excluído.

> **Resposta Correta: B**
> **Explicação:** Scripts `onLoad` são acionados assim que a interface do formulário termina de carregar no browser.

### Questão 38

Quando o tipo de Client Script `onChange` é disparado na plataforma?

* \[ \] A) Quando o usuário faz logout do sistema.

* \[x\] **B) Sempre que o valor de um campo específico monitorado no formulário é modificado pelo usuário.**

* \[ \] C) Apenas quando a página é atualizada com a tecla F5.

* \[ \] D) Quando o relatório quinzenal é gerado.

> **Resposta Correta: B**
> **Explicação:** O script `onChange` reage em tempo real à alteração do valor de um campo selecionado no formulário.

### Questão 39

Qual é a principal utilidade de um Client Script do tipo `onSubmit`?

* \[ \] A) Mudar a cor de fundo da tabela no banco de dados.

* \[x\] **B) Validar os campos do formulário antes do envio e cancelar a submissão (retornando `false`) caso os dados estejam incorretos.**

* \[ \] C) Criar um backup automático da instância.

* \[ \] D) Enviar uma mensagem para o Microsoft Teams.

> **Resposta Correta: B**
> **Explicação:** O script `onSubmit` roda quando o usuário clica em Save/Submit, permitindo validar informações e impedir o salvamento se necessário.

### Questão 40

O que são os *OnCellEdit Client Scripts*?

* \[ \] A) Scripts executados quando o servidor entra em manutenção.

* \[x\] **B) Scripts que executam lógica no navegador quando um usuário edita o valor de um campo diretamente na visão de lista (List View).**

* \[ \] C) Validações para campos do tipo anexo de imagem.

* \[ \] D) Scripts exclusivos para o aplicativo móvel da ServiceNow.

> **Resposta Correta: B**
> **Explicação:** *OnCellEdit* atua especificamente nas edições feitas diretamente nas células das listas, sem abrir o formulário.

### Questão 41

Qual é a principal diferença entre marcar um campo como `Mandatory` (Obrigatório) no Dicionário de Dados versus em uma UI Policy?

* \[ \] A) Não existe diferença; ambos agem apenas no navegador.

* \[x\] **B) No Dicionário de Dados a obrigatoriedade é aplicada em nível de banco de dados (todas as operações/API), enquanto na UI Policy ela se aplica dinamicamente na interface gráfica do formulário.**

* \[ \] C) A UI Policy torna o campo obrigatório apenas para usuários administradores.

* \[ \] D) O Dicionário de Dados é usado apenas para campos de texto longo.

> **Resposta Correta: B**
> **Explicação:** Validações de Dicionário garantem a regra em qualquer canal (interface, importações, REST/SOAP). A UI Policy governa a dinâmica visual no browser.

### Questão 42

Para que servem as *UI Actions* na interface do usuário da ServiceNow?

* \[ \] A) Para definir os estilos CSS de todas as páginas do portal.

* \[x\] **B) Para adicionar botões, links de cabeçalho, links de menu de contexto e itens de ação que executam scripts no cliente e/ou servidor.**

* \[ \] C) Para limitar o número de logins diários dos usuários.

* \[ \] D) Para criptografar o banco de dados.

> **Resposta Correta: B**
> **Explicação:** *UI Actions* criam elementos interativos na tela (ex: botões *Submit*, *Resolve*, *Approve*) para disparar ações.

### Questão 43

Qual é o local de execução de uma *UI Action* na plataforma?

* \[ \] A) Exclusivamente no cliente (browser).

* \[ \] B) Exclusivamente no servidor (server-side).

* \[x\] **C) Pode ser configurada para executar no cliente, no servidor ou em ambos.**

* \[ \] D) Executa apenas em instâncias de desenvolvimento.

> **Resposta Correta: C**
> **Explicação:** Uma *UI Action* pode rodar lógicas client-side (ex: confirmação visual) e, em seguida, disparar procedimentos no servidor.

### Questão 44

Qual é a função do *Dictionary Entry* (`sys_dictionary`) para um campo de formulário?

* \[ \] A) Definir o idioma padrão do usuário logado.

* \[x\] **B) Definir as propriedades estruturais da coluna na tabela (tipo de dado, tamanho máximo, rótulo, valor padrão, referência e regras de obrigatoriedade).**

* \[ \] C) Gravar a hora exata em que o usuário clicou no campo.

* \[ \] D) Agendar o envio de e-mails de notificação.

> **Resposta Correta: B**
> **Explicação:** O registro no Dicionário de Dados armazena a definição técnica da coluna no banco de dados.

### Questão 45

O que faz um *Reference Qualifier* em um campo do tipo *Reference* em um formulário?

* \[ \] A) Altera a cor do texto do campo de referência.

* \[x\] **B) Aplica um filtro para restringir quais registros aparecem nas opções de seleção do campo de referência.**

* \[ \] C) Converte o valor do campo para letras maiúsculas automaticamente.

* \[ \] D) Apaga os registros referenciados após 30 dias.

> **Resposta Correta: B**
> **Explicação:** O *Reference Qualifier* limita a lista de registros selecionáveis (ex: exibir apenas usuários ativos pertencentes a um departamento específico).

### Questão 46

Qual ferramenta visual o administrador deve utilizar para criar, reorganizar ou remover seções e campos de um formulário de maneira ágil?

* \[ \] A) Import Set Engine

* \[x\] **B) Form Designer / Form Builder**

* \[ \] C) Access Control List Manager

* \[ \] D) System Properties

> **Resposta Correta: B**
> **Explicação:** O *Form Designer* e o *Form Builder* são as ferramentas visuais para estilizar o layout de campos e seções de formulários.

### Questão 47

O que é uma *Business Rule* do tipo `Async` (Assíncrona)?

* \[ \] A) Uma regra que roda no navegador do usuário antes do envio da página.

* \[x\] **B) Uma regra que roda no servidor em segundo plano após o registro ser salvo, liberando a interface do usuário sem causar travamentos ou lentidão.**

* \[ \] C) Uma regra que cancela todas as alterações feitas na tabela.

* \[ \] D) Uma regra que funciona apenas em redes sem fio.

> **Resposta Correta: B**
> **Explicação:** Business Rules `Async` processam tarefas no servidor sem prender a navegação do usuário, oferecendo melhor performance.

### Questão 48

O que são as *Query Business Rules* na ServiceNow?

* \[ \] A) Regras usadas para alterar as imagens de fundo do portal.

* \[x\] **B) Regras executadas no servidor antes de uma consulta ao banco de dados ser realizada, permitindo filtrar e restringir linhas visíveis ao usuário.**

* \[ \] C) Relatórios automáticos gerados por e-mail.

* \[ \] D) Consultas que atualizam o fuso horário dos usuários.

> **Resposta Correta: B**
> **Explicação:** *Query Business Rules* alteram a cláusula `WHERE` da consulta no banco de dados, filtrando quais registros o usuário tem permissão ou necessidade de listar.

## Domínio 4: Data Integration & Migration (Import Sets, Transform Maps e CMDB)

### Questão 11

Qual é a ordem correta do fluxo de importação de dados para dentro da plataforma ServiceNow usando o mecanismo de Import Sets?

* \[ \] A) Transform Map $\rightarrow$ Target Table $\rightarrow$ Load Data $\rightarrow$ Import Set Table

* \[x\] **B) Load Data (Import Set Table)** $\rightarrow$ **Criação/Seleção do Transform Map** $\rightarrow$ **Execução da Transformação (Target Table)**

* \[ \] C) Target Table $\rightarrow$ Transform Map $\rightarrow$ Data Cleansing $\rightarrow$ Load Data

* \[ \] D) Export Set $\rightarrow$ Transform Map $\rightarrow$ CMDB Sync

> **Resposta Correta: B**
> **Explicação:** O fluxo correto carrega primeiro os dados para uma tabela temporária (`Import Set Table`), mapeia as colunas via `Transform Map` e executa para a tabela de destino (`Target Table`).

### Questão 12

O que representam os Configuration Items (CIs) e como o Dependency Map os utiliza na plataforma?

* \[x\] **A) CIs são componentes de infraestrutura ou serviços monitorados, e o Dependency Map exibe visualmente as relações de dependência e impacto entre eles.**

* \[ \] B) CIs são arquivos de log de erros gerados pelo sistema operacional Linux da instância.

* \[ \] C) CIs são regras de segurança de rede aplicadas via firewall virtual.

* \[ \] D) CIs representam exclusivamente contas de usuários inativas no Active Directory.

> **Resposta Correta: A**
> **Explicação:** No CMDB, CIs são os ativos e serviços de TI, e o Dependency Map permite visualizar a estrutura de interdependência entre eles para análise de impacto.

### Questão 49

Ao realizar uma operação de *Load Data* na importação de dados, onde os registros brutos ficam armazenados antes da execução do *Transform Map*?

* \[ \] A) Na tabela final de destino (`Target Table`).

* \[x\] **B) Em uma tabela temporária de *Import Set* criada especificamente para a carga.**

* \[ \] C) No cache do navegador do usuário.

* \[ \] D) Na tabela `sys_audit`.

> **Resposta Correta: B**
> **Explicação:** O *Load Data* grava os registros em uma tabela temporária de staging (*Import Set Table*). A tabela de destino só é afetada ao executar o *Transform Map*.

### Questão 50

Qual é a principal função do *Transform Map* durante o processo de importação por *Import Sets*?

* \[ \] A) Converter arquivos PDF para documentos do Microsoft Word.

* \[x\] **B) Mapear a correspondência entre os campos da tabela temporária de Import Set e os campos da tabela de destino final no sistema.**

* \[ \] C) Excluir os registros duplicados diretamente no computador do usuário.

* \[ \] D) Alterar a senha dos usuários importados.

> **Resposta Correta: B**
> **Explicação:** O *Transform Map* define qual coluna da planilha/fonte de origem corresponde a qual campo do banco de dados na ServiceNow.

### Questão 51

O que o parâmetro `Coalesce` faz quando marcado em um campo dentro de um *Transform Map*?

* \[ \] A) Apaga o campo se estiver em branco.

* \[x\] **B) Funciona como uma chave primária de busca para determinar se um registro existente deve ser atualizado ou se um novo registro deve ser criado.**

* \[ \] C) Criptografa o valor do campo com chave RSA.

* \[ \] D) Oculta o campo no formulário de destino.

> **Resposta Correta: B**
> **Explicação:** Se o valor do campo `Coalesce` for encontrado na tabela de destino, o registro existente é **atualizado**; caso contrário, um novo registro é **inserido**.

### Questão 52

O que acontece se uma importação de dados for executada via Transform Map sem nenhum campo configurado com `Coalesce`?

* \[ \] A) A importação será cancelada com erro crítico.

* \[x\] **B) Todos os registros da fonte serão inseridos como novos registros na tabela de destino, podendo gerar duplicatas.**

* \[ \] C) Os registros antigos da tabela de destino serão sobrescritos aleatoriamente.

* \[ \] D) O sistema criará uma nova tabela para cada linha da planilha.

> **Resposta Correta: B**
> **Explicação:** Sem um parâmetro de unicidade (`Coalesce`), o sistema assume que todas as linhas são novas e insere cada uma delas no banco de dados.

### Questão 53

Qual é a tabela central e raiz no CMDB da qual deriva a maioria das classes de Configuration Items (CIs)?

* \[ \] A) `cmdb`

* \[x\] **B) `cmdb_ci`**

* \[ \] C) `cmdb_rel_ci`

* \[ \] D) `asset`

> **Resposta Correta: B**
> **Explicação:** `cmdb_ci` é a tabela base para os Configuration Items na infraestrutura da ServiceNow.

### Questão 54

Qual tabela armazena os relacionamentos muitos-para-muitos (N:M) e a estrutura de associação entre CIs e tarefas (`Task`)?

* \[ \] A) `cmdb_rel_ci`

* \[x\] **B) `task_ci`**

* \[ \] C) `sys_task_cmdb`

* \[ \] D) `cmdb_ci_service`

> **Resposta Correta: B**
> **Explicação:** A tabela `task_ci` vincula múltiplos CIs afetados a uma tarefa específica (como uma Mudança ou Incidente).

### Questão 55

O que é a *Identification and Reconciliation Framework* (IRE) no contexto do CMDB?

* \[ \] A) Um mecanismo para cobrança de licenças de uso de hardware.

* \[x\] **B) Um conjunto de regras centralizado que garante a integridade dos dados do CMDB, prevenindo a duplicação de CIs ao receber dados de múltiplas fontes de integração.**

* \[ \] C) Um relatório estatístico de acesso ao portal de autoatendimento.

* \[ \] D) Uma ferramenta para compactação de arquivos de log.

> **Resposta Correta: B**
> **Explicação:** A IRE avalia regras de identificação e prioridade de fontes de dados para evitar registros duplicados e manter o CMDB confiável.

### Questão 56

Por que é uma boa prática integrar o CMDB com os módulos de gerenciamento de Incidentes e Mudanças?

* \[ \] A) Para permitir que usuários comuns alterem o sistema operacional dos servidores.

* \[x\] **B) Para identificar o impacto em cascata de falhas ou alterações em serviços de negócio e componentes de infraestrutura.**

* \[ \] C) Para reduzir o custo das licenças de software.

* \[ \] D) Para desativar a necessidade de backups diários.

> **Resposta Correta: B**
> **Explicação:** Ao associar CIs a incidentes e mudanças, as equipes conseguem analisar o impacto cruzado em serviços críticos da empresa.

## Domínio 5: Platform Administration, Management & Upgrades

### Questão 57

O que é um *Update Set* na plataforma ServiceNow?

* \[ \] A) Um conjunto de dados de usuários exportados em formato XML.

* \[x\] **B) Um contêiner que captura alterações de configuração e customizações realizadas no sistema para permitir sua movimentação entre instâncias (ex: de Dev para Teste/Prod).**

* \[ \] C) Uma ferramenta para atualizar a versão da linguagem Java na instância.

* \[ \] D) Um relatório semanal de desempenho de chamados.

> **Resposta Correta: B**
> **Explicação:** *Update Sets* capturam mudanças em tabelas de sistema, scripts, formulários e configurações (`sys_update_xml`) para migração entre ambientes.

### Questão 58

Quais destes itens **NÃO** são capturados automaticamente dentro de um *Update Set*?

* \[ \] A) Business Rules e Client Scripts.

* \[ \] B) Modificações em formulários e tabelas.

* \[x\] **C) Dados transacionais do dia a dia (registros de novos Incidentes, Usuários, Tarefas e CIs do CMDB).**

* \[ \] D) Workflows e UI Policies.

> **Resposta Correta: C**
> **Explicação:** *Update Sets* capturam **configurações e estrutura** (customizações), mas **não salvam dados transacionais** (registros criados por usuários).

### Questão 59

O que o processo de *Preview Update Set* realiza durante a migração de customizações entre instâncias?

* \[ \] A) Apaga permanentemente a instância de destino.

* \[x\] **B) Compara as alterações do Update Set com o ambiente atual e identifica potenciais conflitos ou dependências ausentes antes do commit.**

* \[ \] C) Executa um backup completo do servidor em nuvem.

* \[ \] D) Envia um e-mail para todos os usuários cadastrados.

> **Resposta Correta: B**
> **Explicação:** A etapa de *Preview* inspeciona o pacote de alterações para garantir que não haja erros ou conflitos com o ambiente de destino.

### Questão 60

O que exatamente é mantido dentro de cada registro na tabela de personalizações do Update Set (`sys_update_xml`)?

* \[ \] A) O arquivo binário do sistema operacional.

* \[x\] **B) O código XML que representa a alteração de configuração efetuada por um desenvolvedor ou administrador.**

* \[ \] C) A imagem do perfil do usuário.

* \[ \] D) O histórico de chamadas de voz efetuadas pela equipe.

> **Resposta Correta: B**
> **Explicação:** Cada alteração capturada por um Update Set é gravada sob a forma de um nó XML na tabela `sys_update_xml`.

### Questão 61

Qual é a finalidade do módulo *Guided Setup* na plataforma ServiceNow?

* \[ \] A) Ensinar programação avançada em Python.

* \[x\] **B) Fornecer uma lista de verificação e assistente passo a passo para orientar os administradores na configuração inicial de instâncias e aplicações.**

* \[ \] C) Agendar tarefas de limpeza de cache de memória.

* \[ \] D) Bloquear conexões de usuários não autorizados.

> **Resposta Correta: B**
> **Explicação:** O *Guided Setup* orienta administradores nas etapas fundamentais para colocar módulos e aplicações em operação.

### Questão 62

O que é um *Skip Log* gerado após a execução de uma atualização de versão da instância (*System Upgrade*)?

* \[ \] A) Um erro que força a restauração do backup.

* \[x\] **B) Um registro indicando que uma alteração nativa foi ignorada durante o upgrade porque o artefato correspondente foi customizado localmente.**

* \[ \] C) O registro de usuários que não fizeram login no último ano.

* \[ \] D) A lista de e-mails de notificação descartados.

> **Resposta Correta: B**
> **Explicação:** Quando um objeto nativo é modificado pela equipe local, o processo de upgrade preserva a versão customizada e gera uma entrada no *Skip Log* para revisão.

### Questão 63

Por que é essencial revisar a *Upgrade History* após atualizar uma instância para uma nova versão da ServiceNow (ex: Washington DC, Xanadu)?

* \[ \] A) Para apagar os usuários inativos.

* \[x\] **B) Para tratar conflitos apontados no Skip Log e decidir entre manter a customização local ou adotar a nova versão padrão da ServiceNow.**

* \[ \] C) Para redefinir as chaves de acesso da API REST.

* \[ \] D) Para recriar todas as tabelas do banco de dados.

> **Resposta Correta: B**
> **Explicação:** A revisão garante que a instância aproveite as correções e novidades da nova versão sem quebrar regras de negócio locais.

### Questão 64

O que faz a ferramenta *Automated Test Framework* (ATF) na plataforma?

* \[ \] A) Realiza testes de estresse em roteadores de rede física.

* \[x\] **B) Permite criar e executar testes automáticos em formulários, portais e rotinas para validar que o sistema continua funcionando após upgrades ou mudanças.**

* \[ \] C) Envia questionários de satisfação para clientes.

* \[ \] D) Testa a velocidade de digitação dos analistas de atendimento.

> **Resposta Correta: B**
> **Explicação:** O ATF automatiza os testes regressivos e funcionais da plataforma, garantindo estabilidade rápida após customizações e upgrades.

### Questão 65

Para que serve o módulo *Scheduled Jobs* na administração da instância?

* \[ \] A) Para criar reuniões no Google Calendar.

* \[x\] **B) Para agendar a execução automática e recorrente de scripts, relatórios ou tarefas em horários pré-determinados no servidor.**

* \[ \] C) Para desligar o servidor durante os finais de semana.

* \[ \] D) Para limitar as horas de trabalho dos analistas.

> **Resposta Correta: B**
> **Explicação:** *Scheduled Jobs* permitem automatizar rotinas do sistema (ex: limpar logs antigos, enviar relatórios toda segunda-feira às 08:00).

### Questão 66

Qual é a principal utilidade do aplicativo *App Engine Studio* (AES) / *Studio* na ServiceNow?

* \[ \] A) Editar arquivos de áudio e vídeo do portal.

* \[x\] **B) Oferecer um ambiente de desenvolvimento integrado (IDE) para criar e gerenciar aplicações escopadas, formulários, fluxos e dados de forma visual.**

* \[ \] C) Fazer a gestão da folha de pagamento de funcionários.

* \[ \] D) Monitorar o tráfego da rede Wi-Fi da empresa.

> **Resposta Correta: B**
> **Explicação:** O *Studio* e o *App Engine Studio* são os ambientes focados no desenvolvimento low-code e pro-code de aplicações escopadas na ServiceNow.

### Questão 67

Como um administrador pode restringir a exibição de módulos ou aplicações inteiras no menu de navegação (*Application Navigator*)?

* \[ \] A) Excluindo o arquivo de código do servidor.

* \[x\] **B) Configurando o campo *Roles* no registro da Aplicação ou Módulo para indicar quais papéis são exigidos para sua visualização.**

* \[ \] C) Alterando a resolução de tela do monitor.

* \[ \] D) Ocultando a barra de rolagem do navegador.

> **Resposta Correta: B**
> **Explicação:** A visibilidade de itens no *Application Navigator* é governada pelas *Roles* configuradas nos módulos e menus do aplicativo.

### Questão 68

Qual é a utilidade das *Notifications* (`sysevent_email_template` / `sysevent_in_app_notification`) na plataforma?

* \[ \] A) Exibir avisos de atualização de antivírus.

* \[x\] **B) Disparar automaticamente mensagens por e-mail ou alertas no aplicativo quando eventos específicos ocorrem no banco de dados ou via fluxo.**

* \[ \] C) Aumentar o tamanho do texto nos formulários.

* \[ \] D) Impedir o salvamento de chamados em duplicidade.

> **Resposta Correta: B**
> **Explicação:** O sistema de Notificações envia comunicados e alertas para usuários quando gatilhos ou eventos do sistema são acionados.

### Questão 69

O que são os *Events* no gerenciamento de eventos da plataforma (`sysevent`)?

* \[ \] A) Conferências presenciais promovidas pela ServiceNow.

* \[x\] **B) Registros especiais gerados pelo sistema ou por scripts para sinalizar que algo relevante aconteceu, podendo disparar notificações ou rotinas.**

* \[ \] C) Erros fatais que interrompem a execução do servidor.

* \[ \] D) Entradas no calendário pessoal dos analistas.

> **Resposta Correta: B**
> **Explicação:** *Events* funcionam como sinalizadores internos (ex: `incident.inserted`, `password.reset`) que podem ser consumidos por notificações e automações.

### Questão 70

Como o parâmetro de cálculo de Prioridade em uma tarefa (`Task`) é determinado por padrão na ServiceNow?

* \[ \] A) Selecionado manualmente sem nenhuma relação com outros campos.

* \[x\] **B) Calculado automaticamente combinando os valores dos campos de Impacto (*Impact*) e Urgência (*Urgency*).**

* \[ \] C) Definido pelo cargo do usuário solicitante.

* \[ \] D) Gerado aleatoriamente pelo banco de dados.

> **Resposta Correta: B**
> **Explicação:** A plataforma utiliza uma matriz de prioridade padrão que cruza **Impacto** e **Urgência** para definir o valor do campo **Priority**.

### Questão 71

O que faz a opção *Update Selected* disponível na visão de lista (*List View*) de registros?

* \[ \] A) Atualiza o navegador do usuário.

* \[x\] **B) Abre um formulário em branco onde as alterações feitas serão aplicadas simultaneamente a todos os registros selecionados por caixa de seleção.**

* \[ \] C) Exclui os registros selecionados sem confirmação.

* \[ \] D) Exporta apenas os registros selecionados para o formato PDF.

> **Resposta Correta: B**
> **Explicação:** O *Update Selected* permite a edição em lote dos campos escolhidos para múltiplos registros marcados na lista.

### Questão 72

O que é uma *Metric* (Métrica) na plataforma ServiceNow?

* \[ \] A) A quantidade de linhas de código gravadas em um script.

* \[x\] **B) Um recurso que mede e registra o tempo que um registro passa em determinado estado ou sob a responsabilidade de um valor específico.**

* \[ \] C) A velocidade de download da conexão de internet.

* \[ \] D) O número de cliques que o usuário faz em um botão.

> **Resposta Correta: B**
> **Explicação:** Métricas servem para medir a duração de estados (ex: quanto tempo um chamado ficou no estado *Awaiting Caller*).

### Questão 73

Qual é o objetivo dos *Dashboards* na plataforma ServiceNow?

* \[ \] A) Permitir o envio de mensagens de texto entre usuários.

* \[x\] **B) Centralizar relatórios, indicadores de desempenho (KPIs) e guias analíticas em um painel visual e dinâmico para acompanhamento.**

* \[ \] C) Armazenar cópias de backup das tabelas do sistema.

* \[ \] D) Substituir o uso de senhas de acesso.

> **Resposta Correta: B**
> **Explicação:** *Dashboards* reúnem relatórios, widgets de Performance Analytics e dados em tempo real em uma única página interativa.

### Questão 74

Qual é a finalidade dos *Data Collectors* no Performance Analytics?

* \[ \] A) Importar contatos de e-mail do Microsoft Outlook.

* \[x\] **B) Executar rotinas agendadas para coletar e agregar dados históricos de tendências para análise contínua de indicadores.**

* \[ \] C) Apagar registros duplicados do banco de dados.

* \[ \] D) Validar se as senhas dos usuários expiraram.

> **Resposta Correta: B**
> **Explicação:** *Data Collectors* buscam dados periodicamente no banco para criar relatórios históricos de tendências no Performance Analytics.

### Questão 75

O que o módulo *System Localization* permite fazer na instância?

* \[ \] A) Rastrear a localização geográfica de notebooks via GPS.

* \[x\] **B) Configurar traduções de idioma, formatos de data/hora, símbolos de moeda e mensagens do sistema para diferentes regiões.**

* \[ \] C) Mudar o centro de dados onde a instância em nuvem está hospedada.

* \[ \] D) Alterar o idioma de programação do servidor.

> **Resposta Correta: B**
> **Explicação:** O módulo de *Localization* gerencia a internacionalização, traduções e regionalização da interface da plataforma.

### Questão 76

O que é a integração por Web Services (REST / SOAP) na plataforma ServiceNow?

* \[ \] A) Um plugin para navegação na internet dentro do portal.

* \[x\] **B) Interfaces padronizadas que permitem que sistemas externos consultem, insiram ou atualizem dados e registros dentro do ServiceNow de forma automatizada.**

* \[ \] C) Uma extensão para conexões via modem discado.

* \[ \] D) Um protocolo exclusivo para envio de relatórios impressos.

> **Resposta Correta: B**
> **Explicação:** APIs REST e SOAP permitem a integração de sistemas externos com o banco de dados e processos do ServiceNow.

### Questão 77

Qual é a utilidade da conta no *ServiceNow Developer Portal* (`developer.servicenow.com`) para quem está estudando para a certificação CSA?

* \[ \] A) Comprar licenças de uso comercial do sistema.

* \[x\] **B) Solicitar uma Instância Pessoal de Desenvolvimento (PDI) gratuita para praticar e ter acesso à documentação técnica e cursos.**

* \[ \] C) Agendar viagens para eventos da empresa.

* \[ \] D) Fazer o pagamento da taxa de exame de certificação.

> **Resposta Correta: B**
> **Explicação:** O Developer Portal disponibiliza PDIs gratuitas, sendo o ambiente ideal para praticar todos os cenários cobrados na prova de certificação CSA.