# SQL-repo-1
Contains code for SQL Island mini-game, with the respective output for each query if needed.

# SQL ISLAND mini-game

The game starts with you stranded on an island with 3 villages and random inhabitants of the village.  You have to talk to the right people and find the correct information to obtain food and money, and finally leave the island.

# Tables Given: 
  
  VILLAGE (villageid, name, chief)
  
  INHABITANT (personid, name, villageid, gender, job, gold, state)
  
  ITEM (item, owner)

# All Queries Used

1.	SELECT * FROM village

![Screenshot 2023-03-29 022514](https://user-images.githubusercontent.com/123727289/228371068-7d0876f6-302e-4938-b465-662613c67224.png)

2.	SELECT * FROM inhabitant

![Screenshot 2023-03-29 022652](https://user-images.githubusercontent.com/123727289/228371242-fd6aafb4-b56e-4938-bf5e-27d079218a89.png)

3.	SELECT * FROM item

![Screenshot 2023-03-29 025429](https://user-images.githubusercontent.com/123727289/228371475-1e048ece-062d-4ea3-99f5-8afe20096d8b.png)

4.	SELECT * FROM inhabitant WHERE state="friendly"

![Screenshot 2023-03-29 022801](https://user-images.githubusercontent.com/123727289/228371521-f1946386-32c2-4622-8ed7-d80b42417ef8.png)

5.	SELECT * FROM inhabitant WHERE state="friendly" AND job="weaponsmith"

![Screenshot 2023-03-29 022845](https://user-images.githubusercontent.com/123727289/228371607-8c32d170-cf71-417a-8cf8-5e5b6d363f6c.png)

6.	SELECT * FROM inhabitant WHERE state="friendly" AND job LIKE "%smith"

![Screenshot 2023-03-29 022917](https://user-images.githubusercontent.com/123727289/228371628-6a0361b5-12b1-499e-b4fa-3e9754fea1f4.png)

7.	INSERT INTO inhabitant (name, villageid, gender, job, gold, state) VALUES ('Stranger', 1, '?', '?', 0, '?')

8.	SELECT personid FROM inhabitant WHERE name="Stranger"'

![Screenshot 2023-03-29 023003](https://user-images.githubusercontent.com/123727289/228371789-31181b1e-22c3-43d4-9587-36cf6bab4c05.png)

9.	SELECT gold FROM inhabitant WHERE name="Stranger"

![Screenshot 2023-03-29 023032](https://user-images.githubusercontent.com/123727289/228371874-dd2a2317-87eb-4ef6-b078-24db25a54ec4.png)

10.	SELECT * FROM item WHERE owner IS NULL

![Screenshot 2023-03-29 023536](https://user-images.githubusercontent.com/123727289/228371934-376a6254-284d-4b72-ad9f-80d7caa42cbd.png)

11.	UPDATE item SET owner = 20 WHERE owner IS NULL

12.	SELECT * FROM item WHERE owner="20"

![Screenshot 2023-03-29 023419](https://user-images.githubusercontent.com/123727289/228371962-61736a1d-3a8c-459b-92dd-7d048dc6198e.png)

13.	SELECT * FROM inhabitant WHERE state="friendly" AND job="dealer" OR job="merchant"	

![Screenshot 2023-03-29 023445](https://user-images.githubusercontent.com/123727289/228372556-7adce830-33b9-43d9-a84c-7f259d5cc49b.png)

14.	UPDATE item SET owner = 15 WHERE item = "ring" OR item = "teapot" 

15.	UPDATE inhabitant SET name = "Akash" WHERE personid=20

16.	SELECT * FROM inhabitant WHERE job="baker" ORDER BY gold DESC

![Screenshot 2023-03-29 023939](https://user-images.githubusercontent.com/123727289/228372674-3708a3b4-e3da-445c-8ddf-3820dbf77681.png)

17.	SELECT * FROM inhabitant WHERE job="pilot"

![Screenshot 2023-03-29 024035](https://user-images.githubusercontent.com/123727289/228372580-8dd9dd9b-2f42-44ca-9603-bada5ce9705c.png)

18.	SELECT village.name FROM village LEFT JOIN inhabitant WHERE village.villageid = inhabitant.villageid AND inhabitant.name = 'Dirty Dieter'

![Screenshot 2023-03-29 024108](https://user-images.githubusercontent.com/123727289/228372715-32b3cc41-b63b-424e-9032-f73c3e9d6161.png)

19.	SELECT inhabitant.name FROM inhabitant LEFT JOIN village WHERE village.chief = inhabitant.personid AND village.name ="Onionville"

![Screenshot 2023-03-29 024150](https://user-images.githubusercontent.com/123727289/228372731-b9f132e9-99d7-4b10-9db5-ba3a3e1e5ca5.png)

20.	SELECT COUNT (*) FROM inhabitant LEFT JOIN village WHERE village.villageid = inhabitant.villageid AND village.name ="Onionville" AND gender="f"

![Screenshot 2023-03-29 024249](https://user-images.githubusercontent.com/123727289/228372763-a9d3fbbf-3f3e-492b-aba1-6c00553cd153.png)

21.	SELECT inhabitant.name FROM inhabitant LEFT JOIN village WHERE village.villageid = inhabitant.villageid AND village.name ="Onionville" AND gender="f"

![Screenshot 2023-03-29 024336](https://user-images.githubusercontent.com/123727289/228372874-51140a99-f464-494d-822a-5342085087ad.png)

22.	SELECT SUM(inhabitant.gold) FROM inhabitant LEFT JOIN village WHERE village.villageid = inhabitant.villageid AND village.name = 'Cucumbertown'

![Screenshot 2023-03-29 024418](https://user-images.githubusercontent.com/123727289/228372892-f604bee9-3d2c-4eca-95e9-995098f7a168.png)

23.	SELECT SUM(inhabitant.gold) FROM inhabitant WHERE job = “baker” OR job = “dealer” OR job = “merchant”

![Screenshot 2023-03-29 031543](https://user-images.githubusercontent.com/123727289/228374352-4e2317b3-447f-4820-bd4f-8a137e0013b0.png)

24.	SELECT * FROM inhabitant LEFT JOIN item WHERE item.owner = inhabitant.personid AND item.owner = 20

![Screenshot 2023-03-29 024445](https://user-images.githubusercontent.com/123727289/228372904-45a41cb6-8d54-48a9-9cf2-d3b70d891c6c.png)

25.	SELECT job, SUM(inhabitant.gold), AVG(inhabitant.gold) FROM inhabitant GROUP BY job ORDER BY AVG(inhabitant.gold)

![Screenshot 2023-03-29 025209](https://user-images.githubusercontent.com/123727289/228375362-dc1cc31d-3683-49a5-8ebc-e3dc680a7bec.png)

26.	SELECT state, AVG(inhabitant.gold) FROM inhabitant GROUP BY state ORDER BY AVG(inhabitant.gold)    

![Screenshot 2023-03-29 025234](https://user-images.githubusercontent.com/123727289/228375386-8b1fd5f2-1ba7-4789-8370-1371f3dc9b38.png)

27.	DELETE FROM inhabitant WHERE name = 'Dirty Dieter'

28.	DELETE FROM inhabitant WHERE name = "Dirty Diane"

29.	UPDATE inhabitant SET state = "friendly" WHERE state = "kidnapped”
