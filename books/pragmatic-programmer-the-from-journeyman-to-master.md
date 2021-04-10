# Pragmatic Programmer, The: From Journeyman to Master

## Summary

This book gives some tips to improve your career in the technical and personal field by a solid and practical knowledge.

## A Pragmatic Philosophy

In general, the pragmatic programmer has a different attitude, style and philosophy of approaching problems and their solution.

They think beyond the immediate problem, placing it in its larger context and seeking out the bigger picture.

They take responsibility for everything they do, what means they will not sit idly by and watch their projects fail apart through neglect.

In the end, pragmatic programming stems from a philosophy of pragmatic thinking and there are a lot of tips of how to improve on that.

### It's your life

*"I'm not in this world to live up to your expectations and you're not in this world to ive up to mine - Bruce Lee"*

Software development must appear close to the top of any list of careers where you have control and so, per example:

> If you feel like you are stagnating on your job, you can change it by studying by yourself when you are able to.
>
> If you want to work remotely, try to find a job that make you able to do that.

### It's not my problem

*"The greatest of all weaknesses is the fear of appearing weak - J.B Bossuet"*

One of the most important things about pragmatic philosophy is to take responsibility of your career advancement, your learning and education, your project, and your day-to-day work. It basically means that pragmatic programmers are not afraid to admit ignorance or error.

> Try to avoid blaming someone or something else, or make up an excuse. Don't blame all the problems on a vendor, a programming language, management, or you coworkers. Any and all of these may play a role, but it is up to you to provide solutions, not excuses.

### Software Entropy

Entropy is a term from physics that refers to the amount of disorder in a system. Some folks might call it by the more optimistic term, "technical debt", with the implied notion that they will pay it back someday. They probably will not.

There are too many factors that can contribute to software rot. The most important one seems to be the psychology, or culture, at work on a project.

That way, we can understand that hopelessness inside a project can be contagious. A common and wrong think is "All the rest of this code is crap, I will just follow suit".

> Don't leave bad designs, wrong decisions, or poor code un-repaired. Fix each one as soon as it is discovered and, if there is insufficient time to fix it properly, then board it up.
>
> Don't cause collateral damage just because there is a crisis of some sort. One broken window is one too many.

### Be a Catalyst for Change

*"People find it easier to join an ongoing success. Show them a glimpse of the future and you will get them to rally around"*

Sometimes you can be on a situation where you know exactly what need doing and how to do it, but after asking permission to tackle the whole thing you will probably be met with delays and blank stares. People will form committees, budgets will need approval, and things will get complicated. Everyone will guard their own resources.

> Work out what you can reasonably ask for. Develop it well. Once you've got it, show people, and let them marvel.
>
> Constantly review what is happening around you, not just what you personally are doing.

### Good-Enough Software

*"Striving to better, oft we mar what's well - Shakespeare"*

Usually the real world just will not let us produce much that is truly perfect, particularly not bug-free software. Time, technology, and temperature all conspire against us.

The phrase "good enough" does not imply sloppy or poorly produced code. All systems must meet they users requirements to be successful, and meet basic performance, privacy, and security standards.

> Try to put some users to test the software, because that way you will find what is the good enough software.
>
> You can discipline yourself to write software that's good enough - good enough for users, for future maintainers, for you own peace of mind. You will find that you are more productive and your users are happier.
>
> Try to make quality a requirements issue.
>
> Know when to stop, don't spoil a perfectly good program by overembellishment and overrefinement. Move on, and let your code stand in its own right for a while. It may not be perfect. Don't worry: it could never be perfect.

### Your knowledge portfolio

*"An investment in knowledge always pays the best interest - Benjamin Franklin"*

Your knowledge and experience are your most important day-to-day professional assets. Unfortunately, they are expiring assets, so, your knowledge becomes out of date as new techniques, languages, and environments are developed.

Your ability to learn new things is your most important strategic asset.

> Try to invest regularly in your knowledge portfolio by studying new topics you find to be good.
>
> Try to diversify your knowledge, because the more things you know, the more valuable you are.
>
> Critically analyze what you read and hear, try to ask "why", dig deeper, ask "why" again, and so on, till you go down some abstraction layers on a topic (Who does this benefit? What's the context? When or Where would this work? Why is this a problem?).

### Communicate

*"I believe that it is better to be looked over than it is to be overlooked - Mae West"*

As developers, we have to communicate on many levels. We spend hours in meetings, listening and talking. We work with end users, trying to understand their needs. We write code, which communicates out intentions to a machine and documents our thinking for future generations of developers. We write proposals and memos requesting and justifying resources, reporting our status, and suggesting new approaches. And we work daily within our teams to advocate our ideas, modify existing practices, and suggest new ones.

> Know your audience, you are communicating only if you are conveying what you mean to convey. So try to communicate in a way your audience understands you.
>
> Try to show your idea in a easier way to understand, by making a lot of use of drawings and even by sorting out the topic you want to talk about (introduction, development, conclusion).

## A Pragmatic Approach

There are a lot of tips we can follow in order to become a pragmatic programmer. Some of them will be shown below:

### The Essence of Good Design

There are a lot of "rules" to follow when it comes to design good software. You will notice that most of them leads to a design that is easy to change (Decoupling, Single Responsibility Principle, Naming).

> Usually a good designed code/architecture is easier to change than bad design, what means that you have flexibility to change something later. Most of the time it will help you taking paths during software development.
>
> Try to think "Did the thing I just did make the overall system easier or harder to change?"

### Don't Repeat Yourself

In our day-to-day work, while creating features, doing some maintenance on the system, it gets easier to duplicate knowledge (business rules).

Knowledge duplication is considered to be a bad thing since if you change it in some place, you will have to change in another as well since it is duplicated. If you forget to change on all places, you will probably face a bug on your production environment.

> Every piece of knowledge must have a single, unambiguous, authoritative representation within a system.
>
> DRY is about the duplication of knowledge, of intent. It's about expressing the same thing in two different places, possibly in two totally different ways.
>
> All services offered by a module should be available through a uniform notation, which does not betray whether they are implemented through storage or through computation.
>
> Make sure the knowledge you write is easy to find and reuse existing stuff than to write it yourself.

### Orthogonality

In computing, two or more things are orthogonal if changes in one do not affect any of the others.

In case a change affects an unrelated part of the system, you will probably face bugs on production.

> Try to avoid creating side effects between unrelated things. It means that you must write code in a way that you mix same contexts and not different contexts.
>
> Try to design components that are self-contained: independent, and with a single, well-defined purpose.
>
> Try to draw the architecture design and think if some unrelated part of it changes another. That way you will be able to architecture code in a orthogonality way.
>
> Keep your code decoupled, avoid global data, avoid similar functions.
>
> Get into the habit of being constantly critical of your code. Look for any opportunities to reorganize it to improve its structure and orthogonality (it is what we call refactoring).

### Reversibility

*"Nothing is more dangerous than an idea if it's the only one you have - Emil-Auguste Chartier"*

There is always more than one way to implement something, and there is usually more than one vendor available to provide a third-party product.

If you go into a project hampered by the myopic notion that there is only one way to do it, you may be in for an unpleasant surprise.

With reversibility, we are able to create our own implementation for third part integrations of our system and make it more flexible for future changes.

> Try to create an interface on the front of specific part of your system (such as database implementations, etc).
>
> Try to think about maintaining flexibility in the areas of architecture, deployment, and vendor integration.

### Tracer Bullets

*"Ready, fire, aim... - Anon"*

*"Thinking before doing - Guilherme Mota"*

We use the term tracer bullet development to visually illustrate the need for immediate feedback under actual conditions with a moving goal.

The tracer code approach has many advantages: **Users get to see something working early, Developers build a structure to work in, You have an integration platform, You have something to demonstrate, You have a better feel for progress.**

> Look for the important requirements, the ones that define the system. Look for the areas where you have doubts, and where you see the biggest risks. Then prioritize your development so that these are the first areas you code.
>
> Focus on doing the important stuffs for the system to work and so, later on you can do the improvements.
>
> You will not always hit the target, so you just have to adjust your aim until you hit it. Sometimes the user will not like the layout, the data will not be available for you, the system will bad perform, but the only thing you need to do is to adjust your changes to improve all of that.
>
> Tracer code is lean but complete, and forms part of the skeleton of the final system. Think of prototyping as the reconnaissance and intelligence gathering that takes place before a single tracer bullet is fired.

### Prototypes and Post-it Notes

Prototypes must be a simple way to test your ideas, so it means that you do not need to write code to that. Sometimes the only thing you need to do is to create a drawing or doing manual stuffs.

Common things to be prototyped: **Architecture, New functionality in an existing system, structure or contents of external data, third-party tools or components, performance issues, user interface design.**

Some questions you are able to answer: **Are the responsibilities of the major areas well defined and appropriate? Are the collaborations between major components well defined? Is coupling minimized? Can you identify potential sources of duplication? Are interface definitions and constraints acceptable? Does every module have an access path to the data it needs during execution? Does it have that access when it needs it?**

> Prototype to learn.
>
> When prototyping, you can ignore: Correctness, completeness, robustness, style.

### Domain Languages

*"The limits of language are the limits of one's world. - Ludwig Wittgenstein"*

Computer languages influence how you think about a problem, and how you think about communicating.

Sometimes pragmatic programmers can actually program using the vocabulary, syntax and semantics of the domain.

> When programming in some language, try to write the code closer to that domain language, per example, if you programmed in Java fro 10 years and start learning LUA, you will try to apply domain concepts of Java on it, but the correct stuff to do is to get into the LUA domain without trying to write Java on it.

### Estimating

By learning to estimate, and by developing this skill to the point where you have an intuitive feel for the magnitudes of things, you will be able to show an apparent magical ability to determine their feasibility.

The first part of any estimation exercise is building an understanding of what is being asked.

> When someone asks for an estimate, try to ask yourself: Do they need high accuracy, or are they looking for a ballpark figure?
>
> Try to build a model for what is being estimate (write down the requirements and everything that need to be done in order to get it to work).

## The Basic Tools

In everything we do on our life, most of the time we are able to use some tools to help us increasing productivity or even quality.

### IDE

An IDE is an example of a tool that help us a lot when programming, since we can use a lot of shortcuts to deal with code and even some plugins to help us understand lots of things.

> Always be on the lookout for better ways of doing things.
>
> Try to achieve editor fluency.
>
> Try to learn the IDE commands that make your life easier.

### Version Control

*"Progress, far from consisting in change, depends on retentiveness. Those who can not remember the past are condemned to repeat it. - George Santayana"*

One of the most important tools are the ones that help you making code version control, since if you change to a version that broken everything, you can turn it back and even debug which version caused it.

Usually we use **Git** for versioning our code, it keeps in track every code line change made by everyone that is contributing to some code repository.

### Debugging

*"It is a painful thing to look at your own trouble and know that you yourself and no one else has made it. - Sophocles"*

On our day-to-day work, we will always encounter bugs during the programming process, so embrace the fact that debugging is just problem solving, and attack it as such.

Beware of myopia when debugging. Resist the urge to fix just the symptoms you see: it is more likely that the actual fault may be several steps removed from what you are observing, and may involve a number of other related things. Always try to discover the root cause of a problem, not just this particular appearance of it.

Sometimes by forcing yourself to isolate the circumstances that display the bug, you will even gain an insight on how to fix it. The act of writing the test informs the solution.

Sometimes you need to watch the state of a program or a data structure over time. You can do that by simply logging variables after executions.

A very simple but particularly useful technique for finding the cause of a problem is simply to explain it to someone else.

If you "changed only one thing" and the system stopped working, that one thing was likely to be responsible, directly or indirectly, no matter how farfetched it seems.

When you come across a surprise bug, beyond merely fixing it, you need to determine why this failure was not caught earlier. Consider whether you need to amend the unit or other tests so that they would have caught it.

A debugging checklist:
- Is the problem being reported a direct result of the underlying bug, or merely s symptom?
- Is the bug really in the framework you are using? Is it in the OS? Or is it in your code?
- If you explained this problem in detail to a coworker, what would you say?
- If the suspect code passes its unit tests, are the tests complete enough? What happens if you run the tests with this data?
- Do the conditions that caused this bug exist anywhere else in the system? Are there other bugs still in the larval stage, just waiting to hatch?

> It does not really matter whether the bug is your fault or someone else's. It is still your problem.
>
> You may need to interview the user who reported the bug in order to gather more data than you were initially given.
>
> You must brutally test both boundary conditions and realistic end-user usage patterns. You need to do this systematically.
>
> Read the error message. Most of the time just reading when the exception happened will give you a beautiful insight about what need to be done.
>
> Don't assume what caused the bug but prove it.

### Engineering Daybooks

Usually on our day-to-day work we will be in touch with insights, talks and a lot of important information that can be forgot. Being minded about that, it is a good practice to write down theses ideas in other to get back to then later.

The main benefits of a daybook is:
- It is more reliable than memory.
- It gives you a place to store ideas that are not immediately relevant to the task at hand.
- It acts as a kind of rubber duck. When you stop to write something down, your brain may switch gears, almost as if talking to someone. You may start to make a note and then suddenly realize that what you had just done, the topic of the note, is just plain wrong.
- Every now and then you can look back at what you were doing sometime ago.

## Pragmatic Paranoia

Perfect software does not exist. No one in the brief history of computing has ever written a piece of perfect software.

Pragmatic programmers try to drive defensively. We look out for trouble before it happens, anticipate the unexpected, and never put ourselves into a position from which we can not extricate ourselves.

Pragmatic programmers take a step further when writing software. We don't trust ourselves, either. Knowing that no one writes perfect code, including ourselves, we build in defenses against our own mistakes.

### Design by Contract

*"Nothing astonishes men so much as common sense and plain dealing. - Ralph Waldo Emerson"*

Dealing with computer systems is hard. Dealing with people is even harder. One of the best solutions for ensuring plain dealing is the contract.

A contract defines your rights and responsibilities, as well as those of the other party.

Designing by contract is a simple yet powerful technique that focuses on documenting (and agreeing to) the rights and responsibilities of software modules to ensure program correctness. A correct program is the one that does no more and no less than it claims to do. Documenting and verifying that claim is the heart of **Design by Contract**.

Every function and method in a software system does something. Before it starts that something, the function or method may have some expectation about the state of the world:

- **Preconditions:** What must be true in order for the routine to be called; the routine requirements. A routine should never get called when its preconditions would be violated. It is the caller's responsibility to pass good data.

- **Postconditions:** What the routine is guaranteed to do; the state of the world when the routine is done. The fact that the routine has a postcondition implies that it will conclude: infinite loops are not allowed.

- **Class invariants:** A class ensures that this conditions is always true from the perspective of a caller. During internal processing of a routine, the invariant may not hold, but by the time the routine exists and control returns to the caller, the invariant must be true.

- **Semantic invariants:** In case there is a requirement that qualifies, it needs to become a well-known part of whatever documentation that are being produced to the software. *Ex: Error in favor of the consumer*.

The contract between a routine and any potential caller can thus be read as if all the routine's preconditions are met by the caller, the routine shall guarantee that all postconditions and invariants will be true when it completes.

### Dead programs tell no lies

All errors give us information. Pragmatic programmers believe that if there is an error, something very, very bad has happened.

One way of detecting problems earlier is by crashing the application when an error happens instead of handling it.

When your code discovers that something that was supposed to be impossible just happened, your program is no longer viable. Anything it does from this point forward becomes suspect, so terminate it as soon as possible. A dead program normally does a lot less damage than a crippled one.

### Assertive Programming

*"There is a luxury in self-reproach. When we blame ourselves we feet no one else has a right to blame us. - Oscar Wilde"*

There is a mantra that every programmer must memorize early in his or her career that comes from the idea of *"This can never happen..."*.

Examples:
- "This application will never be used abroad, so why internationalize it?"
- "Count can not be negative"
- "Logging can not fail"

We need to avoid this kind of self-deception when coding. Whenever you find yourself thinking "but or course that could never happen", add code to check it. The easiest way to do this is with assertions.

### How to Balance Resources

*"To light a candle is to cast a shadow... - Ursula K. Le Guin"*

We all manage resources whenever whe code: memory, transactions, threads, network connections, files, timers, etc. Most of the time, resource usage follows a predictable pattern: you allocate the resource, use it, and the deallocate it.

Some tips for routines that need more than one resource at a time:

- Deallocate resources in the opposite order to that in which you allocate them. That way you won't orphan resources if one resource contains references to another.

- When deallocating the same set of resources in different places in your code, always allocate them in the same order. This will reduce the possibility of deadlock.

> The function or object that allocates a resource should be responsible for deallocating it.

### Don't Outrun Your Headlights

*"It's tought to make predictions, especially about the future. - Lawrence "Yogi" Berra"*.

In software development, we can't see too far ahead into the future, and the further off-axis you look, the darker it gets. Being minded about that, *pragmatic programmers take small steps - always*.

Some feedback examples:

- Result in a REPL provide feedback on your understanding of APIs and algorithms.

- Unit tests provide feedback on your last code change.

- User demo and conversation provide feedback on features and usability.

> Always take small, deliberate steps, checking for feedback and adjusting before proceeding. Consider that the rate of feedback is your speed limit. You never take on a tep or a task that's too big.
>
> Instead of wasting effort designing for an uncertain future, you can always fall back on designing your code to be replaceable. Make it easy to throw out your code and replace it with something better suited. Making code replaceable will also help with cohesion, coupling, decoupling, and DRY, leading to a better design overall.

## Bend, or Break

Life doesn't stand still. Neither can the code that we write. In order to keep up with today's near-frantic pace of change, we need to make every effort to write code that's *as loose - as flexible - as possible*. Otherwise we may find our code quickly becoming outdated, or too brittle to fix, and may ultimately be left behind in the mad dash toward the future.

A good way to stay flexible is to write less code. Changing code leaves you open to the possibility of introducing new bugs.

### Decoupling

*"When we try to pick out anything by itself, we find it hitched yo everything else in the Universe. - John Muir"*.

Coupling is the enemy of change, because it links together things that must change in parallel. This makes change more difficult: either you spend time tracking down all the parts that need changing, or you spend time wondering why things broke when you changed "just one thing" and not the other things to which it was coupled.

When you're designing bridges, you want them to hold their shape; you need them to be rigid. But when you're designing software that you'll want to change, you want exactly the opposite: you want it to be flexible. And to be flexible, individual components should be coupled to as few other components as possible.

Some symptoms of coupling:

- Wacky dependencies between unrelated modules or libraries.

- "Simple" changes to one module that propagate through unrelated modules in the system or break stuff elsewhere in the system.

- Developers who are afraid to change code because they are not sure what might be affected.

- Meetings where everyone has to attend because no one is sure who will be affected by a change.

Some tips to avoid coupling:

- "Tell, Don't ask". This principle says that you should not make decisions based on the internal state of an object and then update that object.

- "The law of Demeter". A method defined in a class should only call: Other instance methods; its parameters; methods in objects that it creates, both on the stack and in the heap; global variables.

- "Don't Chain Method Calls". Only use chaining with things that are expected not to change most of the time.

- "Avoid global variables". Each piece of global data acts as if every method in your application suddenly gained an additional parameter: after all, that global data is available inside every method.

### Juggling the Real World

*"Things don't just happen; they are made to happen. - John F. Kennedy"*.

Today we expect that computers have to integrate into our world, not the other way around. And our world is messy: things are constantly happening, stuff gets moved around, we change our minds, ... And the applications we write somehow have to work out what to do.

**Events**

An event represents the availability of information. It might come from the outside world: a user clicking a button, or a stock quote update. It might be internal: the result of a calculation is ready, a search finishes. It can even be something as trivial as fetching the next element in a list. Whatever the source, if we write applications that respond to events, and adjust what they do based on those events, those applications will work better in the real world. Their users will find them to be more interactive, and the applications themselves will make better use of resources.

There are some strategies that help achieving the event idea:

- **Finite State Machines:** A state machine is basically just a specification of a set of states, one of which is the current state. For each state, we list the events that are significant to that state. For each of those events, we define the new current state of the system.

- **The Observer Pattern:** In the observer pattern we have a source of events, called the observable and a list of clients, the observers, who are interested in those events.

- **Publish/Subscribe:** ...
