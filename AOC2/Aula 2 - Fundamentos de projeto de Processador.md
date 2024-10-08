### Notas
- Crescimento de 52% ao ano é atribuído a inovações arquitetônicas e organizacionais avançadas e altas taxas de clock
- Garantiu a supremacia dos microcomputadores baseados em um único processador (PCs). Minicomputadores foram substituídos por microcomputadores, Mainframes e até supercomputadores foram substituídos pela união de microcomputadores (sistemas distribuídos).
- A Arquitetura de computadores, portanto, precisou se adequar as novas tendências.
- O crescimento de 22% ao ano é decorrente de um processo de paralelização através da técnica de multicores.
- A redução da taxa de crescimento é devido a:
	- Superaquecimento, necessitando de refrigeração forçada.
	- Saturação do paralelismo em nível de instrução (ILP).
	- Saturação da velocidade (tempo de resposta) da memória.
- Em anos recentes o aumento da velocidade de clock tem caído a 1% ao ano.
**Lei de Moore**
- o número de transistores em um único chip dobram no período de 18 a 24 meses.

- Intel anunciou, em 2004, que abandonaria o projeto de um novo processador mais veloz e passaria a garantir maior desempenho através de múltiplos processadores por chip.
- Portanto, as novas arquiteturas deixaram de focar em paralelismo a nível de instrução (ILP) para focar em paralelismo a nível de thread (TLP) e paralelismo a nível de dados (DLP)
- Atualmente o ILP é feito implicitamente, de modo transparente ao programador, diferentemente do TLP e DLP, onde o programador necessita explicitar o paralelismo.

### Tendências na Tecnologia
- Tecnologia do circuito lógico integrado
	- a densidade de transistores aumenta em cerca de 35% ao ano e o tamanho do die variando de 10-20% ao ano - mais funcionalidades
- A velocidade dos transistores melhora linearmente com o tamanho
	- equação complexa envolvendo tensões, resistências, capacitâncias, o que pode resultar em aumento das taxas de clock!
- Aumento da capacidade e densidade de memórias DRAMs semicondutoras e flash semicondutoras.
- Escala de desempenho de transistores e fios
	- atrasos em fios não reduzem na mesma escala dos atrasos nos circuitos lógicos.
- A barreira da potência: não é possível consistentemente operar em frequências altas sem alcançar os limites de potência/térmicos.
	- Overclocking: Turbo Mode pode rodar em uma taxa maior de clock por um curto intervalo de tempo.

### O que melhora o desempenho?
- **Nota: sem aumentar a velocidade de clock**
- Realizar mais trabalho por ciclo de clock
	- considerando que os transistores são mais rápidos e de maior eficiência energética...
- Melhorias arquiteturais:
	- explorar mais paralelismo em um thread, melhorar a previsão dos desvios, melhorar as políticas de cache, melhorar as organizações de memória, explorar mais o paralelismo em nível de threads, etc..

### Qual é o caminho a seguir?
- Melhorias nas taxas de clock estão diminuindo.
	- restrições da eficiência energética.
- É cada vez mais difícil otimizar o desempenho individual de um núcleo de processador (core).
- Multi-cores: a cada nova geração o chip microprocessador acomodará um número maior de núcleos de processamento.
- Precisamos de melhores modelos de programação e eficiência na execução de aplicativos multithreaded.
- Precisamos de uma melhor hierarquia de memória
- Precisamos de uma maior eficiência energética
	- Em alguns domínios, os núcleos mais simples são atraentes.
	- Redução da movimentação de dados.

### Potência e Energia: uma perspectiva de sistema
- Como um arquiteto de sistema deve pensar sobre o desempenho, a potência e energia?
- Qual é a potência máxima que um processador pode exigir?
	- se um processador tentar obter mais potência do que a fornecida por um sistema de alimentação, em geral o resultado é uma queda de tensão que pode levar a falha do sistema.
	- Solução: indexação da tensão com a redução da taxa de clock.
- Qual é o consumo de potência sustentado?
	- Projeto Térmico de Potência (Thermal Design Power – TDP)
- Energia e Eficiência Energética:
	- Potência é energia por unidade de tempo – 1 watt = 1 joule por segundo

### Potência x Energia
- Qual é a métrica correta para comparar processadores: energia ou potência?
	- em geral, a energia sempre é uma métrica melhor.
	- a energia mostra o custo "real" para realizar uma tarefa.
- Exemplo:
	- Se um processador A consome 1.2x a potência do processador B, mas finaliza a tarefa em tempo 30% menor, sua energia relativa é 1.2 X 0.7 = 0.84; Portanto, o processador A é melhor, considerando que 1.2x potência poderá ser suportada pelo sistema.

### Energia Dinâmica
- Para os chips CMOS, o consumo de energia dominante tem ocorrido no chaveamento dos transistores, também chamada de energia dinâmica
- $$Energia_d = Carga_c \times Voltagem²$$
	- considerando o pulso de transição lógica de 0->1->0 ou 1->0->1
- A energia de uma única transição (0 -> 1 ou 1 -> 0), é então:
	- $$Energia_d = \frac{1}{2}Carga_c \times Voltagem²$$
- A potência necessária por transistor é somente o produto da energia de uma transição multiplicada pela frequência das transições
	- $$Potencia_d = \frac{1}{2}Carga_c \times Voltagem² \times FrequenciaChaveamento$$

### A questão do consumo de energia
- A capacitância dos transistores e os níveis de tensão (voltagem) estão reduzindo, mas a densidade de transistores está aumentando em taxas muito elevadas; assim, a velocidade de clock não deve ser alterada (kept steady)
- A potência de fuga está subindo -- é função da quantidade de transistores, corrente de fuga e fonte de tensão (voltagem).
- O consumo de energia nos processadores de alto desempenho está na faixa de 100-150W.    
  $$Energy = power \times time = (dynpower + lkgpower) \times time$$
### Reduzindo Potência e Energia
- Distribuir a potência, retirar o calor e impedir pontos quentes tem se tornado desafios cada vez mais difíceis
- Ideia: melhorar a eficiência energética.
	- desligar o clock de circuitos inativos (reduz a potência de fuga - leakage)
	- Escalonamento dinâmico de voltagem-frequência
		- Dinamic Voltage-Frequency Scaling – DVFS
	- Projetar para o caso típico
- DFS: Dynamic frequency scaling -- only reduces frequency and dynamic power, but hurts energy
- DVFS: Dynamic voltage and frequency scaling – can reduce voltage and frequency by (say) 10%; can slow a program by (say) 8%, but reduce dynamic power by 27%, reduce total power by (say) 23%, reduce total energy by 17%

### Tendências recentes do microprocessador:
- Frequências base tendem a se estabilizar;
- Processamento paralelo tende a aumentar;
- Transistores aumentam (Lei de Moore);
- Se tornam mais eficientes energeticamente (energia dinâmica);
- Número de cores aumentam significativamente;
- Processamento sequencial tende a se estabilizar.

#### Outras tendências na tecnologia:
- A densidade DRAM aumenta em 40-60% ao ano, a latência reduziu 33% dentro de 10 anos, a largura de banda tem dobrado com a diminuição da latência;
- A densidade dos armazenadores secundários melhoram em 100% todo ano, a melhoria de latência é similar à DRAM;
- O surgimento da tecnologia NVRAM pode servir de ponte entre a tecnologia DRAM e HDDs;
- Confiabilidade (reliability): transistores menores, operando em baixa tensão e em grande quantidade.

### Confiabilidade e Disponibilidade
- Os sistemas alternam entre dois estados de serviço em relação a um SLA - Service Level Agreements
	1. Realização do Serviço (service accomplishment)
		- o serviço é realizado conforme especificado
	2. Interrupção do Serviço (service interruption)
		- O serviço entregue é diferente do acordado (SLA)
- As transições entre os dois estados são causados por falhas (do status 1 para o 2) ou as restaurações (do status 2 para o 1.)
- Quantificar essas transições leva as duas principais medidas de dependência:
	- Confiabilidade do módulo - Reliability measures continuous service accomplishment and is usually expressed as mean time to failure (MTTF)
	- Disponibilidade do módulo - Availability measures fraction of time that service matches specifications, expressed as MTTF / (MTTF + MTTR)

### Custo
- O custo é determinado por muitos fatores: volume da produção, curva de aprendizagem, commodities, etc.
- Um fator determinante e importante: área do chip
	- Menor área ⟶ mais chips por wafer
	- Menor área ⟶ um defeito leva-nos a descartar uma pequena área do wafer, i.e., produção cresce.
		- Roughly speaking, half the area ➔ one-third the cost
- O mercado de informática funciona como commodity. DRAMs, HDs, monitores, teclados, etc... Todos são padronizados e encontrados similares em qualquer canto e feito por qualquer fabricante. Nos últimos anos, muitos computadores pessoais viraram commodity focado em vender desktop e laptop com sistema microsoft windows.
- Como todos os vendedores vendem praticamente a mesma coisa, a competição é altíssima, o que diminui as margens de lucro. Fora o fato da demanda ser altíssima.
- O circuito integrado possui o seu custo relativo ascendente.

