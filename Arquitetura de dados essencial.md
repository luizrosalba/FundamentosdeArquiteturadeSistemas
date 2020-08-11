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
![](https://github.com/luizrosalba/FundamentosdeArquiteturadeSistemas/blob/master/4444.PNG?raw=true)

- Funções de conjunto - Sun , min , max, avg dentre outras que podem ser utiizadas para aplicar uma operação a collunas de um BD 
- Exemplo de query de funções de conjunto : 

![](https://github.com/luizrosalba/FundamentosdeArquiteturadeSistemas/blob/master/55555.PNG?raw=true)

- Indexadores Um index é uma pequena tabela extraida da tabela original apenas com as colunas que desejamos ordenar . Ela é física (armazenada no servidor )e memória (estará ocupando memória) . Podemos criar quantos indices forem necessarios para uma tabela . Indices afetam os recursos no dml . Ao incluir uma nova linha o sistema precisará fazer a mesma coisa no index 


## Transactions 
- Consumo e tratamento de informações em um nivel de isolamento. O sistema gerenciador de banco de dados deve permitir a concorrencia de recursos para muitos usuarios (transactions , ou aquilo que se pode fazer dentro de uma sessão).  Cada operação realiza dentre de um BD é tratada como uma transação independente, tem começo , meio e fim . 
- O padrão de isolamento é o reading commited. Pode-se ler aquilo que já foi aplciado no banco 
- Em uma transação diversos usuarios podem sobrepor informações 
- Ex : 
- Inicio (Insert, Delete, Update) 
- resolução (commit ou rollback ) 
- Fim ( novos dados ou dados originais) 

- Conceito ACID 
- Atomicidade Todas as operações são executadas com sucesso, commit ou rollback , mesmo com a conexão interrompida 
- Consistencia Unicidade de chaves, restrições de integridade lógica , etc (não posso infringir regras do modelo) 
- Isolamento   Varias transações podem acessar simultaneamento o mesmo registro ou parte do registro. REspeita-se a ordem de chegada 
- Durabilidadae  Depois do commit , mesmo com erros, queda de energia, etc as alterações devem ser aplicadas 

## SGDBR na prática 

-SGDBs-R (relacionais) : 
-  Todos tem versões com features reduzidas para aprendizagem ou pequenos negócios 
-  ORACLE , Microsoft Sql Server , IBM DB2 , 
-  PostGreSql (gratuito) , Mysql , Sqlite (embarcados , não é bom para sistemas distribuidos, mas pode rodar até mesmo no celular ) 

- Instalamos o postgree sql 
- no chrome http://127.0.0.1:16751/browser/ 
- Server 
- Nome 
_ connections localhost port 5432 
- postgree - local onde serão salvos os metadados ( dicionario de dados) nada deve ser alterado ali 
- criamos uma nova database chamada aula 
- schema : mapeia o quesito logico da operação 
- fomos em aula , botao direito , query tool 
-  executamos no query editor :
```Javascript
create table client
(codigo numeric(10) not null primary key ,
nome varchar (100) not null , 
telefone varchar(15))
```
- clicando no play a tabela será criada e dando um refresh na database aula você vera a table client 
- Comando ddl (criacao etc;) nao necessitam de commit cuidado , pois nao tem volta. dar um drop na tabela nao tem volta 
- Inserimos 
```Javascript
insert into client (codigo,nome,telefone)
values(1,'Lorem Ipsum', '(88)- 8888 9999')
```
- e para que seja acplicada aplicamos commit 
- ao realizar um select * from client vemos o usuario adicionado 




