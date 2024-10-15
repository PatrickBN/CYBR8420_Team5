# Assurance Claim 5: BitWarden Encypts Customer Supplier Contracts
[Linked Assurance Cases](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Assurance%20Cases.md)

### Summary :>

The goal of this Assurance case is to clarify the way the system, handles an important part of the customer supplier process utilizing Bitwarden. [***Contracts!***] Bitwarden ensures that any and all documents are secured properly and are encrypted, stored, and transmitted in a a linear way allowing the data to be secured from unauthorized access. This also assists in guaranteeing the their integrity and confidentiality. Even with all that, there are many iterations of vunerabilities that could occur such as human error, and threats surrounding the ecosystem of the company or person in question. Such as hackers, disgruntled employees, rival businesses, and more. The important introduction to this assurance case is the notion that any questions to the integrity of the security will be swifty nullified and explained with detailed evidence.  

### Argument :{

***1->*** BitWarden enables measures to ensure there is avaliablity and data integrity. [Security Whitepaper](https://bitwarden.com/help/bitwarden-security-white-paper/) This is strengthen by the encrypted backups that are made on a regular basis to prevent any data loss. [Encryption](https://bitwarden.com/help/what-encryption-is-used/#:~:text=Bitwarden%20uses%20AES-CBC%20256-bit%20encryption%20for%20your%20vault,anything%20is%20sent%20to%20cloud%20servers%20for%20storage.) This is further strengthend by integrity checks and auto synced devices ensure that no tampering has taken place. [Encrypted Exports](https://bitwarden.com/help/encrypted-export/#:~:text=Bitwarden%20provides%20two%20encrypted%20export%20types%3A%201%20Account,protected%20with%20a%20password%20of%20your%20choosing.%20)

***2->*** Bitwarden guarantees that users retain control of their Encryption Keys. This is supported by the fact that master passwords are never transmitted or stored. There is further evidence with keys being derived via PBKDF2-SHA256. The 3rd supporting evidence comes Bitwarden providing secure account restricted exporting.  [Account Encryption Key](https://bitwarden.com/help/account-encryption-key/).

***3->*** Bitwarden secures documents using strong cryptography. This is showcased from the fact that BitWarden utilizes AES-256 bit encryption for data at rest, which is further expanded by Zero -Knowledge. This ensures that BitWarden as a program has no access to decryption keys. This is further expanded on with the TLS 1.3 ensuring secure data transmissions throughout the process. Finally, it encrypts the clients' documents before transmission ensureing a secure advanced standard. [Sensitive Info](https://bitwarden.com/blog/how-to-share-files-and-sensitive-information-securely/). [FAQ](https://bitwarden.com/help/security-faqs/).

***4->*** Bitwarden could limit granted access to documents via RBAC or Role-based access control and provide support for 2FA using TOTP, hardware keys, and biometrics with vault and auto - timeout settings. [Roles n Permissions](https://bitwarden.com/help/user-types-access-control/)

### Diagram :]
***Securing Secret Documents!!*** ![Assurance Case drawio](https://github.com/user-attachments/assets/5235aad6-3beb-4303-a5c7-d54eddc7f4cc)
