# Schemas and relationships




## What kinds of data relationships are there?




## What's a foreign key? How can they help us design schemas with relational data?


A FOREIGN KEY is a key used to link two tables together.

A FOREIGN KEY is a field (or collection of fields) in one table that refers to the PRIMARY KEY in another table.

The table containing the foreign key is called the child table, and the table containing the candidate key is called the referenced or parent table.


![](https://i.imgur.com/LGzXPYM.png)


#### The "PersonID" column in the "Orders" table is a FOREIGN KEY in the "Orders" table.

while creating the ORDERS TABLE:
FOREIGN KEY (PersonID) REFERENCES Persons(PersonID)

The FOREIGN KEY constraint is used to prevent actions that would destroy links between tables.

The FOREIGN KEY constraint also prevents invalid data from being inserted into the foreign key column, because it has to be one of the values contained in the table it points to.The FOREIGN KEY constraint is used to prevent actions that would destroy links between tables.

The FOREIGN KEY constraint also prevents invalid data from being inserted into the foreign key column, because it has to be one of the values contained in the table it points to.

### Many-to-many relationships and junction tables

Often, representing a many-to-many relationship in Airtable is as easy as linking two tables together. However, in some situations, you don’t just need to know that there is a relationship between two entities—you also need to be able to express and store other information about that relationship. In these cases, you’ll need to create a third table, called a junction (or join) table. You can think of the junction table as a place to store attributes of the relationships between two lists of entities.








![](https://i.imgur.com/PnXJWf2.png)


---------------------





https://www.youtube.com/watch?v=tJvffU98xw0

![](https://i.imgur.com/Evl9yB7.png)


![](https://i.imgur.com/r1dwz6F.jpg)
![](https://i.imgur.com/gGpOqUs.png)
![](https://i.imgur.com/OVJWgFA.png)
# 2 x (one to many )

![](https://i.imgur.com/AyMcdQe.png)
![](https://i.imgur.com/pcomPEH.png)
![](https://i.imgur.com/4Q3j3Cs.png)
                          
