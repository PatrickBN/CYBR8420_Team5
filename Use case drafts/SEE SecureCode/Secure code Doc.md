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
