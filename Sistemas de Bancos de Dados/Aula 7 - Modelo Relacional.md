- Introduzido por Ted Codd da IBM em 1970
	- Simplicidade e base matemática
	- Base teórica na teoria de conjuntos e na lógica de predicados de primeira ordem
- BD
	- representado como uma coleção de relações
- Relação
	- possui um nome único
	- é uma tabela bi-dimensional

### Tabela Bi-Dimensional
- Características
	- cada coluna tem um nome distinto e representa um atributo
	- cada atributo possui um domínio de valores
	- cada domínio possui valores atômicos
		- por atômico entendemos que o valor é indivisível no domínio
	- todos os valores de uma coluna são valores do mesmo atributo
	- cada linha da tabela representa o relacionamento entre um conjunto de valores
	- cada linha é distinta e representa uma tupla
	- uma n-tupla representa uma tupla que possui n valores
		- grau da relação: número n de atributos de sua relação esquema

### Definições Formais
- Relação esquema R:
	- utilizada para descrever uma relação
	- denotada por R(A1, A2,..., An)
	- formada por
		- um nome de relação R
		- uma lista de atributos A1, A2, ..., An
	- para cada atributo Ai (1 <= i <= n)
		- dom(Ai) : domínio de Ai
		- domínio: conjunto de valores atômicos
	- caracteriza a intenção do BD
- Exemplos de domínios para
	- Aluno (==nmat==, nome, telefone, celular, idade)
		- Números de telefone
		- Nomes de aluno
		- Idade
- Um método comum para especificar o domínio compreende
	- definição lógica
	- definição do tipo de dado ou formato
- Aluno (==nmat==, nome, telefone, celular, idade)
	- Definição lógica
		1. Números de matrícula: conjunto de dígitos válidos para matrícula de alunos
		2. Números de telefone: conjunto de números de telefone válido no Brasil
		3. Nomes de aluno: conjunto de todos os nomes possíveis para pessoas
		4. Idade: conjunto de idades possíveis para alunos
	- Definição do tipo de dado ou formato
		1. Números de matrícula: inteiro com 8 dígitos
		2. Números de telefone: inteiro com 10 dígitos
		3. Nomes de aluno: string de 60 caracteres
		4. Idade: inteiro entre 15 e 100