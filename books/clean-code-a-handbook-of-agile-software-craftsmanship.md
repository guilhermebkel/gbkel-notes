# Clean Code: A Handbook of Agile Software Craftsmanship

## Summary

This book gives some tips about how to create code easy to change, maintain and understand.

## Introduction

*"The only valid measurement of code quality: WTFs/minute"*

Usually when you have too many WTFs/minute while dealing with some code, it probably means that you are in touch with bad code.

Being minded about it, there are many principles, patterns, practices and heuristics which can help creating code with less WTFs/minute.

## Clean Code

### What is Clean Code

Let's get a look at how some important people describe what is clean code:

- **Bjarne Stroustrup**: *"I like my code to be elegant and efficient. The logic should be straightforward to make it hard for bugs to hide, the dependencies minimal to ease maintenance, error handling complete according to an articulated strategy, and performance close to optimal so as not to tempt people to make the code messy with unprincipled optimizations. Clean code does one thing well."*

- **Grady Booch**: *"Clean code is simple and direct. Clean code reads like well-written prose. Clean code never obscures the designer's intent but rather is full of crisps abstractions and straightforward lines of control."*

- **Dave Thomas**: *"Clean code can be read and enhanced by a developer other than its original author. It has unit and acceptance tests. It has meaningful names. It provides one way rather than many ways for doing one thing. It has minimal dependencies, which are explicitly defined, and provides a clear and minimal API. Code should be literate since depending on the language, not all necessary information can be expressed clearly in code alone."*

- **Michael Feathers**: *"I could list all of the qualities that I notice in clean code, but there is one overarching quality that leads to all of them. Clean code always looks like it was written by someone who cares. There is nothing obvious that you can do to make it better. All of those things were thought about by the code's author, and if you try to imagine improvements, you're led back to where you are, sitting in appreciation of the code someone left for you - code left by someone who cares deeply about the craft."*

- **Ron Jeffries**: *"In recently years I beging, and nearly end, with Beck's rules of simple code. In priority order, simple code: Run all tests; Contains no duplication; Expresses all the design ideas that are in the system; Minimizes the number of entities such as classes, methods, functions, and the like. Of these, I focus mostly on duplication. When the same thing is done over and over, it's a sign that there is an idea in our mind that is not well represented in the code. I try to figure out what it is. Then I try to express that idea more clearly. Expressiveness to me includes meaningful names, and I am likely to change the names of things several times before I settle in. With modern coding tools such as Eclipse, renaming is quite inexpensive, so it doesn't trouble me to change. Expressiveness goes beyond names, however. I also look at whether an object of method is doing more than one thing. If it's an object, it probably needs to be broken into two or more objects. If it's a method, I will always use the Extract Method refactoring on it, resulting in one method that says more clearly what it does, and some submethods saying how it is done. Duplication and expressiveness take me a very long way into what I consider clean code, and improving dirty code with just these two things in mind can make a huge difference. There is, however, one other thing that I'm aware of doing, which is a bit harder to explain. After years of doing this work, it seems to me that all programs are made up of very similar elements. One example if "find things in a collection." Whether we have a database of employee records, or a hash map of keys and values, or an array of items of some kind, we often find ourselves wanting a particular item from that collection. When I find that happening, I will ofter wrap that particular implementation in a more abstract method of class. That gives me a couple of interesting advantages. I can implement the functionality now with something simple, say a hash map, but since now all the references to that search are covered by my little abstraction, I can change the implementation any time I want. I can go forward quickly while preserving my ability to change later. In addiction, the collection abstraction often calls my attention to what's "really" going on, and keeps me from running down the path of implementing arbitrary collection behavior when all I really need is a few fairly simple ways of finding what I want. Reduced duplication, high expressiveness, and early building of simple abstractions. That's what makes clean code for me."*

- **Ward Cunningham**: *"You know you are working on clean code when each routine you read turns out to be pretty much what you expected. You can call it beautiful code when the code also makes it looks like the language was made for the problem."*

## Meaningful Names

Names are everywhere in software. We name our variables, our functions, our arguments, classes, and packages. We name our source files and the directories that contain them. We name our jar files and war files and ear files. We name and name and name. Because we do so much of it, we'd better do it well.

### Use Intention-Revealing Names

Names should reveal intent. So take care with your names and change them when you find better ones. Everyone who reads your code (including you) will be happier if you do. If a name requires a comment, then the name does not reveal its intent.

### Avoid Disinformation

Programmers must avoid leaving false clues that obscure the meaning of the code. We should avoid words whose entrenched meanings vary from our intended meaning *(Per example: using hp instead of hypotenuse)*.

### Make Meaningful Distinctions

Programmers create problems for themselves when they write code solely to satisfy a compiler or interpreter. Distinguish names in such a way that the reader known that the differences offer *(Per example: customerInfo is indistinguishable from customer)*.

### Use Pronounceable Names

Words are, by definition, pronounceable. So if you can't pronounce it, you can't discuss it without sounding like an idiot *(Per example: genymdhms is not pronounceable)*.

### Use Searchable Names

Single-letter names and numeric constants have a particular problem in that they are not easy to locate across a body of text.

### Avoid Encodings

Encoding type or scope information into names simply adds an extra burden of deciphering. It hardly seems reasonable to require each new employee to learn yet another encoding "language" in addition to learning the body of code they'll be working in. Encoded names are seldom pronounceable and are easy to mis-type.

### Avoid Mental Mapping

Readers shouldn't have to mentally translate your names into other names they already know. This problem generally arises from a choice to use neither problem domain terms nor solution domain terms.

- **Class Names:** A class name should not be a verb *(Per example: Account, Customer)*.

- **Method Names:** Methods should have verb or verb phrase names *(Per example: postPayment, deletePage, save)*.

### Don't Be Cute

If names are too clever, they will be memorable only to people who share the author's sense of humor, and only as long as these people remember the joke *(Per example: using HolyHandGrenade instead of DeleteItems)*.

Say what you mean. Mean what you say.

### Pick One Word per Concept

Pick one word for one abstract concept and stick with it. For instance, it's confusing to have *fetch, retrieve and get* as equivalent methods of different classes. Likewise, it's confusing to have *a controller and a manager and a driver* in the same code base.

A consistent lexicon is a great boon to the programmers who must use your code.

### Don't Pun

Avoid using the same word for two purposes. Using the same term for two different ideas is essentially a pun *(Per example: having a class with an add method that creates a new data on database and a class with an add method that inserts a new data inside a in-memory collection)*.

### Use Solution Domain Names

Remember that the people who read your code will be programmers. So go ahead and use computer science terms, algorithm names, pattern names, math terms, and so forth *(Per example: the JobQueue name should be meaningful for the most programmers)*.

### Use Problem Domain Names

When there is no "programmer-eese" for what you are doing, use the name from the problem domain. At least the programmer who maintains your code can ask a domain expert what it means.

Separating solution and problem domain concepts is part of the job of a good programmer and designer. The code that has more to do with problem domain concepts should have names drawn from the problem domain.

### Add Meaningful Context

There are a few names which are meaningful in and of themselves - most are not. Instead, you need to place names in context for your reader by enclosing them in well-named classes, functions, or namespaces. When all else fails, then prefixing the name may be necessary as a last resort.

### Don't Add Gratuitous Context

Shorter names are generally better than longer ones, so long as they are clear. Add no more context to a name than is necessary *(Per example: it is a bad idea to in an application called Gas Station Deluxe to prefix every class with GSD)*.

## Functions

### Small!

The first rule of functions is that they should be small. The second rule of functions is that they should be smaller than that.

### Blocks and Indenting

The indent level of a function should not be greater than one or two. This, of course, makes the functions easier to read and understand.

### Do One Thing

Functions should do one thing. They should do it well. They should do it only. A way to know that a function is doing more than "one thing" is if you can extract another function from it with a name that is not merely a restatement of its implementation.

### One Level of Abstraction per Function

In order to make sure your functions are doing "one thing", we need to make sure that the statements within our function are all at the same level of abstraction. Mixing levels of abstraction within a function is always confusing.

We want the code to read like a top-down narrative. We want every function to be followed by those at the next level of abstraction so that we can read the program, descending one level of abstraction at a time as we read down the list of functions.

To say this differently, we want to be able to read the program as though it were a set of TO paragraphs, each of which is describing the current level of abstraction and referencing subsequent TO paragraphs at the next level down.

### Switch Statements

Unfortunately we can't always avoid switch statements, but we can make sure that each switch statement is buried in a low-level class and is never repeated. We usually do this with polymorphism.

### Use Descriptive Names

Don't be afraid to make a name long. A long descriptive name is better than a short enigmatic name. Choosing descriptive names will clarify the design of the module in your mind and help you to improve it.

### Function Arguments

The ideal number of arguments for a function is zero. Next comes one, followed closely by two. Three arguments should be avoided where possible *(Per example: call consolidateUser(user) instead of consolidateUser(id, name, email))*.

Arguments are hard, they take a lot of conceptual power *(Per example: includeSetupPage() is easier to understand than includeSetupPageInto(newPageContent))*.

### Flag Arguments

Flag arguments are ugly. Passing a boolean into a function is a truly terrible practice. It immediately complicates the signature of the method, loudly proclaiming that this function does more than one thing. It does one thing if the flag is true and another if the flag is false.

### Dyadic Functions

A function with two arguments is harder to understand than a monadic function *(Per example: writeField(name) is easier to understand than writeField(outputStream, name))*.

Dyads aren't evil. and you will certainly have to write them. However, you should be aware that they come at a cost and should take advantage of what mechanims may be available to you to convert them into monads.

### Triads

Functions that take three arguments are significantly harder to understand than dyads. The issues of ordering, pausing, and ignoring are more than doubled. Think very carefully before creating a triad.

### Argument Objects

When a function seems to need more than two or three arguments, it is likely that some of those arguments ought to be wrapped into a class of their own. Reducing the number of arguments by creating objects out of them may seem like cheating, but it's not. When groups of variables are passed together, the way x and y are in the example above, they are likely part of a concept that deserves a name of its own.

### Verbs and Keywords

Choosing good names for a function can go a long way toward explaining the intent of the function and the order and intent of the arguments. In the case of a monad, the function and argument should form a very nice verb/noun pair.

### Have No Side Effects

Side effects are lies. Your function promises to do one thing, but it also does other hidden things. Sometimes it will make unexpected changes to the variables of its own class. Sometimes it will make them to the parameters passed into the function or to system globals. In either case they are devious and damaging mistruths that often result in strange temporal coupling and other dependencies.

### Output Arguments

Arguments are most naturally interpreted as inputs to a function *(Per example: appendFooter(s) append s as the footer to something or does it append footer to s?)*.

### Command Query Separation

Functions should either do something or answer something, but not both. Either your function should change the state of an object, or it should return some information about that object. Doing both often leads to confusion.

### Prefer Exceptions to Returning Error Codes

Returning error codes from command functions is a subtle violation of command query separation. It promotes command being used as expressions in the predicates of if statements. What basically means that for every new method you create, you have to treat its error as well, since if you forget to do it, it will cause some bugs to the system.

### Don't Repeat Yourself

Code duplication may be the root of all evil in software. Many principles and practices have been created for the purpose of controlling or eliminating it.

## Comments

Comments can be sometimes damaging or helpful, and the proper use of it is to compensate for our failure to express ourself in code.

Most of the time we need them because we are writing bad code, what means that we need to focus on being better on expressing ourself in code. Being minded about it, sometimes even writing good code we will need some comments to express something.


### Good Comments
#### Legal Comments

Sometimes we need to add comments for legal reasons, per example copyright and authorship statements are necessary and reasonable things to put into a comment at the start of each source file.

#### Informative Comments

It is sometimes useful to provide basic information with a comment *(Per example: we have a Regex on the code and we add a comment saying what is this Regex expected to match)*.

#### Explanation of Intent

Sometimes a comment goes beyond just useful information about the information about the implementation and provides the intent behind a decision.

#### Clarification

Sometimes it is just helpful to translate the meaning of some obscure argument or return value into something that's readable.

#### Warning of Consequences

Sometimes it is useful to warn other programmers about certain consequences.

#### TODOs

Sometimes it is useful to keep TODO comments in the code to explain why the function has a degenerate implementation and what that function's future should be.

Even though, you don't want your code to be littered with TODOs, so scan through them regularly and eliminate the ones you can.

#### Amplification

A comment may be used to amplify the importance of something that may otherwise seem inconsequential.

### Bad Comments

#### Mumbling

Adding a comment just because you feel you should or because the process requires it. If you decide to write a comment, then spend the time necessary to make sure it is the best comment you can write.

#### Redundant Comments

Usually some comments are not informative since the code is already easy to understand.

#### Misleading Comments

Sometimes, with all the best intentions a programmer makes a statement in his comments that isn't precise enough to be accurate.

#### Mandated Comments

It is just plain silly to have a rule that says that every function/variable must have a comment. Comments like this just clutter up the code, propagate lies, and lend to general confusion and disorganization.

#### Noise Comments

Sometimes you see comments that are nothing but noise. They restate the obvious and provide no new information. These comments are so noisy that we learn to ignore them. As we read through code, our eyes simply skip over them.

#### Commented-Out Code

Others who see commented-out code won't have courage to delete it. So don't be shy to delete it, since you can go back with git and get the code back if you need.

### Inobvious Connection

The connection between a comment and the code it describes should be obvious.

## Formatting

When people look under the hood, we want them to be impressed with the neatness, consistency, and attention to detail that they perceive.

You should take care that your code is nicely formatted. You should choose a set of simple rules that govern the format of your code, and then you should consistently apply those rules.

### Vertical Openness Between Concepts

Nearly all code is read left to right and top to bottom. Each line represents an expression or a clause, and each group of lines represents a complete thought. Those thoughts should be separated from each other with blank lines.

### Vertical Density

If openness separates concepts, then vertical density implies close association. So lines of code that are tightly related should appear vertically dense.

### Vertical Distance

Concepts that are closely related should be kept vertically close to each other.

### Variable Declarations

Variables should be declared as close to their usage as possible.

### Instance Variables

Instance variables, on the other hand, should be declared at the top of the class.

### Dependent Functions

If one function calls another, they should be vertically close, and the caller should be above the callee, if at all possible.

### Conceptual Affinity

Certain bits of code want to be near other bits. They have a certain conceptual affinity. The stronger the affinity, the less vertical distance there should be between them.

### Vertical Ordering

In general we want function call dependencies to point in the downward direction. That is, a function that is called should be below a function that does tha calling.

### Team Rules

Every programmer has his own favorite formatting rules, but if he works in a team, then the team rules. A team of developers should agree upon a single formatting style, ant then every member of that team should use that style.

## Objects and Data Structures

### Data Abstraction

Hiding data implementation is not just a matter of putting a layer of functions between the variables. Hiding implementation is about abstractions. A class exposes abstract interfaces that allow its users to manipulate the essence of the data, without having to know its implementation.

We do not want to expose the details of our data. Rather we want to express our data in abstract terms.

### Data/Object Anti-Symmetry

Objects hide their data behind abstractions and expose functions that operate on that data. Data structure expose their data and have no meaningful functions.

Procedural code (code using data structures) makes it easy to add new functions without changing the existing data structures, OO code, on the other hand, makes it easy to add new classes without changing existing functions. Also, procedural code makes it hard to add new data structures because all the functions must change. OO code makes it hard to add new functions because all the classes must change.

### The Law of Demeter

A module should not know about the innards of the objects it manipulates. This means that an object should not expose its internal structure through accessors because to do so is to expose, rather than to hide, its internal structure.

### Data Transfer Objects

DTOs are very useful structures, especially when communicating with databases or parsing messages from sockets, and so on. They often become the first in a series of translation stages that convert raw data in a database into objects in the application code.

### Active Record

Active Records are a special form of DTOs. They are data structures with public variables, but they typically have navigational methods like save and find. Typically theses Active Records are direct translations from database tables, or other data sources.

## Error Handling

Error handling is important, but if it obscures logic, it's wrong.

### Use Exceptions Rather Than Return Codes

The problem in return codes is that the caller must check for errors immediately after the call. Unfortunately, it's easy to forget. For this reason it is better to throw an exception when you encounter an error.

### Write Your Try-Catch-Finally Statement First

One of the most interesting things about exceptions is that they define a scope within your program. In a way, try blocks are like transactions. Your catch has to leave your program in a consistent state, no matter what happens in the try. For this reason it is good practice to start with a try-catch-finally statement when you are writing code that could throw exceptions.

### Provide Context with Exceptions

Each exception that you throw should provide enough context to determine the source and location of an error. Create informative error messages and pass them along with your exceptions. Mention the operation that failed and the type of failure. If you are logging in your application, pass along enough information to be able to log the error in your catch.

### Don't Return Null

Any discussion about error handling should include mention of the things we do that invite errors. The first on the list is returning null. When we return null, we are essentially creating work for ourselves and foisting problems upon our callers. All it takes is one missing null check to send and application spinning out of control.

### Don't Pass Null

Returning null from methods is bad, but passing null into methods is worse. Unless you are working with an API which expects you to pass null, you should avoid passing null in your code whenever possible.

## Boundaries

We seldom control all the software in our systems. Sometimes we buy third-party packages or use open source. Other times we depend on teams in our own company to produce components or subsystems for us. Somehow we must cleanly integrate this foreign code with our own.

### Using Third-Party Code

There is a natural tension between the provider of an interface and the user of an interface. Providers of third-party packages and frameworks strive for broad applicability so they can work in many environments and appeal to a wide audience. Users, on the other hand, want an interface that is focused on their particular needs. This tension can cause problems at the boundaries of our systems.

### Exploring and Learning Boundaries

Third-party code helps us get more functionality delivered in less time. Learning the third-party code is hard. Integrating the third-party code is hard too. Doing both at the same time is doubly hard. Instead of experimenting and trying out the new stuff in our production code, we could write some tests to explore our understanding of the third-party code.

### Using Code That Does Not Yet Exist

There is another kind of boundary, one that separates the known from the unknown. There are often places in the code where our knowledge seems to drop off the edge. Sometimes what is on the other side of the boundary is unknowable. Sometimes we choose to look no farther than the boundary.

### Clean Boundaries

Interesting things happen at boundaries. Change is one of those things. Good software designs accommodate change without huge investments and rework. When we use code that is out of our control, special care must be taken to protect our investment and make sure future change is not oo costly.

Code at the boundaries needs clear separation and tests that define expectations. We should avoid letting too much of our code know about the third-party particulars. It's better to depend on something you control than on something you don't control, lest it end up controlling you.

We manage third-party boundaries by having very few places in the code that refer to them. We may wrap them with an Adapter to convert from our perfect interface to the provided interface. Either way our code speaks to us better, promotes internally consistent usage across the boundary, and has fewer maintenance points when the third-party code changes.

## Unit Tests

### The Three Laws of TDD

**1º** You may not write production code until you have written a failing unit test.

**2º** You may not write more unit test than is sufficient to fail, and not compiling is failing.

**3º** You may not write more production code than is sufficient to pass the currently failing test.

These three laws lock you into a cycle that is perhaps thirty seconds along. The tests and the production code are written together, with the tests just a few seconds ahead of the production code.

### Keeping Tests Clean

Having dirty tests is equivalent to, if not worse than, having no tests. The problem is that tests must change as the production code evolves. The dirtier the tests, the harder they are to change. The more tangled the test code, the more likely it is that you will spend more time cramming new tests into the suite than it takes to write the new production code. As you modify the production code, old tests start to fail, and the mess in the test code makes it hard to get those tests to pass again.

### Tests Enable the -ilities

If you don't keep your tests clean, you will lose them. And without them, you lose the very thing that keeps your production code flexible.

No matter how flexible your architecture is, no matter how nicely partitioned your design, without tests you will be reluctant to make changes because of the fear that you will introduce undetected bugs. With tests that fear virtually disappears. The higher your test coverage, the less you fear.

So having an automated suite of unit tests that cover the production code is the key to keeping your design and architecture as clean as possible.

### Clean Tests

What makes a clean test? Readability, readability and readability.

Readability is perhaps even more important in unit tests than it is in production code.

What makes tests readable? Clarity, simplicity and density of expression.

### Single Concept per Test

It is good to minimize the number of asserts in a test, perhaps, a better rule is that we want to test a single concept in each test function. We don't want long test functions that go testing one miscellaneous thing after another.

### F.I.R.S.T.

Clean tests follow five other rules that form the above acronym:

**Fast** Tests should be fast. They should run quickly. When tests run slow, you won't want to run them frequently. If you don't run them frequently, you won't find problems early enough to fix them easily. You won't feel as free to clean up the code. Eventually the code will begin to rot.

**Independent** Tests should not depend on each other. One test should not set up the conditions for the next test. You should be able to run each test independently and run the tests in any order you like. When tests depend on each other, then the first one to fail causes a cascade of downstream failures, making diagnosis difficult and hiding downstream defects.

**Repeatable** Tests should be repeatable in any environment. You should be able to run the tests in the production environment, in the QA environment, and your laptop while riding home on the train without a network. If your tests aren't repeatable in any environment, then you'll always have an excuse for why they fail. You'll also find yourself unable to run the tests when the environment isn't available.

**Self-Validating** The tests should have a boolean output. Either they pass or fail. You should not have to read through a log file to tell whether the tests pass. You should not have to manually compare two different text files to see whether the tests pass. If the tests aren't self-validating, then failure can become subjective and running tests can require a long manual evaluation.

**Timely** The tests need to be written in a timely fashion. Unit tests should be written just before the production code that makes them pass. If you write tests after the production code, then you may find the production code to be hard to test. You may decide that some production code is too hard to test. You may bot design the production code to be testable.

## Classes

### Class Organization

A class should begin with a list of variables. Public static constants, if any, should come first. Then private static variables, followed by private instance variables.

Public functions should follow the list of variables. We like to put the private utilities called by a public function right after the public function itself.

### Encapsulation

We like to keep our variables and utility functions private, but we're not fanatic about it. Sometimes we need to make a variable or utility function protected so that it can be accessed by a test. For us, tests rule. If a test in the same package needs to call a function or access a variable, we'll make it protected or package scope.

### Classes Should be Small!

The first rule of classes is that they should be small. The second rule of classes is that they should be smaller than that.

The name of a class should describe what responsibilities it fulfills. In fact, naming is probably the first way of helping determine class size. If we can not derive a concise name for a class, then it's likely too large. The more ambiguous the class name, the more likely it has too many responsibilities.

### The Single Responsibility Principle

The SRP states that a class or module should have one, and only one, reason to change. This principle gives us both a definition of responsibility, and a guidelines for class size. Class should have one responsibility - one reason to change.

### Cohesion

Classes should have a small number of instance variables. Each of the methods of a class should manipulate one or more of those variables. In general the more variables a method manipulates the more cohesive that method is to its class. A class in which each variable is used by each method is maximally cohesive.

### Organizing for Change

For most systems, change is continual. Every change subjects us to the risk that the remainder of the system no longer works as intended. In a clean system we organize our classes so as to reduce the risk of change.

Following the OCP, classes should be open for extension but closed for modification.

We want to structure our systems so that we muck with as little as possible when we update them with new or changed features. In an ideal system, we incorporate new features by extending the system, not by making modifications to existing code.

### Isolating from Change

Needs will change, therefore code will change. There are concrete classes, which contain implementation details and abstract classes, which represent concepts only. A client class depending upon concrete details is at risk when those details change. We can introduce interfaces and abstract classes to help isolate the impact of those details.

## Systems

Software systems should separate the startup process, when the application objects are constructed and the dependencies are "wired" together, from the runtime logic that takes over after startup.

### Separate Constructing a System from Using It

The startup process is a concern that any application must address. We should modularize this process separately from the normal runtime logic and we should make sure that we have a global, consistent strategy for resolving our major dependencies.

#### Separation of Main

One way to separate construction from use is simply to move all aspects of constructions to main, or modules called by main, and to design the rest of the system assuming that all objects have been constructed and wired up appropriately.

The flow control is easy to follow. The main function build the objects necessary for the system, then passes them to the application, which simply uses them.

Notice the direction of the dependency arrows crossing the barrier between main and the application. They all go one direction, pointing away from main. This means that the application has no knowledge of the main or of the construction process. It simply expects that everything has been build properly.

#### Factory

We can use a factory to give the application control of when to build a object, but keep the details of that construction separate from the application code.

#### Dependency Injection

A powerful mechanism for separating construction from use is Dependency Injection, the application of Inversion Control to dependency management.

Inversion of Control moves secondary responsibilities from an object to other objects that are dedicated to the purpose, thereby supporting the Single Responsibility Principle. In the context of dependency management, an object should not take responsibility for instantiating dependencies itself. Instead, it should pass this responsibility to another "authoritative" mechanism, thereby inverting the control. Because setup is a global concern, this authoritative mechanism will usually be either the "main" routine or a special-purpose container.

### Scaling Up

It is a myth that we can get systems "right at the first time". Instead, we should implement only today's stories, then refactor and expand the system to implement new stories tomorrow. This is the essence of iterative and incremental agility. Test-driven development, refactoring, and the clean code they produce make this work at the code level.

Software systems are unique compared to physical systems. Their architecture can grow incrementally, if we maintain the proper separation of concerns.

An optimal system architecture consists of modularized domains of concern, each of which is implemented with Plain Old Objects. The different domains are integrated together with minimally invasive Aspects or Aspect-like tools. This architecture can be test-driven, just like the code.

### Optimize Decision Making

Modularity and separation of concerns make decentralized management and decision making possible. In a sufficiently large system, whether it is a city of a software project, no one person can make all the decisions.

We all know it is best to give responsibilities to the most qualified persons. We often forget that it is also best to postpone decisions until the last possible moment. This isn't lazy or irresponsible; it lets us make informed choices with the best possible information.

A premature decision is a decision made with suboptimal knowledge. We will have that much less customer feedback, mental reflection on the project, and experience with our implementation choices if we decide too soon.

The agility provided by POO system with modularized concerns allows us to make optimal, just-in-time decisions, based on the most recent knowledge. The complexity of these decisions is also reduced.

### Use Standards Wisely, When They Add Demonstrable Value

Building construction is a marvel to watch because of the pace at which new buildings are built and because of the extraordinary designs that are possible with today's technology. Construction is a mature industry with highly optimized parts, methods, and standard that have evolved under pressure for centuries.

Standards make it easier to reuse ideas and components, recruit people with relevant experience, encapsulate good ideas, and wire components together. However, the process of creating standards can sometimes take too long for industry to wait, and some standards lose touch with the real needs of the adopters they are intended to serve.

### System Need Domain-Specific Languages

Building construction, like most domain, has developed a rich language with a vocabulary, idioms, and patterns that convey essential information clearly and concisely.

A good DSL minimizes the "communication gap" between a domain concept and the code that implements it, just as agile practices optimize the communication within a team and with the project's stakeholders. If you are implementing domain logic in the same language that a domain expert uses, there is less risk that you will incorrectly translate the domain into the implementation.

DSLs, when used effectively, raise the abstraction level above code idioms and design patterns. They allow the developer to reveal the intent of the code at appropriate level of abstraction.

Domain-Specific-Languages allow all levels of abstraction and all domains in the application to be expressed as POOs (Plain Old Objects), from high-level policy to low-level details.

## Emergence

### Getting Clean via Emergent Design

According to Kent, a design is "simple" if it follows these rules (the rules are given in order of importance):

#### Runs all the tests
A system that is comprehensively tested and passes all of its tests all of the time is a testable system. Systems that aren't testable aren't verifiable. Arguably, a system that cannot be verified should never be deployed. Tight coupling makes it difficult to write tests.

So, similarly, the more tests we write, the more we use principles like DIP and tools like dependency injection, interfaces, and abstraction to minimize coupling. Our designs improves even more.

Once we have tests, we are empowered to keep our code and classes clean. We do this by incrementally refactoring the code. The fact that we have tests eliminates the fear that cleaning up the code will break it.

During this refactoring step, we can apply anything from the entire body of knowledge about good software design. We can increase cohesion, decrease coupling, separate concerns, modularize system concerns, shrink our functions and classes, choose better names, and so on.

This is also where we apply the final three rules of simple design: Eliminate duplication, ensure expressiveness, and minimize the number of classes and methods.

#### Contains no duplication

Duplication is the primary enemy of a well-designed system. It represents additional work, additional risk, and additional unnecessary complexity. Duplication manifests itself in many forms. Lines of code that look exactly alike are, of course, duplication.

#### Expresses the intent of the programmer

Most of us have had the experience of working on convoluted code. Many of us have produced some convoluted code ourselves.

It's easy to write code that we understand, because at the time we write it we're deep in an understanding of the problem we're trying to solve. Other maintainers of the code aren't going to have so deep an understanding.

The majority of the cost of a software project is in long-term maintenance. In order to minimize the potential for defects as we introduce change, it's critical for us to ble able to understand what a system does.

As systems become more complex, they take more and more time for a developer to understand, and there is an ever greater opportunity for a misunderstanding. Therefore, code should clearly express the intent of its author. The clearer the author can make the code, the less time others will have to spend understanding it. This will reduce defects and shrink the cost of maintenance.

You can express yourself by choosing good names. We want to be able to hear a class or function name and not be surprised when we discover its responsibilities.

You can also express yourself by keeping your functions and classes small. Small classes and functions are usually easy to name, easy to write, and easy to understand.

You can also express yourself by using standard nomenclature. Design patterns, for example, are largely about communication and expressiveness.

But the most important way to be expressive is to try. All too often we get our code working and then move on to the next problem without giving sufficient thought to making that code easy for the next person to read. Remember, the most likely next person to read the code will be you.

So take a little pride in your workmanship. Spend a little time with each of your functions and classes. Choose better names, split large functions into smaller functions, and generally just take care of what you've created. Care is a precious resource.

#### Minimizes the number of classes and methods

In an effort to make our classes and methods small, we might create too many tiny classes and methods. So this rule suggests that we also keep our function and class counts low.

Remember that this rule is the lowest priority of the four rules of Simple Design. So, although it's important to keep class and function count low, it's more important to have tests, eliminate duplication, and express yourself.

## Concurrency

Writing clean concurrent programs is hard - very hard. It is much easier to write code that executes in a single thread. It is also easy to write multithreaded code that looks fine on the surface but is broken at a deeper level. Such code works fine until the system is placed under stress.

### Why Concurrency?

Concurrency is a decoupling strategy. It helps us decouple what gets done from when it gets done. In single-threaded applications what and when are so strongly coupled that the state of the entire application can often be determined by looking at the stack backtrace.

Decoupling what from when can dramatically improve both the throughtput and structures of an application. From a structural point of view the application looks like many little collaborating computers rather than one big main loop. This can make the system easier to understand and offers some powerful ways to separate concerns.

#### Myths and Misconceptions

Consider these common myths and misconceptions:

- **Concurrency always improves performance:** Concurrency can sometimes improve performance, but only when there is a lot of wait time that can be shared between multiple threads or multiple processors. Neither situation is trivial.

- **Design does not change when writing concurrent programs:** In fact, the design of a concurrent algorithm can be remarkably different from the design of a single-threaded system. The decoupling of what from when usually has a huge effect on the structure or the system.

- **Understanding concurrency issues is not important when working with a container such as a Web or EJB container:** In fact, you'd better know just what your container is doing and how to guard against the issues of concurrent update and deadlock described later in this chapter.

Here are a few more balanced sound bites regarding writing concurrent software:

- **Concurrency incurs some overhead, both in performance as well as writing additional code**

- **Correct concurrency is complex, even for simple programs**

- **Concurrency bugs aren't usually repeatable, so they are often ignored as one-offs instead of the true defects they are**

- **Concurrency often requires a fundamental change in design strategy**

### Concurrency Defense Principles

What follows is a series of principles and techniques for defending your systems from the problems of concurrent code.

#### Single Responsibility Principle

The SRP states that a given method/class/component should have a single reason to change. Concurrency design in it's own right and therefore deserves to be separated from the rest of the code. Unfortunately, it is all too common for concurrency implementation details to be embedded directly into other production code. Here are a few things to consider:

- **Concurrency-related code has its own life cycle of development**, change, and tuning

- **Concurrency-related code has its own challenges**, which are different from and often more difficult than nonconcurreny-related code

- The number of ways in which miswritten concurrency-based code can fails makes it challenging enough without the added burden of surrounding application code

**Recommendation:** Keep your concurrency-related code separate from other code.

#### Corollary: Limit the Scope of Data

As we saw, two threads modifying the same field of a shared object can interfere with each other, causing unexpected behavior. One solution is to use the synchronized keyword to protect a critical section in the code that uses the shared object.

The more places shared data can get updated, the more likely:

- You will forget to protect one or more of those places - effectively breaking all code that modifies that shared data.

- There will be duplication of effort required to make sure everything is effectively guarded.

- It will be difficult to determine the source of failures, which are already hard enough to find.

**Recommendation:** Take data encapsulation to heart; severely limit the access of any data that may be shared.

#### Corollary: Use Copies of Data

A good way to avoid shared data is to avoid sharing the data in the first place. In some situations it is possible to copy objects and treat them as read-only. In other cases, it might be possible to copy objects, collect results from multiple threads in these copies and then merge the results in a single thread.

If there is an easy way to avoid sharing objects, the resulting code will be far less likely to cause problems. You might be concerned about the cost of all the extra object creation. It is worth experimenting to find out if this is in fact a problem. However, if using copies of objects allows the code to avoid synchronizing, the savings in avoiding the intrinsic lock will likely make up for the additional creation and garbage collection overhead.

#### Corollary: Threads Should Be as Independent as Possible

Consider writing your threaded code such that each thread exists in its own world, sharing no data with any other thread. Each thread processes one client request, with all of its required data coming from an unshared source and stored as local variables. This makes each of those threads behave as if it were the only thread in the world and there were no synchronization requirements.

**Recommendation:** Attempt to partition data into independent subsets than can be operated on by independent threads, possibly in different processors.

#### Know Your Execution Models

There are several different ways to partition behavior in a concurrent application. To discuss them we need to understand some basic definitions:

- **Bound Resources:** Resources of a fixed size or number used in a concurrent environment. Examples include database and fixed-size read/write buffers.

- **Mutual Exclusion:** Only one thread can access shared data or a shared resource at a time.

- **Starvation:** One thread or a group of threads is prohibited from proceeding for an excessively long time or forever. For example, always letting fast-running threads through first could starve out longer running threads if there is no end to the fast-running threads.

- **Deadlock:** Two or more threads waiting for each other to finish. Each thread has a resource that the other thread requires and neither can finish until it gets the other resource.

- **Livelock:** Threads in lockstep, each trying to do work but finding another "in the way". DUe to resonance, threads continue trying to make progress but are unable to for an excessively long time - or forever.

#### Producer-Consumer

One or more producer threads create some work and place it in a buffer of queue. One or more consumer threads acquire that work from the queue and complete it. The queue between the producers and consumers is a bound resource. This means producers must wait for free space in the queue before writing and consumers must wait until there is something the queue to consume.

Coordination between the producers and consumers via the queue involves producers and consumers signaling each other. The producers write to the queue and signal that the queue is no longer empty. Consumers read from the queue and signal that the queue is no longer full. Both potentially wait to be notified when the can continue.

#### Readers-Writers

When you have a shared resource that primarily serves as source of information for readers, but which is occasionally updated by writers, throughput is an issue.

Emphasizing throughput can cause starvation and the accumulation of stale information. Allowing updated can impact throughput. Coordinating readers so they do not read something a writer is updating and vice versa is a tough balancing act. Writers tend to block many readers for a long period of time, thus causing throughput issues.

The challenge is to balance the needs of both readers and writers to satisfy correct operation, provide reasonable throughput and avoiding starvation. A simple strategy makes writers wait until there are no readers before allowing the writer to perform an update. If there are continuous readers, however, the writers will be starved. On the other hand, if there are frequent writers and they are given priority, throughput will suffer. Finding that balance and voiding concurrent update issues is what the problem addresses.

**Recommendation:** Learn these basic algorithms and understand their solutions.

#### Beware Dependencies Between Synchronized Methods

Dependencies between synchronized methods cause subtle bugs in concurrent code. If there is more than one synchronized method on the same shared class, then your system may be written incorrectly.

**Recommendation:** Avoid using more than one method on a shared object.

There will be times when you must use more than one method on a shared object. When this is the case, there are three ways to make the code correct:

- **Client-Based Locking:** Have the client lock the server before calling the first method and make sure the lock's extent includes code calling the last method.

- **Server-Based Locking:** Within the server create a method that locks the server, calls all the methods, and then unlocks. Have the client call the new method.

- **Adapted Server:** create an intermediary that performs the locking. This is an example of server-based locking, where the original server cannot be changed.

#### Keep Synchronized Sections Small

The synchronized keyword introduces a lock. All sections of code guarded by the same lock are guaranteed to have only one thread executing through them at any given time. Locks are expensive because they create delays and add overhead. So we don't want to litter our code with synchronized statements. On the other hand, critical sections must be guarded. So we want to design our code with as few critical sections as possible.

**Recommendation:** keep your synchronized sections as small as possible.

#### Writing Correct Shut-Down Code Is Hard

Writing systems that is meant to stay live and run forever is different from writing something that works for awhile and then shuts down gracefully.

Graceful shutdown can be hard to get correct. Common problems involve deadlock, with threads waiting for a signal to continue that never comes.

If you must write concurrent code that involves shutting down gracefully, expect to spend much of your time getting the shutdown to happen correctly.

**Recommendation:** Think about shut-down early and get it working early. It's going to take longer than you expect. Review existing algorithms because this is probably harder than you think.

#### Testing Threaded Code

Providing that code is correct is impractical. Testing does not guarantee correctness. However, good testing can minimize risk. This is all tru in a single-threaded solution. As soon as there are two or more threads using the same code and working with shared data, things get substantially more complex.

**Recommendation:** Write tests that have the potential to expose problems and then run them frequently, with different programatic configurations and system configurations and load. If tests ever fail, track down the failure. Don't ignore a failure just because the test pass on a subsequent run.

That is a whole lot to take into consideration. Here are a few more fine-grained recommendations:

- Treat spurious failures as candidate threading issues
- Get your nonthreaded code working first
- Make your threaded code pluggable
- Make your threaded code tunable
- Run with more threads than processors
- Run on different platforms
- Instrument your code to try and force failures

#### Treat Spurious Failures as Candidate Threading Issues

Threaded code causes things to fail that "simply cannot fail". Most developers do not have an intuitive feel for how threading interacts with other code. Bugs in threaded code might exhibit their symptoms once in a thousand, or a million, executions.

Attempts to repeat the systems can be frustratingly. This often leads developers to write off the failure as a cosmic ray, a hardware glitch, or some other king of "one-off". It is best to assume that one-offs do not exist. The longer these "one-offs" are ignored, the more code is built on top of a potentially faulty approach.

**Recommendation:** Do not ignore system failures as one-offs.

#### Get Your Nonthreaded Code Working First

This may seem obvious, but it doesn't hurt to reinforce it. Make sure code works outside of its use in threads. Generally, this means creating POOs that are called by your threads. The POOs are not thread aware, and can therefore be tested outside of the threaded environment. The more of your system you can place in such POOs the better.

**Recommendation:** Do not try to chase down nonthreading bugs and threading bugs at the same time. Make sure your code works outside of threads.

#### Make Your Threaded Code Pluggable

Write the concurrency-supporting code such that it can be run in several configurations:

- One thread, several threads, varied as it executes
- Threaded code interacts with something that can be both real or a test double
- Execute with test doubles that run quickly, slowly, variable
- Configure tests so they can run for a number of interactions

**Recommendation:** Make your thread-based code especially pluggable so that you can run it in various configurations.

#### Make Your Threaded Code Tunable

Getting the right balance of threads typically requires trial an error. Early on, find ways to time the performance of your system under different configurations. Allow the number of threads to be easily tuned. Consider allowing it to change while the system is running. Consider allowing self-tunning based on throughput and system utilization.

#### Run with More Threads Than Processors

Things happen when the system switches between tasks. To encourage task swapping, run with more threads than processors or cores. The more frequently your tasks swap, the more likely you'll encounter code that is missing a critical section or causes deadlock.

#### Run on Different Platforms

Different operating systems have different threading policies, each of which impacts the code's execution.

**Recommendation:** Run your threaded code on all target platforms early and often.
