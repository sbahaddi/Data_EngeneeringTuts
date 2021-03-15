# Data_EngeneeringTuts
Practice

An online retailer has a website where you can purchase widgets in a variety of colors. The website is backed by a relational database. Every transaction is stored in the database. How many blue widgets did the retailer sell in the last quarter?
To answer this question, you could run a SQL query on the database. This doesn't rise
to the level of needing a data engineer. But as the site grows, running queries on the production database is no longer practical. Furthermore, there may be more than one database that records transactions. There may be a database at different geographical locations – for example, the retailers in North America may have a different database than the retailers in Asia, Africa, and Europe.
Now you have entered the realm of data engineering. To answer the preceding question, a data engineer would create connections to all of the transactional databases for each region, extract the data, and load it into a data warehouse. From there, you could now count the number of all the blue widgets sold.
Rather than finding the number of blue widgets sold, companies would prefer to find the answer to the following questions:
    • How do we find out which locations sell the most widgets?
    • How do we find out the peak times for selling widgets?
    • How many users put widgets in their carts and remove them later?
    • How do we find out the combinations of widgets that are sold together?

Let's now answer the questions in the preceding list one by one:
    • Extract the data from each database.
    • Add a field to tag the location for each transaction in the data
    • Transform the date from local time to ISO 8601.
    • Load the data into the data warehouse.


The combination of extracting, loading, and transforming data is accomplished by the creation of a data pipeline. The data comes into the pipeline raw, or dirty in the sense that there may be missing data or typos in the data, which is then cleaned as it flows through the pipe. After that, it comes out the other side into a data warehouse, where it can be queried. The following diagram shows the pipeline required to accomplish the task:

<img src="img/1.1.png">