# Domain-Driven Design: Tackling Complexity in the Heart of Software

## Putting the Domain Model to Work

A model is a simplification. It is an interpretation of reality that abstracts the aspects relevant to solving the problem at hand and ignores extraneous detail.

Every software program relates to some activity or interest of its user. That subject area to which the user applies the program is the domain of the software.

Some domains involve the physical world: The domain of an airline-booking program involves real people getting on real aircraft.

Some domains are intangible: The domain of an accounting program is money and finance.

A model is a selectively simplified and consciously structured form of knowledge. An appropriate model makes sense of information and focuses it on a problem.

### The Utility of a Model in Domain-Driven Design

In domain-driven design, three basic uses determine the choice of a model.

**1. The model and the heart of the design shape each other:** It is the intimate link between the model and the implementation that makes the model relevant and ensures that the analysis that went into it applies to the final product, a running program. The binding of model and implementation also helps during maintenance and continuing development, because the code can be interpreted based on understanding the model.

**2. The model is the backbone of a language used by all team members:** Because of the binding of model and implementation, developers can talk about the program in this language. They can communicate with domain experts without translation. And because the language is based on the model, our natural linguistic abilities can be turned to refining the model itself.

**3. The model is distilled knowledge:** The model is the team's agreed-upon way of structuring domain knowledge and distinguishing the elements of most interest. A model captures how we choose to think about the domain as we select terms, break down concepts, and relate them. The shared language allows developers and domain experts to collaborate effectively as they wrestle information into this form. The binding of model and implementation makes experience with early versions of the software applicable as feedback into the modeling process.

### The Heart of Software

The heart of software is its ability to solve domain-related problems for its user. All other features, vital though they may be, support this basic purpose. When the domain is complex, this is a difficult task, calling for the concentrated effort of talented and skilled people.

## Crunching Knowledge

### Ingredients of Effective Modelling

**1. Binding the model and the implementation:** Making sure that during the implementation you apply model terms, business rules, etc.

**2. Cultivating a language based on the model:** Making sure anyone can take terms straight out of the model, organize them into sentences consistent with the structure of the model, and be unambiguously understood without translation.

**3. Developing a knowledge-rich model:** The objects have behavior and enforced rules. The model is not just a data scheme; it is integral to solving a complex problem. It captures knowledge of various kinds.

**4 Distilling the model:** Important concepts are added to the model as it becomes more complete, but equally important, concepts are dropped when they didn't prove useful or central. When a unneeded concept is tied to one that is needed, a new model is found that distinguishes the essential concept so that the other could be dropped.

**5. Brainstorming and experimenting:** The language, combined with sketches and a brainstorming attitude, turns out discussions into laboratories of the model, in which hundreds of experimental variations can be exercised, tried, and judged. As the team goes through scenarios, the spoken expressions themselves provide a quick viability test of a proposed model, as the ear can quickly detect either the clarity and ease or the awkwardness of expression.

### Knowledge Crunching

Financial analysts crunch numbers. They sift through reams of detailed figures, combining and recombining them looking for the underlying meaning, searching for a simple presentation that brings out what is really important - an understanding that can be the basis of a financial decision.

Effective domain modelers are knowledge crunchers. They take a torrent of information and probe for the relevant trickle. They try one organizing idea after other, searching for the simple view that makes sense of the mass. Many models are tried and rejected or transformed. Success comes in an emerging set of abstract concepts that makes sense of all the detail. This distillation is a rigorous expression of the particular knowledge that has been found most relevant.

In the old waterfall method, the business experts talk to the analysts, and analysts digest and abstract and pass the result to the programmers, who code the software. This approach fails because it completely lacks feedback. The analysts have full responsibility for creating the model, based only on input from the business experts. They have no opportunity to learn from the programmers or gain experience with early versions of software. Knowledge trickles in one direction, but does not accumulate.

Other projects use an iterative process, but the fail to build up knowledge because they don't abstract. Developers get the experts to describe a desired feature and then they go build it. They show the experts the result and ask what to do next. If the programmers practice refactoring, they can keep the software clean enough to continue extending it, but if programmers are not interested in the domain, they learn only what the application should do, not the principles behind it.

The constant refinement of the domain model forces the developers to learn the important principles of the business they are assisting, rather than to produce functions mechanically.

### Continuous Learning

When we set out to write sofwtare, we never know enough. Knowledge on the project is fragmented, scattered among many people and documents, and it's mixed with other information so that we don't even know which bits of knowledge we really need.

Domains that seem less technically daunting can be deceiving: we don't realize how much we don't know. This ignorance leads us to make false assumptions.

Meanwhile, all projects leak knowledge. People who have learned something move on. Reorganization scatters the team, and the knowledge is fragmented again.

Highly productive teams grow their knowledge consciously, practicing continuous learning. For developers, this means improving technical knowledge, along with general domain-modeling skills. But it also includes serious learning about the specific domain they are working in.

### Knowledge-Rich Design

Business activities and rules are as central to a domain as are the entities involved; any domain will have various categories of concepts. Knowledge crunching yields models that reflect this kind of sight. In parallel with model changes, developers refactor the implementation to express the model, giving the application use of that knowledge.

It is with this move beyond entities and values that knowledge crunching can get intense, because there may be actual inconsistency among business rules. Domain experts are usually not aware of how complex their mental processes are as, in the course of their work, they navigate all these rules, reconcile contradictions, and fill in gaps with common sense.

A domain model and corresponding design can be used to secure and share knowledge. The more explicit design has these advantages:

1. In order to bring the design to this stage, the programmers and everyone else involved will have come to understand the nature of overbooking as a distinct and important business rule, not just an obscure calculation.

2. Programmers can show business experts technical artifacts, even code, that should be intelligible to domain experts (with guidance) thereby closing the feedback loop.

### Deep Models

Useful models seldom lie on the surface. As we come to understand the domain and the needs of the application, we usually discard superficial model elements that seemed important in the beginning, or we shift their perspective. Subtle abstractions emerge that would not have ocurred to us at the outset but that pierce to the heart of the matter.

Knowledge crunching is an exploration, and you can't know where you will end up.

## Communication and the Use of Language

A domain model can be the core of a common language for a software project. The model is a set of concepts built up in the heads of people on the project, with terms and relationships that reflect domain insight. These terms and interrelationships provide the semantics of a language that is tailored to the domain while being precise enough for technical development. This is a crucial cord that weaves the model into development activity and binds it with the code.

This model-based communication is not limited to diagrams. To make most effective use of a model, it needs to pervade every medium of communication. It increases the utility of written text documents, as well as the informal diagrams and casual conversation reemphasized in Agile process. It improves communication through the code itself and through the tests for that code.

The use of language on a project is subtle but all-important.

### Ubiquitous Language

Domain experts have limited understanding of the technical jargon of software development, but they use the jargon of their field - probably in various flavors. Developers, on the other hand, may understand and discuss the system in descriptive, functional terms, devoid of the meaning carried by the experts language. Or developers may create abstractions that support their design but are not understood by the domain experts. Developers working on different parts of the problem work out their own design concepts and ways of scribing the domain.

On a project without a common language, developers have to translate for domain experts. Domain experts translate between developers and still other domain experts. Developers even translate for each other. Translation muddles model concepts, which leads to destructive refactoring of code. The indirectness of communication conceals the formation of schisms - different team members use terms differently but don't realize it. This leads to unreliable software that doesn't fit together. The effort of translation prevents the interplay of knowledge and ideas that lead to deep model insights.

A project faces serious problems when its language is fractured. Domains experts use their jargon while technical team members have their own language tuned for discussing the domain in terms of design.

The terminology of day-to-day discussions is disconnected from the terminology embedded in the code. And even the same person uses different language in speech and in writing, so that the most incisive expressions of the domain often emerge in a transient form that is never captured in the code or even in writing.

Translation blunts communication and makes knowledge crunching anemic. Yet none of these dialects can be a common language because none server all needs.

A project needs a common language that is more robust than the lowest common denominator. With a conscious effort by the team, the domain model can provide the backbone for that common language, while connecting team communication to the software implementation. That language can be ubiquitous in the team's work.

The vocabulary of that ubiquitous language includes the names of classes and prominent operations.

The model-based language should be used amont developers to describe not only artifacts in the system, but tasks and functionality.

By using a ubiquitous language, we are able to know if the model lacks something or not, or even if there is anything that needs to change inside it.

So, being minded about it, try to:

- Use the model as the backbone of a language. Commit the team to exercising that language relentlessly in all communication between within the team and in the code. Use the same language in diagrams, writing, and especially speech.

- Iron out difficulties by experimenting with alternative expressions, which reflect alternative models. Then refactor the code, renaming classes, methods, and modules to conform to the ned model. Resolve confusion over terms in conversation, in just the way we come to agree on the meaning of ordinary words.

- Recognize that a change in the ubiquitous language is a change to the model.

- Domain experts should object to terms or structures that are awkward or inadequate to convey domain understanding; developers should watch for ambiguity or inconsistency that will trip up design.

### Modeling Out Loud

Unfortunately, when people speak, they usually don't use the language of the domain model.

One of the best ways to refine a model is to explore with speech, trying out loud various constructs from possible model variations.

It is vital that we play around with words and phrases, harnesssing our linguistic abilities to the modelling effort, just as it is vital to engage our visual/spatial reasoning by sketching diagrams.

As we use the Ubiquitous Language of the domain model in discussions - especially the ones in which developers and domain experts hash our scenarios and requirements - we become more fluent in the language and teach each other its nuances.

So, being minded about it, try to:

- Play with the model as you talk about the system. Describe scenarios out loud using the elements and interactions of the model, combining concepts in ways to say what you need to say, and then take those new ideas back down to the diagrams and code.

### One Team, One Language

Technical people often feel the need to "shield" the business experts from the domain model. They say:

> "Too abstract for them."
>
> "They don't understand objects."
>
>"We have to collect requirements in their therminology."

These are just a few of the reasons for having two languages on the team. Forget them.

Of course there are technical components of the design that may not concern the domain experts, but the core of the model had better interest them. Too abstract? Then how do you know the abstractions are soung? Do you understand the domain as deeply as they do? Sometimes specific requirements are collected from lower-level users, and a subset of the more concrete terminology may be needed for them, but a domain expert is assumed to be capable of thinking somewhat deeply about his or her field.

- If sophisticated domain experts don't understand the model, there is something wrong with the model.

### Documents and Diagrams

Diagrams are a means of communication and explanation, and they facilitate brainstorming. They serve these ends best if they are minimal. Comprehensive diagrams of the entire object model fail to communicate or explain; they overwhelm the reader with detail and they lack meaning.

It leads us toward simplified diagrams of conceptually important parts of the object model that are essential to understanding the design. They simplify, explain, and even incorporate a bit of nonstandard notation when it clarifies their point. They show design specifications in every detail and represent the skeletons of ideas.

The vital detail about design is captured in the code. A well-written implementation should be transparent, revealing the model underlying it. Supplemental diagrams and documents can guide people's attention to the central points. Natural language discussion can fill in the nuances of meaning.

Always remember that the model is not the diagram. The diagram's purpose is to help communicate and explain the model. The code can serve as a repository of the details of the design.

#### Written Design Documents

Once a document takes on a persistent form, it often loses its connection with the flow of the project. It is left behing by the evolution of the code, or by the evoltuion of the language of this project.

**1. Documents Should Complement Code and Speech**

Each agile process has its own philosophy about documents. Extreme Programming advocates using no extra design documents at all and letting the code speak for itself.

This dependence on the code as communication medium motivates developers to keep the code clean and transparent.

But code as a design document does have its limits. It can overwhelm the reader with detail. Although its behavior is ambiguous, that doesn't mean it is obvious. And the meaning behind a behavior can be hard to convey.

**2. Documents Should Work for a Living and Stay Current**

The greatest value of a design document is to explain the concepts of the model, help in navigating the detail of the code, and perhaps give some insight into the model's intended style of use. Depending on the philosophy of the team, the whole design document could be as simple as a set of sketches posted on the walls, or it could be substantial.

Listen to the Ubiquitous Language and how it is changing. If the terms explained in a design document don't start showing up in conversations and code, the document is not fullfilling its purpose. Maybe the document is too big or complicated. Maybe it is not focused on a sufficiently important topic.

Conversely, you may hear the Ubiquitous Language changing naturally while a document is being left behind.

By keeping documents minimal and focusing them on complementing code and conversation, documents can stay connected to the project. Let the Ubiquitous Language and its evolution be your guide to choosing documents that live and get woven into the project's activity.

### Explanatory Models

One model should underlie implementation, design, and team communication. Having separate models for these separate purposes poses a hazard.

Models can also be valuable as education aids to teacha about the domain, but it may aid learning to have other views, used only as educational tools, to communicate general knowledge of the domain.

One particular reason that other models are needed is scope. The technical model that drives the software development process mustbe strictly pared down to the necessary minimum to fulfill its functions. An explanatory model can include aspects of the domain that provide context that clarifies the more narrowly scoped model.

Explanatory models offer the freedom to create much more communicative styles tailored to a particular topic. Visual metaphors used by the domain experts in a field often present clearer explanations, educating developers and harmonizing experts. Explanatory models also present the domain in a way that is simply different, and multiple, diverse explanations help people learn.

There is no need for explanatory models to be object models, and it is generally best if they are not. Even though the explanatory model and themodel that drives design do often correspond, the similarities will seldom be exact. To avoid confusion, everyone must be conscious of the distinction.

## Binding Model and Implementation

What good is a model on paper unless it directly aids the development of running software?

Projects that have no domain model at all, but just write code to fulfill one function after another, gain few of the advantages of knowledge crunching and communication. A complex domain will swamp them.

On the other hand, many complex projects do attempt some sort of domain model, but they don't maintain a tight connection between the model and the code. The model they develop, possibly useful as an exploratory tool at the outset, becomes increasingly irrelevant and even misleading. All care lavished on the model provides little reassurance that the design is correct, because the two are different.

This connection can break down in many ways, but the detachment is often a conscious choice. Many design methodologies advocate an analysis model, quite distinct from the design and usually developed by different people. It is called an analysis model because it is the product of analyzing the business domain to organize its concepts without any consideration of the part it will play in a software system. An analysis model is meant as a tool for understading only; mixing in implementation concerns is thought to muddy the waters. Later, a design is created that may have only a loose correspondence to the analysis model. The analysis model is not created with design issues in mind, and therefore it is likely to be quite impractical for those needs.

Some knowledge crunching happens during such an analysis, but most of it is lost when coding begins, when the developers are forced to come up with new abstractions for the design. Then there is no guarantee that the insights gained by the analysts and embedded in the model will be retained or rediscovered. At this point, maintaining any mapping between the design and the loosely connected model is not cost-effective.

The pure analysis model even falls short of its primary goal of understanding the domain, because crucial discoveries always emerge during the design/implementation effort. Very specific, unanticipated problems always arise. An up-front model will go into depth about some irrelevant subjects, while it overlooks some important subjects. Other subjects will be represented in ways that are not useful to the application. The result is that pure analysis models get abandoned soon after coding starts, and most of the ground has to be covered again. But the second time around, if the developers perceive analysis to be a separate process, modeling happens in a less disciplined way. If the managers perceive analysis to be a separate process, the development team may not be given adequate access to domain experts.

If the design, or some central part of it, does not map to the domain model, that model is of little value, and the correctness of the software is suspect. At the same time, complex mappings between models and design functions are difficult to understand and, in practice, impossible to maintain as the design changes. A deadly divide opens between analysis and design so that insight gained in each of those activities does not feed into the other.

An analysis must capture fundamental concepts from the domain in a comprehensible, expressive way.

Being minded about that, try to:

- Design a portion of the software system to reflect the domain model in a very literal way, so that mapping is obvious. Revisit the model and modify it to be implemented more naturally in software, even as you seek to make it reflect deeper insight into the domain. Demans a single model that serves both purposes well, in addition to supporting a robust Ubiquitous Language.

- Draw from the model the terminology used in the design and the basic assignment of responsibilities. The code becomes an expression of the model, so a change to the code may be a change to the model. Its effect must ripple through the rest of the project's activities accordingly.

- To tie the implementation slavishly to a model usually requires software development tools and languages that support a modeling paradigm, such as object oriented programming.

### Letting the Bones Show: Why Models Matter to Users

Model-driven design calls for working with only one model (within any single context). Most of the advice and examples go to the problems of having separate analysis models and design models, but here we have a problem arising from a different pair of models: the user model and the design/implementation model.

When a deisng is based on a model that reflects the basic concerns of the users and domain experts, the bones of the design can be revealed to the user to a greater extent than with other design approaches. Revealing the model gives the user more access to the potential of the software and yields consistent, predictable behavior.

### Hands-On Modeleres

Highly skilles engineers design, less skilled laborates assemble the products. This assumption has messed up a lot of projects for one simple reason - software development is all design. All teams have specialized roles for members, but overseparation of responsibility for analysis, modeling, design, and programming interferes with Model-driven design.

If the people who write the code do not feel responsible for the model, or don't understand how to make the model work for an application, then the model has nothing to do with the software. If developers don't realize that changing code changes the model, then their refactoring will weaken the model rather than strengthen it. Meanwhile, when a modeler is separated from the implementation process, he or she never acquires, or quickly loses, a feel for the constraints of implementation. The basic constraint of Model-driven design - that the model supports an effective implementation and abstracts key domain knowledge - is halfgone, and the resulting models will be impractical. Finally, the knowledge and skills of experienced designers won't be transferred to other developers if the division labor prevents the kind of collaboration that conveys the subtleties of coding a Model-drive design.

The need o Hands-On Modelers does not mean that team members cannot have speciailized roles. The problem arises from separating two tasks that are coupled in a Model-driven design, modeling and implementation.

The effectiveness of an overall design is very sensitive to the quality and consistency of fine-grained deisng and implementation decisions.

Any technical person contributing to the model must spend some time touching the code, whatever primary role he or she plays on the project. Anyone responsible for changing code must learn to express a model through the code. Every developer must be involved in some level of discussion about the model and have contact with domain experts. Those who contribute in different ways must consciously engage those who touch the code in a dynamic exchange of model ideas through the Ubiquitous Language.

## The Building Blocks of a Model-Driven Design

To keep a software implementation crisp and in lockstep with a model, in spite of messy realities, you must apply the best practices of modeling and design. Certain kinds of decisions keep the model and implementation aligned with each other, each reinforcing the other's effectiveness. This alignment requires attention to the details of individual elements. Developing a good domain model is an art. But the practical design and implementation of a model's individual elements can be relatively systematic. Isolating the domain design from the mass of other concerns in the software system will greatly clarify the design's connection to the model. Defining model elements according to certain distinctions sharpens their meanings. Following proven patterns for individual elements helps produce a model that is practical to implement.

### Isolating the Domain

The part of the software that specifically solves problems from the domain usually constitutes only a small portion of the entire software system, although its importance is disproportionate to its size. To apply our best thinking, we need to be able to look at the elements of our model and see them as a system. We must not be forced to pick them out of a much larger mix of objects, like trying to identify constelations in the night sky. We need to decouple the domain objects from other functions of the system, so we can avoid confusing the domain concepts with other concepts related only to software technology or losing sight of the domain altogether in the mass of the system.

In an object-oriented program, UI, database, and other support code often gets written directly into the business objects. Additional business logic is embedded in the behavior of UI widgets and database scripts. This happens because it is the easiest way to make things work, in the short run.

When the domain-related code is diffused through such a large amount of other code, it becomes extremely difficult to see and to reason about. Superficial changes to the UI can actually change business logic. To change a business rule may require meticulous tracing of UI code, database code, or other program elements. Implementing coherent, model-driven objects becomes impractical. Automated testing is awkward. With all the technologies and logic involved in each activity, a program must be kept very simple or it becomes impossible to understand.

There are all sorts of ways a software system might be divided, but through experience and convention, the industry has converged on Layered Architectures, and specially a few fairly standard layers. The value of layers is that each specializes in a particular aspect of a computer program. This specialization allows more cohesive designs of each aspect, and it makes these designs much easier to interpret. Of course, it is vital to choose layers that isolate the most important cohesive design aspects.

Partition a complex program into layers. Develop a design within each layer that is cohesive and that depends only on the layers below. Follow standard architectural patterns to provide loose coupling to the layers above. Concentrate all the code related to the domain model in one layer and isolate it from the user interface, application, and infrastructure code. The domain objects, free of the responsibility of displaying themselves, storing themselves, managing application tasks, and so forth, can be focused on expressing the domain model. This allows a model toe volve to be rich enough and clear enough to capture essential business knowledge and put it to work.

Although there are many variations, most successfull architectures use some version of these four conceptual layers:

- **User Interface (or Presentation Layer)**

Responsible for showing information to the use and interpreting the user's commands. The external actor might sometimes be another computer system rather than a human user.

- **Application Layer**

Defines the jobs the software is supposed to do and directs the expressive domain objects to work out problems. The tasks this layer is responsible for are meaningful to the business or necessary for interaction with the application layers of other systems.

This layer is kept thin. It does not contain business rules or knowledge, but only coordinates tasks and delegates work to collaborations of domain objects in the next layer down. It does not have state reflecting the business situation, but it can have state that reflects the progress of a task for the user or the program.

- **Domain Layer (or Model Layer)**

Responsible for representing concepts of the business, information about the business situation, and business rules. State that reflects the business situation is controlled and used here, even though the technical details of storing it are delegated to the infrastructure. This layer is the heart of busines software.

- **Infrastructure Layer**

Provides generic technical capabilities that support the higher layers: message sending for the application, persistence for the domain, drawing widgets for the UI, and so on. The infrastructure layer may also support the pattern of interactions between the four layers through an architectural framework.

#### Relating the Layers

Layers are meant to be loosely coupled, with design dependencies in only one direction. Upper layers can use or manipulate elements of lower ones straightforwardly by calling their public interfaces, holding references to them, and generally using conventional means of interaction. But when a object of a lower level needs to communicate upward, we need another mechanism, drawing on architectural patterns for relating layers such as callbacks or observers.

The infrastructure layers usually does not initiate action in the domain layer. Being "below" the domain layer, it should have no specific knowledge of the domain it is serving. Indeed, such technical capabilities are most often offered as services. The main benefit is simplifying the application layer, keeping it narroly focused on its job: knowing when to do something, but not burdened with how.

The application and domain layers call on the services provided by the infrastructure layer.

### A Model Expressed in Software

To compromise in implementation without losing the punch of a Model-Driven Design requiresa regraming of the basics. Connecting model andimplementation has to be done at the detail level.

#### Associations

The interaction between modeling and implementation is particularly tricky with the associations between objects.

For every traversable association in the model, there is a mechanism in the software with the same properties.

There are at least three ways of making associations more tractable:

1. Imposing a traversal direction.
2. Adding a qualifier, effectively reducing multiplicity.
3. Eliminating nonessential associations.

It is important to constrain relationships as much as possible. A bidirectional association means that both objects can be understood only together. When application requirements do not call for traversal in both directions, adding a traversal direction reduces interdependence and simplifies the design. Understanding the domain may reveal a natural directional bias.

Constraining the traversal direction of a many-to-many association effectively reduces its implementation to one-to-many - a much easier design.

Consistently constraining associations in ways that reflect the bias of the domain not only makes those associations more communicative and simpler to implement, it also gives significance to the remaining bidirectional associations.When the bidirectionality of a relationship is a semantic characteristic of the domain, when it's needed for application functionality, the retention of both traversal directions conveys that.

#### Entities (a.k.a. Reference Objects)

Many objects are not fundamentally defined by their attributes, but rather by a thread of continuity and identity.

Some objects are not defined primarly by their attributes. They represent a thread of identity that runs through time and often across distinct representations. Sometimes such an object must be matched with another object even though attributes differ. An object must be distinguished from other objects even though they might have the same attributes. Mistaken identity can lead to data corruption.

An object defined primarly by its identity is called an Entity. Entities have special modeling and design considerations. They have life cycles that can radically change their form and content, but a thread of continuity must be maintained. Their identities must be defined so that they can be effectvely tracked. Their class definitions, responsibilities, attributes, and associations should revolve around who they are, rather than the particular attributes they carry. Even for Entities that don't transform so radically or have such complicated life cycles, placing them in the semantic category leads to more lucid models and more robust implementations.

On the other hand, not all objects in the model are Entities, with meaningful identities. Identity is a subtle and meaning attribute of Entities, which can't be turned over to the automatic features of the language.

When an object is distinguished by its identity, rather than its attributes, make this primary to its definition in the model. Keep the class definition simple and focused on life cycle continuity and identity. Define a means of distinguishing each object regardless of its form or history. Be alert to requirements that call for matching objects by attributes. Define an operation that is guaranteed to produce by attaching a symbol that is guaranteed unique. This means of identification may come from the outside, or it may be an arbitrary identifier created by and for the system, but it must correspond to the identity distinctions in the model. The model must define what it means to be the same thing.

**Modeling Entities**

It is natural to think about the attributes when modeling an object, and it is quite important to think about its behavior. But the most basic responsibility of Entities is to establish continuity so that behavior can be clear and predictable. Rather than focusing on the attributes or even the behavior, strip the Entity object's definition down to the most intrinsic characteristics, particularly those that identify it or are commonly used to find or match it. Add only behavior that is essential to the concept and attributes that are required by the behavior. Beyond that, look to remove behavior and attributes into other objects associated with the core Entity. Some of these will be other Entities. Some will be Value Objects. Beyond identity issues, Entities tend to fulfill their responsibilities by coordinating the operations of objects they own.

**Designing the Identity Operation**

Each Entity must have an operational way of establishing its identity with another object - distinguishable even from another object with the same descriptive attributes. An identifying attribute must be guaranteed to be unique within the system however that system is defined - even if distributed, even when objects are archived.

When there is no true unique key made up of the attributes of an object, another common solution is to attach to each instance a symbol that is unique within the class. Once this ID symbol is created and stored as an attribute of the Entity, it is designated immutable. It must never change, even if the development system is unable to directly enforce this rule.

Often the ID is generated automatically by the system. The generation algorithm must guarantee uniqueness within the system, which can be a challenge with concurrent processing and in distributed systems.

When the ID is automatically generated, the use may never need to see it. The ID may be needed only internally, such as in a contact management application that lets the user find records by a person's name. The program needs to be able to distinguish two contacts with exactly the same name in a simple, unambiguous way. The unique, internal IDs let the system do just that.

There are cases in which a generated ID is of interest to the user. When I ship a package through a parcel delivery service, I'm given a tracking number, generated by the shipping company's software, which I can use to identify and follow up on my package.

In some cases, the uniqueness of the ID must apply beyond the computer system's boundaries. For example, if medical records are being exchanged between two hospitals that have separate computer systems, ideally each system will use the same patient ID, but this is difficult if they generate their own symbol.

#### Value Objects

Many objects have no conceptual identity. These objects describe some characteristic of a thing.

Tracking the identity of Entities is essential, but attaching identity to other objects can hurt system performance, add analytical work, and muddle the model by making all objects look the same.

Software design is a constant battle with complexity. We must make distinctions so that special handling is applied only where necessary.

However, if we think of this category of object as just the absence of identity, we haven't added much to our toolbox or vocabulary. In fact, these objects have characteristics of their own and their own significance to the model. These are the objects that describe things.

An object that represents a descriptive aspect of the domain with no conceptual identity is called a Value Object. Value Objects are instantiated to represent elements of the design that we care about only for what they are, not who or which they are.

When you care only about the attributes of an element of the model, classify it as a Value Object. Make it express the meaning of the attributes it conveys and give it related functionality. Treat the Value Object as immutable. Don't give it any identity and avoid the design complexities necessary to maintain Entities.

**Designing Value Objects**

We don't care which instance we have of a Value Object. This lack of constraints gives us design freedom we can use to simplify the design or optimize performance. This involves making choices about copying, sharing, and immutability.

The economy of copying versus sharing depends on the implementation environment. Although copies may clog the system with huge numbers of objects, sharing can slow down a distributed system. When a copy is passed between two machines, a single message is sent and the copy lives independently on the receiving machine. But if a single instance is being shared, only a reference is passed, requiring a message back to the object for each interaction.

Sharing is best restricted to those cases in which it is most valuable and least troublesome:

- When saving space or object count in the database is critical.
- When communication overhead is low (such as in a centralized server).
- When the shared object is strictly immutable.

As long as a Value Object is immutable, change management is simple - there isn't any change except full replacement. Immutable objects can be freely shared, as in the electrical outlet example. If garbage collection is reliable, deletion is just a matterof dropping all references to the object. When a Value Object is designated immutable in the design, developers are free to make decisions about issued such as copying and sharing on a purely technical basis, secure in the knowledge that the application does not rely on particular instances of the objects.

**Special Cases: When to Allow Mutability**

Immutability is a great simplifier in an implementation, making sharing and reference passing safe. It is also consistent with the meaning of a value. If the value of an attribute changes, you use a different Value Object, rather than modifying the existing one. Even so, there are cases when performance considerations will favor allowing a Value Object to be mutable. These factors would weigh in favor of a mutable implementation:

- If the Value changes frequently.
- If object creation or deletion is expensive.
- If replacement (rather than modification) will disturb clustering (as discussed in the previous example).
- If there is not much sharing of Values, or if such sharing is forgone to improve clustering or for some other technical reason.

Just to reiterate: If a Value's implementation is to be mutable, then it must not be shared. Wheter you will be sharing or not, design Value Objects as immutable when you can.

The technique of storing multiple copies of the same data is alled denormalization and it often used when access time is more critical than storage space or simplicity of maintenance.

In a relational database, you might want to put a particular Value in the table of the Entity that owns it, rather than creating an association to a separate table.

**Designing Associations That Involve Value Objects**

While bidirectional associations between Entities may be hard to maintain, bidirectional associations between two Value Objects just make no sense. Without identity, it is meaningless to say that an object points back to the same Value Object that points to it. The most you could say is that it points to an object that is equal to the one pointing to it, but you would have to enforce that invariant somewhere. And although you could do so, and set up pointers going both ways, it is hard to think of examples where such an arrangement would be useful.

Try to completely eliminate bidirectional associations between Value Objects. If in the end such associations seem necessary in your model, rethink the decision to declare the object a Value Object in the first place. Maybe it has an identity that hasn't been explicitly recognized yet.

#### Services

In some cases, the clearest and most pragmatic design includes operations that do not conceptually belong to any object. Rather than force the issue, we can follow the natural contours of the problem space and include Services explicitly in the model.

There are important domain operations that can't find a natural home in an Entity or Value Object. Some of these are intrinsically activities or actions, not things, but since our modeling paradigm is objects, we try to fit them into objects anyway.

Some concepts from the domain aren't natural to model as objects. Forcing the required domain functionality to be the responsibility of an Entity or Value either distorts the definition of a model-based object or adds meaningless artificial objects.

A Service is an operation offered as an interface that stands alone in the model, without encapsulating state, as Entities and Value Objects do. Services are a common pattern in technical frameworks, but they can also apply in the domain layer.

A Service tends to be named for an activity, rather than an entity - a verb rather than a noun. A Service can still have an abstract, intentional definition; it just has a different flavor than the definition of an object. A Service should still have a defined responsibility, and that responsibility and the interface fulfilling it should be defined as part of the domain model. Operation names should come from the Ubiquitous Language or be introduced into it.

Services should be used judiciously and not allowed to strip the Entities and Value Objects of all their behavior, But when an operation is actually an important domain concept, a Service forms a natural part of a Model-Driven Design. Declared in the model as a Service, rather than as a phony object that doesn't actually represent anything, the standalone operation will not mislead anyone.

A good Service has three characteristics:

1. The operation relates to a domain concept that is not a natural part of an Entity or Value Object.

2. The interface is defined in terms of other elements of the domain model.

3. The operation is stateless.

When a significant process of transformation in the domain is not a natural responsibility of an Entity or Value Object, add an operation to the model as a standalone interface declared as a Service. Define the interface in terms of the language of the model and make sure the operation name is part of the Ubiquitous Language. Make the Service stateless.

**Services and the Isolated Domain Layer**

This pattern is focused on those Services that have an important meaning in the domain in ther own right, but of course Services are not used only in the domain layer. It takes care to distinguish Services that belong to the domain layer from those of other layers, and to factor responsibilities to keep that distinction sharp.

It can be harder to distinguish application Services from domain Services. The application layer is responsible for ordering the notification. The domain layer is responsible for determining if a threshold was met - though this task probably does not call for a Service, because it would fit the responsibility of an "account" object.

Many domain or application Services are built on top of the populations of Entities and Values, behaving like scripts that organize the potential of the domain to actually get something done.

**Partitioning Services into Layers**

- **Application** *(Funds Transfer App Service)*
  - Digests input (such as an XML request).
  - Sends message to domain service for fulfillment.
  - Listens for confirmation.
  - Decides to send notification using infrastructure service.

- **Domain** *(Funds Transfer Domain Service)*
  - Interacts with necessary Account an Ledger objects, making appropriate debits and credits.
  - Supplies confirmation of result (transfer allowed or not, and so on.).

- **Infrastructure** *(Send Notification Service)*
  - Sends e-mails, letters, and other communications as directed by the application.

**Granularity**

Medium-grained, stateless Services can be easier to reuse in large systems because they encapsulate significant functionality behind a simple interface. Also, fine-grained objects can lead to inefficient messaging in a distributed system.

This patterns favors inteface simplicity over client control and versatility. It provides a medium grain of functionality very useful in packaging components of large or distributed systems. And sometimes a Service is the most natural way to express a domain concept.

#### Modules

Modules are an old, established design element. There are technical considerations, but cognitive overload is the primary motivation for modularity. Modules give people two views of the model: They can look at detail within a Module without being overwhelmed by the whole, or they can look at relationships between Modules in views that exclude interior detail.

Everyone uses Modules, but few treat them as full-fledged part of the model. Code gets broken down into all sorts of categories, from aspects of the technical architecture to developers work assignments. Even developers who refactor a lot tend to content themselves with Modules conceived early in the project.

It is a truism that there should be low coupling between Modules and high cohesion within them. Explanations of coupling and cohesion tend to make them sound like technical metrics, to be judged mechanically based on the distributions of associations and interactions. Yet it isn't just code being divided into Modules, but concepts. There is a limit to how many things a person can think about at once (hence low coupling). Incoherent fragments of ideas are as hard to understand as an undifferentiated soup of ideas (hence high cohesion).

Modules are a communications mechanism. The meaning of the objects being partitioned needs to drive the choice of Modules. When you place some classes together in a Module, you are telling the next developer who looks at your design to think about them together. If your model telling a story, the Modules are chapters. The name of Module conveys its meaning. These names enter the Ubiquitous Language. "Now let's talk about the 'customer' module", you might say to a business expert, and the context is set for your conversation.

Choose Modules that tell the story of the system and contain a cohesive set of concepts. This often yields low coupling between Modules, but if it doesn't, look for a way to change the model to disentangle the concepts, or search for an overlooked concept that might be the basis of a Module that would bring the elements together in a meaningful way. Seek low coupling in the sense of concepts that can be understood and reasoned about independently of each other. Refine the model until it partitions according to high-level domain concepts and the corresponding code is decoupled as well.

Give the Modules names that become part of the Ubiquitous Language. Modules and their names should reflect insight into the domain.

### The Life Cycle of a Domain Object

Every object has a life cycle. An object is born, it likely goes through various states, and it eventually dies - being either archived or deleted. But other objects have longer lives, not all of which are spent in active memory. They have complex interdependencies with other objects. They go through changes of state to which invariants apply.

The challenges fall into two categories:

1. Maintaining integrity throughout the life cycle.
2. Preventing the model from getting swamped by the complexity of managing the life cycle.

#### Aggregates

Minimalist design of associations helps simplify traversal and limit the explosion of relationships somewhat, but most business domains are so interconnected that we still end up tracing long, deep paths through object references. In a way, this tangle reflects the realities of the world, which seldom obliges us with sharp boundaries. It is a problem in a software design.

The problem is acute in a system with concurrent access to the same objects by multiple clients. With many users consulting and updating different objects in the system, we have to prevent simultaneous changes to interdependent objects. Getting the scope wrong has serious consequences.

It is difficult to guarantee the consistency of changes to objects in a model with complex associations. Invariants need to be maintained that apply to closely related groups of objects, not just discrete objects. Yet cautious locking schemes cause multiple users to interfere pointlessly with each other and make a system unusable.

An Aggregate is a cluster of associated objects that we treat as aunit for the purpose of data changes. Each Aggregate has a root and a boundary. The boundary defines what is inside the Aggregate. The root is a single, specific Entity contained in the Aggregate. The root is the only member of the Aggregate that outside objects are allowed to hold references to, although objects within the boundary may hold references to each other. Entities other than the root have local identity, but that identity needs to be distinguishable only within the Aggregate, because no outside object can ever see it out of the context of the root Entity.

Invariants, which are consistency rules that must be maintained whenever data changes, will involve relationships between members of an Aggregate. Any rule that spans Aggregates will not be expected to be up-to-date at all times. Through event processing, batch processing, or other update mechanisms, other dependencies can be resolved within some specified time. But the invariants applied within an Aggregate will be enforced with the completion of each transaction.

Now, to translate that conceptual Aggregate into the implementation, we need a set of rules to apply to all transactions:

- The root Entity has global identity and is ultimately responsible for checking invariants.

- Root Entities have global identity. Entities inside the boundary have local identity, unique only within Aggregate.

- Nothing outside the Aggregate boundary can hold a reference to anything inside, except to the root Entity. The root Entity can hand references to the internal Entities to other objects, but those objects can use them only transiently, and they may not hold on to the reference. The root may hand a copy of a Value Object to another objects, and it doesn't matter what happens to it, because it's just a Value and no longer will have any association with the Aggregate.

- As a corollary to the previous rule, only Aggregate roots can be obtained directly with database ueries. All other objects must be found by traversal of associations.

- Objects within the Aggregate can hold references to other Aggregate roots.

- A delete operation must remove everything within the Aggregate boundary at once. (With garbage collection, this is easy. Because there are no outside references to anything but the root, delete the root and everything else will be collected).

- When a change to any object within the Aggregate boundary is committed, all invariants of the whole Aggregate must be satisfied.

Cluster the Entities and value Objects into Aggregates and define boundaries around each. Choose one Entity to be the root of each Aggregate, and control all access to the objects inside the boundary through the root. Allow external objects to hold references to the root only. Transient references to internal members can be passed out for use within a single operation only. Because the root controls access, it cannot be blindsided by changes to the internals. This arrangement makes it practical to enforce all invariants for objects in the Aggregate and for the Aggregate as a whole in any state change.

#### Factories

When creation of an object, or an entire Aggregate, becomes complicated or reveals too much of the internal structure, Factories provide encapsulation.

An object should be distilled until nothing remains that does not relate to its meaning or support its role in interactions.

Creation of an object can be a major operation in itself, but complex assembly operations do not fit the responsibility of the created objects. Combining such responsibilities can produce ungainly designs that are hard to understand. Making the client direct construction muddies the design of the client, breaches encapsulation of the assembled object or Aggregate, and overly couples the client to the implementation of the created object.

Complex object creation is a responsibility of the domain layer, yet that task does not belong to the objects that express the model.

A program element whose responsibility is the creation of other objects is called a Factory.

Just as the interface of an object should encapsulate its implementation, thus allowing a client to use the object's behavior without knowing how it works, a Factory encapsualtes the knowledge needed to create a complex object or Aggregate. It provides an interface that reflects the goals of the client and an abstract view of the created object.

Shift the responsibility for creating instances of complex objects and Aggregates to a separate object, which may itself have no responsibility in the domain model but is still part of the domain design. Provide an inteface that encapsulates all complex assembly and that does not require the client to reference the concrete classes of the objects being instantiated. Create entire Aggregates as a piece, enforcing their invariants.

The two basic requirements for any good Factory are:

1. Each creation method is atomic and enforces all invariants of the created object or Aggregate. A Factory should only be able to produce an object in a consistent state. For an Entity, this means the creation of the entire Aggregate, with all invariants satisfied, but probably with optional elements still to be added. For an immutable Value Object, this means that all attributes are initialized to their correct final state. If the interface makes it possible to request an object that can't be created correctly, then an exception should be raised or some other mechanism should be invoked that will ensure that no improper return value is possible.

2. The Factory should be abstracted to the type desired, rather than the concrete classes created.

**Choosing Factories and Their Sites**

Generally speaking, you create a factory to build something whose details you want to hide, and you place the Factory where you want the control to be. These decisions usually revolve around Aggregates.

For example, if you needed to add elements inside a preexisting Aggregate, you might create a Factory Method on the root of the Aggregate.

**When a Constructor Is All You Need**

There are times when the directness of a constructor makes it the best choice than using Factories. The trade-offs favor a bare, public constructor in the following circumstances:

- The class is the type. It is not part of any interesting hierarchy, and it isn't used polymorphically by implementing an interface.

- The client cares about the implementation, perhaps as a way of choosing a Strategy.

- All of the attributes of the object are available to the client, so that no object creation gets nested inside the constructor exposed to the client.

- The construction is not complicated.

- A public constructor must follow the same rules as a Factory: It must be an atomic operation that satisfies all invariants of the created object.

Avoid calling constructors within constructors of other classes. Constructors should be dead simple. Complex assemblies, especially of Aggregates, call for Factories. The threshold for choosing to use a little Factory Method isn't high.

**Designing the Interface**

When designing the method signature of a Factory, wheter standalone of Factory Method, keep in mind these two points:

- **Each operation must be atomic:** You have to pass in everything needed to create a complete product in a single interaction with the Factory. You also have tod ecide what will happen if creation fails, in the event that some invariant isn't satisfied. You could throw an exception or just return a null. To be consistent, consider adopting coding standard for failures in Factories.

- **The Factory will be coupled to its arguments:** If you are not careful in your selection of input parameters, you can create a rat's nest of dependencies. The degree of coupling will depend on what you do with the argument. If it is simply plugged into the product, you've created a modest dependency. If you are picking parts out of the argument yo use in the construction, the coupling gets tighter.

**Reconstituting Stored Objects**

A Factory used for reconstitution is very similar to one used for creation, with two major differences:

1. **An Entity Factory used for reconstitution does not assign a new tracking ID:** To do so would lose the continuity with the object's previous incarnation. So identifying attributes must be part of the input parameters in a Factory reconstituting a stored object.

2. **A Factory reconstituting an object will handle violation of an invariant differently:** During creation of a new object, a Factory should simply balk when an invariant isn't met, but a more flexible response may be necessary in reconstitution. If an object already exists somewhere in the system (such as in the database), this fact cannot be ignored. Yet we also can't ignore the rule violation. there has to be some strategy for repairing such inconsistencies, which can make reconstitution more challenging than the creation of new objects.

#### Repositories

<!--- Current Page 146 / Last Page 195 -->