## Questão 05 - Aspectos Tratados pelo SGBD

* **Recuperação (*Recovery*):** É a capacidade de restaurar o banco de dados a um estado consistente em caso de falhas de hardware ou software. O SGBD gerencia através de *logs* de transações (técnicas de UNDO/REDO) e *checkpoints*.
* **Integridade (*Integrity*):** Garante a exatidão e confiabilidade dos dados armazenados. O SGBD gerencia aplicando restrições (*constraints*) na criação de tabelas (ex: Chave Primária, Chave Estrangeira, NOT NULL, CHECK).
* **Redundância (*Redundancy*):** É a duplicação desnecessária de dados em vários locais. O SGBD gerencia através do processo de Normalização de Dados, garantindo que cada dado fique em seu devido local.
* **Inconsistência (*Inconsistency*):** Ocorre quando cópias do mesmo dado apresentam valores divergentes. O SGBD gerencia eliminando a redundância e controlando transações através das regras ACID.