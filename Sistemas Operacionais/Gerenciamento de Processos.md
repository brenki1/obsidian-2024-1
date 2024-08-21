
### Conceito de Processo

- É uma abstração que representa um programa em execução;
- É uma entidade ativa que utiliza um conjunto de recursos, como processador e registradores especiais, para executar uma função (instruções);
- Pode ser referenciado: "task" ou "job".
##### Exemplo: 
cópia de arquivo ou execução de rotinas de um programa.

### Ciclo de vida do processo

**Estado:** durante sua execução, um processo passa por diversos estados, refletindo o seu comportamento dinâmico, isto é, a sua evolução no tempo.

- **Novo:** o processo está sendo criado;
- **Execução:** o processo está utilizando um processador;
- **Pronto:** o processo está apto a utilizar o processador quando estiver disponível;
- **Bloqueado:** o processo está esperando ou utilizando um recurso qualquer de E/S;
- **Encerrado:** processo termina sua execução.

### Bloco de controle de processo


- ##### Bloco de Controle do Processo (BCP) (process control block)
	- Representação de um processo num SO (repositório de informações).
- Contém informações necessárias para a execução do processo: Iniciada, Interrompida e Retomada.
- Normalmente há uma estrutura no kernel:
	- Exemplo: Linux: *struct task_struct*;
	- Usado para gerenciar processos em comutação da CPU.

##### Contém:

- **Estado do processo:** novo, pronto, em execução, parado, etc.
- **Contador de programa:** endereço da próxima instrução.
- **Registradores da CPU:** 
	- variam em número e em tipo, dependendo da arquitetura de computadores.
	- Incluem acumuladores, registradores e pilha.
	- Quando ocorre uma interrupção, essa informação deve ser salva juntamente com o contador do programa.

- estado corrente do processo;
- identificação do processo (PID);
- ponteiro para o processo-pai (parent process);
- prioridade do processo;
- lista de ponteiros para as regiões alocadas de memória;
- conteúdo dos registradores do processador.
==Essas informações são importantes para a troca de processos que ocorre na CPU==

### BCP - Comutação de Contexto

- A troca de contexto (processos) pode gerar overhead.
- O tempo de comutação de contexto pode ser pura sobrecarga;
- **Nenhum trabalho será realizado**;
- O tempo de comutação depende bastante do **suporte de hardware**;
- **O Escalonador ("Scheduler")**:
	- Módulo do S.O responsável pelo controle do recurso "processador", o qual divide o tempo da CPU entre os processos do sistema.

### Escalonadores

- **Scheduler de longo prazo** (job scheduler) - seleciona qual processo deverá ser carregado na memória para execução.
- **Scheduler de curto prazo** (ou CPU scheduler) - seleciona um dos processos prontos para execução e aloca a CPU para ele.
- A distinção entre estes dois é a **frequência de sua execução**.
- Em alguns S.O.s, o **Scheduler de longo prazo** pode não existir ou ser mínimo (ex. UNIX).

##### Escalonadores de longo prazo (jobs)
- Selecionar processos a serem inseridos na fila de pronto;
- Controla o grau de multiprogramação;
- Pode ser mais lento e usar mais informação.
##### Escalonadores de curto prazo (CPU)
- Selecionar os processos a receber a CPU a cada instante;
- Chamadas em milissegundos.

#### Fila dos escalonadores

- **Fila de Jobs** - consiste em todos os processos que estão no sistema.
- **Fila Pronta** - conjunto de processos residente na memória principal que estão prontos e em espera para entrar em execução. Implementando na forma de lista encadeada.
- **Fila de Dispositivos** - conjunto de processos esperando por um dispositivo de E/S;
- Processos migram entre as várias filas.

### Tipos de Processos
- Os processos ou tarefas podem ser descritos da seguinte forma:
	- **Processo I/O-bound** - gasta mais tempo fazendo E/S que cálculo, muito pouco tempo de ocupação de CPU:
		- Devolve deliberadamente o controle da CPU.
	- **Processo CPU-bound** - gasta mais tempo fazendo cálculo, longo tempo de CPU:
		- Pode monopolizar a CPU, dependendo do algoritmo de escalonamento.