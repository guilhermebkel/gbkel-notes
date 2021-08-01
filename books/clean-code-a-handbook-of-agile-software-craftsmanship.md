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

<!--- Loc (Current: 845, End: 8278) --->