- Características:
	- introduz semântica adicional ao modelo ER
	- utilizado na modelagem de aplicações mais complexas, tais como CAD/CAM, BD gráficos, BD geográficos
- Conceitos
	- subclasse, superclasse, hierarquia de herança
	- generalização, especialização e restrições
	- agregação

### Subclasse/Superclasse
- Subclasse
	- agrupamento das entidades de um subgrupo do tipo-entidade
	- Exemplo:
		- superclasse: tipo-entidade empregado
		- subclasses: secretário, engenheiro, técnico

### Herança
- de atributos: atributos da superclasse são herdados pela subclasse
- de relacionamentos: instâncias de relacionamento da superclasse são herdados pelas entidades das subclasses
- **Observação**: 
	- qualquer entidade membro de uma subclasse deve ser também membro da superclasse
	- qualquer entidade membro da superclasse pode ser opcionalmente incluída como membro de qualquer número de subclasses

### Generalização/Especialização
- Especialização: 
	- resultado da separação de um tipo-entidade de nível mais alto (superclasse), formando vários tipos-entidade de nível mais baixo (subclasse)
	- passos: 
		- define-se um conjunto de subclasses de um tipo-entidade
		- associa-se atributos adicionais específicos às subclasses
		- estabelece-se tipos-relacionamento adicionais específicos às subclasses, caso necessário
- Generalização:
	- resultado da união de dois ou mais tipos-entidade de nível mais baixo (subclasse), produzindo um tipo-entidade de nível mais alto (superclasse)
	- é uma abstração de um conjunto de entidades
	- passos:
		- suprime-se as diferenças entre os tipos-entidade
		- identifica-se os atributos em comum
		- generaliza-os em uma superclasse

### Chaves dos Tipo-Entidade
- Restrição de chave do ME-R: todos os tipos-entidade devem ter uma chave única
	- Restrição relaxada para o MER-X
		- subclasses não precisam ter chave explicitamente definida

### Restrições
- Especialização definida pelo atributo
	- as subclasses que participam da hierarquia são determinadas por uma condição baseada em algum atributo da superclasse
	- exemplo: atributo _tipo_empregado
	- denominação:
		- subclasses definidas por predicado (ou definidas por condição)
- Especialização definida pelo usuário
	- o membro da subclasse é determinado pelos usuários na operação que adicionar uma entidade à subclasse
		- um membro é especificado individualmente para cada entidade pelo usuário
**Restrição de Disjunção**
- Subclasses mutuamente exclusivas
	- uma entidade de uma superclasse deve ser membro, quando muito, de apenas uma subclasse
- Subclasses que se sobrepõem
	- uma entidade de uma superclasse pode ser membro de mais do que uma subclasse
**Restrição de Completude**
- Total
	- cada entidade de uma superclasse deve ser membro de alguma subclasse na especialização
- Parcial
	- uma entidade de uma superclasse pode não pertencer a qualquer uma das subclasses

Observações
- Restrições de disjunção e de completude são independentes
- possibilidades de hierarquias
	- total disjunta
	- parcial disjunta
	- total com sobreposição
	- parcial com sobreposição

### Generalização/Especialização
- Uma subclasse pode possuir outras subclasses especificadas a partir dela
- Herança simples
	- cada subclasse participa como subclasse em apenas um relacionamento superclasse/subclasse
- Herança múltipla
	- cada subclasse pode participar como uma subclasse em mais do que um relacionamento superclasse/subclasse

### Herança Múltipla
- Regra
	- se um mesmo atributo ou relacionamento for herdado mais do que uma vez por diferentes relacionamentos superclasse/subclasse então o atributo ou o relacionamento deve ser incluído apenas uma vez na subclasse

### Agregação 
- É um conceito para a construção de objetos compostos a partir de seus objetos componentes
	- Ideia: elementos de modelagem podem associar-se, formando outros elementos que representam essa associação
- Pode assumir diversas formas:
	- Agregando atributos em Tipos-Entidade e Tipos-Relacionamento
		- os valores dos atributos compõem a entidade
	- Agregando Tipos-Entidade e Tipos-Relacionamentos
		- combinar entidades que estão relacionadas por uma instância de relacionamento em uma entidade agregada de alto nível
- Tipos-entidades agregados são representados como tipos-entidades comuns
- Engloba
	- dois tipos-entidades e um tipo-relacionamento
- Situações que indicam a necessidade de agregação:
	1. Quando é necessário identificar cada relacionamento (o relacionamento tem chave)
	2. Quando é necessário mais de um relacionamento envolvendo as mesmas entidades
	3. Quando existe a necessidade de associar dois relacionamentos

### Projeto Lógico de BD
- Classificar tipos-entidades e atributos
	- tipos-entidade possuem informações descritivas, atributos não.
	- atributos devem ser mantidos de forma atômica
	- atributos devem ser relacionados às entidades que eles descrevem
- Identificar chaves primárias
- Identificar tipos-relacionamento e seus atributos
	- determinar o grau dos tipos-relacionamentos
		- definir tipos-relacionamento ternários cuidadosamente
	- identificar as restrições que se aplicam sobre cada tipo-relacionamento
		- cardinalidade
		- participação
	- Caso necessário, definir os papéis]
- Identificar tipo-entidade forte e tipo-entidade fraca
- Verificar os requisitos de operações 
	- se eles se referirem a dados que não estão modelados, repetir os passos anteriores
- Modelar hierarquias de generalização
	- identificar atributos e relacionamentos comuns
	- determinar as restrições de disjunção e completude
- Modelar agregações 