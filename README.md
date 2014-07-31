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
  1. [Questions about Software Lifecycle and Team Management](#management)
  1. [Questions about logic and algorithms](#algorithms)
  1. [Questions about Software Architecture](#architecture)
  1. [Open Questions](#open)
  1. [Questions based on snippets of code](#snippets)


####[[↑]](#toc) <a name='general'>General Questions:</a>

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
* What is the intent of the Null Object Pattern?
* Discuss the advantages of Composition over Inheritance
* What is an Anti-corruption Layer?


####[[↑]](#toc) <a name='languages'>Questions about Languages:</a>

* Why is there a rising interest about Functional Programming?
* What is a closure, and what is useful for?
* What are generics useful for? 
* What are high-order functions? What are they useful for? Write one, in your preferred language. 
* Write a loop, then transform it into a recursive function, avoiding mutability. Discuss. 
* What does it mean when a language treats functions as first-class citizens?


####[[↑]](#toc) <a name='databases'>Questions about Databases:</a>

* How would you manage the migration of a project from MySQL to PostgreSQL?
* Why in SQL ```SELECT * FROM table WHERE field = null``` does not match records with null ``field``?
* What's ACID (Atomicity, Consistency, Isolation, Durability)?
* How would you manage database schema migrations?
* How is Lazy Loading achieved? When is it useful? What are its pitfalls?
* What's the N+1 problem?


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
* How to manage Fault Tolerance in a Web application? And in a Desktop one? 
* What are the general pitfalls of Remote Procecure Call?


####[[↑]](#toc) <a name='management'>Questions about Software Lifecycle and Team Management:</a>

* What is agility?
* How would you deal with Legacy Code?
* What is Kanban?
* What is the biggest difference between Agile and Waterfall?
* Being a team manager, how would you deal with the problem of having too many meetings?


####[[↑]](#toc) <a name='algorithms'>Questions about logic and algorithms:</a>

* Make a FIFO Queue using only LIFO Stacks. Then build a LIFO Stack using only FIFO Queues.
* Write a snippet of code affected by a Stack Overflow 
* Write a tail-recursive version of the factorial function


####[[↑]](#toc) <a name='architecture'>Questions about Software Architecture:</a>

* What is CQRS (Command Query Responsibility Segregation)?
* What is Three-Tier architecture? 
* What are the pros and cons of MicroService architecture?


####[[↑]](#toc) <a name='open'>Open Questions:</a>
* What did you learn this week?
* List the last 5 books you read. 
* Why are Quora's answers better than Yahoo Answers' ones?
* Imagine there's a perfect clone of yourself. Imagine that that clone is your boss. Would you like to work for him/her?


####[[↑]](#snippets) <a name='open'>Questions about snippets of code:</a>
* What's the output of this Javascript function?
```
function hookupevents() {
  for (var i = 0; i < 3; i++) {
    document.getElementById("button" + i)
      .addEventListener("click", function() { 
        alert(i); 
      });
  }
}
```

