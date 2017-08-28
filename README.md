```
id |                 title                 | details | priority |         created_at         |       completed_at

----+---------------------------------------+---------+----------+----------------------------+----------------------
-----
  1 | Renew License                         |         |        1 | 2017-08-28 15:47:30.002585 |
  2 | Connect pan                          +|         |        2 | 2017-08-28 15:47:30.002585 |
    | elists to AGC reps                    |         |          |                            |
  4 | Tidy the deck up                      |         |        4 | 2017-08-28 15:47:30.002585 |
  5 | Prep D&D mater                       +|         |        5 | 2017-08-28 15:47:30.002585 |
    | ials                                  |         |          |                            |
  6 | Connect friends to competition and GA |         |        6 | 2017-08-28 15:47:30.002585 |
  3 | Refresh litter box                    |         |        3 | 2017-08-28 15:47:30.002585 | 2017-08-28 15:50:49.6


```
```
-Created dir
-Created Readme
-created todo.sql
-createdb todolist
-psql todolist
-/d checking it is there
-/q quitting out
-psql -f todo.sql todolist (running file on terminal):
-CREATE TABLE Todolist_Table (
    id SERIAL PRIMARY KEY,
    task VARCHAR(100) NOT NULL,
    completion BOOLEAN NOT NULL DEFAULT 'f'
    );
```
-\d
-INSERT INTO Todolist_Table (task) VALUES ('Renew License'), ('Connect panelists to AGC reps'), ('Refresh litter box'), ('Tidy the deck up'), ('Prep D&D materials'), ('Connect friends to competition and GA');
-select task from todolist_table where completion = 'f';
-alter table todolist_table add column title VARCHAR(255);
-ALTER TABLE todolist_table MODIFY title VARCHAR(255) not null;
-ALTER TABLE todolist_table DROP COLUMN IF EXISTS task;
-DROP TABLE todolist_table;

-START INSERT TABLE OVER:
  -CREATE TABLE Todolist_Table (
  id SERIAL PRIMARY KEY,
  title VARCHAR(255) NOT NULL,
  details VARCHAR(1500) NULL,
  priority INTEGER DEFAULT '1' NOT NULL,
  created_at TIMESTAMP NOT NULL,
  completed_at TIMESTAMP NULL
);

-INSERT STUFF:
  INSERT INTO Todolist_Table (title, priority, created_at) VALUES ('Renew License', 1, Current_Timestamp), ('Connect pan
  elists to AGC reps', 2, Current_Timestamp), ('Refresh litter box', 3, Current_Timestamp), ('Tidy the deck up', 4, Current_Timestamp), ('Prep D&D mater
  ials', 5, Current_Timestamp), ('Connect friends to competition and GA', 6, Current_Timestamp);

-UPDATE INTO Todolist_Table
    UPDATE Todolist_Table SET completed_at = Current_Timestamp WHERE id = 3;

-SELECT STATEMENT "Write a SELECT statement to find all incomplete todos."
  SELECT title FROM todolist_table WHERE completed_at IS NULL;

-SELECT STATEMENT "Write a SELECT statement to find all todos with a priority above 1."
  SELECT title FROM todolist_table WHERE priority > 1;

-UPDATE "Write an UPDATE statement to complete one todo by its id. Your ids may differ, so you will choose the id to up."
  UPDATE Todolist_Table SET completed_at = Current_Timestamp WHERE id = 4;

-DELETE "Write a DELETE statement to delete all completed todos."
  DELETE FROM todolist_table WHERE completed_at IS NOT NULL;
