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