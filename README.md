[![General Assembly Logo](https://camo.githubusercontent.com/1a91b05b8f4d44b5bbfb83abac2b0996d8e26c92/687474703a2f2f692e696d6775722e636f6d2f6b6538555354712e706e67)](https://generalassemb.ly/education/web-development-immersive)

# SQL homework, NBA Style!!

![](https://media.giphy.com/media/3o6gDYD4RxwY8uFot2/giphy.gif)

## Learning Objectives

* Databases
* PostgreSQL

## Resources

* [PostgreSQL Docs](https://www.postgresql.org/docs/9.6/static/index.html)
* [PostgreSQL Tutorial](https://www.tutorialspoint.com/postgresql/index.htm)
* [W3Schools SQL](https://www.w3schools.com/sql/)

## Hints

* In the **Terminal**, `psql` starts a connection to PostgreSQL
* Within **psql**
* **`\l`** lists all of your databases
* **`\c <your database>`** connect to your database
* **`\dt`** displays all tables within current database
* **`\q`** quit psql

## Setup

Use the included files `nba_seed.sql`, `nba_queries.sql` and `nba_season_2011-12.csv` to solve the following problems.

## Completion

Parts 1 - 4

## Assignment

We're going to work on our Postgresql skills by practicing basic SQL commands with some ~~outdated~~ NBA data.

### Part 1 - Create and run an SQL seed file

Let's start by **creating** an empty PSQL database called `nba_db` and then **seeding** that database with raw information from `nba_season_2011_2012.csv`. We're going to accomplish all of this by writing PSQL commands into an SQL script called `nba_seed.sql` and then running that script.

1. From the homework folder, open `nba_seed.sql` in VSCode
2. We have completed the following for you:

* Drop a database called `nba_db` if it exists
* Create a database called `nba_db`
* Connect to `nba_db`

3. Enter **PSQL** commands to complete the following objectives:

* Create a table called `players` with columns for

  * `name`
  * `age`\
  * `team`
  * `games`
  * `points`
   CREATE TABLE players (name varchar(20), age integer, team varchar, games varchar, point varchar);

  **HINT**

  > What datatypes should each of these columns be?

* Insert the player:<br>
  `Anderson Varejao, age: 29, team: CLE, games: 25, points: 271`
  insert into players (name, age, team, games, point) VALUES ('Anderson Varejao', 29, 'CLE', 25, 271);

4. Save your `nba_seed.sql` file
5. Run `nba_seed.sql` by entering the following command into the terminal:

```
$ psql -f nba_seed.sql
```

### Part 2 - Edit our seed file to import from a .csv

In the `nba_seed.sql` file, look at the **COPY players** statement which is currently commented out - what do you think it does?

**Uncomment** the COPY command and change the file path for `nba_season_2011_2012.csv` in order to get it to run on _your_ machine. The command `pwd`(or `DIR` in windows) in your terminal may help!

Afterwards comment out the single insert player command you created in Part 1, and run the seed file again:

```
$ psql -f nba_seed.sql
```

### Part 3 - Basic SQL Queries

**For Parts 3 and 4, work in the `nba_queries.sql` file. Run the file to test your answers by using `psql -f nba_queries.sql`**

Some of the prompts may go a little further including or excluding what we covered in class, If unsure you can easily Google and figure out. Some useful things to look up:

* WHERE
* ORDER BY
* LIMIT
* AVG
* SUM

1. All columns for all players from the New York Knicks (NYK).
2. All columns for all players from the Indiana Packers (IND) who are under 26 years old.
3. All columns for all players, ordered from least points scored to most points scored.
4. Name and Points per game (points/games), for the players with the top 20 points per game.
5. The average age for all players.
6. The average age for all players on the Oklahoma City Thunder (OKC).
7. The average age for all players who played more than 40 games.

### BONUS - Advanced SQL Queries

Add the following to your `nba_queries.sql` file:

1. The team and total points scored from all players on that team (team points) ordered from most team points to least.

2. The age and the average points per game for that age, ordered from oldest to youngest for all ages.

3. The team and the the number of players who score above 12 points per game on that team, ordered from the most number of players to the least number of players.

## Test your code on psql before submission!

