# Software Security Engineering Report

### Use Cases

  1. Logon to User Account
  2. Secure Code
  3. Responding to a Data Breach
  4. Secure Payments
  5. Customer-supplier process

### Findings Summary

  1. Introduction



  2. Use Cases

     * [User logon](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Use%20case%20drafts/SSE%20User%20logon/Use%20case%20user%20logon%20Doc.md)
           Each employee has access to a password manager and secrets manager that will enable them to have assurance when they log into their accounts and submit code using their accounts that they are the only ones with access.
       
     * []()
     * []()
     * []()
     * []() 

# OSS project documentation for security-related configuration and installation issues

  As of September 30, 2024 there are no open security issues, with the security tag, for BitWarden. However, Bitwarden maintains a priavte security issues board that keeps some of these security issues out of the [public eye](https://hackerone.com/bitwarden?type=team). There are installtion concerns for our hypothetical operating environment as listed below. Some of these issues may be security related but they don't appear to impact the security performance of the actual BitWarden software, i.e. no issues with password hashing, or key generation, or operation of the secrets manager.   

  1. Vault domains don't support IPv6 [4102](https://github.com/bitwarden/server/issues/4102)
  2. User creation on new installation not working [#4725](https://github.com/bitwarden/server/issues/4725)
  3. Error pre-validating against SSO service [#3205](https://github.com/bitwarden/server/issues/3205)
  4. Site ICON lookup causing a DNS flood of requests to DNS server [#3179](https://github.com/bitwarden/server/issues/3179)

### Reflections

### Contributions
