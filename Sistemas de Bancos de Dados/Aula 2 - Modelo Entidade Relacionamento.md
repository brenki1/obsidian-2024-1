### Características
- foi desenvolvido para facilitar o projeto lógico do BD
- permite a representação da estrutura lógica global do BD
- é um dos modelos de dados com maior capacidade semântica
- representa um problema como um conjunto de entidades e relacionamentos entre estas entidades

### O ME-R oferece 4 Construtores para a representação da semântica:
- [[#Tipo-Entidade]]
- Atributos de Entidades
- Tipo-Relacionamento
- Atributos de Relacionamentos

### Entidade
- Qualquer coisa do mundo real envolvida no problema
- Possui existência independente
- Pode ser um objeto com:
	- existência física: uma pessoa, um carro;
	- existência conceitual: uma companhia, um emprego, um curso.
- Descrita por propriedades particulares: [[#Atributos]]

### Atributos 
- Caracterizam uma entidade ou um relacionamento
	- exemplo: tipo-entidade **cliente**
			 atributos: **nome_cliente
					 endereço_cliente
					 data_nascimento**
- Domínio de um atributo
	- conjunto de valores possíveis para o atributo
	- pode assumir valor nulo (i.e., null)
	- exemplos: nome_cliente: varchar(50)
						 data_nascimento: date

### Classificação dos Atributos
- Simples _versus_ Compostos
	- atributo simples ou atômico
		- não pode ser decomposto (dividido) em atributos mais clássicos
		- exemplo: **sexo**
	- atributo composto
		- pode ser decomposto (dividido) em vários outros atributos mais básicos
		- possui como valor a concatenação dos valores dos atributos simples que o formam
		- exemplo: atributo **endereço**, composto de _nome_rua, nro_casa, complemento, nome_bairro,_ ...
- Atributos compostos podem formar hierarquias
- Observação: 
	- se nenhuma consulta será realizada sobre os atributos mais básicos de um atributo composto, então o atributo composto pode ser armazenado no BD como um atributo simples

- Monovalorados _versus_ Multivalorados
	- atributo monovalorado
		- possui um único valor para cada entidade
		- exemplo: idade
	- atributo multivalorado
		- possui múltiplos valores para cada entidade
		- exemplo: atributo telefone
		- pode possuir limites inferiror/superior com relação à multiplicidade dos valores assumidos
		- exemplo: nro_min = 0, nro_max = 3

- Armazenados _versus_ Derivados
	- atributo armazenado
		- está realmente armazenado no BD
	- atributo derivado
		- pode ser determinado através de outros atributos ou através de entidades relacionadas
		- exemplo: idade = data_atual - dada_nascimento
		- pode ou não ser armazenado no BD

### Tipo-Entidade
- Conjunto de entidades do mesmo tipo
- Descrito por um nome e uma lista de atributos
- Entidades de um tipo-entidade
	- compartilham os mesmos atributos
	- possuem seus próprios valores para cada atributo
##### Restrição de chave
- Chave primária
	- conjunto mínimo de atributos que identificam de maneira única uma entidade
	- escolhida pelo projetista do BD como o principal meio de identificação de um tipo-entidade

### Relacionamento e Tipo-relacionamento
- Relacionamento: associação entre entidades
- Tipo-relacionamento: conjunto de relacionamentos do mesmo tipo
- Exemplo: pessoa **trabalha para** empresa

##### Papéis nos Relacionamentos
- Cada Tipo-Entidade que participa de um Tipo-Relacionamento tem um **PAPEL** no relacionamento
- A indicação de cada papel:
	- é opcional
	- deve ser feita sempre que possa existir ambiguidade na interpretação

##### Restrição de Cardinalidade
- Determina o número de entidades às quais outras entidades podem ser associadas através de um relacionamento
- Cardinalidades:
	- um-para-um ( 1 : 1 )
	- um-para-muitos ( 1 : n )
	- muitos-para-um ( n : 1 )
	- muitos-para-muitos ( m : n )