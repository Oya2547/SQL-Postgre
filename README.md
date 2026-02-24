# introdução

Neste resumo iremos entender mais sobre banco de dados e MySQL utilizando Postgre


## O que é SQL?
**SQL** significa Linguagem de Consulta Estruturada, usado para interagir com dados armazenados em bancos de dados. Assim, permitindo que os usuários façam cálculos complexos como encontrar "Gasto Total" em grande conjuntos de dados.

## Por que aprender SQL?

- O **SQL** permite comunicar diretamente com sistemas de dados.

- Existe uma alta demanda por habilidades em **SQL** no mercado de trabalho, em várias funções técnicas.
 
 - Essencial para Desenvolvedores de Software, Analistas de Dados, Cientistas de Dados e etc.
 - É uma linguagem padrão usada com ferramentas como o Power BI, Tableau, kafka e Synapse.
 


## Sistema de Gerenciamento de Banco de Dados (DBMS)
Um **DBMS** atua como interface entre o usuário e o banco de dados, realizando tarefas como:
- **Hospedagem do Servidor:** Os bancos de dados normalmente são hospedados em um servidor ou nuvem.
- **Disponibilidade sempre:** Esses sistemas geralmente funcionam o tempo todo para garantir que os dados estejam sempre acessíveis.
- **interação:** Aplicativos, ferramentas de BI e usuários enviam consultas SQL ao DBMS para gerenciar e recuperar dados. 

## Tipos de Bancos de Dados
**Relacional:** Microsoft SQL Server, MySQL, PostgreSQL,  Amazon Redshift.

**Documento:** MongoDB.

**Grafo:** Neo4j.

**Chave-Valor:** Redis, Amazon DynamoDB.

**Base de Coluna:** Apache Cassandra (GitHub).

##  Estrutura de Banco de Dados

Bancos de dados relacionais seguem uma organização hierárquica:
-  **Servidor:** O host principal contendo umou mais bancos de dados.
-  **Banco de Dados:** Contêiner de alto nível para dados, como "Vendas" ou "RH".
-  **Esquema:** Agrupamentos lógicos dentro de um banco de dados, como "Pedidos " ou "Clientes".
-  **Tabela:** Onde os dados são fisicamente armazenados em linhas e colunas.

## Componentes de uma Tabela 

- **Colunas:** Categorias verticais definindo tipos de dados.
-  **Linhas:** Registros horizontais individuais.

-  **Célula:** Uma unidade única de dado na interseção de linha e coluna.
- **Chave Primária:** Identificador único para cada registro em uma tabela.
- **Armazenamento:** Tabelas são armazenadas como arquivos de bancos de dados em disco físico.

#  Tipos de Dados
SQL usa tipos de dados específicos para definir que tipode informação pode ser armazenada:

**Numéricos**
- **INT** - Números inteiros.
- **DECIMAL** - Valores numéricos com frações.
- 
**Texto/String**
- **CHAR** - Strings de comprimento fixo.
- **VARCHAR** - Strings de comprimento variável.

**Data e Hora**
- **DATE** - Formato "YYYY-MM-DD".
- **TIME** - Formato "HH:MM:SS".

#  Tipos de Comandos SQL

## DDL (Linguagem de Definição de Dados)
Usado para definir ou modificar a estrutura do banco de dados.

- CREATE -   Criar  novos  bancos  de dados  ou  tabelas.
- **ALTER** - Modificar  a  estrutura  existente.
- **DROP** - Deletar  um banco  ou  tabela.


## DQL (Linguagem  de Consulta de Dados)

Usada para recuperar dados do banco de dados.
- SELECT - O comando principal para buscar dados
## DML (Linguagem  de  Manipulação  de Dados)
Usada para gerenciar dados dentro das tabelas.
- **INSERT** - Adicionar novos registros.
- **UPDATE** - Modificar registros existentes.
- **DELETE** - Remover registros.

## DCL (Linguagem  de Controle de Dados)

Usada para gerenciar permissões e controle de acesso.
- **GRANT** –  Concede  privilégios  de  acesso.
- **REVOKE** –  Revoga  privilégios.

## TCL (Linguagem  de Controle de  Transações)
Usada para gerenciar transações no banco de dados.
- **COMMIT** –  Salva  mudanças  permanentemente.
- **ROLLBACK** –  Desfaz  mudanças  se  ocorrer  um  erro.
- **SAVEPOINT** –  Define um  ponto  para rollback  parcial.


# DDL - Linguagem de Definição de Dados

## DDL (Linguagem  de  Definição  de Dados)
DDL  significa  Data Definition Language (Linguagem  de  Definição  de Dados).

Enquanto  o **DQL** é  usado  para  consultar  dados e o **DML** é  usado  para manipular dados, o **DDL**  
é  usado  para  definir  a  estrutura  dos  nossos  objetos  de dados (o "esqueleto" do banco de  
dados).


## Operações Principais de DDL
O  **DDL**  permite  que  você  gerencie  a  planta  estrutural  (blueprint)  do  seu  banco de dados  
através  de  três  ações  principais:
- **CREATE** - Usado  para  construir  novos  objetos  (Bancos de Dados  ou  Tabelas) do zero.
- **ALTER** - Usado  para  modificar  a  estrutura  de um  objeto  existente  (ex:  adicionar  uma  nova  coluna  a  
uma  tabela).
- **DROP** - Usado  para  excluir  permanentemente  um  objeto  e  todos  os  seus  dados.



## Criando  Objetos  (CREATE)

- **CREATE DATABASE Sales;** - Para começar um novo projeto, primeiro  criamos  um  contêiner  para  
nossas  tabelas.
- **CREATE TABLE**  -  Ao  criar  uma  tabela,  devemos  definir  as  Colunas  e  seus  Tipos  de Dados  
associados.

**CREATE TABLE** Products (
ProductID INT,
ProductName VARCHAR(100),
Price DECIMAL
);


# Modificando Objetos (ALTER)

Se os requisitos mudarem, usamos o comando **ALTER** para atualizar a estrutura sem excluir a tabela.

**Adicionar uma Coluna**
- ALTER TABLE Products
- ADD Category VARCHAR(50);
**Remover uma coluna**
- ALTER TABLE Products
- DROP COLUMN Price;

## Excluindo  Objetos  (DROP)

O  comando  DROP  é  destrutivo. Ele remove  toda  a  estrutura  e  todos  os  registros  armazenados  
nela.  
• **DROP TABLE** Products;
