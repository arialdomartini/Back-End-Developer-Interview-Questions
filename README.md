Back-End Developer Interview Questions
======================================

This page has been translated to [Chinese](https://github.com/monklof/Back-End-Developer-Interview-Questions) by [monklof](https://github.com/monklof).

I started writing down this list as a personal reminder of topics I had the chance to discuss with colleagues and friends, and that I wanted to deepen...

I'm not a big fan of asking technical questions in job interviews: I rather prefer to sit together with candidates in front of some real code, hands on the keyboard, facing a real problem, and have a full day of pair programming, hopefully rotating with all the other team members. Yet, I feel some technical questions could be a good starting point to begin an engaging and nice conversation, and this can be useful to get a deeper knowledge of each others.

This repo collects a number of back end related questions that can be used when vetting potential candidates. It is by no means recommended to use every single question on the same candidate: that would take hours, and would have no sense at all, as they cover a too broad set of topics for a single developer's to possibly know. Browse the section you find more relevant for your context, and pick the questions that give you more ideas on the conversation to have.

### Notice
Most of the questions are open-ended, and some of them just don't have a *right* or a *wrong* answer. On the contrary, they are intended to be used as the starting point for a conversation that hopefully tells you more about the person's capabilities than a straight answer would. Personally, I would even choose the questions whose answers are not yet clear to me.

Again, I stress that just asking questions is hardly sufficient. Complete the interview with a long pair programming session with your candidates: it is one of the best opportunities to know each others' style and approach and to let candidates know some details about their future day job.

This project is admittedly inspired by [Front-end Job Interview Questions](https://github.com/darcyclarke/Front-end-Developer-Interview-Questions) by [@darcyclarke](https://github.com/darcyclarke)



### Where are the answers?

Sooner or later I will complete it with the relative answers. Feel free to contribute, it would be highly appreciated!


## <a name='toc'>Table of Contents</a>

  1. [Questions about Design Patterns](#patterns)
  1. [Questions about Code Design](#design)
  1. [Questions about languages](#languages)
  1. [Web Questions](#web)
  1. [Databases Questions](#databases)
  1. [NoSQL Questions](#nosql)
  1. [Code Versioning Questions](#codeversioning)
  1. [Concurrency Questions](#concurrency)
  1. [Questions about Distributed Systems](#distributed)
  1. [Questions about Software Lifecycle and Team Management](#management)
  1. [Questions about logic and algorithms](#algorithms)
  1. [Questions about Software Architecture](#architecture)
  1. [Questions about Service Oriented Architecture and Microservices](#soa)
  1. [Questions about Security](#security)
  1. [General Questions](#general)
  1. [Open Questions](#open)
  1. [Questions based on snippets of code](#snippets)
  1. [Bill Gates Style Questions](#billgates)



### [[↑]](#toc) <a name='patterns'>Questions about Design Patterns:</a>

* Why are global and static objects evil? Can you show it with a code example? [Answer](#why-are-global-and-static-objects-evil-can-you-show-it-with-a-code-example)
* Tell me about Inversion of Control and how it improves the design of code. [Answer](#tell-me-about-inversion-of-control-and-how-it-improves-the-design-of-code)
* The Law of Demeter (the Principle of Least Knowledge) states that each unit should have only limited knowledge about other units and it should only talk to its immediate friends (sometimes stated as "don't talk to strangers"). Would you write code violating this principle, show why it is a bad design and then fix it? [Answer](#user-content-the-law-of-demeter-the-principle-of-least-knowledge-states-that-each-unit-should-have-only-limited-knowledge-about-other-units-and-it-should-only-talk-to-its-immediate-friends-sometimes-stated-as-dont-talk-to-strangers-would-you-write-code-violating-this-principle-show-why-it-is-a-bad-design-and-then-fix-it)
* Active-Record is the design pattern that promotes objects to include functions such as Insert, Update, and Delete, and properties that correspond to the columns in some underlying database table. In your opinion and experience, which are the limits and pitfalls of the this pattern? [Answer](#active-record-is-the-design-pattern-that-promotes-objects-to-include-functions-such-as-insert-update-and-delete-and-properties-that-correspond-to-the-columns-in-some-underlying-database-table-in-your-opinion-and-experience-which-are-the-limits-and-pitfalls-of-the-this-pattern)
* Data-Mapper is a design pattern that promotes the use of a layer of Mappers that moves data between objects and a database while keeping them independent of each other and the mapper itself. On the contrary, in Active-Record objects directly incorporate operations for persisting themselves to a database, and properties corresponding to the underlying database tables. Do you have an opinion on those patterns? When would you use one instead of the other? [Answer](#data-mapper-is-a-design-pattern-that-promotes-the-use-of-a-layer-of-mappers-that-moves-data-between-objects-and-a-database-while-keeping-them-independent-of-each-other-and-the-mapper-itself-on-the-contrary-in-active-record-objects-directly-incorporate-operations-for-persisting-themselves-to-a-database-and-properties-corresponding-to-the-underlying-database-tables-do-you-have-an-opinion-on-those-patterns-when-would-you-use-one-instead-of-the-other)
* Why is it often said that the introduction of `null` is a "billion dollar mistake"? Would you discuss the techniques to avoid it, such as the Null Object Pattern introduced by the GOF book, or Option types? [Answer](#why-is-it-often-said-that-the-introduction-of-null-is-a-billion-dollar-mistake-would-you-discuss-the-techniques-to-avoid-it-such-as-the-null-object-pattern-introduced-by-the-gof-book-or-option-types)
* Many state that, in Object-Oriented Programming, composition is often a better option than inheritance. What's you opinion? [Answer](#many-state-that-in-object-oriented-programming-composition-is-often-a-better-option-than-inheritance-whats-you-opinion)
* What is an Anti-corruption Layer? [Answer](#what-is-an-anti-corruption-layer)
* Singleton is a design pattern that restricts the instantiation of a class to one single object. Writing a Thread-Safe Singleton class is not so obvious. Would you try?
* The ability to change implementation without affecting clients is called Data Abstraction. Produce an example violating this property, then fix it. [Answer](#the-ability-to-change-implementation-without-affecting-clients-is-called-data-abstraction-produce-an-example-violating-this-property-then-fix-it)
* Write a snippet of code violating the Don't Repeat Yourself (DRY) principle. Then, fix it. [Answer](#write-a-snippet-of-code-violating-the-dont-repeat-yourself-dry-principle-then-fix-it)
* How would you deal with Dependency Hell? [Answer](#how-would-you-deal-with-dependency-hell)
* Is goto evil? You may have heard of the famous paper "Go To Statement Considered Harmful" by Edsger Dijkstra, in which he criticized the use of the `goto` statement and advocated structured programming instead. The use of `goto` has always been controversial, so much that even Dijkstra's letter was criticized with articles such as "'GOTO Considered Harmful' Considered Harmful". What's your opinion on the use of `goto`? [Answer](#is-goto-evil-you-may-have-heard-of-the-famous-paper-go-to-statement-considered-harmful-by-edsger-dijkstra-in-which-he-criticized-the-use-of-the-goto-statement-and-advocated-structured-programming-instead-the-use-of-goto-has-always-been-controversial-so-much-that-even-dijkstras-letter-was-criticized-with-articles-such-as-goto-considered-harmful-considered-harmful-whats-your-opinion-on-the-use-of-goto)
* The robustness principle is a general design guideline for software that recommends "*be conservative in what you send, be liberal in what you accept*". It is often reworded as "*be a tolerant reader and a careful writer*". Would you like to discuss the rationale of this principle?
* Separation of Concerns is a design principle for separating a computer program into distinct areas, each one addressing a separate concern. There are a lot of different mechanisms for achieving Separation of Concerns (use of objects, functions, modules, or patterns such as MVC and the like). Would you discuss this topic?


### [[↑]](#toc) <a name='design'>Questions about Code Design:</a>

* It is often said that one of the most important goals in Object-Oriented Design (and code design in general) is to have High Cohesion and Loose Coupling. What does it mean? Why is it that important and how is it achieved?
* Why do array indexes start with '0' in most languages?
* How do tests and TDD influence code design?
* Write a snippet of code violating the Don't Repeat Yourself (DRY) principle. Then, explain why it is a bad design, and fix it.
* What's the difference between cohesion and coupling?
* What is refactoring useful for?
* Are comments in code useful? Some say they should be avoided as much as possible, and hopefully made unnecessary. Do you agree?
* What is the difference between design and architecture?
* In TDD, why are tests written before code?
* C++ supports multiple inheritance, and Java allows a class to implement multiple interfaces. What impact does using these facilities have on orthogonality? Is there a difference in impact between using multiple inheritance and multiple interfaces? Is there a difference between using delegation and using inheritance? [This question is from The Pragmatic Programmer, by Andrew Hunt and David Thomas]
* What are the pros and cons of holding domain logic in Stored Procedures?
* In your opinion, why has Object-Oriented Design dominated the market for so many years?
* What would you do to understand if your code has a bad design?


### [[↑]](#toc) <a name='languages'>Questions about Languages:</a>

* Tell me the 3 worst defects of your preferred language
* Why is there a rising interest on Functional Programming?
* What is a closure, and what is useful for? What's in common between closures and classes?
* What are generics useful for?
* What are higher-order functions? What are they useful for? Write one, in your preferred language.
* Write a loop, then transform it into a recursive function, using only immutable structures (i.e. avoid using variables). Discuss.
* What does it mean when a language treats functions as first-class citizens?
* Show me an example where an anonymous function can be useful.
* There are a lot of different type systems. Let's talk about static and dynamic type systems, and about strong and weak ones. You surely have an opinion and a preference about this topic. Would you like to share them, and discuss why and when would you promote one particular type system for developing an enterprise software?
* What are namespaces useful for? Invent an alternative.
* Talk about interoperability between Java and C# (in alternative, choose 2 other arbitrary languages)
* Why do many software engineers not like Java?
* What makes a good language good and a bad language bad?
* Write two functions, one referentially transparent and the other one referentially opaque. Discuss.
* What is a stack and what is a heap? What's a stack overflow?
* Why is it important that in a language functions are first class citizens?
* Some languages, especially the ones that promote a functional approach, allow a technique called pattern matching. Do you know it? How is pattern matching different from switch clauses?
* Why do some languages have no exceptions by design? What are the pros and cons?
* If `Cat` is an `Animal`, is `TakeCare<Cat>` a `TakeCare<Animal>`?
* In Java, C# and many other languages, why are constructors not part of the interface?
* In the last years there has been a lot of hype around Node.js. What's your opinion on using a language that was initially conceived to run in the browser in the backend?
* Pretend you have a time machine and pretend that you have the opportunity to go to a particular point in time during Java's (or C#, Python, Go or whatever) history, and talk with some of the JDK architects. What would you try to convince them of? Removing checked exceptions? Adding unsigned primitives? Adding multiple-inheritance?



### [[↑]](#toc) <a name='web'>Questions about Web development:</a>
* Why are first-party cookies and third-party cookies treated so differently?
* How would you manage Web Services API versioning?
* From a backend perspective, are there any disadvantages or drawbacks on the adoption of Single Page Applications?
* Why do we usually put so much effort for having stateless services? What's so good in stateless code and why and when is statefulness bad?
* REST and SOAP: when would you choose one, and when the other?
* In web development, Model-View Controller and Model-View-View-Model approaches are very common, both in the backend and in the frontend. What are they, and why are they advisable?


### [[↑]](#toc) <a name='databases'>Questions about Databases:</a>

* How would you migrate an application from a database to another, for example from MySQL to PostgreSQL? If you had to manage that project, which issues would you expect to face? [Answer](#how-would-you-migrate-an-application-from-a-database-to-another-for-example-from-mysql-to-postgresql-if-you-had-to-manage-that-project-which-issues-would-you-expect-to-face)
* Why do databases treat null as a so special case? For example, why does ```SELECT * FROM table WHERE field = null``` not match records with null ``field`` in SQL? [Answer](#why-do-databases-treat-null-as-a-so-special-case-for-example-why-does-select--from-table-where-field--null-not-match-records-with-null-field-in-sql)
* ACID is an acronym that refers to Atomicity, Consistency, Isolation and Durability, 4 properties guaranteed by a database transaction in most database engines. What do you know about this topic? Would you like to elaborate? [Answer](#acid-is-an-acronym-that-refers-to-atomicity-consistency-isolation-and-durability-4-properties-guaranteed-by-a-database-transaction-in-most-database-engines-what-do-you-know-about-this-topic-would-you-like-to-elaborate)
* How would you manage database schema migrations? That is, how would you automate changes to database schema, as the application evolves, version after version? [Answer](#how-would-you-manage-database-schema-migrations-that-is-how-would-you-automate-changes-to-database-schema-as-the-application-evolves-version-after-version)
* How is lazy loading achieved? When is it useful? What are its pitfalls? [Answer](#how-is-lazy-loading-achieved-when-is-it-useful-what-are-its-pitfalls)
* The so called "N + 1 problem" is an issue that occurs when code needs to load the children of a parent-child relationship with a ORMs that have lazy-loading enabled, and that therefore issue a query for the parent record, and then one query for each child record. How to fix it? [Answer](#the-so-called-n--1-problem-is-an-issue-that-occurs-when-code-needs-to-load-the-children-of-a-parent-child-relationship-with-a-orms-that-have-lazy-loading-enabled-and-that-therefore-issue-a-query-for-the-parent-record-and-then-one-query-for-each-child-record-how-to-fix-it)
* How would you find the most expensive queries in an application? [Answer](#how-would-you-find-the-most-expensive-queries-in-an-application)
* In your opinion, is it always needed to use database normalization? When is it advisable to use denormalized databases? [Answer](#in-your-opinion-is-it-always-needed-to-use-database-normalization-when-is-it-advisable-to-use-denormalized-databases)
* Of of the Continuous Integration's techniques is called Blue-Green Deployment: it consists in having two production environments, as identical as possible, and in performing the deployment in one of them while the other one is still operating, and than in safely switching the traffic to the second one after some convenient testing. This technique becomes more complicated when the deployment includes changes to the database structure or content. I'd like to discuss this topic with you. [Answer](#of-of-the-continuous-integrations-techniques-is-called-blue-green-deployment-it-consists-in-having-two-production-environments-as-identical-as-possible-and-in-performing-the-deployment-in-one-of-them-while-the-other-one-is-still-operating-and-than-in-safely-switching-the-traffic-to-the-second-one-after-some-convenient-testing-this-technique-becomes-more-complicated-when-the-deployment-includes-changes-to-the-database-structure-or-content-id-like-to-discuss-this-topic-with-you)


### [[↑]](#toc) <a name='nosql'>Questions about NoSQL:</a>

* What is eventual consistency?
* Brewer's Theorem, most commonly known as the CAP theorem, states that in the presence of a network partition (the P in CAP), a system's designer has to choose between consistency (the C in CAP) and availability (the A in CAP). Can you think about examples of CP, AP and CA systems?
* How would you explain the recent rise in interest in NoSQL?
* How does NoSQL tackle scalability challenges?
* When would you use a document database like MongoDB instead of a relational database like MySQL or PostgreSQL?


### [[↑]](#toc) <a name='codeversioning'>Questions about code versioning:</a>

* Why is branching with Mercurial or git easier than with SVN?
* What are the pros and cons of distributed version control systems like Git over centralized ones like SVN?
* Could you describe GitHub Flow and GitFlow workflows?
* What's a rebase?
* Why are merges easier with Mercurial and Git than with SVN and CVS?


### [[↑]](#toc) <a name='concurrency'>Questions about Concurrency:</a>

* Why do we need concurrency, anyway? Explain.
* Why is testing multithreaded/concurrent code so difficult?
* What is a race condition? Code an example, using whatever language you like.
* What is a deadlock? Would you be able to write some code that is affected by deadlocks?
* What is process starvation? If you need, let's review its definition.
* What is a wait free algorithm?


### [[↑]](#toc) <a name='distributed'>Questions about Distributed Systems:</a>

* How would you test a distributed system?
* When would you apply asynchronous communication between two systems?
* What are the general pitfalls of remote procedure calls?
* If you are building a distributed system for scalability and robustness, what are the different things you'd think of if you are working in a closed and secure network environment versus when you are working in a geographically distributed and public system?
* How would you manage fault tolerance in a web application? What about in a desktop one?
* How would you deal with failures in a distributed system?
* Let's talk about the several approaches to reconciliation after network partitions.
* What are the fallacies of distributed computing?
* When would you use request/reply and when publish/subscribe?
* Suppose the system you are working on does not support transactionality. How would you implement it from scratch?


### [[↑]](#toc) <a name='management'>Questions about Software Lifecycle and Team Management:</a>

* What is agility?
* How would you deal with legacy code?
* Say I'm your project manager, and I'm no expert in programming. Would you try explaining to me what legacy code is and why should I care about code quality?
* I'm the CEO of your company. Explain to me Kanban and convince me to invest in it.
* What is the biggest difference between Agile and Waterfall?
* Being a team manager, how would you deal with the problem of having too many meetings?
* How would you manage a very late project?
* "*Individuals and interactions over processes and tools*" and "*Customer collaboration over contract negotiation*" comprise half of the values of the Agile Manifesto. Discuss
* Tell me what decisions would you take if you could be the CTO of your Company.
* Are program managers useful?
* Organize a development team using flexible schedules (that is, no imposed working hours) and "take as you need" vacation policy
* How would you manage a very high turn over and convince developers not to leave the team, without increasing compensation? What could a company improve to make them stay?
* What are the top 3 qualities you look for in colleagues, beyond their code?
* What are the top 3 things you wish non-technical people knew about code?
* Imagine your company gives you 1 month and some budget to improve your and your colleagues' daily life. What would you do?


### [[↑]](#toc) <a name='algorithms'>Questions about logic and algorithms:</a>

* Make a FIFO queue using only LIFO stacks. Then build a LIFO stack using only FIFO queues.
* Write a snippet of code affected by a stack overflow.
* Write a tail-recursive version of the factorial function.
* Using your preferred language, write a REPL that echoes your inputs. Evolve it to make it an RPN calculator.
* How would you design a "defragger" utility?
* Write a program that builds random mazes.
* Write a sample program that produces a memory leak.
* Generate a sequence of unique random numbers.
* Write a simple garbage collection system.
* Write a basic message broker, using whatever language you like.
* Write a very basic web server. Draw a road map for features to be implemented in the future.
* How would you sort a 10GB file? How would your approach change with a 10TB one?
* How would you programmatically detect file duplicates?


### [[↑]](#toc) <a name='architecture'>Questions about Software Architecture:</a>

* When is a cache not useful or even dangerous?
* Why does Event-Driven Architecture improve scalability?
* What makes code readable?
* What is the difference between emergent design and evolutionary architecture?
* Scale out vs scale up: how are they different? When to apply one, when the other?
* How to deal with failover and user sessions?
* What is CQRS (Command Query Responsibility Segregation)? How is it different from the oldest Command-Query Separation Principle?
* The so called "multitier architecture" is an approach to design a client–server system aimed to keep physically and logically separated presentation, application processing, data management and other functions. The most widespread of the multitier architectures is the three-tier architecture. Would you discuss the pros and cons of such an approach?
* How would you design a software system for scalability?
* Someone gave the name "The "C10k problem" to the problem of optimising network sockets to handle over 10.000 open connections at once. While handling 10.000 concurrent clients is not the same as handling 10.000 open connection, the context is similar. It's a tough challenge anyway, and no one is expected to know every single detail to solve it. It may be interesting to discuss the strategies you know to deal with that problem. Would you like to try?
* How would you design a decentralized (that is, with no central server) P2P system?
* You may recall that Common Gateway Interface (CGI) is a standard protocol for web servers to execute programs (CGI scripts) that execute as Command-line programs on a server, and that dynamically generate HTML pages when invoked by a HTTP request. Perl and PHP used to be common languages for such scripts. In CGI, a HTTP request generally causes the invocation of a new process on the server, but FastCGI, SCGI and other approaches improved the mechanism, raising the performance, with techniques such as preforking processes. Can you discuss why CGI became obsolete, and was instead replaced with other architectural approaches?
* How would you defend the design of your systems against vendor Lock-in?
* What are the disadvantages of the publish-subscribe pattern at scale?
* What's new in CPUs since the 80s, and how does it affect programming?
* In which part of the lifecycle of a software performance should be taken in consideration, and how?
* How could a denial of service arise not maliciously but due to a design or architectural problem?
* What’s the relationship between performance and scalability?
* When is it OK (if ever) to use tight coupling?
* What characteristic should a system have to be cloud ready?
* Does unity of design imply an aristocracy of architects? Putting it simple: can good design emerge from a collective effort of all developers?
* What's the difference between design, architecture, functionality and aesthetic? Discuss.



### [[↑]](#toc) <a name='soa'>Questions about Service Oriented Architecture and Microservices:</a>
* Why, in a SOA, long-lived transactions are discouraged and sagas are suggested instead?
* What are the differences between SOA and microservice?
* Let's talk about web services versioning, version compatibility and breaking changes.
* What's the difference between a transaction and a compensation operation in a saga, in SOA?
* When is a microservice too micro?
* What are the pros and cons of microservice architecture?


### [[↑]](#toc) <a name='security'>Questions about Security:</a>
* How do you write secure code? In your opinion, is it one of the developer's duties, or does it require a specialized role in the company? And why?
* Why is it said that cryptography is not something you should try to invent or design yourself?
* What is two factor authentication? How would you implement it in an existing web application?
* If not carefully handled, there is always a risk of logs containing sensitive information, such as passwords. How would you deal with this?
* Write down a snippet of code affected by SQL injection and fix it.
* How would it be possible to detect SQL injection via static code analysis? I don't expect you to write an algorithm capable of doing this, as it is probably a huge topic, but let's discuss a general approach.
* What do you know about Cross-Site Scripting? If you don't remember it, let's review online its definition and let's discuss about it.
* What do you know about Cross-Site Forgery Attack? If you don't remember it, let's review online its definition and let's discuss about it.
* How does HTTPS work?
* What's a man-in-the-middle Attack, and why does HTTPS help protect against it?
* How can you prevent the user's session from being stolen? Chances are you remember what session or cookie hijacking is, otherwise let's read its Wikipedia page together.


### [[↑]](#toc) <a name='general'>General Questions:</a>

* Why does functional programming matter? When should a functional programming language be used?
* How do companies like Microsoft, Google, Opera and Mozilla profit from their browsers?
* Why does opening a TCP socket have a large overhead?
* What is encapsulation important for?
* What is a real-time system and how is it different from an ordinary system?
* What's the relationship between real-time languages and heap memory allocation?
* Immutability is the practice of setting values once, at the moment of their creation, and never changing them. How can immutability help write safer code?
* What are the pros and cons of mutable and immutable values.
* What's the Object-Relational impedance mismatch?
* Which principles would you apply to define the size of a cache?
* What's the difference between TCP and HTTP?
* What are the tradeoffs of client-side rendering vs. server-side rendering?
* How could you develop a reliable communication protocol based on a non-reliable one?
* [Tony Hoare](https://en.m.wikipedia.org/wiki/Tony_Hoare) who invented the null reference once said "*I call it my billion-dollar mistake*" since it led to "*innumerable errors, vulnerabilities, and system crashes, which have probably caused a billion dollars of pain and damage in the last forty years*". Imagine you want to remove the possibility to have null references in your preferred language: how would you achieve this goal? What consequences could this have?


### [[↑]](#toc) <a name='open'>Open Questions:</a>
* Why do people resist change?
* Explain threads to your grandparents
* As a software engineer you want both to innovate and to be predictable. How those two goals can coexist in the same strategy?
* What makes good code good?
* Explain streaming and how you would implement it.
* Say your company gives you one week you can use to improve your and your colleagues' lifes: how would you use that week?
* What did you learn this week?
* There is an aesthetic element to all design. The question is, is this aesthetic element your friend or your enemy?
* List the last 5 books you read.
* How would you introduce Continuous Delivery in a successful, huge company for which the change from Waterfall to Continuous Delivery would be not trivial, because of the size and complexity of the business?
* When does it make sense to reinvent the wheel?
* Let's have a conversation about "*reinventing the wheel*", the "*not invented here syndrome*" and the "*eating your own food*" practice
* What's the next thing you would automate in your current workflow?
* Why is writing software difficult? What makes maintaining software hard?
* Would you prefer working on green field or brown field projects? Why?
* [What happens when you type google.com into your browser and press enter?](https://github.com/alex/what-happens-when)
* What does an operating system do when it has got no custom code to run, and therefore it looks idle? I would like to start a discussions about interrupts, daemons, background services, polling, event handling and so on.
* Explain Unicode and database transactions to a 5 year old child.
* Defend the monolithic architecture.
* What does it mean to be a "professional developer"?
* Is developing software an art, a craftsmanship or an engineering endeavour? Your opinion.
* "People who like this also like... ". How would you implement this feature in an e-commerce shop?
* Why are corporations slower than startups in innovating?
* What have you achieved recently that you are proud of?



### [[↑]](#toc) <a name='snippets'>Questions about snippets of code:</a>
* What's the output of this Javascript function?
```javascript
function hookupevents() {
  for (var i = 0; i < 3; i++) {
    document.getElementById("button" + i)
      .addEventListener("click", function() {
        alert(i);
      });
  }
}
```

* About Type Erasure, what's the output of this Java snippet, and why?
```java
ArrayList<Integer> li = new ArrayList<Integer>();
ArrayList<Float> lf = new ArrayList<Float>();
if (li.getClass() == lf.getClass()) // evaluates to true
  System.out.println("Equal");
```


* Can you spot the memory leak?
```java
public class Stack {
    private Object[] elements;
    private int size = 0;
    private static final int DEFAULT_INITIAL_CAPACITY = 16;

    public Stack() {
        elements = new Object[DEFAULT_INITIAL_CAPACITY];
    }

    public void push(Object e) {
        ensureCapacity();
        elements[size++] = e;
    }

    public Object pop() {
        if (size == 0)
            throw new EmptyStackException();
        return elements[--size];
    }

    /**
     * Ensure space for at least one more element, roughly
     * doubling the capacity each time the array needs to grow.
     */
    private void ensureCapacity() {
        if (elements.length == size)
            elements = Arrays.copyOf(elements, 2 * size + 1);
    }
}
```

* `if`s and in general conditional statements lead to procedural and imperative programming. Can you get rid of this `switch` and make this snippet more object oriented?

```java
public class Formatter {

    private Service service;

    public Formatter(Service service) {
        this.service = service;
    }

    public String doTheJob(String theInput) {
        String response = service.askForPermission();
        switch (response) {
        case "FAIL":
            return "error";
        case "OK":
            return String.format("%s%s", theInput, theInput);
        default:
            return null;
        }
    }
}
```


* Can you get rid of these `if`s and make this snippet of code more object oriented?

```java
public class TheService {
    private final FileHandler fileHandler;
    private final FooRepository fooRepository;

    public TheService(FileHandler fileHandler, FooRepository fooRepository) {
        this.fileHandler = fileHandler;
        this.fooRepository = fooRepository;
    }

    public String Execute(final String file) {

        final String rewrittenUrl = fileHandler.getXmlFileFromFileName(file);
        final String executionId = fileHandler.getExecutionIdFromFileName(file);

        if (executionId.equals("") || rewrittenUrl.equals("")) {
            return "";
        }

        Foo knownFoo = fooRepository.getFooByXmlFileName(rewrittenUrl);

        if (knownFoo == null) {
            return "";
        }

        return knownFoo.DoThat(file);
    }
}
```

* How would you refactor this code?

```js
function()
{
    HRESULT error = S_OK;

    if(SUCCEEDED(Operation1()))
    {
        if(SUCCEEDED(Operation2()))
        {
            if(SUCCEEDED(Operation3()))
            {
                if(SUCCEEDED(Operation4()))
                {
                }
                else
                {
                    error = OPERATION4FAILED;
                }
            }
            else
            {
                error = OPERATION3FAILED;
            }
        }
        else
        {
            error = OPERATION2FAILED;
        }
    }
    else
    {
        error = OPERATION1FAILED;
    }

    return error;
}
```

* Answer :

```js
function()
{
    HRESULT error = S_OK;

    if( !SUCCEEDED(Operation1() ) return OPERATION1FAILED;
    if( !SUCCEEDED(Operation2() ) return OPERATION2FAILED;
    if( !SUCCEEDED(Operation3() ) return OPERATION3FAILED;
    if( !SUCCEEDED(Operation3() ) return OPERATION3FAILED;
    if( !SUCCEEDED(Operation4() ) return OPERATION4FAILED;

}
```

### [[↑]](#toc) <a name='billgates'>Bill Gates Style Questions:</a>
This section collects some weird questions along the lines of the [Manhole Cover Question](https://en.wikipedia.org/wiki/Microsoft_interview#Manhole_cover_question).

* What would happen if you put a mirror in a scanner?
* Imagine there's a perfect clone of yourself. Imagine that that clone is your boss. Would you like to work for him/her?
* Interview me.
* Why are Quora's answers better than Yahoo Answers' ones?
* Let's play a game: defend Cobol against modern languages, and try to find as many reasonable arguments as you can.
* Where will you be in 10 years?
* You are my boss and I'm fired. Inform me.
* I want to refactor a legacy system. You want to rewrite it from scratch. Argument. Then, switch our roles.
* Your boss asks you to lie to the company. What's your reaction?
* If you could travel back in time, which advice would you give to your younger self?


---


### Why are global and static objects evil? Can you show it with a code example?

1. Global and static objects causes implicit dependencies/coupling, thus breaks the idea of encapsulation.
2. It's hard to reason about them - logical scope for understanding behaviour of these objects is expanded to the whole program.
3. It's Hard to mock/stub them.
4. Global objects pollutes the main scope.

Bad:
```javascript
class Player {
    walk() {
        this.x = nextDestination.x;
        this.y = nextDestination.y;
    }
}
```

Good:
```javascript
class Player {
    walk(destination) {
        this.x = destination.x;
        this.y = destination.y;
    }
}
```
<br>[⬆ Back to top](#table-of-contents)

### Tell me about Inversion of Control and how it improves the design of code.

Inversion of Control is a pattern in which we reverse the relation of the code execution: we don't call the external code, external code calls our code.
E.g. when working we libraries, we usually import some module and call functions from that module. When working with frameworks, our custom code 
is called by the framework code. This is also known as the Hollywood Principle - "Don't call us, we'll call you".
It may help keeping single responsibility of the specific classes and design more concise API's.
<br>[⬆ Back to top](#table-of-contents)

### The Law of Demeter (the Principle of Least Knowledge) states that each unit should have only limited knowledge about other units and it should only talk to its immediate friends (sometimes stated as "don't talk to strangers"). Would you write code violating this principle, show why it is a bad design and then fix it?

Code violating The Law of Demeter:
```javascript
class Plane {
    constructor(crew) {
        this.crew = crew;
    }
    
    getPilotsName() {
        this.crew.pilot.getName();
    }
}

class Crew {
    constructor(pilot) {
        this.pilot = pilot;
    }
}

class Pilot {
    getName() {
        // ...
    }
}
```
It's bad, because it creates tight coupling between objects - they are dependent on internal structure of other objects.

Fixed code:
```javascript
class Plane {
    getPilotsName() {
        this.crew.getPilotsName();
    }
}

class Crew {
    constructor(pilot) {
        this.pilot = pilot;
    }

    getPilotsName() {
        return this.pilot.getName();
    }
}
```
<br>[⬆ Back to top](#table-of-contents)

### What is an Anti-corruption Layer?
    
It's a layer in the system which is responsible for communication between subsystems (most likely with the external or legacy system) which don't operate on the same models.
Its purpose is to create an isolating layer which provides clients with functionality in terms of their own domain model.
### The so called "N + 1 problem" is an issue that occurs when code needs to load the children of a parent-child relationship with a ORMs that have lazy-loading enabled, and that therefore issue a query for the parent record, and then one query for each child record. How to fix it?

It depends on the ORM engine, but generally, the fix is to use `JOIN` query. In hibernate it's e.g. `join fetch` which results in `INNER JOIN` SQL query.

<br>[⬆ Back to top](#table-of-contents)

### The ability to change implementation without affecting clients is called Data Abstraction. Produce an example violating this property, then fix it.
### How would you find the most expensive queries in an application?

Data Abstraction violation:
```javascript
class Book {
    constructor(pages) {
        this.pages = pages;
    }
}

const myBook = new Book([{ text: 'content of the title page'}, { text: '...'}]);
const titlePage = myBook.pages[0];
```
I worked mainly with mySql database. It provides a tool for monitoring slow queries. All You have to do is enabling logging slow queries into the specified file. You can also specify the minimum time threshold.
Additionally, if app is deployed to the cloud, probably there is an option to setup an email notifications which will notify you if those queries were executed.

<br>[⬆ Back to top](#table-of-contents)

### In your opinion, is it always needed to use database normalization? When is it advisable to use denormalized databases?

I think that database denormalization is needed only if we need to improve the performance of our queries, and the other optimizations (indexing, sql views) are not enough.
We need to remember that the cost of database denormalization is to build and maintain tools for keeping our data consistent (e.g. crons).

<br>[⬆ Back to top](#table-of-contents)

Fixed:
```javascript
class Book {
    constructor(title, pages) {
        this.title = title;
### Of of the Continuous Integration's techniques is called Blue-Green Deployment: it consists in having two production environments, as identical as possible, and in performing the deployment in one of them while the other one is still operating, and than in safely switching the traffic to the second one after some convenient testing. This technique becomes more complicated when the deployment includes changes to the database structure or content. I'd like to discuss this topic with you.

This is the most tricky part of the Blue-Green Deployment. The common solution for this case is to have an intermediate release, with database schema which will be supported by both previous and the next release.
With this approach, we still have all the benefits of the Blue-Green Deployment, including quick revert. The cost is an overhead with the intermediate release.

        this.pages = pages;
    }

    getTitlePage() {
        return this.pages[0];
    }   
}

const myBook = new Book([{ text: 'content of the title page'}, { text: '...'}]);
const titlePage = myBook.getTitlePage();
```
<br>[⬆ Back to top](#table-of-contents)

### Active-Record is the design pattern that promotes objects to include functions such as Insert, Update, and Delete, and properties that correspond to the columns in some underlying database table. In your opinion and experience, which are the limits and pitfalls of the this pattern?

1. Those objects are hard to test - they are tied to the data layer.
2. This design violates SRP, so it might lead us to huge classes with lots of responsibilities.
4. It's easy to hit the database multiple times (e.g. in foreach loop) because of the leaking abstraction.
<br>[⬆ Back to top](#table-of-contents)
### Write a snippet of code violating the Don't Repeat Yourself (DRY) principle. Then, fix it.
### How would you migrate an application from a database to another, for example from MySQL to PostgreSQL? If you had to manage that project, which issues would you expect to face?

The strategy would highly depend on application downtime possibility. If some downtime would be possible, migration would be much easier. I would pay attention especially to:
1. Consistency in data changes after migration has been started (if downtime is not possible).
2. Data types compatibility between different db engines.
3. Database api changes.
4. Security issues (we would transfer a lot of sensitive data through the network).
5. Troublesome potential revert.
<br>[⬆ Back to top](#table-of-contents)

### Why do databases treat null as a so special case? For example, why does ```SELECT * FROM table WHERE field = null``` not match records with null ``field`` in SQL?

"NULL", basically means "a missing unknown value". It requires often special treatment because it represents something that doesn't exist.
The example above doesn't work, because the result of any arithmetic comparison with NULL is NULL itself, e.g.:

```sql
1 = NULL, 1 <> NULL, 1 < NULL, 1 > NULL
```
, and even
```sql
NULL = NULL
```
It somehow makes sense, because how would you compare a number to something that doesn't exist, or how would you compare something that doesn't exist to something that doesn't exist?!
<br>[⬆ Back to top](#table-of-contents)

### ACID is an acronym that refers to Atomicity, Consistency, Isolation and Durability, 4 properties guaranteed by a database transaction in most database engines. What do you know about this topic? Would you like to elaborate?

1. Atomicity specifies that if any query in a single transaction fails, the whole transaction also fails and the database is left unchanged. By "fail" we mean not only application errors, but also external factors, like a power outage.
2. Consistency specifies that each transaction has to lead the database from one valid state to another valid state. It has to maintain its invariants.
3. Isolation specifies that each transaction has to be performed in isolation of each other. There are different levels of isolation:
    * "read uncommitted" - no isolation - we can read uncommitted data from another transaction
    * "read committed" - better isolation - we can read only committed data from other transactions. It leads to inconsistencies if a concurrent transaction has been started during another transaction, but has been finished earlier.
    * "repeatable read" - usually "good enough" isolation - each query in the transaction sees only committed updates at the beginning of the transaction. It might be implemented with locks or versioning. Phantom reads might occur.
    * "serializable" - the highest level of isolation - transactions are not executed concurrently, they are executed consecutively.
    
    The performance goes down with the level of isolation. That's why "repeatable read" is used most often.
    Also, presented model is often more complicated in some db engines implementation. You can find the details here https://github.com/ept/hermitage
4. Durability specifies that after a transaction has been committed, the data will remain even after power outage or crash.
    
<br>[⬆ Back to top](#table-of-contents)

### How would you manage database schema migrations? That is, how would you automate changes to database schema, as the application evolves, version after version?

I would use migration scripts which would be tracked in the version control system. Each change to database schema would be a script ordered chronologically, e.g. they would be named `1_add_age_to_user`, `2_add_price_to_order`.
I would also track in database which migration scripts were executed already. With setup like this, it would be easy to execute migration scripts automatically - in development environment on application start, and in CI - before deployment. 

Code violating the DRY principle:
```javascript
class Employee {
    calculateSalaryNet() {
        return this.hoursWorked * this.hourlyWage;
    }

    calculateSalaryGross() {
        return this.hoursWorked * this.hourlyWage + TAX;
<br>[⬆ Back to top](#table-of-contents)

### How is lazy loading achieved? When is it useful? What are its pitfalls?

Lazy loading is a pattern in which we delay loading the data until it's actually needed. Lazy loading data from the database is usually achieved by Implementing proper Proxy class.
It might be useful if we have an object which requires a lot of data to be fetched from the database, but probably we don't need all the data in every case. It might reduce object initialization phase and memory usage.
On the other hand, we might end up with a lot of database queries to get small chunks of data, and it might cause performance problems. It's not so hard to do that because lazy loading is a very leaking abstraction.
Another pitfall, probably more important is that we might work with inconsistent data. If we loaded user data first, and then after some time we loaded user orders, we can't be sure that the orders data wasn't modified already by someone else.

    }
}
```

Fixed code:
```javascript
class Employee {
    calculateSalaryNet() {
        return this.hoursWorked * this.hourlyWage;
    }

    calculateSalaryGross() {
        return this.calculateSalaryNet() + TAX;
    }
}
```
<br>[⬆ Back to top](#table-of-contents)


### How would you deal with Dependency Hell?

1. The most basic approach is to manually update dependencies to satisfy other package versioning or to ask the maintainer to do this.
2. If I trust the semantic versioning libraries I use, I try to do more relaxed versioning.
2. A better solution for this problem is to keep projects in monorepo. This approach implies other challenges though.
3. Another interesting solution is a [system for easier dependencies management](https://www.youtube.com/watch?v=VNqmHJtItCs) introduced by Netflix Engineering. 

<br>[⬆ Back to top](#table-of-contents)

### Is goto evil? You may have heard of the famous paper "Go To Statement Considered Harmful" by Edsger Dijkstra, in which he criticized the use of the `goto` statement and advocated structured programming instead. The use of `goto` has always been controversial, so much that even Dijkstra's letter was criticized with articles such as "'GOTO Considered Harmful' Considered Harmful". What's your opinion on the use of `goto`?

I wouldn't be so radical in either direction. I think that structured programming won the debate because it's the right thing to do. It's easier to reason about a program written in this manner.
On the other hand, even writing this kind of programs we often use the `goto` like style (early returns, exception handling) and it doesn't do any harm.
In my opinion the same applies to the `goto` statements - function-scoped `goto` statements here and there might really make our program simpler and easier to understand.

### Data-Mapper is a design pattern that promotes the use of a layer of Mappers that moves data between objects and a database while keeping them independent of each other and the mapper itself. On the contrary, in Active-Record objects directly incorporate operations for persisting themselves to a database, and properties corresponding to the underlying database tables. Do you have an opinion on those patterns? When would you use one instead of the other?

1. ActiveRecord violates the SRP principle and it's hard to test. If we would have a simple application which only read and stores data, with no business logic included, Active Directory seems to be the best choice. In every other case,
I would go with Data-Mappers.
<br>[⬆ Back to top](#table-of-contents)

### Why is it often said that the introduction of `null` is a "billion dollar mistake"? Would you discuss the techniques to avoid it, such as the Null Object Pattern introduced by the GOF book, or Option types?

The presence of null and its assignability to any type makes programs error-prone. Since any variable can be "null", we never know when we may want to call e.g. some method on null instead of the real object.

Null object pattern mail lead to silent errors. It may be also tedious in maintenance, because we have to update it often when original class changes. It would be helpful when we really want to apply default behavior for some cases.

Option types are awesome, because they are completely safe. However, they might create some overhead with a lot of additional code.
<br>[⬆ Back to top](#table-of-contents)

### Many state that, in Object-Oriented Programming, composition is often a better option than inheritance. What's you opinion?

It depends on the case. The issue with inheritance is that it breaks encapsulation and creates a tight coupling between the parent class and subclasses.
We might end up also with a single big class. On the other hand, with the composition, we might end up with a lot of small classes. If the relation between the object is `is a` and we
want to have slightly different behavior, I would choose inheritance. In other cases, I would choose a composition.
<br>[⬆ Back to top](#table-of-contents)
