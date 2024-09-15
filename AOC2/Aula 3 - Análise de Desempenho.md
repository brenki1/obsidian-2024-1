### Princípios quantitativos do Projeto de Computadores
- Estudo anterior: potência/energia, custo, confiabilidade.
- Estudo corrente: como definir, medir e resumir desempenho?
	- podemos explorar orientações e princípios que são úteis no projeto e na análise de computadores (equações para avaliar alternativas).
- Observações importantes sobre o projeto:
	- Tirar proveito do paralelismo
	- Explorar o princípio da localidade
	- Foco no caso comum ([[Lei de Amdahl]])
- O objetivo é introduzir o conceito de desempenho em arquitetura de computadores, quais fatores são determinantes para o desempenho, como medir o desempenho e mostrar que o tempo de execução é a medida mais confiável.

### Motivação para o estudo de Análise de Desempenho
- O que é desempenho?
- Como medir o desempenho?
- Quais são as métricas básicas para a análise de desempenho?
- Avaliando o desempenho:
	- Por que alguns HWs tem melhor desempenho para programas diferentes?
	- Quais fatores de desempenho do sistema estão relacionados com o hardware? i.e., necessito de uma nova máquina ou de um novo sistema operacional?
	- Como o conjunto de instruções da máquina afeta o desempenho?

### Desempenho Computacional
- Tempo de Resposta (latência)
	- Quanto tempo leva para executar (rodar) meu programa?
	- Quanto tempo leva para executar um programa qualquer?
	- Quanto tempo eu devo esperar para uma consulta ao banco de dados?
- Vazão (Throughput)
	- Quantos processos (threads) a máquina pode executar por vez?
	- Qual é a taxa média de execução?
	- Quanto trabalho foi feito?
- As seguintes alterações num sistema aumentam o throughput, diminuem a latência ou ambos?
	- Se atualizamos (upgrade) a máquina com um novo processador mais rápido.
	- Se adicionamos uma nova máquina num sistema que utiliza múltiplos processadores para tarefas distintas.

### O que é o tempo?
- Tempo Consumido (Elapsed Time)
	- Contabiliza tudo (disk and memory accesses, I/O, etc)
	- É um número útil, mas frequentemente não é uma boa medida para fins de comparação
- Tempo de CPU (CPU time)
	- Não contabiliza I/O ou tempo gasto para rodar outros programas.
	- Pode ser quebrado em tempo de sistema e tempo de usuário
		- pode ser medido com o comando UNIX "time".
- Nosso interesse: tempo de CPU do usuário
	- tempo gasto efetivamente para executar as linhas de código do programa usuário.

### Definição de Desempenho
- Dado duas plataformas X e Y
	- X é 'n' vezes mais rápida do que Y para uma determinada aplicação se
	- $$ n = \frac{Tempo_y}{Tempo_x}$$
	- Desempenho de "X é n vezes mais rápido do que Y"
	- $$n = \frac{Tempo_y}{Tempo_x} = \frac{\frac{1}{Desempenho_y}}{\frac{1}{Desempenho_x}} = \frac{Desempenho_x}{Desempenho_y}$$

### Exemplo

Problema:

- Máquina A executa o programa P em 20 segundos
- Máquina B executa o programa P em 25 segundos
- $$n = \frac{25}{20} = 1.25$$
- A é mais rápida do que B por um fator de 1.25 (taxa)
- Precisamos de medidas
	- Comparação das propriedades das máquinas
	- Comparação das propriedades de software (compiladores)
- Qual é o propósito?
	- Tomar decisões de aquisição
	- Desenvolvimento de novas arquiteturas

### Ciclo de Clock (Clock cycle)
- Em vez de considerar tempo de execução em segundos, muitas vezes utilizamos a unidade de ciclos. Assim, a referência do desempenho frequentemente é baseada em ciclos de clock.
- $$\frac{segundos}{programa} = \frac{ciclos}{programa} \times \frac{segundos}{ciclos}$$
- Eventos de clock indicam quando começam as atividades
- Tempo de ciclo = tempo entre os eventos de clock.
- Taxa de clock = ciclos/segundo
- Um clock de 500mhz tem um tempo de 2ns.

### Métricas Básicas
- Ciclos de clock de CPU para um programa
- $$tempoCPU = ciclosClockProg \times TempoCicloClock$$
- $$tempoCPU = \frac{ciclosClockProg}{frequenciaClock}$$
- Além do número de ciclos de clock, também podemos contar o número de instruções executadas (Instruction Count - IC)
- Se soubermos o número de ciclos de clock e o IC, poderemos calcular o número médio de ciclos de clock por instruções (Clock Cicle per Instruction - CPI)
- Projetistas também usam Instruções por clock (IPC)

### Tempo de CPU

$$ Tempo de CPU = IC \times CPI \times TempoCiclo de Clock$$
- O tempo de CPU do processador depende igualmente dessas três características. Para melhorar o desempenho devemos:
	- Aumentar a frequência do clock = diminuir o período do clock.
	- Reduzir o número de ciclos por instrução (CPI)
	- Reduzir a quantidade de instruções (IC)
- É difícil mudar um parâmetro de modo completamente isolado, pois as tecnologias envolvidas na mudança de característica são interdependentes:
	- Tempo de ciclo de clock ⟶ tecnologia e organização do Hardware
	- CPI ⟶ organização e arquitetura do conjunto de instruções (ISA)
	- IC ⟶ ISA e tecnologia do compilador (implementação)
- O termo CPI utilizado na formula acima é um valor médio de todas as instruções executadas na aplicação.
- Diferentes instruções podem consumir quantidades diferentes de ciclos para executarem, assim: $$ TempoCPU = (\sum_{i=1}^{n} IC_i \times CPI_i) \times ClockTime$$
- Onde o índice i representa as diversas classes de instruções e seus respectivos CPIs.