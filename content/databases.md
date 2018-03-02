## Questions about Databases

* How would you migrate an application from a database to another, for example from MySQL to PostgreSQL? If you had to manage that project, which issues would you expect to face?
* Why databases treat null as a so special case? For example, why in SQL ```SELECT * FROM table WHERE field = null``` does not match records with null ``field``?
* ACID is an acronym that refers to Atomicity, Consistency, Isolation and Durability, 4 properties guaranteed by a database transaction in most of the database engines. What do you know about this topic? Would you like to elaborate?
* How would you manage database schema migrations, that is, how would you automate the changes a database schema is affected to, as the application evolve, version after version?
* How is Lazy Loading achieved? When is it useful? What are its pitfalls?
* The so called "N + 1 problem" is an issue that occurs when the code needs to load the children of a parent-child relationship with a ORMs that have lazy-loading enabled, and that therefore issue a query for the parent record, and then one query for each child record. How to fix it?
* How would you find the most expensive queries in an application?
* In your opinion, is it always needed to use database normalization? When is it advisable to use denormalized databases?
* Of of the Continuous Integration's techniques is called Blue-Green Deployment: it consists in having two production environments, as identical as possible, and in performing the deployment in one of them while the other one is still operating, and than in safely switching the traffic to the second one after some convenient testing. This technique becomes more complicated when the deployment includes changes to the database structure or content. I'd like to discuss this topic with you.
