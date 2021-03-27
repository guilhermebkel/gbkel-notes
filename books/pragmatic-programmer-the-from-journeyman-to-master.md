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