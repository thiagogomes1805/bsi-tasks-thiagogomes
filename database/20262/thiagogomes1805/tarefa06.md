## Questão 06 - Mini-Projeto Conceitual (Empresa de Software)

### Entidades Principais
1. **Cliente:** Empresas contratantes.
2. **Projeto:** Projetos desenvolvidos para cada cliente.
3. **Squad:** Equipes multifuncionais.
4. **Membro:** Integrantes da empresa (devs, testadores, líderes, etc.).
5. **Sprint:** Iterações do projeto.
6. **Tarefa (Issue):** Atividades e demandas de desenvolvimento.
7. **Release:** Versões entregáveis do software.

### Atributos das Entidades
* **Cliente:** `id_cliente`, `razao_social`, `cnpj`, `email`.
* **Projeto:** `id_projeto`, `nome`, `descricao`, `data_inicio`.
* **Squad:** `id_squad`, `nome_squad`.
* **Membro:** `id_membro`, `nome`, `email`, `papel` (Dev, Testador, Líder Técnico, Supervisor, Gerente de Produto).
* **Sprint:** `id_sprint`, `numero`, `data_inicio`, `data_fim`, `objetivo`.
* **Tarefa:** `id_tarefa`, `titulo`, `descricao`, `status` (A Fazer, Em Andamento, Concluída), `horas_estimadas`.
* **Release:** `id_release`, `versao`, `data_lancamento`.

### Relacionamentos e Cardinalidades
* **Cliente -> Projeto (1:N):** Um cliente pode ter vários projetos, mas cada projeto pertence a apenas um cliente.
* **Squad -> Membro (1:N):** Uma squad possui vários membros, e cada membro pertence a apenas uma squad por vez.
* **Squad -> Projeto (N:M):** Uma squad pode atuar em vários projetos, e um projeto pode ter várias squads envolvidas.
* **Projeto -> Sprint (1:N):** Um projeto é dividido em várias sprints, e cada sprint pertence a apenas um projeto.
* **Sprint -> Tarefa (1:N):** Uma sprint agrupa várias tarefas, e uma tarefa é planejada para uma sprint.
* **Membro -> Tarefa (1:N):** Um membro pode ser responsável por várias tarefas, e uma tarefa é atribuída a um membro.
* **Projeto -> Release (1:N):** Um projeto possui várias releases, e cada release pertence a um projeto.
* **Release -> Tarefa (1:N):** Uma release inclui várias tarefas concluídas.

### Regras de Integridade (Restrições)
1. Toda squad deve possuir exatamente um membro com a função de "Líder Técnico".
2. Toda tarefa precisa estar obrigatoriamente vinculada a um projeto ativo.
3. Uma tarefa só pode ser atribuída a um membro pertencente à squad alocada naquele projeto.
4. A data de término de uma sprint deve ser estritamente posterior à sua data de início.
5. Uma tarefa só pode ser vinculada a uma release se o seu status for "Concluída".