# Assurance Case #2: Bitwarden Uses Secrets to Ensure Code is Protected From Unauthorized Users
[Back to Assurance Cases](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Assurance%20Cases.md)

### Summary

In our hypothetical environment, using BitWardens secret manager is needed to protect our public facing systems, and our internal resources. It provides strong encryption, which makes sure that sensitive data are protected during storage and transit. This protects us against potential breaches. Access to the secrets is restricted to authorized personnel. Bitwarden also allows centralized management through a secure admin console, making it easy to manage staff access. The system also makes sure their is regular rotation of secrets, minimizing the risk of compramised credentials. Finally, it maintains secure logs for accountability. This allows us to operate confidently, knowing our data and systems are protected from unauthorized access and vulnerabilities.

### Arguments

E1: BitWardens encryption policy review comfirms that strong encryption algorithms are used in agreement with with industries best practice. This ensures that secrets are stored with a high level of security, severely reducing the risk of unauthorized access through weak encryption. [Source](https://bitwarden.com/help/bitwarden-security-white-paper/) 

E2: Bitwardens Configuration Settings shows that RBAC and MFA are properly configured and enforced, which makes sure that authorized users are the only one's that have access to secrets. This reduces the likelyhood of unauthorized access due to misconfiguration. [Source](https://bitwarden.com/help/user-types-access-control/) [Source #2](https://bitwarden.com/help/bitwarden-authenticator/)

E3: Bitwardens Secret Rotation policy review shows that Bitwarden enforces a regular secret rotation scheudle. This minimizes the risl of compramised secrets that are used for extended periods of times. Secrets are automatically refreshed, which reduces the window of oppurtunity for attakers. [Source](https://bitwarden.com/help/account-encryption-key/)

E4: BitWardens logging review verifies that comprehensive audit logs are maintained for all secret access and modification events. This supports traceability, and and accountability, which makes sure that all actions on secrets are recorded. This minimizes the risk of tampering. [Source](https://bitwarden.com/help/bitwarden-security-white-paper/#logging-monitoring-and-alert-notification)

### Diagram

![](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Assurance%20Cases/Bitwarden%20Using%20Secrets%20To%20Ensure%20Code%20Is%20Protected/Assurance%20Case.drawio.png)
