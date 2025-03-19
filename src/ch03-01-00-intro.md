# System Health Rating

We consistently observe the improvements teams make to their ecosystems by treating health ratings as equally important as other service-level objectives (SLOs) and prioritizing enhancements accordingly, rather than solely focusing on tracking technical debt. By efficiently allocating resources to address the most impactful health-related issues, teams and organizations can reduce long-term maintenance costs and evolve products more effectively. This approach also enhances communication between technical and non-technical stakeholders, fostering a shared understanding of the system's state. While specific metrics may vary across organizations (see examples in this blog post), they ultimately contribute to long-term sustainability and ensure software remains adaptable and competitive. In a rapidly evolving digital landscape, prioritizing system health tracking over technical debt provides a structured and evidence-based strategy to maintain and enhance systems.

## The mechanics

Each criterion has been designed to be as objective as possible but systems live in specific contexts and sometimes more information is needed to guide the answer. You will find the details below.

There are three lenses through which systems must be rated: [Development](./ch03-01-01-development.md), [Operations](./ch03-01-02-operations.md) and [Architecture](./ch03-01-03-architecture.md).

Each lens will yield a traffic light result. <span style="background:green">Green</span>, <span style="background:orange">Yellow</span> or <span style="background:red">Red</span>..

For a system to be rated Yellow, all criteria in the Yellow category must be answered with YES or Not Applicable (N/A). If any is a NO the system is deemed Red for that lens.

For a system to be rated Green, all criteria in the Green AND Yellow category must be answered with YES or Not Applicable (N/A). If a criterion for Green is a No then the system is deemed Yellow for that lens or Red if it also receives a No on any Yellow criterion.

p.s. More importantly, different organizations can customize health criterion based on their actual conditions.

## Examples
| Case | Green Category                        | Yellow Category                                            | Rate                                          |
| ---- | ------------------------------------- | ---------------------------------------------------------- | --------------------------------------------- |
| 1    | Criterion D: YES<br> Criterion E: YES | Criterion A: YES<br> Criterion B: YES<br> Criterion C: N/A | <span style="background:green">Green</span>   |
| 2    | Criterion D: NO<br> Criterion E: YES  | Criterion A: YES<br> Criterion B: YES<br> Criterion C: N/A | <span style="background:orange">Yellow</span> |
| 3    | Criterion D: NO<br> Criterion E: YES  | Criterion A: YES<br> Criterion B: NO<br> Criterion C: YES  | <span style="background:red">Red</span>     
