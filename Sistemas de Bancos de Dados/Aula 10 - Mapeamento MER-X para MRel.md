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
- Observação importante
	- esta alternativa não é indicada quando:
		- houver necessidade frequente de acessar informações envolvendo todas as entidades genéricas
		- houver a possibilidade de existirem especializações não previstas a priori

### Generalização/Especialização Opção de mapeamento (8C)
- Modelo entidade relacionamento
	- E1: superclasse
	- E2, ..., En: subclasses de E1
- Modelo relacional
	- a tabela de E1 possuirá:
		- os atributos de E1
		- os atributos de E2, ..., En
		- o atributo discriminador, caso necessário

### Generalização/Especialização Opção de mapeamento (8D)
- Modelo entidade relacionamento
	- E1: superclasse
	- E2, ..., En: subclasses de E1
- Modelo relacional
	- a tabela de E1 possuirá:
		- os atributos de E1
		- os atributos de E2, ..., En
		- vários atributos discriminadores de valores booleanos, cada um referente à uma subclasse

### 8C e 8D
- Interessantes quando
	- existem poucos atributos específicos nas subclasses
	- houver a possibilidade de existirem especializações (sem atributos específicos) não previstos a priori


### MER-X -> MRel - Os 9 passos do procedimento
1. Mapear todos os tipos-entidade forte que não são subclasses
2. Mapear todos os tipos-entidade fraca que não são subclasses
3. Mapear todos os tipos-relacionamento 1:1
4. Mapear todos os tipos-relacionamento 1:n
5. Mapear todos os tipos-relacionamento n:m
6. Mapear todos os atributos multivalorados
7. Mapear todos os tipos-relacionamento de grau > 2
8. Mapear todas as ocorrências de abstração de generalização/especialização
9. Mapear todas as ocorrências de agregação

### Agregação
- Para mapear ocorrências de agregação
	- considerar cada um dos casos de como o tipo-entidade resultante da agregação é identificado
	- levar em consideração as chaves dos tipos-entidade componentes, o tipo-relacionamento gerador, os atributos do tipo relacionamento gerador, o tipo-entidade agregação, e os atributos do tipo-entidade agregação

##### Opção 1:
- deve ser usada:
	- quando o tipo-entidade agregação é identificado por atributo próprio + chave dos tipos-entidade que participam do tipo-relacionamento gerador
	- uma mesma instância do tipo-relacionamento gerador resulta em mais de uma entidade agregada
##### Opção 2:
- deve ser usada:
	- quando o tipo-entidade agregação é identificado por um de seus ar