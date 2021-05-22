# Refactoring: Improving the Design of Existing Code

## Summary

This book gives some tips about how/when to refactor software and anything that revolves around it.

## Introduction

The compiler does not mind if the code is ugly or beautiful. Besides, if I change the system, there is a human being involved and the human beings care about it. A system with bad design is hard to change - because it is hard to identify how/what/where to change.

Being minded about it, sometimes you will try to add some functionality but the existing code makes it hard to do. Most of the time it is something that we want to avoid, but in case it happens, refactor it in order to get it easier to add the functionality and so do that.

*"In case you are adding a new functionality to program but the code is not good structured, refactor it before adding the functionality in order to make it easier to add it."*

Since during refactors we want to avoid changing the program behavior, testing the program after every refactor is a important habit even if simple. Testing after every change means that if I make some mistake, I'll need to change only a small part of the code (so it is easier to find it and change it). That's the essence of refactor process: small changes and tests before every change. In case I try to do a lot of changes, making some mistake will drive me to a hard debugging moment that can takes a lot of time.

*"Refactoring changes the programs in small steps, in a way that if we make some mistake, it is easy to get it."*

Since the program will need to be changed in the future, try to mind earlier about who will read your code in the future.

*"Any fool is able to write code that a computer understands. Good programmers write code that the human beings are able to understand."*

So most of the time when dealing with a good program writing, we need to mind about software performance? In case you measured the code before and after the refactor, you were probably going to not recognize any change in the speed (most of the time it is what happens). Most of the programmers (even the more experienced ones) have a bad understanding about the real performance of the code. Many of our feelings are misunderstands by the smart compilers, modern technics of caching, etc. The performance of the software in general depends on specific parts of the code and changes in any other place do not make any difference. But, "general" is not the same as "always". Sometimes a refactor will give us a bad performance but it is always easier to change the performance of a good code than the bad one.

*"Most of the time you will need to ignore performance. If your refactor adds reductions in performance, finish refactoring at first and so make the performance adjustments."*

*"Break complex code into small simple parts and give it good names."*

*"The conciseness is the soul of acuteness, but the clearness is the soul of a software capable of evolution."*

*"When programming, follow the camp rule: Always try to make the code base healthier than it was when you found it."*

The code must be obvious: when someone has to make some change, this person need to be able to easy find the code to change and even to make a fast change without adding any bug. A health codebase maximizes our productivity, making us able to create new functionalities in a faster and cheaper way.

*"The true test for a good code is the facility the it can be changed."*

*"The secret of a effective refactor is to recognize that you are faster when making small steps since the code will never get into failures."*

## The Refactoring Principles

**Refactoring:** A change to be done in the internal software structure to make it easier to understand and cheaper to change, without changing its observable behavior.

**Refactor:** Restructuring the software through a series of refactors without changing its observable behavior.

### Small refactors

Every refactor must be something small and individual (or the combination of small steps). That way, when you are refactoring, the code does not need to keep a lot of time in a state of failures, making us able to stop refactoring everytime needed even if we have not finished it yet.

### Observable Behavior

Any bug the we find during a refactoring must keep present after it.

The refactoring is pretty similar to a performance optimization, since each of them make manipulation to code that does not change the code behavior at all. The difference is in the intention: The refactoring is always done to make the code easier to understand and cheaper to change (it can make the code faster of lazier).

### Refactor Moment

When developing software, we usually take different ways through the end of the functionality. Per example: We start trying to add a feature, so we realize that it was going to be easier in case the software was structured in a different way, being minded about it, we refactor the code and after doing that, we start adding the feature again.

### Why we need to refactor?

- **Refactoring improves software design:** Most of the time without refactors the software architecture tends to get into bad format, since if it has a bad design (most of the time we are not able to create a excellent design in the start of the project), the other developers will not be able to understand the patterns and will add something in a different way that it is expected to be done.

- **Refactoring improves software understanding:** Programming is the talk with a computer (I write a code that says to the computer what it needs to do), but in some months, a human being will try to read your code to make changes. This user that we usually do not care about in fact is the most important. Who minds about the computer taking more cycles to compile something? But you will mind in case a developer takes more than a week to do a change that could be done in a hour if the code was good structured.

*"Try to put everything in code that you would need to remember in other that you do not need to remember these infos later."*

- **Refactoring helps us finding bugs:** Some people are capable of reading a small part of the code and recognizing bugs. But in case we refactor code, do a hard work to understand what it does and it put this new comprehension directly back to code it is easier to find bugs.

- **Refactoring helps me programming faster:** In the end, all the explanations above converges to that current one. A software with good internal quality make us able to easy understand how/where to make changes and adding new features. A good modularity make us capable of understand only a part of the software to make a change. In case the software is easy to understand, there is less chance to add new bugs and in case you do that, the debugging is much easier.

*"Since it is really hard to make a good software design earlier, the refactoring becomes something important to get into the way of fast/cheap feature creations"*

### When to refactor?

- **Preparative Refactor - Getting the software easier to add a feature:** Most of the time the better moment to refactor is right after adding a feature to the codebase.

- **Comprehension Refactor - Getting the software easier to understand:** Everytime we get in touch with code and need to think in order to understand its behavior, we can think if we are able to refactor it and get it easier to understand.

- **Garbage Collector Refactor:** When we understand what the code does in a easy way but the code itself does it in a bad manner (the logic is confuse, there are duplicated functions), so it could be good to refactor its internal looking.

- **Planned and Opportunist Refactor:** All the refactors above are opportunists since we don't make it in a proper time, but we use the opportunity when we need to use that code. Try to always think on a refactor as something opportunist (it belongs to the programming process, it do not need to be another task).

*"You need to refactor when you come across a ugly code - but a excellent code needs a lot of refactors as well"*

*"For every desired change, make it to be easy and so make the easy change"*

- **Code Review Refactor:**  The code reviews help us getting new ideas of the code (like an easier logic, a better way to understand the code, etc). Most of the time it is good to have the code author and the revisor getting into the code review together (that way one can explain to another how something should work or even its current behavior now).

- **Long Term Refactor:** Some refactors are fast to do, other take a lot of time, in the long term refactors, try to do that by steps (like starting to work on it by small pieces till you get everything done).

### When not to refactor?

When we come across a code that is confuse but its refactor will not help me doing my current task faster or in a better looking, maybe I do not need to refactor it (since it will probably help in the cases I need to go into that confuse code).

Sometimes it will be easier to rewrite the code instead of refactoring it.

A good way to know if I can refactor something is to try it until I spend a lot of time doing that and understand the difficult to do that.

### Code Owner

Some organizations try to break the code into owners, but sometimes it can be harmful for refactoring since there are functions integrated with a lot of other parts of the code (what means you are probably going to change something made by another person and sometimes you will not have permission to change it).

### Branches

Try to improve the CI process of the applications, what means you should not keep a branch opened for more than a week per example. When you keep up old branches when compared to the main branch, refactor changes will probably generate merge conflict issues.

### Testing

Since refactor does not change the internal behavior of the system, tests would probably help you making sure that the changes you have made did not break anything.

### Legacy Code

Refactoring can help understanding some legacy systems, since most of the time they have ugly functions and bad logics as well. When refactoring a legacy system, try to that by small steps.

### Database

When refactoring databases, try to do what a refactor is expected to do: "Improving speed without changing the internal behavior". Per example, in case you need to change a column name, create a new column, change the code to use it, keep the old one until you feel confident enough to remove it.

### Refactor and Architecture

The main problem of attempting to finish the architecture before programming is that it premises that you got all the software requirements (what most of the time is wrong since it changes during all the software lifetime).

Being minded about that, try to create a software that solves all the needed requirements in the moment, but do that in a way the architecture design is excellent for that requirements. So, use refactoring to adapt the architecture through all the software lifetime. Make it flexible.

### Refactoring and Performance

Most of the time to get the software easier to understand, we make changes that get the application to execute slower.

A refactoring can probably get a software slower but too much more friendly to the performance adjustments.

## The Code Smells

Deciding when to start refactoring - and when to stop - is way too much more important than understanding how to deal with its working. Being minded about it, it is good to refactor based in the feeling you have about the code.

### Mysterious Name

One of the most important parts of a clean code is the good names. Being minded about it, we need to think about good names for our functions, modules, variables and classes. Unfortunately, naming is one of the most difficult stuffs in programming.

### Duplicated Code

A code duplication means that everytime you read the duplication, you will probably need to do that carefully to get if there are some difference. In case you need to change it, you need to change in all the needed places.

### Long Function

A long function that is broken into small functions is better to debug, maintain and understand.

### Long Param List

In case you are able to get all the needed params only with the help of one (per ex using an ID to get all the other params using a service), it is expected to be better since you will only need to maintain the method internal logic (and will avoid changing its param calling, etc).

### Global Data

Global data can be used by a lot of resources of our software and can be changed by everyone, so if you change it, you will need to change all the places that use it, it will be harder to know which resources are changing the global data, etc.

### Mutable Data

Data changes can result in unexpected issues and complex bugs (per example, I can change some data here without getting that the software expects something different in another place).

### Diverging Change

We usually try to structure our software in a way to make easier to change it. A divergent change happens when a module is frequently changed in a lot of ways for different reasons (per example, you look at a module and think "I will need to change these three functions everytime a new database arrives and so these financial module").

Being minded about it, try to keep things that change together in the same place/context.

### Resources Envy

We call it "resources envy" when a system module spends more time talking to another modules in another contexts instead of its own context.

When that happens, it probably means that this module does not belong to that context, so move it to the proper one (usually the one that is most used by that module).

### Primitive Obsession

Most of the programs are created using the native language types (such as array, map, string, number, etc). Sometimes it is good to have its own types in your system domain (per example, a type to represent a currency, coordinate, etc).

### Repetitive Switches

Sometimes it is good to use polymorphism instead a switch to handle how some kind of data need to be treated.

### Loops

Sometimes it is better to use pipeline methods (per example map and filter) to deal with the data instead creating a lot of loops to handle it.

### Idle Elements

Sometimes we create functions, methods in a expectation that it would be used but it is not. Since it will probably not be used, it is good to delete it.

### Generality Speculation

Most of the time that you think like "I think that we will need that kind of stuff some day", you are probably going to not need it. Most of the time you will create code that will be boring to maintain.

Being minded about that, try to do the following stuffs: Remove abstract classes that do not do anything; Remove useless delegations; Remove unused parameters from functions.

### Temporary Field

Sometimes you see a class that a field is defined rarely. A code like that is hard to understand since you will expect to need all the fields (trying to understand why the field does not exist when it looks like to not be used will drive you insane).

### Message Chain

A message chain happens when a client asks an object to another object, which client asks to another object, which client asks to another object and so on.

In these cases, if something change in the relation of one of the clients, a lot of things will need to change.

### Intermediate

One of the main characteristics of object orientation programming is the encapsulation. The encapsulation most of the time comes with delegation.

Sometimes you will look at a class interface and will get that half of its methods are delegating the calling to another class.

Being minded about it, try to call the delegated class directly.

### Hidden Exchanges

People that work with software usually like robust walls between the program modules and claim way too much about how data exchange increases the coupling.

In case the modules are rarely with each other, try to keep it separated, if not, try to create a third module that make that conversation.

### Big Classes

Try to break big classes into small modules.

### Alternative Classes With Different Interfaces

One of the most advantages of using classes is the substitution support, making it able to be exchanged by another classes when needed. But, it only works if the used interfaces are the same for these classes.

### Refused Inheritance

Subclasses inherit methods and data from its parents, but sometimes they receive everything from them, but only use little stuffs.

When that happens, it probably means the hierarchy is wrong.

### Comments

Avoid using comments due to a bad method/function code writing, instead, try to use it most of the time to explain routines and why you did something.

*"When feeling the need to write a comment, experiment to refactor the code before in a way the comment becomes useless"*

## Writing Tests

Refactoring is a important tool but most of the time it needs another tools to get better.

### The Importance of Auto Testable Codes

When you test something, you are assuming the way the the software behaves. So in case you change the behavior of something, you have a test that gives you feedback about it. What means that in case you are refactoring something and you introduces an old bug, you would receive an instant feedback about it.

### Getting into the boundaries

Sometimes it is good to make boundary tests to know what happens if something not probably supposed to go wrong to do that.

### The Good Test Suite

The better way to know if a test suite is good is your confidence level that in case someone introduces something bad in the code, the test will fail.

In case I can refactor the code while making sure that I did not introduce any bug because my tests gave green signal, so I can be grateful for having good tests.

