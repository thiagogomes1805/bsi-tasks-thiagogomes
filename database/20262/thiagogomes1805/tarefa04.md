## Questão 04 - Análise de Cenários ACID

* **a) Queda de energia no meio de uma transferência deixou o valor debitado da conta de origem, mas não creditado na conta de destino.**
  * **Propriedade violada:** **Atomicidade**.
  * **Justificativa:** A transação foi executada apenas pela metade. Sem a atomicidade, o sistema não desfez (*rollback*) o débito quando ocorreu a falha.

* **b) Dois atendentes debitam, ao mesmo tempo, o mesmo saldo de uma conta.**
  * **Propriedade envolvida:** **Isolamento**.
  * **Justificativa:** Trata-se do controle de concorrência. O isolamento garante que o segundo débito aguarde ou leia o saldo atualizado após a execução do primeiro.

* **c) O sistema confirma a operação, mas após reiniciar o servidor o dado foi perdido.**
  * **Propriedade violada:** **Durabilidade**.
  * **Justificativa:** Uma vez realizada a confirmação (*commit*), os dados deveriam estar salvos em meio não volátil de forma permanente.

* **d) Uma transferência que levaria o saldo abaixo do limite permitido é rejeitada pelo banco.**
  * **Propriedade atuando:** **Consistência**.
  * **Justificativa:** O SGBD barrou a transação para impedir a violação de uma regra de negócio / restrição de integridade do sistema.