
### Mapeamentos
- Geram três tipos de relação:
	- relação entidade com a mesma informação que o tipo-entidade original
	- relação entidade com a chave estrangeira de um outro tipo-entidade
	- relação relacionamento com as chaves primárias de todos os tipos-entidade relacionados, além dos atributos do tipo-relacionamento

### Passo 1: Tipo-Entidade forte
- Modelo entidade relacionamento
	- tipo-entidade E
	- atributos a1, a2, ..., an
- Modelo relacional
	- tabela de n colunas distintas, correspondendo aos n atributos de E

### Passo 2: Tipo-Entidade fraca
- Modelo entidade relacionamento
	- tipo-entidade forte E: chaves primárias b1, b2, ..., bm
	- tipo-entidade fraca A: atributos a1, a2, ..., an
- Modelo relacional
	- tabela de n+m colunas distintas, correspondendo às m chaves de E e aos n atributos de A

### Passo 3: Tipo-Relacionamento (1:1)
- Modelo entidade relacionamento
	- tipo-relacionamento binário: E1 relacionando-se com E2
	- cardinalidade: 1:1
- Modelo relacional (3 opções para a chave estrangeira)
	- repete-se a chave primária de E1 em E2 e vice versa
	- repete-se a chave primária de E1 em E2
	- repete a chave primária de E2 em E1
- Chave estrangeira: 
	- chave primária de uma relação que é inserida em outra relação
	- utilizada para recuperar informações de outras relações
- Outras alternativas de mapeamento
	- Opção da relação unificada (apropriada quando ambas participações são totais)
	- Opção de referência cruzada (ou relação relacionamento)

### Passo 4