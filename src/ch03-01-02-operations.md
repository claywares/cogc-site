# Operations

## Definition

***"Can I deploy the system, understand it (and dependencies), handle DR [disaster recovery], and know if it is performing in line with established SLAs (Service Level Agreements)?"***

Operations Lens relates to the reliability and maintenance of the production environment. We need high-performing systems to provide the best possible user experience, and we need repeatable, automated processes to reduce errors and inefficiencies. A well-operationalized system ensures smooth deployments, minimizes downtime, and enhances overall system stability.

## Evaluation criterion

| Criterion                    | Required For                                  |
|------------------------------|-----------------------------------------------|
| 1pager                       | <span style="background:orange">Yellow</span> |
| Logs  Management             | <span style="background:orange">Yellow</span> |
| Infrastructure Scanning      | <span style="background:orange">Yellow</span> |
| Infrastructure as Code (IaC) | <span style="background:green">Green</span>   |
| Cost Saving                  | <span style="background:green">Green</span>   |
| Recovery Plan                | <span style="background:green">Green</span>   |
| Alerts Management            | <span style="background:green">Green</span>   |
| Incidents Not Occurring      | <span style="background:green">Green</span>   |

### 1pager

In team collaboration, we often say, "Let's stay on the same page." This means that maintaining a consistent context among team members is essential for effective cooperation. During project development, ensuring that the team has a clear and unified understanding of the project's background, objectives, and system functionality can significantly improve collaboration efficiency and problem-solving capabilities. Therefore, documenting and maintaining as much project context as possible is crucial.

Therefore, a healthy system must meet the following requirements:

1. The 1-pager document must be stored in the project repository in Markdown format.
2. The 1-pager document must include the following information:   
    Basic Information: Defines the project's objectives, applicable scenarios, and key functionalities.   
    Maintenance Information: Specifies the project maintainers, maintenance cycles, and how to contact relevant personnel.   
    System Architecture Design: Provides an overview of the system's overall design, main components, and their interactions.   
    Key Operational Guidelines: Includes known issues, troubleshooting steps for common problems, and usage instructions for diagnostic tools.   

### Logs Management

A well-managed and detailed logging system is a crucial component of maintaining system health. It not only helps teams quickly diagnose and resolve issues but also aids in detecting security threats, ensuring compliance, optimizing system performance, supporting disaster recovery, and facilitating cross-team collaboration. For modern distributed systems, a robust logging system is fundamental to ensuring reliability, security, and maintainability.

Therefore, a healthy system must meet the following requirements:

1. A centralized log management system where all system logs can be processed centrally. The log management system's entry point should be included in the 1-pager.
1. Logs must not contain restricted information, such as personal or financial data (e.g., credit card numbers, email addresses, etc.).
1. Key system events must be logged, including but not limited to:   
    User logins (successful or failed).   
    Modifications to private data.   
    Application crashes or failures.   
1. If the system is a static website deployed via S3 or a database system, this requirement may be marked as N/A.

### Infrastructure Scanning

Regularly scanning cloud resources is essential for maintaining system health. Regardless of whether an application runs in the cloud or a data center, it may still be vulnerable to attacks—even without direct exposure to the internet. Infrastructure scanning enables organizations to centrally manage security policies, promptly detect potential vulnerabilities, enhance overall security visibility, and monitor abnormal activities that may indicate system compromise. This effectively reduces security threats and ensures stable business operations.

Therefore, a healthy system must meet the following requirements:

1. Cloud resources must be regularly scanned using a product like [Wiz](https://www.wiz.io/).
1. If the system does not use any cloud resources, this requirement is N/A.

### Infrastructure as Code (IaC)

IaC manages and configures infrastructure through code, replacing traditional manual operations. This automation not only reduces the risk of human error but also significantly improves efficiency. System administrators and developers can quickly deploy and update infrastructure using code, minimizing wait times and accelerating value delivery.

IaC enables infrastructure configurations to be version-controlled, ensuring consistency across development, testing, and production environments. Whether for system failures or disaster recovery, IaC allows for rapid infrastructure reconstruction. It also facilitates team collaboration and knowledge sharing while improving system maintainability and traceability through code version control.

Therefore, a healthy system must meet the following requirements:

1. All infrastructure must be defined as code and stored in a Git repository.
1. Infrastructure changes should be continuously deployed through CI/CD, just like other code changes.
1. This requirement is only N/A if the system has no infrastructure or if the vendor tools in use do not support IaC.

### Cost Saving

Regular cost reviews are essential for maintaining a healthy system. While the flexibility and agility of cloud computing accelerate innovation, unmanaged costs can quickly spiral out of control. By regularly reviewing cloud expenses, organizations can optimize resource utilization, prevent waste, and ensure budgets remain under control—all while maintaining business agility and innovation capabilities. Only with efficient cost management can cloud infrastructure support business growth while remaining financially sustainable.

Therefore, a healthy system must meet the following requirements:

1. Perform regular (every six months or quarterly) cost reviews of the infrastructure in use, such as verifying whether allocated CPU and memory resources are being fully utilized, and document the whole process in the repository.
1. System maintainers should adopt cost optimization recommendations provided by the cloud provider.

### Recovery Plan

A Disaster Recovery Plan (DRP) is essential for ensuring business continuity and data security. Whether due to hardware failures, cyberattacks, or accidental human errors, systems are always at risk of disruption. Without a well-defined recovery plan, organizations may face data loss, business downtime, and even financial and reputational damage.

For critical systems, merely having a recovery plan is not enough—regular testing of these plans is equally crucial. Testing helps verify whether the Recovery Time Objective (RTO) and Recovery Point Objective (RPO) are within expected limits, ensuring that systems can recover quickly with minimal data loss in the event of a failure. RTO directly impacts business recovery speed, while RPO determines the acceptable level of data loss.

Therefore, a healthy system must meet the following requirements:

1. Every system must have a documented disaster recovery plan, recorded in the 1-pager.
1. For critical systems, the disaster recovery plan must be tested regularly (every six months or annually) and documented in the 1-pager.

### Alerts Management

Timely and efficient notification of system administrators is crucial when a system failure occurs. Administrators must be made aware of issues as soon as they arise to take swift action and minimize the impact on customers, consumers, and business operations.

Therefore, a healthy system must meet the following requirements:

1. Real-time Monitoring & Alerts: The system should have comprehensive monitoring capabilities to continuously track key metrics and performance data. 
1. Multi-Channel Notifications: Alerts should be delivered via multiple channels (e.g., email, SMS, instant messaging tools, or phone calls) to ensure administrators receive them promptly during support hours.
1. Clear Alert Information: Alerts should include detailed information about the issue, such as the time of occurrence, affected components or services, and potential impact, allowing administrators to quickly understand and address the problem.
1. Alert Prioritization: Alerts should be categorized by severity to ensure critical issues receive immediate attention while low-priority alerts do not cause unnecessary distractions.
1. Rapid Response Process: A well-documented alert management process should be in place, including key alert details, emergency response procedures, and troubleshooting steps. This documentation should be included in the 1-pager to help administrators quickly identify and resolve issues.

### Incidents Not Occurring

When evaluating system health, downtime duration and impact scope are two key metrics. Downtime duration reflects the efficiency of system recovery, while impact scope indicates the extent of the disruption and its actual effect on users and business operations. These metrics help teams assess system stability and availability while providing insights for continuous improvement.

A healthy system should minimize downtime and use efficient response mechanisms and redundancy strategies to reduce the impact on users. This approach ensures consistent, high-quality service for end users, strengthening user trust and enhancing the project's long-term value.

Therefore, a healthy system must meet the following requirements:

1. Have a reliable monitoring and alerting system.
1. Have experienced no downtime, or only minimal downtime with no significant user impact, in the past three months.
1. If downtime occurred in the past three months, its impact scope must have been minimal.
