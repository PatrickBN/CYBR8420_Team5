[Back to Assurance Cases](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Assurance%20Cases.md)
# Assurance Claim 1: Bitwarden checks if passwords have been in data breaches using Have I Been Pwned (HIBP) database


# Assurance: This feature gives users proactive alerts to change compromised passwords, further securing their online accounts.

### Summary
The Data Breach reports identify compromised data (email addresses, passwords, credit cards, DoB, and more) in known breaches, using a service called Have I Been Pwned (HIBP). Bitwarden uses the same HIBP database to check if  any of the stored passwords have appeared in data breaches. Users are alerted and prompted to update their password if any matches are found in the HIBP database

### Argument
Bitwarden checks for compromised passwords through its integration with breach detection services Have I Been Pwned (HIBP). When a user saves or updates a password in their vault, Bitwarden does not send the full password to these services for checking. Instead, it uses a technique called k-anonymity to protect user privacy. This method involves hashing the password and only sending a portion of the hashed value (the first few characters) to the breach detection service. The service then returns potential matches for the partial hash, and Bitwarden compares these results locally to determine if the full hashed password is found in the list of breached credentials.

If Bitwarden detects that a password has been compromised in a known data breach, it notifies the user, recommending that they update the exposed password. Bitwarden also provides tools to help users strengthen their security, such as generating strong, unique passwords and enabling two-factor authentication. Additionally, Bitwarden’s Vault Health Reports allow users to regularly check for weak, reused, or compromised passwords, further enhancing their overall security. This system ensures that users can stay informed about potential threats without compromising their privacy or exposing their credentials during the checking process.

[Bitwarden](https://bitwarden.com/blog/have-you-been-pwned/)

[Bitwarden Reports](https://bitwarden.com/help/reports/#:~:text=The%20Data%20Breach%20report%20identifies,before%20deciding%20to%20use%20it.)

[Bitwarden FAQ](https://haveibeenpwned.com/FAQs#:~:text=Pastes%20are%20often%20transient;%20they,longer%20exists%20at%20the%20source.)

[Consumer Reports](https://www.consumerreports.org/electronics/data-theft/how-to-use-have-i-been-pwned-data-breach-a6598286668/)

### Diagram
![](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Assurance%20Cases/Bitwardern%20checks%20in%20a%20password%20is%20compromized/Bitwarden.png)
