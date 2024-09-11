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
	- resri