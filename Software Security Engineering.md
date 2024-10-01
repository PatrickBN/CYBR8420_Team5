# Software Security Engineering Report

### Use Cases

  1. Logon to User Account
  2. Secure Code
  3. Responding to a Data Breach
  4. Secure Payments
  5. Customer-supplier process

### Findings Summary

  1. Introduction

BitWarden's use in our hypothetical operating environment is essential for maintaining the security of the business operations. From employee *User Logon* we are able to ensure that when an employee logs onto their account the actions taken can be reasonably assumed to be the actions of an employee. With *Secure Code* can be be assured that the code for our hypothetical operating environment isn't compromised by a threat actor. With *Responding to a Data Breach* we can be aware of events that may have impacted the security of our systems. *Secure Payments* allows us to maintain company cards/accounts that can be monitored. And *Customer-Supplier process* keeps our supply chain intact, ensuring our hypothetical operating environment will continue operating. These use cases take an indepth look at how BitWarden will protect our hypothetical operating environment from misuse.

  2. Use Cases

     * [User logon](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Use%20case%20drafts/SSE%20User%20logon/Use%20case%20user%20logon%20Doc.md)
           Each employee has access to a password manager and secrets manager that will enable them to have assurance when they log into their accounts and submit code using their accounts that they are the only ones with access.
       
     * [Secure Code](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Use%20case%20drafts/SEE%20SecureCode/Secure%20code%20Doc.md)
           An employee is using Bitwarden for secure storage and management of sensitive information such as credentials, API keys, or other secrets.
     * [Responding to a Data Breach](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Use%20case%20drafts/SSE_Responding_to_a_Data_Breach_Alert/Use_Case_Doc.md)
     * [Secure Payments](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Use%20case%20drafts/SSE%20Secure%20Payments/Secure%20Payments.md)
           This use case secures employees company credit/debit cards using BitWarden and assigns their use to employees with access controls and multi-factor authentication.
     * [Customer-Supplier process](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Use%20case%20drafts/SSE%20Customer%20Supplier/Customer_Supplier%20Doc.md) 
           This displays the relationship between front-end customer, supplier, bank, and 'possible' outside threats.
## OSS project documentation for security-related configuration and installation issues

  As of September 30, 2024 there are no open security issues, with the security tag, for BitWarden. However, Bitwarden maintains a priavte security issues board that keeps some of these security issues out of the [public eye](https://hackerone.com/bitwarden?type=team). There are installtion concerns for our hypothetical operating environment as listed below. Some of these issues may be security related but they don't appear to impact the security performance of the actual BitWarden software, i.e. no issues with password hashing, or key generation, or operation of the secrets manager.   

  1. Vault domains don't support IPv6 [4102](https://github.com/bitwarden/server/issues/4102)
  2. User creation on new installation not working [#4725](https://github.com/bitwarden/server/issues/4725)
  3. Error pre-validating against SSO service [#3205](https://github.com/bitwarden/server/issues/3205)
  4. Site ICON lookup causing a DNS flood of requests to DNS server [#3179](https://github.com/bitwarden/server/issues/3179)

### Reflections

Tobias Lathrop: Although we still have to work around our various schedules the team managed to pull together, and even after adding a new team member halfway through the week, put together a Software Security Engineering document that exceeds my expectations. The quality of work from the group for this assignment is something I hope to bring to the rest of the project. While I would still like to improve my communication effiency and clarity I am happy with how this has turned out. I would also like to work on getting my part of the project done in a more timely manner so that I can provide more in depth feedback to my teammates and provide more of a guide as the team leader.

Conner Braley:

Kwanz Skinner:

Patrick Nikiema:

Debaris Ezumah:

### Contributions
