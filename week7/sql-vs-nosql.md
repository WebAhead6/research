# Relational vs Non Relational Databases


## :memo: Data structure


## Relational Databases


relational database consists of two or more **tables** with **columns** and **rows**. Each row represents an entry, and each column sorts a very specific type of information, like a name, address, and phone number. The relationship between tables and field types is called a schema. In a relational database, the **schema** must be clearly defined before any information can be added.


### How SQL Databases Work

For an SQL database, setting up a database for addresses begins with the **logical construction** of the **format** and the expectation that the records to be stored are going to remain **relatively unchanged**. 

After analyzing the expected query patterns, an SQL database might optimize storage in two tables, one for **basic information** and one pertaining to being a **customer**, with last name being the key to both tables. **Each row** in each table is a *single customer*, and **each column** has the following *fixed attributes*:

**Basic information**
Last name :: first name :: middle initial :: address fields :: email address :: phone number
**Customer**
Last name :: date of birth :: account number :: customer years :: communication preferences



![](https://i.imgur.com/SJF4T1A.jpg)


![](https://i.imgur.com/vLLxC81.jpg)



## Non-Relational Databases 
NoSQL aka "not only SQL"


Non-relational databases come in a variety of **types** based on their data model. The main types are :
1. **Document** - store data in documents similar to JSON 
> Each document contains pairs of **fields** and **values**. 
The values can typically be a variety of types including things like strings, numbers, booleans, arrays, or objects
2. **Key-value databases**- keys and values
> A value can typically only be retrieved by referencing its value
3. **Wide-column stores** - tables, rows, and dynamic columns.
> flexibility over relational databases because each row is not required to have the same columns.
> Many consider wide-column stores to be two-dimensional key-value databases.
4. **Graph databases** - store data in nodes and edges.
> typically store information about **people**, **places**, and things while edges store information about the relationships between the nodes.


### How NoSQL Databases Work
Four types previously described each has its own data model.

Each type of NoSQL database would be designed with a **specific customer situation** in mind, and there would be **technical reasons** for how each kind of database would be organized. The simplest type to describe is the document database, in which it would be natural to combine both the *basic information* and the *customer information* in one JSON document. In this case, each of the SQL column attributes would be fields and the details of a customer’s record would be the data values associated with each field.

**Basic information: customer information**
For example: Last_name: "Jones", First_name: "Mary", Middle_initial: "S", etc



![](https://i.imgur.com/Zig8GIs.png)


### Which companies use relational databases?

* Microsoft
* NTT Data
* Cognizant
* Dell
* Accenture
* Stack Overflow


### Which companies use non relational databases?
* Amazon
* Adobe
* Capgemini
* SAP
* Qualcomm
* J.P. Morgan

<hr>

# 2. What are some advantages of relational data? Are there disadvantages?


##### :memo: Relational vs non-relational databases: advantages and disadvantages

> Explaining a database and its types to a non-tech person may be hard. But Basheer and I accepted the challenge. In this Technical Spike, we compare relational vs. non-relational databases and help you make the right decision for your project![color=red]

![](https://clockwise.software/img/blog/relational-vs-non-relational-databases-advantages-and-disadvantages/header-background.jpg)

:rocket: lets get started

Does a web app need a database? Well, both yes and no. Everything depends on the type of the web app.

Databases aren’t a crucial element. You can build a web app without it. However, this would make it a very basic static website with limited functionality, static content, and lack of customer interaction.

If this doesn’t satisfy your requirements, then you need a web app with a database behind it


USAGE OF DATABASES:
- [ ] Static protoflio site
- [x] Webapp with authentication
- [x] Social media apps

<hr>

### What is a database used for?
==A database is integral to any dynamic website.==

When asking a user to register on your website or subscribe to your blog - their personal information lands in a database. 

For some website, lets say a portfolio, or a static webapp taht lacks user interatcions database are not so crucial!

but for others, like a social media web app, a database is crucial, since this web app completely relies on user-generated content. 

>Thousands of images and millions of text messages are generated daily - guess where they all land? Of course, in a **database**, where they are safe and ready to be pulled up at any time.[color=blue]

So, you now understand the true power of a database behind your web app. Now it’s time to review how it works!



# Comparison of the two types of databases
You can store your data in two ways:

**Structured**( SQL ) - organizing data into rows and columns. As a result, you have a table (or multiple interconnected tables) where all your data is organized and stored clearly.
:::info 
exampled of a well known SQL dbs: 
* PostgreSQL
  * One of the oldest relational databases, PostgreSQL is still on top. It’s reliable, robust and offers exceptional performance, which are the main reasons for its popularity.  

* MySQL
    * This popular relational database is used in various development stacks,  MySQL is a universal solution and is compatible with major platforms (Linux, Windows, Mac, BSD, and Solaris). Many tech giants, including Facebook, Twitter, Yahoo!, and YouTube have websites based on MySQL.
    
* MS SQL Server
    * An open-source Microsoft database is usually used as a part of the Windows environment. 
:::

**Document-like**( noneSQL ) - storing all data concerning a person/item in a single document(think like a JSON). This means you will have an array of documents, with all types of structured data.
:::info 
exampled of a well known NoneSQL dbs: 
* MongoDB -- The true leader on the market is an open source database MongoDB.

    * Entries are stored as a BSON document, (a modification of JSON). MongoDB powers Craigslist, eBay, Foursquare, and The New York Times websites among others. 
* DynamoDB

    * This is a popular Amazon Web Services product used for storing and processing data. DynamoDB is appreciated for built-in security (encryption of documents) and in-memory caching for faster interactions. Samsung, Netflix, and Lyft are among the prominent users of DynamoDB.
    
* Elasticsearch
    * Elasticsearch is a full-text search engine that is also often used as a non-relational database. The benefit of Elastic is the simplicity of its data architecture. Also, the response is much faster when compared to SQL databases.
:::

Depending on how you prefer to store your data, you’ll have to make a choice between database type: relational vs. non-relational database.

Basheer already explained how data is structured in a SQL db vs nonSQL db

so ill jump into concluding the adv bs disAdv: 

**obviously**,
A non-relational, or NoSQL database, works differently. It has to deal with semi-structured data. Each entry fits in a single JSON record. So, a NoSQL database looks like a folder with files rather than a table. 
![](https://clockwise.software/img/blog/relational-vs-non-relational-databases-advantages-and-disadvantages/table-02.jpg)

> **The obvious advantage of a non-relational database is the ability to store and process large amounts of unstructured data.** [color=purple]

**As a result**, it can process ==**ANY**== type of data without needing to modify the **WHOLE** architecture.

>So, creating and maintaining a NoSQL database is faster and cheaper.[color=green]

However, there are disadvantages as well.

>You’ll have to pay for this flexibility with extra processing efforts.[color=red] 

>Also, administration of a NoSQL database is more complicated.[color=red]

>> Due to an imprecise data structure, transferring records to strongly typed programming languages becomes a challenge.

When is non-relational database useful?
>Social media, analytics software - the more various data types the application has to handle, the more obvious the usage of a NoSQL database becomes.
[color=green]
>> this however is also open for a debate, a very interesting example that contradicts  this can be found in the **appropriately and conveniently** titled link below 
>> :::info 
>> :pushpin: [Why You Should Never Use MongoDB](http://www.sarahmei.com/blog/2013/11/11/why-you-should-never-use-mongodb/)
>> :::


# Conclusion
The choice between a relational and non-relational database may seem difficult, but actually, all you have to do is define your needs and analyze the advantages and disadvantages of both types.

If you work with well-structured, more or less constant data - an SQL database will be a better choice. It keeps your information organized and will save you storage space. However, if you have to handle various types of data, be ready for challenging database updates and maintenance.

Otherwise, you can decide to use a NoSQL database, which stores all available data as files. Yes, it is less structured, but it takes much less time to create and maintain such a database.

