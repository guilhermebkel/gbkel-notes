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

<!--- Current Page 45 / Last Page 83 -->