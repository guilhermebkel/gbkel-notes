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

<!--- Current Page 15 / Last Page 40 -->