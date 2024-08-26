
### Visão Geral

- Um processo é composto por contexto, código, dados, heap e pilha.
- Processo demanda uma quantidade de sobrecarga para a execução.
- O que ocorre quando há múltiplas ações ao mesmo tempo?
- Se há vários processos que estão executando de forma paralela. Como isso é tratado em uma única CPU?
- No momento de finalizar um processo, quais estruturas serão destruídas?

**Processo leve** (Lightweight Process - Thread)

- Ano de 1979, foi introduzido o conceito (o thread), onde o espaço de endereçamento era compartilhado;
- **Definição:** unidade básica de utilização da CPU, que compreende um ID, um contador de programa, um conjunto de registradores e uma pilha;]
- Um processo pode consistir de vários threads, cada uma executada de forma separada.