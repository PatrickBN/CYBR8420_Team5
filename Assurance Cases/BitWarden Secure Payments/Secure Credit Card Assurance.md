# Assurance Claim 1: BitWarden Secures Credit Card Payment Information
[Back to Assurance Cases](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Assurance%20Cases.md)

### Summary

This assurance case demonstrates that the system, which manages company credit cards through BitWarden, provides robust security mechanisms, including Role-Based Access Control (RBAC), encryption, and network monitoring, to mitigate risks from both internal and external threats. However, several potential vulnerabilities challenge the completeness of this claim. These include human error, sophisticated attacks that bypass defenses, insider threats, and physical risks like lost credit cards. Additionally, compliance with security standards does not guarantee total protection. Overall, while the system offers substantial safeguards, the assurance case acknowledges that certain risks, especially those involving human factors and unforeseen vulnerabilities, remain critical challenges to address.

### Argument

E1: BitWarden's encryption policy centers around using end-to-end encryption (E2EE) to protect user data. All sensitive information, including vault items such as passwords, notes, and credit card details, is encrypted locally on the user's device using AES-256 bit encryption before it is transmitted to Bitwarden servers. Bitwarden also implements PBKDF2 with SHA-256 to derive a secure encryption key from the user's master password, ensuring that only the user can decrypt their vault. [Encryption Policy](https://bitwarden.com/help/what-encryption-is-used/).

E2: TThe Data Breach report identifies compromised data (email addresses, passwords, credit cards, DoB, and more) in known breaches, using a service called Have I Been Pwned (HIBP). When you create a Bitwarden account, you'll have the option to run this report on your master password before deciding to use it. To run this report, a hash of your master password is sent to HIBP and compared to stored exposed hashes. Your master password itself is never exposed by Bitwarden.  [Data Breach Report](https://bitwarden.com/help/reports/#data-breach-report-individual-vaults-only).

E3: Bitwarden's approach to onboarding and succession planning for members are [here](https://bitwarden.com/help/onboarding-and-succession/#the-bitwarden-approach). Bitwarden utilizes the following key security measures to protect data stored in [Bitwarden](https://bitwarden.com/help/bitwarden-security-white-paper/#key-security-measures)


### Diagram
![](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Assurance%20Cases/BitWarden%20Secure%20Payments/Assurance%20Case%20Secure%20Payments.png)
