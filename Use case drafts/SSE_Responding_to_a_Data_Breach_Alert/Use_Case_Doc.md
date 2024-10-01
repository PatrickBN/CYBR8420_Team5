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
//TODO


