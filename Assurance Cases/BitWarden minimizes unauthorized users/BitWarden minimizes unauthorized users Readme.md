# Assurance Claim 1: BitWarden minimizes unauthorized users
[Back to Assurance Cases](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Assurance%20Cases.md)

### Summary

In order for the employees to logon into the hypothetical operating enivronment system they must use the BitWarden OSS. This requires each employee to go through authorization, because of the need to ensure proper authorization, assurance is required to mitigate the doubts about BitWardens ability to provide trustworthy user authentication.

### Argument

E1: The BitWarden password policy is set by the admin, while the default length is 5, the admin has a lot of control over how long the password can be and what special characters can be in it. [Here is the source code](https://github.com/bitwarden/clients/blob/main/libs/tools/generator/core/src/types/password-generator-policy.ts)

E2: The BitWarden 2-FA is a 5-10 digit code that uses SHA-1 to generate a new code every 30 seconds [Source](https://bitwarden.com/help/bitwarden-authenticator/). BitWarden also allows for Duo, Email, and Yubikey [authenticators](https://github.com/bitwarden/clients/blob/main/libs/angular/src/auth/components/two-factor-auth/two-factor-auth.component.ts#L53) this grants a wide range of secured ways to use 2-FA whil retaining the security requirements for the hypothetical operating environment.

E3: The encryption protecting the passwords utilizes [PBKDF2](https://github.com/bitwarden/clients/blob/main/libs/node/src/services/node-crypto-function.service.ts#L13) to generate the hash and salt the password. The full process is described [here](https://bitwarden.com/help/what-encryption-is-used/#pbkdf2)

E4: The account recovery keys are [encrypted](https://bitwarden.com/help/account-recovery/#encryption) by using a public key belonging to the organziation and the users account encryption key and decrypted with the oganizations private key.


### Diagram
![](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Assurance%20Cases/BitWarden%20minimizes%20unauthorized%20users/Assurance%20Cases%20draft%203.png)
