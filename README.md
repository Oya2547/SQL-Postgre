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

# DML - Linguagem de Manipulação de Dados

Nós usamos DML (Data Manipulation Language) para alterar os dados reais armazenados dentro de nossas tabelas. Enquanto a DDL define o "recipiente", a DML nos permite gerenciar o conteúdo interno.

## Operações Principais de DML
Nós contamos com três comandos primários para manipular nossos dados:
- **INSERT**: Nós usamos para adicionar novas linhas de dados em uma tabela.
- **UPDATE**: Nós usamos para modificar informações existentes dentro de uma tabela.
- **DELETE**: Nós usamos para remover registros específicos de uma tabela.

## Adicionando Dados (INSERT)
Quando queremos popular nossas tabelas, temos dois métodos principais para inserir dados:

**Método 1: Entrada Manual (VALUES)**
Nós especificamos manualmente os valores que queremos adicionar a colunas específicas.


INSERT INTO Products (ProductID, ProductName, Price)
VALUES (1, 'Laptop', 1200.00);

---

### Código Markdown - Aula 3.2


# Anatomia de uma Declaração SQL

Uma instrução SQL é composta de elementos específicos que dizem ao banco como processar o pedido:

- **Comentários (--)** – Documentam o código.
- **Palavras-chave** – Reservadas e com significado especial.
- **Cláusulas** – Blocos que constroem a instrução.
- **Funções** – Ferramentas internas que transformam dados.
- **Identificadores** – Nomes de objetos de banco como tabelas ou colunas.
- **Operadores** – Usados para comparações.
- **Literais** – Valores constantes ou strings.

## Estrutura Básica de Consulta
SELECT
  column_name
FROM
  table_name;

  # Chave Estrangeira

O que é Chave Estrangeira (Foreign Key)?
A chave estrangeira é um campo de uma tabela que aponta para a chave primária de outra tabela. Ela serve para criar relacionamento entre tabelas.
Em outras palavras:
A chave estrangeira é o que “liga” uma tabela à outra em um banco de dados relacional.

## Por que precisamos dela?
**Sem chave estrangeira:**
- As tabelas ficam isoladas
- Não há garantia de que os dados combinam
- Podem existir registros “órfãos” (sem relação real)

**Com chave estrangeira:**
- O banco garante integridade dos dados
- Evita erros e inconsistências
- Representa relações do mundo real (cliente → pedido, aluno → matrícula, etc.)

## Exemplo prático - Tabela de Clientes
| Id (PK) | Nome |
| :--- | :--- |
| 1 | Ana Silva |
| 2 | João Souza |

## Exemplo prático - Tabela de Pedidos
| Id (PK) | clienteId (FK) | Total |
| :--- | :--- | :--- |
| 1001 | 1 | 3500 |
| 1002 | 2 | 200 |
| 1003 | 1 | 1200 |

# Normalização

Normalizar um banco de dados é organizar as informações para que cada dado exista apenas uma vez, evitando repetição, erros e bagunça nas tabelas.

## Forma Não Normalizada (UNF)
Todos os dados estão misturados em uma única tabela, com grupos repetidos.
- Dados do cliente repetidos.
- Difícil de consultar e manter.

## Primeira Forma Normal (1FN)
Os campos devem ser atômicos (um único valor por célula).

**Problema:**
- Dados do cliente continuam duplicados.
- Total pertece APENAS ao pedido.
- Ainda existem dependências (responsabilidades) na mesma tabela.

## Segunda Forma Normal (2FN)
**Regras:**
- Deve estar na 1FN.
- Removemos dependências parciais.
- Cada entidade passa a ter sua própria tabela e ter sua própria chave primária.

**Problema:**
- Produto é um texto livre... está "solto".

## Terceira Forma Normal (3FN)
**Regras:**
- Deve estar na 2FN.
- Remover dependências transitivas.
- Campos não-chave DEVEM depender apenas da chave.

## Resultado
O banco de dados agora possui:
- Ausência de redundância.
- Relacionamentos claros (Chaves Estrangeiras).
- Estrutura relacional correta.
- Melhor desempenho.
- Manutenção facilitada.

**Isso torna os bancos de dados:**
- Mais eficientes.
- Mais confiáveis.
- Mais fáceis de escalar.
- Mais fáceis de entender.

# Métodos de Combinação

## JOINS (Adição de Colunas - Horizontal)
Conectamos tabelas lateralmente através de uma coluna comum (Chave).

- **Inner Join**: Apenas o que existe em ambas as tabelas.
- **Left Join**: Mantemos tudo da tabela à esquerda e trazemos o que houver da direita.
- **Right Join**: Mantemos tudo da direita e trazemos o que houver da esquerda.
- **Full Join**: Trazemos tudo de ambos os lados, independentemente de haver correspondência.

**Como Usamos Joins:**
SELECT
 TabelaA.Nome,
 TabelaB.Pais
FROM
 TabelaA INNER JOIN TabelaB ON TabelaA.id = TabelaB.id;
