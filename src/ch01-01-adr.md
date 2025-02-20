# Architecture Decision Record

## WHY
### Challenges
Software development teams often face the following challenges:

- Knowledge Loss: Over time, team members may leave the project, taking their knowledge with them. This can make it difficult for new developers to understand the reasoning behind design choices.
- Inconsistent Decision-Making: Without a documented record of decisions, it can be challenging to ensure that everyone on the team is making consistent choices based on the same criteria. This can lead to technical debt and increased maintenance costs.
- Technical Debt: Unstructured decision-making can lead to technical debt, as poor design choices accumulate over time. This can make it difficult to maintain and extend the software.
- Increased Risk: Without a clear understanding of the rationale behind design decisions, it can be difficult to assess the risks associated with changes to the software. This can lead to unexpected problems and delays.

### Benefits of ADRs
- Improved understanding: They help future developers understand the reasoning behind design choices, making it easier to maintain and extend the codebase.
- Enhanced communication: ADRs provide a common language for discussing architectural decisions, reducing misunderstandings and improving collaboration.
- Reduced technical debt: By documenting decisions, ADRs can help prevent technical debt from accumulating over time.
- Improved decision-making: ADRs can help teams make more informed and consistent decisions.

## WHAT
An Architecture Decision Record (ADR) is a document that records the reasoning behind a significant design decision made during software development. It provides a structured way to capture the context of the decision, the options considered, the rationale for the chosen option, and the potential consequences of that choice. Architecture Decision Records (ADRs) are used to capture a log of technical decisions for each system.

## WHEN
ADRs are typically written for significant design decisions that have a long-term impact on the software project. This might include below items but not limited to:

- Technology stack selection: Choosing programming languages, frameworks, and libraries.
- Architectural patterns: Deciding on design patterns like MVC, microservices, or event-driven architecture.
- Data storage: Selecting databases or data storage solutions.
- Deployment strategies: Determining how the application will be deployed (e.g., on-premises, cloud).
- Security measures: Implementing security best practices and controls.


## HOW
- Every system repository will have a "docs/adrs" directory. This directory will contain all the ADRs for that system.
- ADRs are the outcome of decision processes and not the processes themselves. In order to produce a high-quality and detailed ADR, you need to explore possible solutions in advance and conduct detailed research and analysis on each solution.  
- The name of each ADR file should follow the format "NNN-short-description.md", where NNN is a unique number and short-description is a brief description of the decision.
- Assets like diagrams, images, or other supporting documents should be stored in the "docs/adrs/assets" directory.
- Organize sessions to review and discuss ADRs with the team. This will help ensure that everyone is on the same page and that the decisions are well understood.
- Everyone in the team should be able to propose an ADR, and everyone in the team should understand the problem, the context, and the potential consequences of each option. This will help ensure that decisions are made collaboratively in the team and that everyone has a voice in the process.

```
docs
└── adrs
    ├── assets
    │   └── images
    │       └── 001-diagram.png
    ├── 001-what-will-we-use-to-ship-logs.md
    ├── 002-how-should-we-support-ipv6-for-pods.md
    ├── 003-which-multi-tenancy-solution-should-we-choose-for-paas.md
    └── README.md
```

Check the template [here](./ch01-01-01-adr-template.md). Please note, we ofter name each ADR doc with naming covention like `001-TopicName`.

## References
- [ADR](https://www.thoughtworks.com/radar/techniques/lightweight-architecture-decision-records)
- [adr-tools](https://github.com/npryce/adr-tools)
