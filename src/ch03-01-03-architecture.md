# Architecture

## Definition

***"How can I quickly familiarize myself with this system? Does the system encapsulate a single responsibility with a clearly defined interface?"***

Architecture Lens relates to the system's responsibility within a domain and its long-term adaptability. Poorly architected systems require significant effort to modify, are difficult to migrate to the cloud, and create substantial barriers to innovation and experimentation. A well-structured system ensures that responsibilities are clearly defined, reducing complexity and enabling easier integration with future technologies.


## Evaluation criterion

| Criterion               | Required For                                  |
|-------------------------|-----------------------------------------------|
| Architecture Design     | <span style="background:orange">Yellow</span> |
| API/Interface Documents | <span style="background:orange">Yellow</span> |
| Single Responsibility   | <span style="background:green">Green</span>   |
| PII Data                | <span style="background:green">Green</span>   |
| Data Management         | <span style="background:green">Green</span>   |

### Architecture Design

System architecture diagrams clearly illustrate how the system interacts with its external environment, the composition of internal components, and the direction of data flow. This visual representation is essential for onboarding new team members, facilitating cross-team collaboration, and troubleshooting system issues. Moreover, architecture diagrams help prevent knowledge silos. If the architecture exists only in the minds of certain team members, the team risks knowledge loss when those members leave or transition to other roles.

Therefore, a healthy system must:

1. Store system architecture diagrams in the system's repository.
1. Retain source files of architecture diagrams whenever possible to facilitate future modifications.
1. Follow the C4 model as much as possible for architecture design.

### API/Interface Documents

When a system provides an API, it is essentially offering a contract that defines how the system can be accessed and interacted with. This contract must be clearly and accurately documented to ensure that all developers using the API can correctly understand its functionality, input requirements, return values, and potential errors. The system providing the contract is responsible for ensuring that it is well-defined and documented alongside the system.

Therefore, a healthy system must:

1. Document all provided APIs and interfaces, using tools such as Swagger or other similar products.
1. If the system does not provide any APIs or interfaces, this requirement may be marked as N/A.


### Single Responsibility

A healthy system should focus on a single domain to ensure clear objectives, well-defined responsibilities, and understandable inputs and outputs. If a system is difficult to describe within a single domain, it may indicate that unrelated business requirements have been introduced. In such cases, the system should be split to maintain clear domain boundaries, improving maintainability and long-term scalability.

Therefore, a healthy system must:

1. Ensure that all its functionalities remain focused on a single domain.
1. If the system is a Monorepo, this requirement may be marked as N/A.

### PII Data

Protecting privacy data assets is essential for maintaining a healthy system. Data is not only a core asset for business growth and profitability but also the foundation of user trust. Successful digital enterprises rely on data to enhance products, gain insights, and drive monetization. However, if data is siloed, difficult to manage, or lacks transparency, its value diminishes significantly. Additionally, customer expectations for the protection of personally identifiable information (PII) continue to rise. Businesses must adopt best practices for data management to ensure the security and compliance of sensitive data.

Therefore, as a collector and manager of PII data, a healthy system must:

1. Complete a Privacy Impact Assessment (PIA) before generating any PII data and record it in the 1-pager. This helps identify and mitigate privacy risks in advance, enhances compliance, and strengthens user trust.
1. Properly label PII data at the time of generation, including whether it qualifies as PII and its privacy classification.
1. If the system does not generate any data or only collects front-end data, this requirement may be marked as N/A.

### Data Management

A system should manage data in a clear and consistent manner to prevent confusion and issues arising from multiple systems handling the same data. Without a single system of record, data quality may degrade due to latency issues and conflicts between different sources. Therefore, each system should document the data it produces and specify whether it serves as the primary data source to ensure data consistency and reliability.

Therefore, a healthy system must:

1. Clearly document the data it generates.
1. Assign explicit ownership and access permissions to every data asset it produces.
1. If the system does not generate any data or only collects front-end data, this requirement may be marked as N/A.
