# Auto Scripts

## WHY
### Challenges
- Inconsistency in Development and Operations: Different developers within a team may perform tasks like builds, deployments, or tests differently, leading to inconsistent results or unexpected behavior in different environments.
- Manual, Error-Prone Processes: Repeated manual steps (e.g., building, testing, deploying) are prone to human errors, such as misconfiguration or forgotten steps.
- Difficulty in Onboarding New Developers: New team members often struggle to set up development environments and understand project workflows, leading to delays in productivity.
- "It Works on My Machine" Syndrome: Developers frequently face issues where code works on one machine but fails on another due to differences in environment setup, configurations, or dependencies.
- Lack of Repeatability and Standardization: Without standardized processes, repeating certain tasks (e.g., deployments, builds) consistently can be difficult, leading to unpredictable outcomes.
- Difficulty Managing CI/CD Pipelines: Continuous Integration and Deployment (CI/CD) pipelines often require complex setups and orchestration of multiple steps (building, testing, deploying), which are hard to maintain manually.
- Difficulty in Cross-Team Collaboration: Teams working independently may develop divergent workflows and processes, making it hard to collaborate or integrate their work smoothly.

### Solution
- Containerize to resolve the issue that may be caused by different environments.
- Standardise on the location and naming of automation entrypoint scripts.

## WHAT
**Auto Scripts** are a set of executable files (typically shell scripts) in an `auto` subdirectory, that automate common development and operations tasks, such as building, testing, and deploying software. These scripts are version-controlled, documented, and can be shared across the team to ensure consistency and repeatability in workflows.

## WHEN
This pattern should be used when automation, consistency, or standardization is needed to improve the efficiency and reliability of processes in a software development or operations environment of an application.

## HOW
The folder structure of the repo should look like this:
```
auto
├── build
├── deploy
├── test
└── package
bin
├── shellcheck
├── terraform
└── yamllint
```

- Scripts should not use `.sh` suffix since the scripts can be implemented in other languages as well.
- `auto` scripts are generally the scripts that are actually run directly in CI steps. Essentially it's the "entry-point for automation". Therefore, name the script with `auto/ACTION` format, where ACTION is the operation to perform e.g. 
  - auto/build
  - auto/test
  - auto/deploy
  - auto/package
  - auto/lint
- Putting tools in `bin` folder allows people to run them locally, but they are not meant to be run in CI/CD pipelines. However, they can be used in `auto` scripts.
  - bin/shellcheck
  - bin/terraform
  - bin/yamllint
- Find examples [here](./ch02-01-01-examples.md).
