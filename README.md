# Comandos Básicos de SQL

## Comando SELECT 

Seleciona uma quantidade especifica de Linhas com um tipo específico de Categorias.

* SELECT { coluna } FROM { tabela }
  
* SELECT * FROM { tabela }

OBS: o * seleciona todas as colunas

Um exemplo:
```
SELECT { coluna }
FROM { tabela }
```

<br>

## Comando DISTINCT

Omitir dados duplicados de uma tabela (retornar apenas dados únicos).

* SELECT DISTINCT { coluna } FROM { tabela }

<br>

## Comando WHERE

Extrair apenas alguns dados de acordo com sua condição.

* SELECT { coluna } FROM { tabela } WHERE { condição }

```
SELECT { coluna }
FROM { tabela }
WHERE LastName = 'miller' AND firstName = 'anna'
```

OBS: Operadores para as condições:
* = IGUAL
* > MAIOR QUE
* < MENOR QUE
* >= MAIOR QUE OU IGUAL
* <= MENOR QUE OU IGUAL
* <> DIFERENTE DE
* AND OPERADOR 'E'
* OR OPERADOR 'OU'

## Comando COUNT

O comando COUNT serve para retornar a quantidade de linhas de acordo com a sua condição.

```
SELECT DISTINCT COUNT(*)
FROM { tabela }
```

<br>

## Comando TOP

O comando TOP ele filtra (limita) o que é retornado de um SELECT.

```
SELECT TOP 10 *
FROM { tabela }
```

<br>

## Comando ORDER BY

O comando ORDER BY permite que você ordene os resultados pela coluna em ordem crescente ou decrescente.
```
SELECT { coluna }
FROM { tabela }
ORDER BY { coluna } ASC or DESC
```

<br>

## Comando BETWEEN

O comando BETWEEN é usado para encontrar valor, entre um valor mínimo e um valor máximo.

```
SELECT { coluna }
FROM { tabela }
WHERE { coluna } BETWEEN 100 AND 200;
```

Para fazer o contrário basta utilizar o NOT.

```
SELECT { coluna }
FROM { tabela }
WHERE { coluna } NOT BETWEEN 100 AND 200;
```

<br>

## Comando IN

O comando IN é utilizado em conjunto com o WHERE, para verificar se um valor correspondem com qualquer valor passado na lista de valores.

OBS: Novamente, caso queira o contrário da sua condição, utilize o NOT.

```
SELECT { coluna }
FROM { tabela }
WHERE { coluna } IN(valor1, valor2, valor3);
```

<br>

## Comando LIKE
O comando LIKE é utilizado para encontrar um dado específico com fragmentos do nome (Exemplo: Você sabe que o nome da pessoa que você quer encontrar começa com 'ped' mas não lembra o restante do nome).

```
SELECT { coluna }
FROM { tabela }
WHERE { coluna } LIKE 'ped%';
```

OBS: o '%' significa que não importa oque vem depois dele (ele é um limitador de caracteres) ele vai buscar tudo no seu banco de dados que comece com 'ped'.

É possível buscar entre os % também. Por exemplo: '%nessa$', vai aparecer Vanessa.

OBS: Para limitar apenas um caracter você pode utilizar o '_' (underline)

<br>

## Comando CREATE TABLE

O comando CREATE TABLE é utilizado para criar uma tabela para o banco de dados e utilizar algumas restrições.

Principais tipos de restrições que podem ser aplicadas
* NOT NULL - Não permite nulos
* UNIQUE - Força que todos os valores em uma coluna sejam diferentes
* PRIMARY KEY - Uma junção de NOT NULL e UNIQUE
* FOREIGN KEY - Identifica únicamente uma linha em outra tabela. (relaciona as tabelas)
* CHECK - Força uma condição específica em uma coluna
* DEFAULT - Força um valor padrão quando nenhum valor é passado

OBS: VARCHAR() é utilizado para colocar um limite de caracteres.

```
CREATE TABLE { nome da tabela } (
{ nome da coluna } INT PRIMARY KEY, // Geralmente usado para ID.
{ nome da coluna } VARCHAR() NOT NULL, //To limitando o numero de caracteres para o nome por exemplo e não estou acetando valores nulos.
{ nome da coluna } INT DEFAULT { valor }, // Estou iniciando uma coluna com um valor padrão.
{ nome da coluna } INT FOREIGN KEY REFERENCES { coluna de outra tabela }, // Estou pegando o valor de outra tabela já existente.
```

<br>

## Comando INSERT INTO

O comando INSERT INTO é utilizado para inserir dados em uma tabela.

**Inserindo dados de uma tabela em uma tabela existente:**

```
INSERT INTO { nova tabela }(nova coluna)
SELECT { coluna existente }
FROM { tabela }
```

**Inserindo dados:**

```
INSERT INTO { nome da tabela }(coluna1, coluna2)
VALUES(valor1, valor2)
```

**Copiar dados de uma tabela e inserir numa tabela existente:**

```
SELECT * INTO { NOVA TABELA }
FROM { TABELA }
```

<br>

## Comando UPDATE

O comando UPDATE é utilizado para atualizar linhas do banco de dados.

```
UPDATE { tabela }
SET { coluna } = { novo valor}
WHERE { coluna } = { novo valor };

SELECT *
FROM { tabela }
```

<br>

## Comando DELETE

O comando DELETE é utilizado para apagar linhas do banco de dados

OBS: Se atente em colocar uma condição para não apagar tudo.

```
SELECT { coluna }
FROM { tabela }

DELETE FROM { tabela }
WHERE { coluna } = { valor }
```

<br>

## Comando DELETE

O comando DELETE é utilizado para apagar linhas do banco de dados

OBS: Se atente em colocar uma condição para não apagar tudo.

```
SELECT { coluna }
FROM { tabela }

DELETE FROM { tabela }
WHERE { coluna } = { valor }
```
