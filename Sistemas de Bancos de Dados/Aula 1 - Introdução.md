### Motivação 

- Necessidade de armazenar grandes quantidades de dados e acessar as informações de maneira eficiente e segura;
- Evolução histórica: desenvolvimento de software + hardware.

### Sistema de Banco de Dados (SBD)

- Sistema de armazenamento de dados
- Objetivos:
	- manter informações
	- torná-las disponível quando necessário
- Armazenamento não volátil
- Componentes:
	- banco de dados
	- sistema gerenciados de banco de dados
	- usuários
	- hardware

### Banco de Dados (BD)

- Depósito de dados armazenados
- Os dados devem ser logicamente coerentes
- Uma coleção randômica não é um BD

### Sistema Gerenciador de Banco de Dados (SGBD)

- Coleção de programas para:
	- criar e manter o banco de dados
- Camada existente entre os dados e os usuários
- Isola os usuários dos detalhes de hardware
- Atende às solicitações dos usuários
- Recursos:
	- adição de novos arquivos
	- inserção, recuperação, atualização e eliminação de dados
	- criação de visões
	- atribuição de privilégios


### Usuários

- ##### Administrador do BD
	- coordena e monitoria o uso do BD
	- autoriza o acesso ao BD
	- adquire software e hardware necessários
	- tem conhecimento total do BD
- ##### Projetista do BD
	- identifica os dados a serem armazenados no BD
	- escolhe as estruturas apropriadas para representar e armazenar esses dados
- ##### Programador de aplicações
	- escreve os programas aplicativos
	- realiza requisições ao SGBD
- ##### Usuário final
	- manipula o BD por meio de
		- linguagens de consulta
		- programas previamente desenvolvidos
	- tipos de usuários:
		- leigos vs sofisticados
		- casuais vs frequentes

### Hardware

- Volumes de armazenamento secundário
- Dispositivos de E/S
- Canais de E/S
- Controladores de dispositivos
- Processador + memórias associadas
	- ULA
	- registradores
	- unidade de controle

### Vantagens da Utilização de SGBD

- ##### [[#Independência de Dados]] 
	- Sistemas de processamento de arquivos gravam seus dados em disco, segundo **Estruturas de dados** próprias
	- Para acessá-los é necessário conhecer estas estruturas - **DEPENDÊNCIA DE DADOS**
	- O SGBD se responsabiliza pela conversão dos dados
	- Cada aplicação:
		- Vê apenas os dados que lhe interessam
		- Não precisa saber detalhes de como seus dados estão fisicamente armazenados
		- Não precisa ser modificada, caso a estrutura de dados que ela utiliza for alterada
- ##### Redundância controlada
	- mesmos dados armazenados várias vezes
- ##### Consistência dos dados armazenados
	- inconsistência
		- quando dados duplicados armazenam valores distintos
		- existe quando a redundância ==não é controlada==
- ##### Segurança
	- com relação ao acesso ao sistema - login dos usuários
	- com relação ao acesso aos dados do sistema
		- visões parciais, de acordo com os usuários
		- acesso controlado, através de graus de privilégios
- ##### Facilidade para a especificação de ==restrições de integridade==
	- ###### restrições de integridade:
		- garantem a precisão dos dados
		- especificam as restrições impostas pelo sistema real
- ##### Garantia de atomicidade
	- Certas operações precisam da garantia de serem realizadas de maneira atômica - elas precisam ocorrer em sua totalidade, ou não devem ocorrer de forma alguma
		- Exemplo: Transferência de fundos entre duas contas bancárias A e B. *slide*
- ##### Compartilhamento de dados
	- base de dados:
		- definida apenas uma vez 
		- compartilhada por vários usuários
- ##### Padronização
	- formato dos dados e domínio dos valores dos dados
		- definidos apenas uma vez
		- compartilhados por vários usuários
- ##### Acesso concorrente
	- coordena os diversos programas de aplicação que acessam um mesmo banco de dados
	- Exemplo: acesso a conta-corrente conjunta com o saldo de R$500,00 *slide*
- ##### Existência de diferentes interfaces
	- GUI ou CLI
- ##### Representação de relacionamento entre os dados
- ##### Recuperação de falhas de software e hardware
- ##### Facilidade no desenvolvimento de novas aplicações

### Arquitetura de Três Níveis

##### Objetivo
- separar as aplicações dos usuários do BD físico
- prover uma visão abstrata dos dados

##### Três níveis de abstração
- organização física dos dados
	- [[#Esquema interno]]
- organização lógica global dos dados
	- [[#Esquema conceitual]]
- organização lógica particular dos dados
	- [[#Esquema externo]] (visão)

##### Esquema interno 
- dados armazenados na memória secundária
- contém definições de estruturas de dados e mecanismos de acesso

##### Esquema conceitual
- definição do conteúdo da informação
- utiliza o conceito de modelo de dados
- independe de estrutura de dados e mecanismos de acesso

##### Esquema externo
- usuário apenas vê parte dos dados
- visões: também chamadas de subesquemas

##### Observações
- Pode não haver distinção entre os esquemas
- ###### BD:
	- único local onde realmente existem dados
	- demais esquemas: apenas descrições
- ###### Interfaces:
	- permitem a comunicação entre dois níveis subjacentes
	- consistem em mapeamentos ou transformações
	- nível físico <--> nível conceitual
	- nível conceitual <--> nível externo


### Instâncias e Esquemas

##### Instância
- coleção de informações armazenadas no BD em um determinado momento
- também chamado de extensão do BD
- sofre alterações constantemente

##### Esquema
- projeto do BD, incluindo as entidades e os relacionamentos entre estas
- também chamado de intenção do BD
- não sofre alterações com frequência


### Estado do Banco de Dados

##### Os dados armazenados em um BD em um determinado momento

##### Estado vazio
- após a criação do BD
##### Estado inicial
- após o povoamento ou carregamento do BD com os dados iniciais
##### Novo estado
- após cada operação realizada nos dados do BD
##### Estado atual
- estado do BD em um determinado momento

### Independência de Dados

- Habilidade de modificar a definição de um esquema em um nível sem afetar a definição do esquema em um nível mais alto

##### Dois tipos
- independência física de dados
- independência lógica de dados
##### Independência física de dados
- modifica o esquema físico
- não modifica os esquemas conceitual e externo
- necessidade: aprimoramento do desempenho

##### Independência lógica de dados
- modifica o esquema conceitual
- não modifica os programas aplicativos
- necessidade: alteração da estrutura do BD

###### Observação:
- independência lógica é mais difícil de ser obtida

### Linguagens Associadas

###### Linguagem de definição de dados (DDL)
###### Linguagem de manipulação de dados (DML)
- Oferecidas pelo SGBD
- Utilizadas pelos usuários para
	- criar: linguagem de definição
	- manipular: linguagem de manipulação
     *o banco de dados*


