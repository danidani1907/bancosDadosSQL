# passo a passo de um banco de dados : Criação de um banco de dados SQL
Tuturial de como criar um  banco de dados SQL que organiza
as informaçoes de 'livros', 'editora', 'autores' e 'assuntos'.
Este guia será dividido em etapas para demonstrar desde a 
criação de tabela, chaves e até manipulação/consulta de dados.

## Resumo de estrutura SQL
 * _CREATE_  para   criar 'Banco de dados ' ou ' Tabelas'
 * _ALTER_ para adicionar ou modificar colunas
 * _DROP_ para remover 'Banco de dados' ou ' 'Tabelas'
 * _INSERT_ para adicionar registros na tabela
 * _UPDATE_ para atualizar os registros
 * _DELETE_ para remover os registros
 * _SELECT_ para consultar e vizualizar dados 

 ## Passo 1: criação do banco de dados e das Tabelas

 #### 1.1 criando o DB

 ```

 CREATE DATABASE biblioteca;
 USE biblioteca;

```

#### 1.2 Criando a tabela 'editora'

```
CREATE TABLE editora (
    id_editora INT PRIMARY KEY AUTO_INCREMENT,
    nome_editora VARCHAR(100) NOT NULL,
    pais VARCHAR(50)
);

```


#### 1.3 Criando a tabela 'autor'

```
CREATE TABLE autor(
    id_autor INT PRIMARY KEY AUTO_INCREMENT,
    nome_autor VARCHAR(200) ,
    data_nascimento DATE
);

```

#### 1.4 Criando a tabela 'assunto'

```
CREATE TABLE assunto(
    id_assunto INT PRIMARY KEY AUTO_INCREMENT,
    descricao_assunto VARCHAR(200) NOT NULL
   );

```


#### 1.5 Criando a tabela 'livro'

```
CREATE TABLE livro(
    id_livro INT PRIMARY KEY AUTO_INCREMENT,
    titulo VARCHAR(150) NOT NULL,
    ano_publicacao YEAR, 
    FOREING KEY(id_editora) REFERENCES editora(id_editora),
    FOREING KEY(id_autor) REFERENCES editora(id_autor),
    FOREING KEY(id_assunto) REFERENCES editora(id_assunto),
   );

```

#### 1.6 Criando a tabela uma tabela extra

```
CREATE TABLE extra(
    id INT PRIMARY KEY AUTO_INCREMENT,
    produtos(150) NOT NULL,
    ano_publicacao VARCHAR NOT NULL(50), 
    quantidade INT(20) NOT NULL,
    preco DOUBLE NOT NULL
    
   );

```

#### passo 2: editar tabelas usando 'ALTER'
Após a criação da tabela, podemos adicionar novos
campos.Vamos adicionar uma coluna 'email' na tabela 'autor'

```SQL
ALTER TABLE autor
ADD COLUMN email VARCHAR(100);

```