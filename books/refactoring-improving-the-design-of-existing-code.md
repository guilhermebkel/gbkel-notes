# Refactoring: Improving the Design of Existing Code

## Summary

This book gives some tips about how/when to refactor software and the anything that revolves around it.

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

- **Comprehension Refactor - Getting the software easier to understand:** ...