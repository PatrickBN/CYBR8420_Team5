**Use Case Description:**<br>
Bitwarden identifies that a password stored in the vault has been compromised in a known data breach. The user receives a notification, logs in to Bitwarden, and updates the breached password, which is then securely saved in the vault.
Preconditions: The user has credentials that were involved in a breach and tied to a known service.
Postconditions: The compromised password is updated, and the user's accounts are now secured.

**Security Requirements:**<br>
For Bitwarden's Responding to a Data Breach Alert scenario, the following security measures are critical to maintaining the system's protection and safeguarding user data.

Bitwarden uses trusted breach detection services and secure protocols to identify compromised credentials.
Breach notifications are be securely delivered and authenticated to prevent phishing or tampering.
Enforcing two-factor authentication (2FA) in enforced
Bitwarden automatically evaluates other stored credentials for reuse of breached passwords and alert users if found.
Users should must update compromised passwords with strong alternatives that are securely stored and synchronized.
All breach-related actions must be securely logged and auditable to detect any unauthorized activity.
Breach notifications are only exposed the necessary information to avoid leaking sensitive data.
Breach alerts are delivered promptly, and users must be immediately prompted to update compromised credentials.
Bitwarden must ensure that user devices and software are secure and resistant to tampering.<br>
<br>**Source: https://bitwarden.com/help/bitwarden-security-white-paper/**<br><br>
**Security Features:**<br>
Bitwarden encrypts all stored data with AES-256, both while it's being transferred and when it's stored, so only the user can access it.
It doesn’t store or know your master password, meaning only you can unlock your vault.
It supports various 2FA methods and includes a secure tool to help users create strong, unique passwords.
Bitwarden syncs encrypted data securely across different devices, like desktop, mobile, and browser extensions.
Users can securely share passwords and other sensitive data through encrypted channels with trusted individuals or organizations.
It notifies users if their credentials appear in known data breaches through integrations like Have I Been Pwned, offers tools to check vault security, including password strength analysis and flagging of weak or reused passwords.
Organizations can choose to self-host Bitwarden to control their own data and infrastructure.
Bitwarden logs all activities within the vault, helping track actions and identify suspicious behavior. Users can designate trusted individuals to access their vault in case of emergency. It provides encrypted backup and recovery options for vault data and allows users to store documents securely by attaching encrypted files to vault items.
Regular third-party security audits ensure that Bitwarden follows the latest best practices for security.

<br>**Source:https://www.techrepublic.com/article/bitwarden-review/**<br>
<br>**https://www.pcmag.com/reviews/bitwarden**<br>
<br>**Source: https://bitwarden.com/help/bitwarden-security-white-paper/**<br><br>

**Diagram:**<br>
![](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Use%20case%20drafts/SSE_Responding_to_a_Data_Breach_Alert/Diagram.png)
