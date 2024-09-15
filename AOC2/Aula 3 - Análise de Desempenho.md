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
	- $$ n = \frac{Tempo_y}{Tempo_x}
