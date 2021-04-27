======Queries======

To add to movies table:

INSERT INTO movies (title, runtime, genre, imdb_score, rating)
VALUES ('Howard the Duck', 110, 'Sci-Fi', 4.6, 'PG');

To select sci-fi movies:
Select * from movies where genre = 'Sci-Fi'

To select scores of movies w/ rating higher than 6.5:
Select * from movies where imdb_score >= 6.5;

PG and G ratings AND runtime < 100:
Select * from movies where (rating = 'PG' or rating = 'G') AND runtime < 100;

Average score < 7.5 grouped by genre:
Select AVG(runtime), from movies where imdb_score < 7.5  GROUP BY genre;

Fix starship troopers rating:
UPDATE movies SET rating = 'R'
WHERE title = 'Starship Troopers';

Show ID and IMDB score of horror and documentary movies:
SELECT id, imdb_score FROM MOVIES where genre = 'Horror' OR genre = 'Documentary';

Avg, max, and min imdb score of each genre:
SELECT AVG(imdb_score), MAX(imdb_score), MIN(imdb_score) from movies GROUP BY genre;

^^ AVG MAX MIN with count > 1
SELECT AVG(imdb_score), MAX(imdb_score), MIN(imdb_score) from movies GROUP BY genre HAVING COUNT(*) > 1;

Delete rated r movies
DELETE from movies where rating = 'R';