## Use Case Secure Code
[Link to SSE document](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Software%20Security%20Engineering.md)

### Description:

An employee is using Bitwarden for secure storage and management of sensitive information such as credentials, API keys, or other secrets.

### A.I. prompts used to help with use/misuse case:

No A.I. prompts where used.

### Analysis:

  1. Security Requirements:
     * Multi-Factor Authentication: To Mitigate the risk of phishing attacks a two-factor authentication method is needed. This makes sure that even if a users credentials are compromised, the attacker cannot gain accsess without the second factor.
     * Role-Based Access Control: This is useful in order to limit the scope of secrets an employee can access. If we don't have RBAC employees could access secrets beyond their role. This increases the risk of misuse or threats. Using RBAC restricts secret access to the employees who need it. This helps lower the impact of a potential insider threat.
     * Audit Logging: This is needed to track people who access, stores, or retrieves secrets. This makes sure that all events are logged, which allows Bitwarden to detect unusual behavior. Logs should also capture any modifications to help show evidence when there is a security incident.

  2. Security Features:
     * Multi-Factor Authentication: Bitwarden has their own two-factor authentication methods. [Here](https://bitwarden.com/help/setup-two-step-login/)
     * Role-Based Access Control: Bitwardens RBAC makes sure that employees only have access to the secretst that is needed by their job function. When an organization uses Bitwarden they are able to set roles and permissions for each user. The roles determine what actions a member can take but don't deterine what collections they have access to. Permissions tell what actions a user can take with the items in the collection. [Here](https://bitwarden.com/help/user-types-access-control/)
     * Audit Logging: These logs are timestamped records of events that occur within a organization. Events are captured at both the Bitwarden client and server. Server event capture is constant and quickly processed, clients push event data to the server every 60 seconds, which could cause some delays. Client events data is communicated data with an API call, and this is retried until their is success. If the user cannot communicate with the API or is somehow modified to not send events then they will not be received and therefore processed. [Here](https://bitwarden.com/help/event-logs/)

### Diagram:

![](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Use%20case%20drafts/SEE%20SecureCode/SecretsManagerDiagram2.png)
