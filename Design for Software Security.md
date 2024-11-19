## 1. Data Flow Diagrams and Threat Modeling

  1. [BitWarden Login Diagram](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Software%20Security%20Engineering/DFDs/Diagram%20login%201.PNG)
  2. [BitWarden Data Breach Diagram](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Software%20Security%20Engineering/DFDs/Diagram%20Breach%202.PNG)
  3. [Threat Modeling](https://htmlpreview.github.io/?https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Software%20Security%20Engineering/DFDs/DFD%20threats.htm)

  ## 2. Introduction

  The DFD we created cover the main use cases we identified earlier on. While most of the use cases were covered by the first diagram the second diagram covers the two use cases that require data being transmitted to and from outside the BitWarden system. This required the second DFD as we were introducing a new possible threat vector from the data coming from outside the BitWarden system. 
  
  The Microsoft threat modelling tool was used to create the list of possible threats from the DFD, those threats are listed below with each having a *description* of the threat as well as the *justification* for mitigation by which it is mitigated through BitWarden or could be mitigated. The Gaps noted in the mitigations will be listed below in the second part where we look at the gaps in BitWarden's mitigation. 
  
  ## 3. Threat review and Mitigation

  1. Spoofing the MFA External Entity
     
     Description:	MFA may be spoofed by an attacker and this may lead to unauthorized access to BitWarden Client. Consider using a standard authentication mechanism to identify the external entity.
     
     Justification: Use of digital certificates ensures proper authentication

  2. Elevation Using Impersonation
     
     Description:	BitWarden Client may be able to impersonate the context of MFA in order to gain additional privilege.
     
     Justification: Authentication is required in order to gain additional privilege

  3. Spoofing the BitWarden Client Process
     
     Description:	BitWarden Client may be spoofed by an attacker and this may lead to information disclosure by MFA. Consider using a standard authentication mechanism to identify the destination process.
     
     Justification: Use of digital certificates ensures proper authentication
     
  4. Potential Lack of Input Validation for BitWarden Client
     
     Description:	Data flowing across 2fa may be tampered with by an attacker. This may lead to a denial of service attack against BitWarden Client or an elevation of privilege attack against BitWarden Client or an information disclosure by BitWarden Client.
     
     Justification: BitWarden uses a validation Service to validate input a user's input is never executed.
     
  5. Potential Data Repudiation by BitWarden Client
     
     Description:	BitWarden Client claims that it did not receive data from a source outside the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.
     
     Justification: BitWarden replaces non-existing files and any files that have been tampered with cause an error that leads to a crash.
     
  6. Data Flow Sniffing
     
     Description:	Data flowing across 2fa may be sniffed by an attacker. Depending on what type of data an attacker can read, it may be used to attack other parts of the system or simply be a disclosure of information leading to compliance violations. Consider encrypting the data flow.
     
     Justification: Sensitive data isn't stored locally and all data sent across a network is encrypted.
     
  7. Potential Process Crash or Stop for BitWarden Client
     
     Description:	BitWarden Client crashes, halts, stops or runs slowly; in all cases violating an availability metric.
     
     Justification: Currently BitWarden crashes with an error message, current coding practices dictate that this be necessary in the case of tampering.

  8. Data Flow 2fa Is Potentially Interrupted

     Description: An external agent interrupts data flowing across a trust boundary in either direction.

      Justification: The 2fa authentication is logged and encryption can be used to prevent data sniffing.
     
  9. BitWarden Client May be Subject to Elevation of Privilege Using Remote Code Execution
     
      Description: MFA may be able to remotely execute code for BitWarden Client.
     
      Justification: Input validation and sanitization is used to disallow local code execution.
     
  10. Elevation by Changing the Execution Flow in BitWarden Client
     
      Description: An attacker may pass data into BitWarden Client in order to change the flow of program execution within BitWarden Client to the attacker's choosing.
     
      Justification: Input validation and sanitization is used to ensure data is sanitized before entering the program flow.
      
  13. Spoofing of the MFA External Destination Entity
     
      Description: MFA may be spoofed by an attacker and this may lead to data being sent to the attacker's target instead of MFA.
     
      Justification: The MFA uses authentication signatures to prevent spoofing.
      
  14. External Entity MFA Potentially Denies Receiving Data
     
      Description: 	MFA claims that it did not receive data from a process on the other side of the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.
     
      Justification: The BitWarden MFA and desktop client both keep logs.
     
 15. Data Flow 2fa confirmation Is Potentially Interrupted
     
      Description: 	An external agent interrupts data flowing across a trust boundary in either direction.
     
      Justification: Use firewalls and Network Access Control Lists (ACLs) to limit communication to authorized IP addresses and ports.

  16. Spoofing of Source Data Store Password DB
     
      Description: 	Password DB may be spoofed by an attacker and this may lead to incorrect data delivered to BitWarden Client. Consider using a standard authentication mechanism to identify the source data store.
     
      Justification: Require the password database to authenticate itself to the BitWarden client using a standard authentication protocol, such as PKI (Public Key Infrastructure) using server-side certificates.
 
  17. Weak Access Control for a Resource
     
      Description: 	Improper data protection of Password DB can allow an attacker to read information not intended for disclosure. Review authorization settings.
     
      Justification: Conduct regular vulnerability scans and penetration tests on the database.
 
  18. Spoofing of the Employee External Destination Entity
     
      Description: 	Employee may be spoofed by an attacker and this may lead to data being sent to the attacker's target instead of Employee. Consider using a standard authentication mechanism to identify the external entity.
     
      Justification: Use mutual TLS (Transport Layer Security) to authenticate both the employee’s device/system and the external destination entity.
 
  19. External Entity Employee Potentially Denies Receiving Data
     
      Description: 	Employee claims that it did not receive data from a process on the other side of the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.
     
      Justification: Sign all transmitted data with a sender’s private key and require the recipient (External Entity Employee) to acknowledge receipt by signing with their private key.

  20. Data Flow Key & confirmation Is Potentially Interrupted
     
      Description: 	An external agent interrupts data flowing across a trust boundary in either direction.
     
      Justification: Using encryption or firewall controls to prevent interception of the data.
 
  21. Spoofing the Employee External Entity
     
      Description: 	Employee may be spoofed by an attacker and this may lead to unauthorized access to BitWarden Client. Consider using a standard authentication mechanism to identify the external entity.
     
      Justification: Establish multiple, independent channels for key exchange and confirmation or Use protocols like TCP for automatic retransmission of lost packets.
 
  22. Elevation Using Impersonation
     
      Description: 	BitWarden Client may be able to impersonate the context of Employee in order to gain additional privilege.
     
      Justification: Require reauthentication (e.g., entering a password or MFA) whenever a user or process requests elevated privileges and monitor for patterns of privilege escalation to detect anomalies. Monitor for unusual patterns, such as privilege escalation attempts outside normal working hours. Use machine learning tools to identify deviations from typical user behavior.
  
  23. Spoofing the BitWarden Client Process
     
      Description: 	BitWarden Client may be spoofed by an attacker and this may lead to information disclosure by Employee. Consider using a standard authentication mechanism to identify the destination process.
     
      Justification: Regularly test the BitWarden Client for vulnerabilities that could enable spoofing. Apply hardening techniques, such as stripping unnecessary metadata from binaries and using memory protection mechanisms.
  
  24. Potential Lack of Input Validation for BitWarden Client
     
      Description: 	Data flowing across Login Request may be tampered with by an attacker. 
     
      Justification: Validate inputs at the client side and revalidate them on the server side. Enforce strict limits on input size to prevent buffer overflows.
 
  25. Potential Data Repudiation by BitWarden Client
     
      Description: 	BitWarden Client claims that it did not receive data from a source outside the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.
     
      Justification: Require the BitWarden Client to digitally sign all transmitted data using a private key. The server verifies the signature using the client’s public key.
  
  26. Data Flow Sniffing
     
      Description: 	Data flowing across Login Request may be sniffed by an attacker. Depending on what type of data an attacker can read, it may be used to attack other parts of the system or simply be a disclosure of information leading to compliance violations. Consider encrypting the data flow. 
     
      Justification: Use strong encryption protocols to encrypt all data in transit using the latest version of Transport Layer Security.
 
  27. Potential Process Crash or Stop for BitWarden Client
     
      Description: 	BitWarden Client crashes, halts, stops or runs slowly; in all cases violating an availability metric.
     
      Justification: Use a watchdog process to monitor the BitWarden Client and restart it if it becomes unresponsive or crashes. Configure timeouts to detect and respond to failures promptly.
 
  28.  Data Flow Login Request is Potentially Interrupted

       Description: An external agent interrupts data flow across a trust boundary in either direction.

       Justification: Use end-to-end encryption with TLS 1.3 with multi-factor authentication.

  29. Bitwarden Client May Be Subject to Elevation of Privilege Using Remote Code Execution

      Description: Employee may be able to remotely execute code for Bitwarden Client.

      Justification: Input validation and sanitization is used to disallow local code execution.

  30. Elevation of Changing the Execution Flow in Bitwarden Client

      Description: An attacker may pass data into BitWarden Client in order to change the flow of program execution within BitWarden Client to the attacker's choosing.

      Justification: Input validation and sanitization is used to ensure data is sanitized before entering the program flow.

  32. Spoofing of Destination Data Store Password DB

      Description: Password DB may be spoofed by an attacker and this may lead to data being written to the attacker's target instead of Password DB. Consider using a standard authentication mechanism to identify the destination data store.

      Justification: Use strong authentication between the database server using mechanisms like TLS with server certificate validation.

  33. Potential Excessive Resource Consumption for BitWarden Client or Password DB

      Description: Password DB may be spoofed by an attacker and this may lead to data being written to the attacker's target instead of Password DB. Consider using a standard authentication mechanism to identify the destination data store.

      Justification: Apply rate limiting and request throttling to control the amount of requests that are proccesed in a given timeframe. Use timeouts for all resource-intensive operations to stop deadlocks.

  34. Spoofing the Account user External Entity

      Description: Account user may be spoofed by an attacker and this may lead to unauthorized access to BitWarden Client. Consider using a standard authentication mechanism to identify the external entity.

      Justification: Use strong multi-factor authentication, impose secure password policies, and confirm sessions using tokens using tokens that are stored in HTTP cookies.

  35. Elevation using Impersonation

      Description: BitWarden Client may be able to impersonate the context of Account user in order to gain additional privilege.

      Justification: Apply strict RBAC to verify that BitWarden client operates within the permissions that are allowed to the authenticated user and that the user can't elevate its privliges.

  36. Spoofing the BitWarden Client Process

      Description: BitWarden Client may be spoofed by an attacker and this may lead to information disclosure by Account user. Consider using a standard authentication mechanism to identify the destination process.

      Justification: Use TLS to authenticate both the client and the server to certify that only processes can establish communication.

  37. Potential Lack of Input Validation for BitWarden Client

      Description: Data flowing across Account activity may be tampered with by an attacker.

      Justification: Apply strict input validation on all of the data flowing into the BitWarden Client by using a allowlist approach to verify inputs are accepted.

  38. Potential Data Repudiation by BitWarden Client

      Description: BitWarden Client claims that it did not receive data from a source outside the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.

      Justification: Use secure logging and auditing mechanisms that record the source, timestamp, and a summary of all of the data recieved.

  39. Data Flow Sniffing

      Description: Data flowing across Account activity may be sniffed by an attacker. Depending on what type of data an attacker can read, it may be used to attack other parts of the system or simply be a disclosure of information leading to compliance violations. Consider encrypting the data flow.

      Justification: Encrypt all of the data using TLS to make sure the confidentiality and integrity of data that flows across across acount activity.

  40. Potential Process Crash or Stop for BitWarden Client

      Description: BitWarden Client crashes, halts, stops or runs slowly; in all cases violating an availability metric.

      Justification: Use robust error handling and input validation to stop crashes caused by unexpected data.

  41. Data Flow Account activity Is Potentially Interrupted

      Description: An external agent interrupts data flowing across a trust boundary in either direction.

      Justification: Use TLS to ensure that data confidentiality and integrity during transmission. 

  42. Bitwarden client may be used to elevate privilege using remote code validation/execution

      Description: Account user may be able to remotely execute code using Bitwarden

      Justification: Input validation and sanitization is used to disallow local code execution.

  43. Elevation by Changing the Execution Flow in BitWarden Client 

      Description: An attacker may pass data into BitWarden Client in order to change the flow of program execution within BitWarden Client to the attacker's choosing.

      Justification: Input validation and sanitization is used to ensure data is sanitized before entering the program flow.

  45. Elevation Using Impersonation

      Description: BitWarden Client may be able to impersonate the context of Breach information processor in order to gain additional privilege.

      Justification: Use OAuth for managing identity authentication.

  46. Spoofing of Source Data Store Database of breaches

      Description: Database of breaches may be spoofed by an attacker and this may lead to incorrect data delivered to Breach information processor. Consider using a standard authentication mechanism to identify the source data store.

      Justification:  Use Bitwarden SHA-256 to ensure data is not tampered with or altered in any notion.

  47. Weak Access Control for a Resource

      Description: Improper data protection of Database of breaches can allow an attacker to read information not intended for disclosure. Review authorization settings.

      Justification:  Use ultrasonic scanners to secure information for the associated party, strengthening authentication.

  48. Spoofing of the Account user External Destination Entity

      Description: Account user may be spoofed by an attacker and this may lead to data being sent to the attacker's target instead of Account user. Consider using a standard authentication mechanism to identify the external entity.

      Justification: Use Bitwarden whitelisting to approve specific email addresses that are verified by domains to ensure verification.

  49. External Entity Account user Potentially Denies Receiving Data

      Description: Account user claims that it did not receive data from a process on the other side of the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.

      Justification: Use automatic receipts to ensure confirmation from sensitive/critical data; that can be verified by the system and finance' encouraging authentication and verification.

  50. Data Flow Breach answer Is Potentially Interrupted

      Description: An external agent interrupts data flowing across a trust boundary in either direction.

      Justification: Use Bitwarden's VPNs for private communication and backups for high availability, incase of disruption.

  51. Spoofing of Destination Data Store Database of breaches

      Description: Database of breaches may be spoofed by an attacker and this may lead to data being written to the attacker's target instead of Database of breaches. Consider using a standard authentication mechanism to identify the destination data store.

      Justification: Use HTTPS with strong TLS configs to secure data connections.

  52. Potential Excessive Resource Consumption for Breach information processor or Database of breaches

      Description: Does Breach information processor or Database of breaches take explicit steps to control resource consumption? 

      Justification: Use CDN to cache data closer to users that use them to reduce resource scaling. 

  53. Elevation Using Impersonation

      Description: Breach information processor may be able to impersonate the context of BitWarden Client in order to gain additional privilege.

      Justification: Use Bitwarden's MFA to add a second layer of verfication, and RBAC to monitor all actions.

  54. Spoofing the Breach Reporter External Entity 

      Description: Breach Reporter may be spoofed by an attacker and this may lead to unauthorized access to Breach information processor. Consider using a standard authentication mechanism to identify the external entity.

      Justification: Use TLS to ensure that data confidentiality and integrity during transmission. 

  55. Elevation Using Impersonation

       Description:	Breach information processor may be able to impersonate the context of Breach Reporter in order to gain additional privilege.

      Justification: Enable multi-factor authentication, enforce least-privilege access, and monitor for unusual account activity to prevent elevation using impersonation.
      
      
  57. Elevation by Changing the Execution Flow in Breach information processor

      Description:	An attacker may pass data into Breach information processor in order to change the flow of program execution within Breach information processor to the attacker's choosing.

      Justification:	Input validation and sanitization is used to ensure data is sanitized before entering the program flow.
      
  58. Breach information processor May be Subject to Elevation of Privilege Using Remote Code Execution 

      Description:	Breach Reporter may be able to remotely execute code for Breach information processor.

      Justification:	Apply regular security patches, use code signing, and implement strict access controls to prevent remote code execution in the breach information processor.
      
  59. Data Flow Breach update Is Potentially Interrupted  

      Description:	An external agent interrupts data flowing across a trust boundary in either direction.

      Justification:	Use robust error handling, retry mechanisms, and secure communication protocols to prevent interruptions in data flow during breach updates.
      
  60. Potential Process Crash or Stop for Breach information processor  

      Description:	Breach information processor crashes, halts, stops or runs slowly; in all cases violating an availability metric.

      Justification:	Implement fault-tolerant designs, resource monitoring, and automated restarts to mitigate process crashes or stops in the breach information processor.
      
  61. Data Flow Sniffing  

      Description:	Data flowing across Breach update may be sniffed by an attacker.

       Justification:	Use end-to-end encryption with TLS to protect data flows from being intercepted or sniffed.
      
  62. Potential Data Repudiation by Breach information processor  

       Description:	Breach information processor claims that it did not receive data from a source outside the trust boundary.

      Justification:	Implement logging with tamper-evident mechanisms and use digital signatures to prevent and detect data repudiation by the breach information processor.
      
  63. Potential Lack of Input Validation for Breach information processor  

       Description:	Data flowing across Breach update may be tampered with by an attacker.
      
      Justification:	Enforce strict input validation and sanitize all inputs to prevent exploitation in the breach information processor.
      
  64. Spoofing the Breach information processor Process 

       Description:	Breach information processor may be spoofed by an attacker and this may lead to information disclosure by Breach Reporter.

      Justification:	Use strong authentication, cryptographic signing, and secure communication channels to prevent spoofing of the breach information processor process.
      
  65. Data Flow Update confirmation Is Potentially Interrupted  

       Description:	An external agent interrupts data flowing across a trust boundary in either direction.

       Justification:	Implement redundant communication channels and use message acknowledgment protocols to ensure data flow update confirmation is not interrupted.
      
  66. External Entity Breach Reporter Potentially Denies Receiving Data  

      Description:	Breach Reporter claims that it did not receive data from a process on the other side of the trust boundary. 

      Justification:	Use reliable transmission protocols, acknowledge receipt with digital signatures, and implement logging to prevent denial of data receipt by external entity breach reporters.
      
  67. Spoofing of the Breach Reporter External Destination Entity 

       Description:	Breach Reporter may be spoofed by an attacker and this may lead to data being sent to the attacker's target instead of Breach Reporter. 

       Justification:	Implement mutual authentication and use secure, encrypted communication channels to prevent spoofing of the breach reporter external destination entity.

   ## 4. Part deux

   Most of BitWarden's main functions can be summarized with the first of the DFDs where theres a external entity interacting with the BitWarden client, and that client sending data to a data store, that then sends the confirmation through the process back to the external entity. This produces vulernabilities in the data flow of the External Entity to the BitWarden client or from the BtWarden client to the data store. Nearly all the threats generated by the Threat modelling tool were marked as High Priority. 
   
   After reading through all 66 threats the team determine that the Cross-site forgery threat was unnecessary to mitigate as the BitWarden client uses API to pull data from data stores and not a browser. The threats 11, 30, 43, and 55 were removed leaving 62 threats.  

   ### 4.1 Gaps

   1. Notable Gap: Ensuring that data hasn't been tampered with or interupted, can lead to DoS.
      a. Threats: 1, 8, 12, 14, or 19
   2. The input sanitization is assumed to be faultless but it could have flaws.
      a. Threats:  
