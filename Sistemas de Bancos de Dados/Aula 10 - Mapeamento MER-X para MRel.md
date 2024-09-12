### Os 7 passos do procedimento
1. Mapear todos os tipos-entidade forte
2. Mapear todos os tipos-entidade fraca
3. Mapear todos os tipos-relacionamento 1:1
4. Mapear todos os tipos-relacionamento 1:n
5. Mapear todos os tipos-relacionamento n:m
6. Mapear todos os atributos multivalorados
7. Mapear todos os tipos-relacionamento de grau > 2

### MER-X -> MRel - Os 8 passos do procedimento
1. Mapear todos os tipos-entidade forte que não são subclasses
2. Mapear todos os tipos-entidade fraca que não são subclasses
3. Mapear todos os tipos-relacionamento 1:1
4. Mapear todos os tipos-relacionamento 1:n
5. Mapear todos os tipos-relacionamento n:m
6. Mapear todos os atributos multivalorados
7. Mapear todos os tipos-relacionamento de grau > 2
8. Mapear todas as ocorrências de abstração de generalização/especialização

### Generalização/Especialização Opção de mapeamento (8A)
- Modelo entidade relacionamento
	- E1: superclasse
	- E2, ..., En: subclasses de E1
- Modelo relacional
	- a tabela de E1 possuirá:
		- os atributos de E1
		- um atributo discriminador, caso necessário
    - as tabelas de E2 a En possuirão:
	    - os seus atributos específicos
	    - a chave primária de E1
- Chave primária das subclasses: chave primária de E1
- Essa opção funciona para qualquer especialização
	- Total ou Parcial
	- Disjuntas ou Sobrepostas
- Interessante quando
	- existem poucas subclasses, cada uma com diversos atributos específicos
	- uma consulta tipicamente se concentra em uma ou poucas subclasses de cada vez

### Generalização/Especialização Opção de mapeamento (8B)
- Modelo entidade relacionamento
	- E1: superclasse
	- E2, ..., En: subclasses de E1
- Modelo relacional
	- as tabelas de E2 a En possuirão:
		- os seus atributos específicos
		- os atributos de E1
		- a chave primária de E1
- Chave primária das subclasses
	- chave primária de E1
- Essa opção funciona
	- apenas para participação total
	- é mais adequada para disjunção, mas suporta sobreposição
- Interessante quando
	- é frequente o acesso a cada entidade em sua totalidade, incluindo-se seus dados genéricos e específicos
		- esta alternativa, comparada com as alternativas que mantêm uma relação para a superclasse, permite evitar uma operação de junção na consulta