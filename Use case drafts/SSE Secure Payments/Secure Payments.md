## Use Case User Logon
[Link to SSE document](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Software%20Security%20Engineering.md)

### Description:

This use case secures employees company credit/debit cards using BitWarden and assigns their use to employees with access controls and multi-factor authentication.

### A.I. Prompts used to assist with use/misuse case:

As a senior software developer generate a diagram that develops a use-case diagram using BitWarden to secure a companies credit cards or debit cards and assigning their use to employees. Iterate between use and misuse cases to elaborate additional security functions. Give me a simple and complex latex coding flowchart for overleaf.

### Analysis:
  
  1. Security Requirements:
      * Multi-Factor Authentication (MFA): Ensures that employees accessing BitWarden and retrieving card information use secure methods to prevent unauthorized access.
      * Role-Based Access Control (RBAC): Limits access to sensitive information based on the employee's role, reducing the risk of insider misuse.
      * Encryption of Sensitive Data: Protects card data and transactions through encryption, ensuring confidentiality during access and usage.
      * Intrusion Detection Systems (IDS): Monitors for unauthorized access attempts, such as credential stuffing or external attacks, to quickly alert administrators.
      * Real-Time Monitoring & Automated Logging: Tracks transactions and generates real-time alerts for anomalies, enhancing oversight and quick response to security incidents.
      * Secure Transaction Process: Validates legitimate access and ensures notifications are sent to maintain accountability for each transaction.

  2. Security Features:
      * Multi-Factor Authentication (MFA): Ensures that employees accessing BitWarden and retrieving card information use secure methods to prevent unauthorized access. [Here](https://bitwarden.com/help/bitwarden-authenticator/)
      * Role-Based Access Control: Bitwardens RBAC makes sure that employees only have access to the secretst that is needed by their job function. When an organization uses Bitwarden they are able to set roles and permissions for each user. The roles determine what actions a member can take but don't deterine what collections they have access to. Permissions tell what actions a user can take with the items in the collection. [Here](https://bitwarden.com/help/user-types-access-control/)
      * Encryption of Sensitive Data: Protects card data and transactions through encryption, ensuring confidentiality during access and usage. [Here](https://bitwarden.com/help/bitwarden-security-white-paper/)
      * Intrusion Detection Systems (IDS): Monitors for unauthorized access attempts, such as credential stuffing or external attacks, to quickly alert administrators. [Here](https://bitwarden.com/help/bitwarden-security-white-paper/)
      * Real-Time Monitoring & Automated Logging: Tracks transactions and generates real-time alerts for anomalies, enhancing oversight and quick response to security incidents. [Here](https://bitwarden.com/help/event-logs/)
      * Secure Transaction Process: Validates legitimate access and ensures notifications are sent to maintain accountability for each transaction. [Here](https://bitwarden.com/help/bitwarden-security-white-paper/)

Diagram:

![](https://github.com/PatrickBN/CYBR8420_Team5/blob/4d1a3793dfebfd19ebfa1a84eed433eb46815118/Use%20case%20drafts/SSE%20Secure%20Payments/Use-Misuse%20Case%204(1-1).drawio.png)
