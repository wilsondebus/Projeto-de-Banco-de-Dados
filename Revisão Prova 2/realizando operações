-- Seleciona o banco de dados que será usado nas consultas
USE editora_db; 

-- Conta quantas linhas existem na tabela Ranking_Semanal
SELECT COUNT(*)
FROM Ranking_Semanal;


-- i. Mostre todos os autores cadastrados

-- Seleciona todas as colunas e todos os registros da tabela Autor
SELECT * 
FROM Autor;


-- ii. Mostre apenas os nomes dos autores

-- Seleciona somente a coluna nome da tabela Autor
SELECT nome
FROM Autor;


-- iii. Mostre o nome e a identificação do autor, nesta ordem

-- Seleciona primeiro o nome e depois o idAutor de cada autor
SELECT nome, idAutor
FROM Autor;


-- iv. Mostre o nome dos autores que aparecem na tabela Livro_Autor

-- Seleciona o nome dos autores
SELECT Autor.nome
-- Usa as tabelas Autor e Livro_Autor
FROM Autor, Livro_Autor
-- Relaciona as tabelas pelo campo idAutor
WHERE Autor.idAutor = Livro_Autor.idAutor;

-- Outra forma de fazer a mesma consulta usando INNER JOIN

-- Seleciona os nomes dos autores sem repetição
SELECT DISTINCT Autor.nome
-- Começa a consulta pela tabela Autor
FROM Autor
-- Junta com a tabela Livro_Autor
INNER JOIN Livro_Autor
-- Define a condição de ligação entre as tabelas
ON Autor.idAutor = Livro_Autor.idAutor;


-- v. Mostre o nome dos autores, sem repetição, presentes na tabela Livro_Autor

-- DISTINCT evita que o mesmo nome apareça mais de uma vez
SELECT DISTINCT Autor.nome
-- Usa as tabelas Autor e Livro_Autor
FROM Autor, Livro_Autor
-- Relaciona o autor com a tabela intermediária Livro_Autor
WHERE Autor.idAutor = Livro_Autor.idAutor;


-- vi. Mostre os autores em ordem alfabética

-- Seleciona os nomes dos autores sem repetição
SELECT DISTINCT Autor.nome
-- Usa as tabelas Autor e Livro_Autor
FROM Autor, Livro_Autor
-- Relaciona as tabelas pelo idAutor
WHERE Autor.idAutor = Livro_Autor.idAutor
-- Ordena os nomes em ordem alfabética crescente
ORDER BY Autor.nome;


-- vii. Mostre o título dos livros que são da editora Rocco ou da editora Scipione

-- Seleciona o título do livro e o nome da editora
SELECT Livro.titulo, Editora.nome
-- Usa as tabelas Livro e Editora
FROM Livro, Editora 
-- Filtra apenas editoras chamadas Rocco ou Scipione
-- E relaciona Livro com Editora pelo idEditora
WHERE (Editora.nome = "Rocco" OR Editora.nome = "Scipione") 
AND Livro.idEditora = Editora.idEditora;


-- viii. Mostre, em ordem alfabética, os autores que começam com M

-- Seleciona o nome dos autores
SELECT nome
-- Da tabela Autor
FROM Autor
-- Filtra nomes que começam com a letra M
WHERE nome LIKE "M%"
-- Ordena em ordem alfabética
ORDER BY nome;


-- ix. Mostre, em ordem alfabética, os autores que começam com L

-- Seleciona o nome dos autores
SELECT nome
-- Da tabela Autor
FROM Autor
-- Filtra nomes que começam com a letra L
WHERE nome LIKE "L%"
-- Ordena em ordem alfabética
ORDER BY nome;


-- x. Mostre, em ordem alfabética, os autores que NÃO começam com L

-- Seleciona o nome dos autores
SELECT nome
-- Da tabela Autor
FROM Autor
-- Filtra nomes que não começam com a letra L
WHERE nome NOT LIKE "L%"
-- Ordena em ordem alfabética
ORDER BY nome;


-- xi. Mostre, em qualquer ordem, os autores que não começam com M

-- Seleciona o nome dos autores
SELECT nome
-- Da tabela Autor
FROM Autor
-- Filtra nomes que não começam com a letra M
WHERE nome NOT LIKE "M%"
-- Ordena pelo nome, embora a questão diga que pode ser em qualquer ordem
ORDER BY nome;


-- xii. Liste apenas os livros das editoras 1 OU 5

-- Seleciona o título do livro e o nome da editora
SELECT Livro.titulo, Editora.nome
-- Usa as tabelas Livro e Editora
FROM Livro, Editora
-- Filtra livros cuja editora seja 1 ou 5
-- E relaciona Livro com Editora pelo idEditora
WHERE (Editora.idEditora = 1 OR Editora.idEditora = 5) 
AND Livro.idEditora = Editora.idEditora;


-- xiii. Mostre os livros infantis das editoras 1 e 5

-- Seleciona o título do livro, o gênero, o código da editora e o nome da editora
SELECT Livro.titulo, 
       Genero.descricao, 
       Livro.idEditora AS "Código Editora", 
       Editora.nome
-- Usa as tabelas Livro, Genero e Editora
FROM Livro, Genero, Editora
-- Filtra apenas livros do gênero Infantil
WHERE Genero.descricao = "Infantil"
-- Relaciona Livro com Genero pelo idGenero
AND Livro.idGenero = Genero.idGenero
-- Filtra livros das editoras 1 ou 5
AND (Livro.idEditora = 1 OR Livro.idEditora = 5)
-- Relaciona Livro com Editora pelo idEditora
AND Livro.idEditora = Editora.idEditora;


-- xiv. Mostre os códigos e os títulos dos livros, com seus respectivos preços

-- Seleciona o código do livro, o título e o preço
SELECT idLivro, titulo, preco 
-- Da tabela Livro
FROM Livro;


-- xv. Mostre os autores em ordem contrária à alfabética

-- Seleciona todos os dados dos autores
SELECT * 
-- Da tabela Autor
FROM Autor 
-- Ordena pelo nome em ordem decrescente, ou seja, de Z para A
ORDER BY nome DESC;


-- xvi. Liste os livros, na ordem de preços do mais caro ao mais barato

-- Seleciona todos os dados dos livros
SELECT * 
-- Da tabela Livro
FROM Livro 
-- Ordena pelo preço em ordem decrescente, do maior para o menor
ORDER BY preco DESC;


-- xvii. Liste os livros, na ordem de preços do mais barato ao mais caro

-- Seleciona todos os dados dos livros
SELECT * 
-- Da tabela Livro
FROM Livro 
-- Ordena pelo preço em ordem crescente, do menor para o maior
ORDER BY preco;


-- xviii. Mostre apenas os livros de auto-ajuda, na ordem crescente de preço

-- Forma 1: usando diretamente o código do gênero
-- Funciona se o idGenero 4 realmente for Auto-ajuda

-- Seleciona título e preço dos livros
SELECT Livro.titulo, Livro.preco 
-- Da tabela Livro
FROM Livro 
-- Filtra livros cujo gênero tem código 4
WHERE idGenero = 4
-- Ordena do menor preço para o maior
ORDER BY preco;


-- Forma 2: usando a tabela Genero
-- Essa forma é melhor para prova, pois filtra pelo nome do gênero

-- Seleciona todas as colunas das tabelas Livro e Genero
SELECT * 
-- Usa as tabelas Livro e Genero
FROM Livro, Genero 
-- Relaciona Livro com Genero pelo idGenero
WHERE Livro.idGenero = Genero.idGenero 
-- Filtra apenas o gênero Auto-ajuda
AND Genero.descricao = "Auto-ajuda" 
-- Ordena pelo preço em ordem crescente
ORDER BY preco ASC;


-- Forma 3: selecionando apenas os dados do livro

-- Seleciona todas as colunas da tabela Livro
SELECT Livro.* 
-- Usa as tabelas Livro e Genero
FROM Livro, Genero 
-- Filtra pelo gênero Auto-ajuda
WHERE Genero.descricao = "Auto-ajuda" 
-- Relaciona Livro com Genero pelo idGenero
AND Livro.idGenero = Genero.idGenero 
-- Ordena pelo preço em ordem crescente
ORDER BY preco ASC;


-- xix. Mostre quantos autores estão cadastrados

-- Conta quantos registros existem na tabela Autor
SELECT COUNT(*)
FROM Autor;


-- xx. Mostre os preços dos livros mais baratos e mais caros da editora 1

-- Retorna o maior e o menor preço dos livros da editora 1
SELECT MAX(preco) AS livroMaisCaro, 
       MIN(preco) AS livroMaisBarato 
-- Da tabela Livro
FROM Livro
-- Filtra apenas livros da editora de código 1
WHERE Livro.idEditora = 1;


-- Mesma consulta, sem apelidos para as colunas
SELECT MAX(preco), MIN(preco) 
FROM Livro 
WHERE idEditora = 1;


-- Essa consulta mostra o título e o preço dos livros mais caro e mais barato da editora 1

-- Seleciona título e preço
SELECT titulo, preco 
-- Da tabela Livro
FROM Livro 
-- Filtra o livro cujo preço é igual ao maior preço da editora 1
WHERE preco = (
    SELECT MAX(preco) 
    FROM Livro 
    WHERE idEditora = 1
)
-- Ou filtra o livro cujo preço é igual ao menor preço da editora 1
OR preco = (
    SELECT MIN(preco) 
    FROM Livro 
    WHERE idEditora = 1
);


-- xxi. Liste a média de preços dos livros da editora 2

-- Calcula a média dos preços dos livros da editora 2
SELECT AVG(preco) AS precoMedio 
FROM Livro 
WHERE idEditora = 2;


-- Mesma consulta, sem apelido
SELECT AVG(preco) 
FROM Livro 
WHERE idEditora = 2;


-- Calcula a média dos preços e arredonda para 2 casas decimais
SELECT ROUND(AVG(preco), 2) 
FROM Livro 
WHERE idEditora = 2;


-- Cria uma VIEW chamada MediaPreco
-- Uma VIEW é uma consulta salva no banco de dados
CREATE VIEW MediaPreco AS
-- Consulta que será salva dentro da VIEW
SELECT ROUND(AVG(preco), 2) 
FROM Livro 
WHERE idEditora = 2;


-- xxii. Mostre os livros com seus respectivos nomes de editoras e gêneros

-- Seleciona o título do livro, o nome da editora e a descrição do gênero
SELECT Livro.titulo, 
       Editora.nome AS editora, 
       Genero.descricao AS genero 
-- Usa as tabelas Livro, Editora e Genero
FROM Livro, Editora, Genero 
-- Relaciona Livro com Editora pelo idEditora
WHERE Livro.idEditora = Editora.idEditora 
-- Relaciona Livro com Genero pelo idGenero
AND Livro.idGenero = Genero.idGenero;


-- Mesma consulta, mudando apenas os nomes exibidos nas colunas
SELECT Livro.titulo, 
       Editora.nome AS "Editora", 
       Genero.descricao AS "Genero" 
FROM Livro, Editora, Genero 
WHERE Livro.idGenero = Genero.idGenero 
AND Livro.idEditora = Editora.idEditora;


-- xxiii. Liste os livros, mostrando o título de cada um bem como o nome do autor

-- Seleciona o título do livro e o nome do autor
SELECT Livro.titulo, Autor.nome 
-- Usa as tabelas Livro, Autor e Livro_Autor
FROM Livro, Autor, Livro_Autor 
-- Relaciona Livro_Autor com Livro pelo idLivro
WHERE Livro_Autor.idLivro = Livro.idLivro 
-- Relaciona Livro_Autor com Autor pelo idAutor
AND Livro_Autor.idAutor = Autor.idAutor;


-- ATENÇÃO:
-- No seu código original apareceu LivroAutor, mas a tabela correta é Livro_Autor.
-- Abaixo está a versão corrigida.

-- Seleciona o título do livro com apelido "livro" e o nome do autor com apelido "autor"
SELECT Livro.titulo AS livro, 
       Autor.nome AS autor 
-- Usa as tabelas Livro, Autor e Livro_Autor
FROM Livro, Autor, Livro_Autor 
-- Relaciona Livro_Autor com Autor pelo idAutor
WHERE Livro_Autor.idAutor = Autor.idAutor 
-- Relaciona Livro_Autor com Livro pelo idLivro
AND Livro_Autor.idLivro = Livro.idLivro;


-- Consulta mais completa: mostra título do livro, autor e editora

-- Seleciona título do livro, nome do autor e nome da editora
SELECT Livro.titulo, 
       Autor.nome, 
       Editora.nome 
-- Usa as tabelas Livro, Autor, Livro_Autor e Editora
FROM Livro, Autor, Livro_Autor, Editora 
-- Relaciona Livro_Autor com Livro
WHERE Livro_Autor.idLivro = Livro.idLivro 
-- Relaciona Livro_Autor com Autor
AND Livro_Autor.idAutor = Autor.idAutor 
-- Relaciona Livro com Editora
AND Livro.idEditora = Editora.idEditora 
-- Ordena o resultado pelo título do livro
ORDER BY Livro.titulo;


-- xxiv. Mostre o título do livro que ficou o maior número de semanas consecutivas em 1º lugar

-- Seleciona o título do livro, a posição no ranking e as semanas consecutivas
SELECT Livro.titulo, 
       Ranking_Semanal.posicao, 
       Ranking_Semanal.semanasConsecutivas 
-- Usa as tabelas Livro e Ranking_Semanal
FROM Livro, Ranking_Semanal 
-- Filtra o registro cuja quantidade de semanas consecutivas é a maior
WHERE Ranking_Semanal.semanasConsecutivas = (
    -- Subconsulta que encontra o maior número de semanas consecutivas
    SELECT MAX(semanasConsecutivas) 
    FROM Ranking_Semanal 
    -- Considera apenas livros que estavam em 1º lugar
    WHERE posicao = 1
)
-- Relaciona Livro com Ranking_Semanal pelo idLivro
AND Livro.idLivro = Ranking_Semanal.idLivro
-- Garante que o resultado seja apenas de livros em 1º lugar
AND Ranking_Semanal.posicao = 1;


-- Outra forma de fazer a mesma consulta usando ORDER BY e LIMIT

-- Seleciona o título do livro, o idLivro e as semanas consecutivas
SELECT Livro.titulo, 
       Ranking_Semanal.idLivro, 
       Ranking_Semanal.semanasConsecutivas 
-- Usa as tabelas Ranking_Semanal e Livro
FROM Ranking_Semanal, Livro 
-- Relaciona Livro com Ranking_Semanal pelo idLivro
WHERE Livro.idLivro = Ranking_Semanal.idLivro
-- Filtra apenas os livros que estavam em 1º lugar
AND Ranking_Semanal.posicao = 1
-- Ordena do maior número de semanas consecutivas para o menor
ORDER BY Ranking_Semanal.semanasConsecutivas DESC 
-- Retorna apenas o primeiro resultado
LIMIT 1;


-- xxv. Mostre o nome dos autores dos livros que estavam no ranking da semana de 24/08/2003 a 30/08/2003

-- Forma 1: usando o idRanking diretamente

-- Seleciona os nomes dos autores sem repetição
SELECT DISTINCT Autor.nome AS autor 
-- Usa as tabelas necessárias para ligar autor, livro e ranking
FROM Livro, Autor, Livro_Autor, Ranking, Ranking_Semanal 
-- Relaciona Livro_Autor com Autor
WHERE Livro_Autor.idAutor = Autor.idAutor 
-- Relaciona Livro_Autor com Livro
AND Livro_Autor.idLivro = Livro.idLivro 
-- Relaciona Ranking_Semanal com Ranking
AND Ranking_Semanal.idRanking = Ranking.idRanking 
-- Relaciona Ranking_Semanal com Livro
AND Ranking_Semanal.idLivro = Livro.idLivro 
-- Filtra o ranking de código 2
AND Ranking.idRanking = 2;


-- Forma 2: usando as datas do ranking
-- Essa forma é melhor para prova, pois usa exatamente o período pedido no enunciado

-- Seleciona os nomes dos autores sem repetição
SELECT DISTINCT Autor.nome AS autor 
-- Usa as tabelas Livro, Autor, Livro_Autor, Ranking e Ranking_Semanal
FROM Livro, Autor, Livro_Autor, Ranking, Ranking_Semanal 
-- Filtra o ranking cuja data inicial é 24/08/2003
WHERE Ranking.dataInicial = "2003-08-24" 
-- Filtra o ranking cuja data final é 30/08/2003
AND Ranking.dataFinal = "2003-08-30"
-- Relaciona Livro_Autor com Autor
AND Livro_Autor.idAutor = Autor.idAutor 
-- Relaciona Livro_Autor com Livro
AND Livro_Autor.idLivro = Livro.idLivro 
-- Relaciona Ranking_Semanal com Ranking
AND Ranking_Semanal.idRanking = Ranking.idRanking 
-- Relaciona Ranking_Semanal com Livro
AND Ranking_Semanal.idLivro = Livro.idLivro;


-- Forma 3: usando subconsulta para encontrar o idRanking pelo período

-- Seleciona o nome do autor
SELECT Autor.nome
-- Usa as tabelas Autor, Ranking, Ranking_Semanal e Livro_Autor
FROM Autor, Ranking, Ranking_Semanal, Livro_Autor
-- Filtra Ranking_Semanal pelo idRanking encontrado na subconsulta
WHERE Ranking_Semanal.idRanking = (
    -- Subconsulta que busca o idRanking da semana desejada
    SELECT idRanking
    FROM Ranking
    WHERE dataInicial = "2003-08-24" 
    AND dataFinal = "2003-08-30"
)
-- Relaciona Ranking com Ranking_Semanal
AND Ranking.idRanking = Ranking_Semanal.idRanking
-- Relaciona Ranking_Semanal com Livro_Autor pelo idLivro
AND Ranking_Semanal.idLivro = Livro_Autor.idLivro
-- Relaciona Livro_Autor com Autor pelo idAutor
AND Livro_Autor.idAutor = Autor.idAutor;
