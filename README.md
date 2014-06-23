Back-End Developer Interview Questions
======================================

This repo contains a number of back-end interview questions that can be used when vetting potential candidates. It is by no means recommended to use every single question here on the same candidate (that would take hours). Choosing a few items from this list should help you vet the intended skills you require.

This project is admittedly inspired by [Front-end Job Interview Questions](https://github.com/darcyclarke/Front-end-Developer-Interview-Questions) by [@darcyclarke](https://github.com/darcyclarke)

**Note:** Keep in mind that many of these questions are open ended and could lead to interesting discussions that tell you more about the person's capabilities than a straight answer would.


## <a name='toc'>Table of Contents</a>

  1. [General Questions](#general)
  1. [Patterns Questions](#patterns)
  1. [Languages Questions](#languages)
  1. [Databases Questions](#databases)
  1. [NoSQL Questions](#nosql)
  1. [Code Revision Questions](#coderevision)
  1. [Concurrency Questions](#concurrency)

####[[↑]](#toc) <a name='general'>General Questions:</a>

* What did you learn yesterday/this week?
* Why Functional Programming matters?
* What is Encapsulation important for?
* What is a real-time system and how is it different from an ordinary system?
* What's the relationship between real-time languages and heap memory allocation?
* Immutability is the practice of setting values once, at the moment of their creation, and never changing them. How immutability can help writing safer code?
* Pro and cons of mutable and unmutable values.
* What's the Object-Relational impedence mismatch?

####[[↑]](#toc) <a name='patterns'>Questions about Patterns:</a>

* Tell me about the Hollywood Principle.
* About the Law of Demeter (the Principle of Least Knowledge): write a code violating it, then fix it.
* Which are the limits and pitfalls of Active-Record?


####[[↑]](#toc) <a name='languages'>Questions about Languages:</a>

* Why is there a rising interest about Functional Programming?
* What is a closure, and what is useful for?
* What are generics useful for? 
* What are high-order functions? What are they useful for? Write one, in your preferred language. 


####[[↑]](#toc) <a name='databases'>Questions about Databases:</a>

* How would you manage the migration of a project from MySQL to PostgreSQL?
* Why in SQL ```SELECT * FROM table WHERE field = null``` does not match records with null ``field``?
* What's ACID (Atomicity, Consistency, Isolation, Durability)?


####[[↑]](#toc) <a name='nosql'>Questions about NoSQL:</a>
* What is Eventual Consistency?


####[[↑]](#toc) <a name='coderevision'>Questions about code revision:</a>

* Why branching with Mercurial or git is easier than with SVN?
* What are the pros and cons of Distributed Version Control Systems like git over Centralized ones like SVN?
* Could you describe GitHubFLow and GitFlow workflows?
* What's a rebase?
* Why merges are easier with Mercurial and git than with SVN and CVS?


####[[↑]](#toc) <a name='concurrency'>Questions about Concurrency:</a>
* What is a Race Condition?
* What is a Deadlock?
* What is Process Starvation?
* What is a Wait Free algorithm?
* In which case whould you apply asynchronously communication between two systems?
* If you are building a distributed system for scalability and robustness, what are the different things you'd think of in the case you are working in a closed and secure network environment or in geographically distributed and public system?
