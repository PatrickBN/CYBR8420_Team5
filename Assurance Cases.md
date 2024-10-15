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

5. Debaris Ezumah - 

### Alignment and Gaps


  1: Bitwarden minimizes unauthorized users 
      
  Alignment: The BitWarden software aligns well with the goal of reducing the instances or likelihood of an unauthorized user gaining access to a user account. The password hashing and salting reduces the chance of an attacker brute forcing the password. The 2 factor authentication further reduces the chance of unauthorized access by adding extra steps if a password is compromised, and the account recovery steps would allow for a user to change their password in the event that the account is compromised and the user needs to reset the password.
      
  Gaps: The main gap in this assurance is the default password policy, the policy is only a minimum of 5 character lengths and contains no special requirements. While this policy is changeable through an admin console a careless admin could easily forget to change the default policy which would greatly weaken all the security features used to minimize authorized users.

  2: BitWarden secures sensitive credit card information

  Alignment: Bitwarden seems to be fit for the purpose of this project, which is protecting the sensitive information and payments on a company’s credit card. The use of encryption to secure the data uses end-to-end encryption to protect all sensitive information and cannot be accessory by unauthorized parties, including Bitwarden itself. Implementation of RBAC is supported by BitWarden’s ability to assign specific permissions to users base on their roles. The ability to focus on mitigating risks from external and internal threats aligns with the overall goal. 

Gaps: While the assurance case focuses on digital security measures it does not fully address the physical risks, such as the loss or theft of company credit cards. Human factors and training could always be a gap. The mishaps of employees can easily be an issue. Another issue is the lack of responsibility the company will take if security measures fail, such as in the event of a breach or insider threat. The assurance case does not consider whether the security mechanisms (encryption, monitoring, etc.) scale effectively as the organization grows or if performance is impacted by security features like constant encryption/decryption or monitoring.
  
  3:
  
  4:
  
  5:

### Reflections

  The assurance cases were developed by extending the work done in the previous deliverable, as we each had more specialized knowledge of the BitWarden software from different viewpoints we were able to more easily move the work done into this deliverable. This project featured much more colloboration and review in between team members. After receiving the professors recommendations the team set out to work together more and create more consistent work. While the work was still split among the team members each team member has been more proactive in getting feedback and aligning our formatting for more consistency across the deliverable. 
  
