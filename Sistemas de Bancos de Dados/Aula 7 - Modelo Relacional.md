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
- Exemplos de domínios para
	-  Aluno (==nmat==, nome, telefone, celular, idade)
		- dom(nmat) = Números de matrícula
		- dom(nome) = Nomes de aluno
		- dom(telefone) = Números de telefone
		- dom(celular) = Números de telefone
		- dom(idade) = Idade
- Relação r da relação esquema R(A1, A2, ..., An)
	- representa a instância da relação
	- denotada por r(R)
	- formanda por um conjunto de n-tuplas r = {t1, t2, ..., tm}
		- cada n-tupla t é uma lista de n valores t = <v1, v2, ..., vn>
		- vi (1 <= i <= n) é um elemento dom(Ai) ou um valor nulo (i.e., null)
		- caracteriza a extensão do BD

- Exemplo de possível relação do esquema
	- Aluno (==nmat==, nome, telefone, celular, idade)
	- r(Aluno) = {<22222222, Júlia, 1134343434, 1126262626, 21>,<11111111, Pedro, 1965656565, 1977777777, 18>,<99999999, Cecília, 1144443333, 1165658888, 23>}

### Características das relações
- Ordenação de tuplas em uma relação (nível abstrato)
	- matematicamente, não há ordem entre os elementos de um conjunto
	- na implementação de um SGBDR existe uma ordem física de armazenamento das tuplas na memória externa
		- determina uma ordem na recuperação das informações
- Ordenação de tuplas em uma relação (nível lógico)
	- muitas ordens lógicas podem ser especificadas para uma relação
		- relação ALUNO pode ser ordenada pelos atributos NOME, DATANASCIMENTO, CPF, etc.
- Ordenação de valores dentro de uma tupla
	- uma tupla é uma lista de n valores dispostos em uma ordem determinada de acordo com a disposição dos atributos no esquema da relação
- Valores nas tuplas
	- são atômicos (monovalorados)
		- relações não permitem atributos multivalorados
	- o valor null deve ser utilizado quando um atributo não possui valor ou seu valor não é conhecido 

### Restrições sobre uma Relação
- Domínio
	- dentro de cada tupla, o valor de cada atributo A deve ser um valor atômico de dom(A)
- Unicidade de chave
	- chave primária
		- identifica de forma única cada tupla da relação
- Valor nulo
	- permitido: null (padrão)
	- não permitido: not null
- Integridade de entidade
	- nenhum valor de chave primária pode ser nulo

### Restrições sobre uma Relação - Chaves e Superchaves
- Uma superchave de uma relação R é um conjunto de atributos S contido em R
	- no qual não haverá duas tuplas t1 e t2 cujo t1[S] = t2[S]
- Uma chave K é uma superchave com a propriedade adicional de que a remoção de qualquer atributo da chave fará com que K não identifique mais unicamente cada tupla da relação
	- a diferença é que uma chave tem que ser mínima

Aluno (==nmat==, nome, telefone, celular, idade)
- Exemplo:
	- {nmat} é uma chave de aluno
	- Superchaves:
		- {nmat, nome}
		- {nmat, nome, telefone}
		- {nmat, nome, telefone, celular}
		- {nmat, nome, telefone, celular, idade}
- Chave candidata:
	- se um esquema de relação tiver mais de uma chave, cada uma delas é chamada chave candidata
	- uma delas é arbitrariamente designada para ser chave primária
- Um atributo de um esquema de relação R é chamado atributo primário se for membro de alguma chave candidata
- Um atributo é dito não primário se não for um atributo primário
- Exemplo:
	- {nmat} é a única chave candidata de aluno, portanto também é a chave primária

### Restrições sobre uma Relação - Chave Primária
- Resumindo:
	- chave primária para u