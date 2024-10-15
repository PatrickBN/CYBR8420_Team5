# Assurance Cases

### Assurance Cases and Summaries

  1. Tobias Lathrop - [BitWarden minimizes unauthorized users](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Assurance%20Cases/BitWarden%20minimizes%20unauthorized%20users/BitWarden%20minimizes%20unauthorized%20users%20Readme.md)

     Summary: In order for the employees to logon into the hypothetical operating enivronment system they must use the BitWarden OSS. This requires each employee to go through authorization, because of the need to ensure proper authorization, assurance is required to mitigate the doubts about BitWardens ability to provide trustworthy user authentication.
            
  2. Conner Braley - [BitWarden Uses Secrets to ensure code is protected from unauthorized access](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Assurance%20Cases/Bitwarden%20Using%20Secrets%20To%20Ensure%20Code%20Is%20Protected/BitWarden%20Using%20Secrets%20to%20Ensure%20Code%20is%20Protected%20Readme.md)

     Summary: In our hypothetical environment, using BitWardens secret manager is needed to protect our public facing systems, and our internal resources. It provides strong encryption, which makes sure that sensitive data are protected during storage and transit. This protects us against potential breaches. Access to the secrets is restricted to authorized personnel. Bitwarden also allows centralized management through a secure admin console, making it easy to manage staff access. The system also makes sure their is regular rotation of secrets, minimizing the risk of compramised credentials. Finally, it maintains secure logs for accountability. This allows us to operate confidently, knowing our data and systems are protected from unauthorized access and vulnerabilities.

3. Kwanz Skinner - [BitWarden Secures Credit Card Payment Information](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Assurance%20Cases/BitWarden%20Secure%20Payments/Secure%20Credit%20Card%20Assurance.md)

    Summary: This assurance case demonstrates that the system, which manages company credit cards through BitWarden, provides robust security mechanisms, including Role-Based Access Control (RBAC), encryption, and network monitoring, to mitigate risks from both internal and external threats. However, several potential vulnerabilities challenge the completeness of this claim. These include human error, sophisticated attacks that bypass defenses, insider threats, and physical risks like lost credit cards. Additionally, compliance with security standards does not guarantee total protection. Overall, while the system offers substantial safeguards, the assurance case acknowledges that certain risks, especially those involving human factors and unforeseen vulnerabilities, remain critical challenges to address.

  4. Patrick Nikiema - [Bitwarden checks if passwords have been in data breaches using Have I Been Pwned (HIBP) database](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Assurance%20Cases/Bitwardern%20checks%20in%20a%20password%20is%20compromized/Bitwarden%20Compromised%20passwords%20Review.md)

     Summary: The Data Breach reports identify compromised data (email addresses, passwords, credit cards, DoB, and more) in known breaches, using a service called Have I Been Pwned (HIBP). Bitwarden uses the same HIBP database to check if any of the stored passwords have appeared in data breaches. Users are alerted and prompted to update their password if any matches are found in the HIBP database

5. Debaris Ezumah - [BitWarden Encrypts Customer Supplier Contracts](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Assurance%20Cases/BitWarden%20Encrypts%20CS%20Contracts/Encrypt%20CS%20Contract%20Assurance.md)

     Summary: Bitwarden’s comprehensive set of security frameworks, encryption, authentication, and admin controls ensures the confidentiality, integrity, and availability of contracts for Enterpenuers and Suppliers to store and call back on in times or renegotiation using our system as a middleman. BitWarden does a good job evidence mapping; showcasing the the safety and reliablity taken with encrption audits, documentation, and incident responses logs. All documentation is encrypted, stored, and transmitted in a way that protects the files using Zero-knowledge and TOTP to name a few. 
   
### Alignment and Gaps


  1: Bitwarden minimizes unauthorized users 
      
  Alignment: The BitWarden software aligns well with the goal of reducing the instances or likelihood of an unauthorized user gaining access to a user account. The password hashing and salting reduces the chance of an attacker brute forcing the password. The 2 factor authentication further reduces the chance of unauthorized access by adding extra steps if a password is compromised, and the account recovery steps would allow for a user to change their password in the event that the account is compromised and the user needs to reset the password.
      
  Gaps: The main gap in this assurance is the default password policy, the policy is only a minimum of 5 character lengths and contains no special requirements. While this policy is changeable through an admin console a careless admin could easily forget to change the default policy which would greatly weaken all the security features used to minimize authorized users.

  2: BitWarden secures sensitive credit card information

  Alignment: Bitwarden seems to be fit for the purpose of this project, which is protecting the sensitive information and payments on a company’s credit card. The use of encryption to secure the data uses end-to-end encryption to protect all sensitive information and cannot be accessory by unauthorized parties, including Bitwarden itself. Implementation of RBAC is supported by BitWarden’s ability to assign specific permissions to users base on their roles. The ability to focus on mitigating risks from external and internal threats aligns with the overall goal. 

Gaps: While the assurance case focuses on digital security measures it does not fully address the physical risks, such as the loss or theft of company credit cards. Human factors and training could always be a gap. The mishaps of employees can easily be an issue. Another issue is the lack of responsibility the company will take if security measures fail, such as in the event of a breach or insider threat. The assurance case does not consider whether the security mechanisms (encryption, monitoring, etc.) scale effectively as the organization grows or if performance is impacted by security features like constant encryption/decryption or monitoring.
  
  3: BitWarden using secrets to ensure that code is protected from unauthorized users 
  
  Encryption policies like AES-256 are well documented and available with no gaps. When it comes to encryption vulnerability testing that is done through BitWardens security audits, project-specific vulnerability assessments should be preformed independently. This helps with protection. Configuration settings for access control are documented but we would need to audit our own configuration to verify proper implementation. For misconfigure alerting, Bitwarden supports it, however custom configurations might need additional setup to make sure that misconfigurations are detected. Secret policies are clearly documented and so is logging. Endpoint security is not documented or covered by BitWarden and will require some additional measures. This will make sure that secrets are safe against endpoint vulnerabilities. 
  
  4: Bitwarden checks if a password has been compromised
  
  Alignment: Bitwarden aligns with checking if a password is compromised by integrating with breach detection services like Have I Been Pwned. It uses a privacy-preserving method called k-anonymity, where only part of the hashed password is sent to the breach service to check against known data breaches without revealing the actual password. If a match is found, Bitwarden alerts the user to the compromised password and prompts them to take action, such as updating the password with a stronger, unique one. This ensures users are notified of potential security risks while keeping their credentials secure throughout the process.
  
  Gaps: Bitwarden’s system for checking compromised passwords has a few key gaps. First, it relies on external services like Have I Been Pwned, meaning it can only detect passwords from publicly known breaches, missing any undisclosed incidents. There can also be delays between when a breach occurs and when it is added to these databases, leaving users exposed in the interim. Additionally, while Bitwarden uses k-anonymity to protect privacy during checks, this method only checks part of the password hash, which could lead to potential inaccuracies. Lastly, Bitwarden does not automate any remediation; it alerts users to compromised passwords, but users must manually update them, which could lead to delays in securing accounts.
  
  5: BitWarden enrcrypts a sensitive contract

  Alignment: Bitwardens approach to encrypting secure notes strongly adheres with the best industry practices. With Zero-Knowledge architeture it cannot decrypt secure notes since no keys are avaliable. There is also the fact that data is being encrypted using TLS 1.3 for secured communication between users and the database. The protection against brute force attacks using AES-256 at rest help limit such threats. Conducting penetration tests and maintaining a scheduled backup is also key in BitWarden being a powerful conductor for encrypting important information that contains legal, finacnial, or anything legally binding signed by both parties.


  Gaps:

### Reflections

  The assurance cases were developed by extending the work done in the previous deliverable, as we each had more specialized knowledge of the BitWarden software from different viewpoints we were able to more easily move the work done into this deliverable. This project featured much more colloboration and review in between team members. After receiving the professors recommendations the team set out to work together more and create more consistent work. While the work was still split among the team members each team member has been more proactive in getting feedback and aligning our formatting for more consistency across the deliverable.   
  
Conner Braley - For this assignment the assurance cases that we developed were done based off of the previous deliverable. I think the teamwork done between us was good as we began to communicate more to give feedback and help each other out with what could be fixed. The team is working hard, however despite all of our different schedules and were able to accomplish this assignment. 

    
Debaris Ezumah - 
