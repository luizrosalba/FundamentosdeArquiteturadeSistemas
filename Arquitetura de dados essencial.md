# Conceitos introdutórios e o que é um banco de dados

SGDB - Sistemas gerenciadores de banco de dados 

- DDL Linguagem de definição -> Definição da estrutura dos dados  
- DML Linguagem de Manipulação -> Recuperação e alteração da informação 
- DQL Dicionario de Dados  - > banco de dados dentro do banco de dados que guarda a estrutura 

## Modelos de Banco de dados 
- Modelo Flat - tabelas com os dados diretamente 
- Modelo Hierárquico  - divisão da informação em árvore hierárquica  (já nao é mais utilizado) (ex: registro do windows) (redundância de informações) 
- Modelo Relacional - mais utilizado atualmente conjunto de tabelas flat que se relacionam obedecendo algumas regras 
- existem vários outros modelos : redes (grapho) , Orientado a objetos . objeto relacional (OO + relacional) , Big data 

## Bando de dados Relacionais (SGDBR ou em ingles RDBMS) 

- Tabelas : Entidades que agrupam as informações 
- Linhas : Registros ou tuplas 
- colunas : Classificação ou definição do que significa cada informação 
- chaves:  Primaria (unicidade do registro ) ou   foreing key (estrangeira) herança da chave primaria de uma outra tabela que cria o relacionamento entre duas tabelas 

## Modelagem 

- 1 Modelo Conceitual - MER 
- 2 Modelo lógico - Implementação 
DER (diagrama de entidade relacionamento) Um desenho que mostra como o modelo se comporta, mostrando como as entidades se relacionam. 
- Dados que não dependem de nenhum outro para existir são chamados de entidades forte ex: usuarios , produtos 
- Dados que dependem de nenhum outro para existir são chamados de entidades fracas  ex: tabela venda depende de produtos e usuarios 
- Exemplo de um relacionamento M x N  ( entidade associativa) 
- no modelo der existe uma notação que vem ao lado da entidade M(1..N) significa que precisa de no minimo 1 e pode ter varios 
- no modelo der existe uma notação que vem ao lado da entidade N(0..N) significa que pode nao ter nenhuma ou N vendas  
- no modelo der existe uma notação que vem ao lado da entidade 1(1..1) 1 venda precisa ter 1 e no maximo 1 cliente 
-  Relacionamentos 1X N , M x N 
![](https://github.com/luizrosalba/FundamentosdeArquiteturadeSistemas/blob/master/Capturar3.PNG?raw=true)

![](https://github.com/luizrosalba/FundamentosdeArquiteturadeSistemas/blob/master/333.PNG?raw=true)
- Transação atomica - 1 venda sem nenhum item 
- Normalização 1 a 5 
- 1,2,3 mais comuns 
- Modelo relacional pode ser criado sem normalizaçao mas pode gerar problemas de controle 
- 1ª forma normal -> Existencia de valores unicos na mesma coluna ex : 2 telefones na mesma coluna 
- Se houver dois telefones ou duas informações , essa informação precisa ser quebrada em uma nova coluna ou nova entidade (tabela com relação de chave estrangeira) 
- 2ª forma normal  resolve o problema da digitação errada ou duplicidade de linhas . Onde havia vendedor com escrita errada , cria-se apenas dois registros ex vendedor ou consultor 
- 3 ª forma normal - os valores devem ser dependendes da chave primaria e não podem ser dependentes de valores que nao são chave (total depende de valor e quantidade o que pode gerar problemas na hroa de armazenar informações pois o usuario pode alterar uma coluna e o totla nao será atualizado) 
-  Obs: Só podemos estar na segunda forma se aplicamos a primeira e assim por diante 

## SGDBR - SQL 

- DDL - Data definition languange 
- Create 
- DML Linguagem de Manipulação 
- Insert, Delete, Update
- DQL Dicionario de Dados
- Select ... from ... where ... groupby ... having ... orderby 

Exemplo : Select quantidade ,valor , descricao from Item_venda Join Produto On Codigo = Cod.Produto Where Valor > 5 
![](https://github.com/luizrosalba/FundamentosdeArquiteturadeSistemas)
