### Restrições nos Tipos-Relacionamento
- Limitam as combinações possíveis de entidades que podem participar dos tipos-relacionamento
- Derivados do minimundo sendo analisado
- Restrições estruturais: cardinalidade e participação

- Restrição de participação
	- Determina se a existência de uma entidade depende ou não do fato dela participar de um relacionamento
	- Tipos de participação: total e parcial

### Graus de Tipos-Relacionamento
- Grau de um tipo-relacionamento
	- número de tipos-entidade participantes
- Unário (ou recursivo)
	- relaciona um tipo-entidade com ela mesma
	- indicado utilizar nomes de papéis
- Binário
	- relaciona um tipo-entidade a outro tipo-entidade
	- grau de relacionamento mais utilizado
- Ternário
	- relaciona três tipos-entidade

- Regra para a determinação das multiplicidades:
	- fixa-se dois elementos (dois tipo-entidade)
	- verifica-se quantos elementos do outro tipo-entidade podem surgir com relação a um elemento de cada tipo-entidade fixada
	- se a quantidade foi indeterminada ou variável
		- então considera-se n
		- senão considera-se 1
- Um relacionamento ternário em geral representa informações diferentes das dos três tipos-relacionamento binários

### Tipo-Entidade Fraca
- Entidades de um tipo-entidade fraca:
	- não podem ser distinguíveis porque a combinação dos valores de seus atributos pode ser idêntica
	- são identificadas através da relação que possuem com entidades pertencentes a tipos-entidade forte
- Representa dependência de existência
	- um tipo-entidade fraca sempre tem uma restrição de participação total com respeito ao relacionamento identificador
- ###### Dependência de Existência:
	- Se uma entidade _x_ depende da existência de uma entidade _y_, então:
		- _x_: entidade subordinada
		- _y_: entidade dominante
	- Se _y_ for removida então _x_ também deve ser removida
	- Exemplos:
		- empregado e dependente
		- conta e transações