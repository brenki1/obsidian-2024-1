
### Máquina de Ciclo Único:

##### Todas as instruções completam em um ciclo de relógio (CPI = 1)

##### Algumas instruções usam mais HW que outras!
- LoadWord ocupa mais HW
	- 5 módulos vs. 4 para Tipo-Re StoreWord ou 3 para BEQ

##### O período do relógio deve garantir o tempo para a instrução mais longa -> ineficiência!
- imagine que MUL é incluída?

### Exemplo numérico

##### Assuma:
- 2ns para acesso as memórias;
- 1ns para leitura ou escrita no banco de registradores;
- 2ns para a ALU;
- No monociclo, período de relógio = 8ns.

##### Imaginemos que um programa seja composto de 24% loads, 12% stores, 44% R-format, 20% branches.

##### Se tivéssemos um relógio variável, como seria o ganho?
- Loads: 24%,       levam 8ns; 1.92
- Stores: 12%       levam 7ns; 0.84
- Tipo-R: 44%,      levam 6ns; 2.64
- BEQ:    20%        levam 5ns; 1.00

Se o relógio fosse variável, o ciclo médio de relógio seria 6.40ns, e a aceleração seria de 1.25 vezes;

Imagine o problema caso incluíssemos um multiplicador, que aumentaria o tempo da ALU em 4ns.

### Implementação Multi-Ciclo

**Queremos uma implementação mais eficiente**

**Cada passo levará um ciclo de relógio**
- Não cada instrução
- CPI > 1
**Menor período
- O ciclo de relógio é restrito pelo passo mais longo, não pela instrução mais longa
- Instruções simples levam menos ciclos
**Maior desempenho no final
**Versátil (pode ser mais facilmente estendido com outras instruções)


### Quão rápida a frequência pode ser?

Depende do que o precisa ser feito por ciclo de relógio

##### Pode fazer: várias operações "baratas" por ciclo
- Portas simples (AND, OR, ...);
- Registradores simples (PC);
- Extensão de sinal, deslocamento, multiplexador.

#### Adicionalmente: um módulo "caro"
- Operações do ULA;
- Acesso ao banco de registradores (duas leituras ou uma escrita);
- Acesso à memória (leitura ou escrita).