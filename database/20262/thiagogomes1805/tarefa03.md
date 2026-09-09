## Questão 03 - Propriedades ACID

### Atomicidade
* **Conceito:** A transação é tratada como uma unidade indivisível ("tudo ou nada"). Ou todas as operações são executadas com sucesso, ou nenhuma é mantida.
* **Exemplo:** Transferência bancária de R$ 100 de A para B (composta por débito em A e crédito em B).
* **Sem a garantia:** Se houver uma falha após o débito em A e antes do crédito em B, o dinheiro sumirá da conta de origem sem chegar à conta de destino.

### Consistência
* **Conceito:** A transação deve levar o banco de um estado válido a outro estado válido, respeitando todas as regras de integridade.
* **Exemplo:** Uma conta não pode ficar com saldo menor que zero se não houver limite de crédito contratado.
* **Sem a garantia:** A conta ficaria com saldo negativo sem autorização, violando as regras do banco.

### Isolamento
* **Conceito:** Transações executadas concorrentemente não devem interferir umas nas outras, comportando-se como se fossem executadas sequencialmente.
* **Exemplo:** Duas transferências simultâneas envolvendo a mesma conta A ocorrem sem que um cálculo de saldo sobrescreva o outro incorretamente.
* **Sem a garantia:** Ocorreriam leituras de dados desatualizados/incompletos e perda de atualizações de saldo.

### Durabilidade
* **Conceito:** Após a confirmação (*commit*) da transação, suas alterações persistem de forma permanente no banco de dados, mesmo em caso de falha de energia ou servidor.
* **Exemplo:** Após a mensagem de "transferência realizada", o novo saldo permanece salvo no disco.
* **Sem a garantia:** Se o servidor reiniciar logo após o comprovante emitido, a transferência poderia sumir e o saldo retornar ao estado antigo.