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

<!--- Loc (Current: 2176, End: 8800) --->