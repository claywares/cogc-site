# System Health Rating

Throughout our long-term collaboration with R Company, Thoughtworks has continuously learned from and incorporated R's best practices in system operations and management, particularly in system health assessments. R Company has long adopted a regular evaluation and maintenance mechanism to ensure system stability and scalability. This approach has helped them avoid the accumulation of technical debt while maintaining high availability and maintainability as their business grows.

Through this collaboration, we have come to deeply understand that if a system lacks regular health checks and maintenance after development, it may gradually be neglected, leading to performance degradation, increased security risks, and significant technical debt when expansion or redevelopment is needed. R Company, based on years of engineering experience, has developed a structured system health assessment methodology, covering key dimensions such as architectural stability, maintainability, security, cost management, and data governance, with quantitative metrics for evaluation. This systematic approach to health management not only helps optimize resource utilization but also effectively mitigates operational risks, ensuring the long-term alignment of technical infrastructure with business needs.

Building upon our in-depth study and application of R Company's practices, Thoughtworks has designed a comprehensive system health evaluation framework, using R's methodology as a blueprint and incorporating our own engineering expertise. This framework clearly defines which key dimensions should be assessed, what standards define system health. Our goal is to ensure that this framework not only serves Thoughtworks's internal system management but also provides a referenceable evaluation model for other enterprises. By implementing this methodology, organizations can establish a long-term system health management mechanism, enhance their technical capabilities, and ensure the sustainable and stable growth of their business.

## The mechanics

Each criterion has been designed to be as objective as possible but systems live in specific contexts and sometimes more information is needed to guide the answer. You will find the details below.

There are three lenses through which systems must be rated: [Development](./ch03-01-01-development.md), [Operations](./ch03-01-02-operations.md) and [Architecture](./ch03-01-03-architecture.md).

Each lens will yield a traffic light result. <span style="background:green">Green</span>, <span style="background:orange">Yellow</span> or <span style="background:red">Red</span>..

For a system to be rated Yellow, all criteria in the Yellow category must be answered with YES or Not Applicable (N/A). If any is a NO the system is deemed Red for that lens.

For a system to be rated Green, all criteria in the Green AND Yellow category must be answered with YES or Not Applicable (N/A). If a criterion for Green is a No then the system is deemed Yellow for that lens or Red if it also receives a No on any Yellow criterion.

## Examples
| Case | Green Category                        | Yellow Category                                            | Rate                                          |
| ---- | ------------------------------------- | ---------------------------------------------------------- | --------------------------------------------- |
| 1    | Criterion D: YES<br> Criterion E: YES | Criterion A: YES<br> Criterion B: YES<br> Criterion C: N/A | <span style="background:green">Green</span>   |
| 2    | Criterion D: NO<br> Criterion E: YES  | Criterion A: YES<br> Criterion B: YES<br> Criterion C: N/A | <span style="background:orange">Yellow</span> |
| 3    | Criterion D: NO<br> Criterion E: YES  | Criterion A: YES<br> Criterion B: NO<br> Criterion C: YES  | <span style="background:red">Red</span>     
