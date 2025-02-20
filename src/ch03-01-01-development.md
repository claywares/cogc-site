# Development

## Definition

***"Can I setup the codebase, understand it, and confidently make changes?"***

Development Lens relates to the changeability of the system. We need software that is easy to modify to support a fast-paced feature rollout and enable quick responses to defects or vulnerabilities. A system that is difficult to change slows down development, increases costs, and makes it harder to keep up with evolving business needs.

## Evaluation criterion

| Criterion                       | Required For                                  |
|---------------------------------|-----------------------------------------------|
| Code Static Analysis            | <span style="background:orange">Yellow</span> |
| Main Language/framework/library | <span style="background:orange">Yellow</span> |
| Containerised                   | <span style="background:green">Green</span>   |
| CI/CD                           | <span style="background:green">Green</span>   |
| Continuous Improvement          | <span style="background:green">Green</span>   |
| Dependency Management           | <span style="background:green">Green</span>   |


### Code Static Analysis

A healthy system should leverage linters or code formatters to automate low-value, repetitive tasks such as standardizing brackets, code indentation, and formatting. This allows developers to focus more on architectural decisions, better abstractions, performance optimization, and security vulnerabilities.

Therefore, a healthy system must meet the following requirements:

1. Use a linter (e.g., ESLint, Pylint, WartRemover) in the pipeline to statically analyze code. This helps identify programming errors, detect bugs, highlight style issues, and flag suspicious structures.   
1. Use a code formatter tool (e.g., Prettier, Scalafmt) appropriate for the language to correct spacing, line breaks, and comments. Enforcing easily automated programming and formatting rules through tools reduces reliance on individual developers for such tasks. By delegating formatting concerns to automation, future code differences can be minimized.

### Main Language/framework

In today's fast-paced tech environment, creating a customized Tech Radar for your organization can help prioritize technologies and align the tech stack across teams. This not only enhances collaboration between projects and departments but also enables the development of a focused technology strategy to stay ahead in a competitive market. For guidance, you can refer to ThoughtWorks's Tech Radar: https://www.thoughtworks.com/radar. If you haven't created your own Tech Radar yet, we strongly recommend using our BYOR tool to build one: https://www.thoughtworks.com/radar/byor.

Therefore, a healthy system must meet the following requirements:

1. Should be `N/A` if your organization does not have a Tech Radar.
1. technologies marked as "Retire" should be avoided. Continuing to use retired languages, frameworks, or libraries increases hidden risks and places a greater burden on maintenance efforts. reqiured for <span style="background:orange">Yellow</span>.
1. Additionally, to ensure better support and seamless integration with other internal systems and tools, these core technologies should be classified as "Adopt" in the radar. <span style="background:green">Green</span>.

### Containerised

Adopting containerization in package management and release processes helps ensure cross-environment consistency, reducing cognitive overhead and making it easier to diagnose and reproduce production issues. Additionally, containerization enables your system to meet several principles of the 12-factor app methodology.

Therefore, a healthy system must meet the following requirements:

1. The system must be containerized.   
1. The local development environment must support a containerized setup.   
1. The CI pipeline must operate within a containerized environment.   
1. Applications must be deployed using containers.   
1. Applications running locally should closely mirror the production environment to better simulate and address potential production issues.   


### CI/CD

In a healthy system, CI/CD (Continuous Integration and Continuous Delivery/Deployment) plays a vital role. By automating build, test, and deployment processes, CI/CD minimizes manual intervention and significantly enhances development and release efficiency.

Through automated testing and quality checks, development teams can quickly identify and resolve issues, reducing defects in production environments. CI/CD enables teams to release small, incremental improvements frequently, rather than waiting for large-scale updates, supporting the agile practice of short release cycles. It fosters collaboration between development, testing, and operations teams via the CI/CD pipeline, breaking down information silos.

Therefore, a healthy system must meet the following requirements:

1. The CI/CD pipeline must include fully automated build, test, and deployment processes.
1. The CI/CD pipeline should utilize fully scripted and high-coverage tests to ensure the successful deployment of changes.
1. Deployments to production must require no manual intervention at any stage.

### Continuous Improvement

A healthy system must maintain a certain level of activity to demonstrate continuous optimization and growth. Metrics such as the frequency of production deployments and the number of developers contributing to the codebase can be used to evaluate this activity. These indicators reflect the team's ongoing improvements to the system and its ability to respond promptly to demands and resolve issues, ensuring long-term stability and competitiveness.

Therefore, a healthy system must meet the following requirements:

1. The project must have had at least two code contributors in the past three months.
1. The project must have been deployed to production at least five times in the past six months.

### Dependency Management

Projects should use the latest major versions of the current language, framework, or libraries because:

1. Newer versions have fewer unknown security vulnerabilities compared to older ones.
1. They provide more features and capabilities.
1. Documentation and community support primarily focus on the latest versions.

Using outdated libraries to build applications exposes the system to security risks and increases the complexity of future upgrades. A consistent vulnerability detection process is essential to ensure confidence in the system's ability to identify potential security threats.

Therefore, a healthy system must meet the following requirements:

1. Ensure periodic library updates using tools like Renovate to reduce the manual workload of updates.
1. Regularly check for security vulnerabilities in dependencies using tools like Dependabot.
1. Avoid using any versions of dependencies with known security vulnerabilities.
