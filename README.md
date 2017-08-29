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

```
  DAY 2
```

priorities, created times, and completed times, with not all having a completed time.

1. INSERT INTO Todolist_Table (title, priority, created_at) VALUES ('Make a new todolist item', 7, Current_Ti
mestamp), ('contemplate todolists', 8, Current_Timestamp), ('contemplate life', 8, Current_Timestamp), ('contemplate tacos', 9, Current_Timestamp), ('Run for class president', 10, Current_Timestamp), ('Make a souffle', 11, Current_Timestamp), ('run a coldwar-era subterfuge mission to recover super secret plans', 12, Current_Timestamp), ('Take plans and put them in the van', 13, Current_Timestamp), ('Enjoy crumpets and tea', 14, Current_Timestamp), ('Get car washed', 15, Current_Timestamp), ('Research how to make pickles without vinegar', 6, Current_Timestamp), ('Actually, research what vinegar even is', 16, Current_Timestamp), ('Research how to make your own vinegar', 17, Current_Timestamp),('Vacuum living room', 18, Current_Timestamp), ('Get gudd', 19, Current_Timestamp), ('Eat lunch', 20, Current_Timestamp);
2. UPDATE Todolist_Table SET completed_at = Current_Timestamp WHERE id = 12;
3. UPDATE Todolist_Table SET completed_at = Current_Timestamp WHERE id = 19;
4. SELECT title FROM todolist_table WHERE priority = 3;
5. "Write a SELECT statement to find the number of incomplete todos by priority."
    - SELECT COUNT(id) FROM todolist_table WHERE completed_at >= IS NULL GROUP BY priority;
6.    SELECT COUNT(id) FROM todolist_table WHERE created_at > NOW() - INTERVAL '30 days' GROUP BY priority; 
7. SELECT title FROM todolist_table WHERE MIN(priority) AND MIN(created_at);
