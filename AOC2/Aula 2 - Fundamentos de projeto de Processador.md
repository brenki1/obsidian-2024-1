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

