# Clean Architecture: A Craftsman's Guide to Software Structure and Design

## Summary

This book gives some tips about how to develop scalable and flexible software.

## Introduction

The main goal of software architecture is to minimize the human resources required to build and maintain a required system.

Software architecture is important to create good coding foundations easy to maintain without spending a lot of time or being stuck and not able to change anything if it was done in a poor way.

The measure of a good design quality is simply the measure of the effort required to meet the needs of the customer. If the effort is low and stays low throughout the lifetime of the system, the design is good. If that effort grows with each new release, the design is bad.

## Important Tips

- Since the architecture needs to be flexible almost all the time in order to provide a good environment for change, it should be as shape agnostic are practical.

- Worrying about a architecture is a must when building a core software that needs scale for a long life-time.

- You do not need a specific language paradigm to use the clean architecture principles (but some times some paradigms can help implementing some good patterns).

- If you are using external libraries on your software, instead of importing them directly to the code, make an adapter for them (wrapper function/class that implements this library) and use this adapter, in order to decrease coupling the system from external libraries (it makes the system flexible to change this library without breaking other modules).

- Even if use cases are too much equal in functionality, try to avoid coupling them, instead of doing that, make them separately and wait for the time to passes by (sometimes we see that use cases does the same thing and so we try to couple it, but, after some time you will notice that these use cases were different from each other and you will have to separate them, what is really hard to do).

- A good architecture should worry about decoupling layers, like decoupling use cases, hardware from software.

- Try to make sure that your UseCases/Entities only receives input data that it understands and outputs a result based on that (avoid passing a request object directly to it per example).

- Try to give names that make sense for your UseCases/Entities (we call ly Screaming Architecture because we just have to look at the name of stuffs and we will understand what each thing means). Your architecture should tell readers about the system, not about the frameworks you used in your system - "frameworks are tools, not ways of life".

- Avoid passing boundary-formed-data across boundaries. For example, many database frameworks return a convenient format in response to a query. We might call this a "row structure". We don't want to pass that row structure inward across a boundary. Doing so would violate the Dependency Rule because it would force an inner circle to know something about an outer circle.

## Design Principles

We have some principles provided by SOLID that tells us how to arrange our functions and data structures into classes and how those classes should be interconnected (classes refers not only to the OO paradigm, but everything that is grouped that way). The goal of it is to create software structures that tolerate changes, are easy to understand and provided a good basis to be used by many software systems.

### 1. SRP: The Single Responsibility Principle

Usually we can divide our software into modules (called domains or contexts). This principle tells us the importance of making sure that a module is only responsible for only one actor.

Ex: If I have a picture service, probably it could own at least the following modules:

- **Macro:** Picture, User, Plan, etc.
- **Micro:** PictureUpload, UserAccount, UserPlan, etc.

So, it is important to divide the software into modules that has a related core actor. That way we can make sure that a change does not affect something that has nothing related to that (so we avoid bugs and useless coupling).

### 2. OCP: The Open-Closed Principle

That principle tells us that a software should be open for extension but closed for modification. Being minded about it, if simple extensions to the requirements force massive changes to the software, we have an architecture problem here.

Ex: When adding a new feature to the software, I will write new code and expect to change no old code at all (when we have to change old code we increase the chance of creating bugs and decrease the productivity).

So, one way to improve the use of this principle is by applying the single responsibility and being minded about separating software into modules that can change without affecting any other (basically partitioning the system into components, and arranging those components into a dependency hierarchy that protects higher-level components from changes in lower-level components).

### 3. LSP: The Liskov Substitution Principle

Usually when we have lot of modules inside our software, it is really easy to have ones implementing a service that returns the same response but can vary its internal business rules. Then, this principle shows us the importance of implementing this services with use of interfaces, in order to be able to easily change the service types without having to change existent classes.

Ex: I have a CustomerUploadService (1) and a PictureUploadService (2). These services implements the same UploadServiceInterface that helps handling multiple UploadServices: the UploadService used by (1) uploads to Dropbox and the (2) uploads to AWS S3 (input/response params are equal, but the business logic inside it vary by each service type).

So, when we have a component that is used by lot of other components and it need to vary its internal business rules, it is important to create generic interfaces that implements these components. That way we decrease coupling, bugs and improve cohesion, maintainability (we don't have to create a new if/else statement inside the same service to handle multiple business logics, so that's obviously something good for future maintains).

### 4. ISP: The Interface Segregation Principle

In some languages, we can avoid deploying small unrelated modules when we change a big module (that sometimes own these small unrelated modules). So, this principle tells us the importance of implementing parts of the components with help of interface segregation in order to *avoid depending on something that you don't need and so avoid troubles that you didn't expect*.

Ex: A CustomerService that implements the following interfaces for its internal methods: CreateCustomer (CustomerService.create), UpdateCustomer (CustomerService.update), DeleteCustomer (CustomerService.delete).

So, that way we can make sure that specific use cases only has access to the needed methods (Ex: If I have a CreateCustomerUseCase, he only needs to care about the CreateCustomer interface, so I will probably implement the CustomerService inside it with the needed interface).

### 5. DIP: The Dependency Inversion Principle

This principle tells us that the most flexible systems are those in which source code dependencies refer only to abstractions, not to concretions. So, one of the main goals is being able to change concrete implementations (to add a functionality per example) without making changes to the interfaces they implement (that way we can avoid changing old code of the components that implement that interface). Being minded about it, we have the following set of good practices:

**1. Don't refer to volatile concrete classes:** Refer to abstract interfaces instead.

**2. Don't derive from volatile concrete classes:** Create new implementations.

**3. Don't override concrete functions:** Create new implementations.

**4. Never mention the name of anything concrete and volatile:** Import a wrapper function/class instead.

So, that way we can make sure that our software code is not coupled directly to volatile implementations and we can avoid changing old code / breaking old implementations.

## Components Principles

Components are the smallest entities that can be deployed separately as part of the system. It means that a component is a group of entities that share the same context.

Suppose we have a context called **Picture**, so we can say that we have a **PictureComponent** that is composed by **PictureController, PictureService, PictureRepository and PictureModel**.

This idea of components came from some problems developers experienced in the future, an example was the application growing a lot that it was really expensive to make deploys since they were slowing so much.

That way, by separating the system into components can help us deploying the part of the system we want to. If components are deployed separately and they are reused all around the application, it is important to give them a version number (Ex: PictureComponent v1.0.2) in order to help other developer teams that are implementing this component to only use the version they are braced for.

### Components Cohesion

We should look for components cohesion, that are basically the idea that the classes and modules that are formed into a component must belong to a cohesive group (it can not be composed of random classes and modules).

**1. The Common Closure Principle**

Try to gather into components those classes that change for the same reasons and at the same times. Separate into different components those classes that change at different time and for different reasons.

In some systems, maintainability is more important than reusability. Being minded about that, you should sometimes worry about confining changes to a single component instead of having to change multiple at a time.

**2. The Common Reuse Principle**

Try not to force users of a component to depend on things they don't need. It states that classes and modules that tend to be reused together belong in the same component.

### Components Coupling

Sometimes we will need to deal with component coupling, that is basically the idea that some components can have a link between them. In order to help getting the best of it, we have some principles to think about.

**1. The Acyclic Dependencies Principle**

Try to not allow no cycles in the component dependency graph. It basically tell us that it is important to keep a dependency relationship flow that goes from higher-level entities to lower-level entities, avoiding to do that upside down as well.

**2. The Stable Dependencies Principle**

Try to depend in the direction of stability. It basically shows us that it is better to depend on things that rarely changes (so we can call them 'stable'), since by doing that, it is less likely to change all the dependent entities.

**3. The Stable Abstractions Principle**

A component should be as abstract as it is stable. Since we want to keep business rules on high level entities, without making all the system being stuck and stable forever, it is good to make use of abstractions (usually with use of interfaces), that way we can make entities more flexible and extensible (that way the dependencies run in the direction of abstraction and not to concrete classes).

## Architecture

### What is architecture?

The architecture of the system is the shape given to that system by those who build it. The form of that shape is in the division of that system into components, the arrangement of those components, and the ways in which those components communicate with each other.

The purpose of that shape is to facilitate the development, deployment, operation and maintenance of the software system contained within it.

The main strategy behind that facilitation is to leave as many options open as possible (maximizing the number of decisions not made), for as long as possible (what means that is really good to make the software flexible enough to work while giving that change to take some important decisions later, since you will have more knowledge about it).

Usually good architecture makes the system easy to understand, easy to develop, easy to maintain and easy to deploy. The ultimate goal is to minimize the lifetime cost of the system and to maximize programmer productivity.

### What a good architecture should support?

**1. The use cases of the system**

The architecture of the system must support the intent of the system. Per example, if the system is a shopping cart application, then the system must support shopping cart use cases.

A shopping cart application with a good architecture will look like a shopping cart application, its use cases will be plainly visible on the system structure and the developers will not have to hunt for behaviors since them will be elements visible at the top level of the system with names that clearly describe their function.

**2. The operation of the system**

If the system must handle 100.000 customers per second, the architecture must support that. If the system must query big data in milliseconds, the architecture must be structure to handle it.

Sometimes it means breaking down the system into processes, threads or even microservices, but, that's a good decision to try to leave open for a long time since you are totally sure about what you are doing.

So, a way to leave this operational decision open is to make an architecture that maintains the proper isolation of its components and not assume the means of communication between those components. That way it will be much easier to break the components down into threads, processes or microservices as the operation needs of the system change over time.

**3. The maintenance of the system**

Every system should be easy to maintain and keep working with little effort. So, try to use some of the best practices of architecture when building the system.

**4. The development of the system**

Any organization that designs a system will produce a design hose structure is a copy of the organization's communication structure.

If a system is being developed with many teams and many concerns, it is important to facilitate independent actions by those teams (so that the teams do not interfere with each other during development).

**5. The deployment of the system**

The goal here is to make a deployment of the system with a single action (without having to execute dozens of scripts).

### Boundaries

We make use of boundaries to separate software elements from one another, and restrict those on one side from knowing about those on the other. Ex: 
- A GUI does not matter to the business rules, so there should be a boundary between them.
- The type of database being used does not matter to business rules, so there should be a boundary between them. 

Some boundaries are drawn very early in the project and others later. The early ones usually are made in order to defer decisions for as long as possible and avoiding those decisions from polluting the core business logic.

Usually to do that boundaries we make the communication of all the sides with help of interfaces. The use of boundaries creates a pattern described as **Plugin architecture**.

Then, a clearly example of a Plugin architecture should be: You have a **Business Rule Module** that is used by a **GUI Module** and a **Database Module**. That way we can make sure that any change we make to outside modules, will not break any business rule or anything that is important for the system to work.

It is very easy when we are dealing with boundaries inside a monolith (since the communications are made only with function calls). The complexity increases when we start making boundaries with threads, local processes and services.

### Policy and Level

Usually the policy is broken down into smaller statements that tell us how some particular business rules are calculated, other tell us how certain reports are to be formatted even others describe how input data are to be validated.

Usually we need to part this policies one from another and group the ones that change for the same reason and the same times (we should keep them in the same component).

When we talk about levels, we are saying that policies can be organized in different levels. Usually the policies that deal with data input/output are on the lower level of policy.

If we create a Encrypt application, it should be organized by policies and levels that way below:
```sh
----------------------------------------- Boundary
             (Encrypt)
        _________|_________
       |                   |
 (Char Reader)       (Char Writer)        # Interfaces
       |                   |
----------------------------------------- Boundary
       |                   |
(Console Reader)    (Console Writer)	  # Plugins
```

### Business Rules

Strictly speaking, business rules are rules of procedures that make or save the business money (it does not matter if is make manually or on a computer).

Usually we divide business rules into objects with the following names:

**1. Entity**

Usually the business rules that are critical to the business itself and would exist even if there were no system to automate them, are called **Critical Business Rules**, and they usually require some data to work with that are called **Critical Business Data**.

The critical business rules are implemented by objects that we call **Entities**. They can access business data really fast and have functions that implement the Critical Business Rules that operate on that data. So, entities are pure business rules and nothing else.

An example of Entity could be a **LoanEntity** that uses the Business Data: **principle, rate, period** and has the Functions/Methods: **makePayment, applyInterest and chargeLateFee**.

**2. UseCases**

Some business rules make or save money for the business by defining and constraining the way that an automated system operates. These rules would not be used in a manual environment, because they make sense only as part of an automated system.

Usually use cases define application-specific business rules as opposed to the Critical Business Rules within Entities.

An example of UseCase could be a **CreateCustomerUseCase** that has a validation inside it to make sure each customer has a unique email value.

So, the use cases define the application-specific rules that govern the interaction between the users and the Entities.

### Clean Architecture

Being minded about the clean architecture, usually the systems that has  been implemented this way has some of the characteristics below:

**1. Independent of frameworks:** Frameworks should be used as tools and should not force you to follow an architecture.

**2. Testable:** The business rules can be tested without UI, database, web server or any other external element.

**3. Independent of the UI:** The UI can change easily without changing the rest of the system.

**4. Independent of the Database:** Your business rules are not bound to the database, so you can swap between them.

**5. Independent of any external agency:** Your business rules don't know anything at all about the interfaces to the outside world.

Being minded about it, an example of a well constructed clean architecture in a hierarchy would be the one that follows the Dependency Rule - "Source code dependencies must point only inward, toward higher level policies":

```sh
# Enterprise Business Rules
Entities                    
--------------------------- Boundary 1
# Application Business Rules
UseCases
--------------------------- Boundary 2
# Interface Adapters
Controllers
Gateways
Presenters
--------------------------- Boundary 3
# Frameworks and Drivers
Devices
Web
UI
Database
External Interfaces
```

### Partial Boundaries

Completely created architectural boundaries are expensive. In many situations a good architect might judge that the expense of such a boundary is too high (but might still want to hold a place for such a boundary in case it is needed later).

This kind of anticipatory design is often frowned by many in the Agile community as a violation of YAGNI: "You aren't Going to Need It". Architects however, sometimes look at the problem and think "Yeah, but I might". In that case, they may implement a partial boundary.

One way to create a partial boundary is to start separating the system into boundaries and component, but all together in the same place (obviously you will use the amount of code you could use for a full boundary, but you will not have to worry about the administration of multiple components).

You are able to make sure the boundaries are partially with use of interfaces between them (usually expensive since you need a interface for each method) or you can even use **Facade Class** pattern which you have a Big class that implements each service that will be used by some boundary.

### Main Component

Every system should have a main component, usually it creates and starts all core dependencies of the system related to higher level policies.

Think of a Main Component of a Plugin, so you can have many main components, one for each configuration of your application (such as database, language, etc)

### Services: Great and Small

Services are just function call across process and/or platform boundaries. Usually that are some benefits implementing the use of services, but we'll take a look of some fallacies that revolve around it:

**1. The Decoupling Fallacy:**

One of the supposed benefits of breaking a system up into services is that services are strongly decoupled from each other.

There is certainly some truth to this, but not very much truth. Services are really decoupled at the level of individual variables, **however they can still be coupled by shared resources within a processor, or on the network**.

Per example, if a new field is added to a data record that is passed between services, then every service that operates on the new field must be changed (the data coupling make them coupled to each other services).

**2. The Fallacy of Independent Development And Deployment:**

Another of the suppose benefits of services is that they can be owned and operated by a dedicated team. This independence of development and deployment is presumed to be scalable, so a large enterprise can be created from dozens, hundreds of even thousand of independently developable and deployable services.

There is some truth to this belief, but only some. First, history has shown that large enterprise systems can be built from monoliths and component-based system as well as service-based systems. Thus services are not the only option for building scalable systems, since we can make independent development and deployment with help of some clean architecture patterns.