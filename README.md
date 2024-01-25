# DIO - Trilha .NET - Banco de Dados

## Contexto
Você é responsável pelo banco de dados de um site de filmes, onde são armazenados dados sobre os filmes e seus atores. Sendo assim, foi solicitado para que você realize uma consulta no banco de dados com o objetivo de trazer alguns dados para análises.

## Proposta
O seu banco de dados está modelado da seguinte maneira:

![Diagrama banco de dados](Imagens/diagrama.png)

As tabelas sao descritas conforme a seguir:

**Filmes**

Tabela responsável por armazenar informações dos filmes.

**Atores**

Tabela responsável por armazenar informações dos atores.

**Generos**

Tabela responsável por armazenar os gêneros dos filmes.

**ElencoFilme**

Tabela responsável por representar um relacionamento do tipo muitos para muitos entre filmes e atores, ou seja, um ator pode trabalhar em muitos filmes, e filmes
podem ter muitos atores.

**FilmesGenero**

Tabela responsável por representar um relacionamento do tipo muitos para muitos entre filmes e gêneros, ou seja, um filme pode ter mais de um gênero, e um genêro pode fazer parte de muitos filmes.

## Objetivo
Você deverá criar diversas consultas, com o objetivo de retornar os dados a seguir. Abaixo de cada pedido tem o retorno esperado. O seu retorno deve ser igual ao da imagem.

## 1 - Buscar o nome e ano dos filmes
SELECT Nome,Ano FROM FILMES <br>

![Exercicio 1](Imagens/1.png)

## 2 - Buscar o nome e ano dos filmes, ordenados por ordem crescente pelo ano
SELECT Nome,Ano FROM FILMES ORDER BY Ano <br>

![Exercicio 2](Imagens/2.png)

## 3 - Buscar pelo filme de volta para o futuro, trazendo o nome, ano e a duração
SELECT*FROM Filmes WHERE Nome='De volta para o futuro' <br>

![Exercicio 3](Imagens/3.png)

## 4 - Buscar os filmes lançados em 1997
SELECT *FROM filmes WHERE Ano=1997 <br>

![Exercicio 4](Imagens/4.png)

## 5 - Buscar os filmes lançados APÓS o ano 2000
SELECT *FROM filmes WHERE Ano>2000 <br>

![Exercicio 5](Imagens/5.png)

## 6 - Buscar os filmes com a duracao maior que 100 e menor que 150, ordenando pela duracao em ordem crescente
SELECT *FROM filmes WHERE duracao>100 AND duracao<150 ORDER BY duracao

![Exercicio 6](Imagens/6.png)

## 7 - Buscar a quantidade de filmes lançadas no ano, agrupando por ano, ordenando pela duracao em ordem decrescente
SELECT Ano, COUNT(*) AS Quantidade FROM Filmes GROUP BY Ano ORDER BY Quantidade DESC

![Exercicio 7](Imagens/7.png)

## 8 - Buscar os Atores do gênero masculino, retornando o PrimeiroNome, UltimoNome
SELECT PrimeiroNome, UltimoNome From Atores WHERE Genero='M'

![Exercicio 8](Imagens/8.png)

## 9 - Buscar os Atores do gênero feminino, retornando o PrimeiroNome, UltimoNome, e ordenando pelo PrimeiroNome
SELECT PrimeiroNome, UltimoNome From Atores WHERE Genero='F' ORDER BY PrimeiroNome

![Exercicio 9](Imagens/9.png)

## 10 - Buscar o nome do filme e o gênero
SELECT Filmes.Nome, Generos.Genero FROM FilmesGenero INNER JOIN Filmes ON Filmes.Id=FilmesGenero.IdFilme  INNER JOIN Generos ON Generos.Id=FilmesGenero.IdGenero

![Exercicio 10](Imagens/10.png)

## 11 - Buscar o nome do filme e o gênero do tipo "Mistério"
SELECT Filmes.Nome, Generos.Genero FROM FilmesGenero INNER JOIN Filmes ON Filmes.Id=FilmesGenero.IdFilme  INNER JOIN Generos ON Generos.Id=FilmesGenero.IdGenero WHERE Genero = 'Mistério'

![Exercicio 11](Imagens/11.png)

## 12 - Buscar o nome do filme e os atores, trazendo o PrimeiroNome, UltimoNome e seu Papel
Select Filmes.Nome, Atores.PrimeiroNome, Atores.UltimoNome, ElencoFilme.Papel From ElencoFilme INNER JOIN Filmes ON  Filmes.Id=ElencoFilme.IdFilme INNER JOIN Atores ON ElencoFilme.IdAtor=Atores.Id

![Exercicio 12](Imagens/12.png)
