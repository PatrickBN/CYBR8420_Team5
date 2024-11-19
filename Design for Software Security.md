## 1. Data Flow Diagrams and Threat Modeling

  1. [BitWarden Login Diagram](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Software%20Security%20Engineering/DFDs/Diagram%20login%201.PNG)
  2. [BitWarden Data Breach Diagram](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Software%20Security%20Engineering/DFDs/Diagram%20Breach%202.PNG)
  3. [Threat Modeling](https://htmlpreview.github.io/?https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Software%20Security%20Engineering/DFDs/DFD%20threats.htm)

  ## 2. Introduction

  The DFD we created cover the main use cases we identified earlier on. While most of the use cases were covered by the first diagram the second diagram covers the two use cases that require data being transmitted to and from outside the BitWarden system. This required the second DFD as we were introducing a new possible threat vector from the data coming from outside the BitWarden system. 
  
  The Microsoft threat modelling tool was used to create the list of possible threats from the DFD, those threats are listed below with each having a *description* of the threat as well as the *justification* for mitigation by which it is mitigated through BitWarden or could be mitigated. The Gaps noted in the mitigations will be listed below in the second part where we look at the gaps in BitWarden's mitigation. 
  
  ## 3. Threat review and Mitigation

  1. Spoofing the MFA External Entity ID:1
     
     Description:	MFA may be spoofed by an attacker and this may lead to unauthorized access to BitWarden Client. Consider using a standard authentication mechanism to identify the external entity.
     
     Justification: Use of digital certificates ensures proper authentication

  2. Elevation Using Impersonation ID:2
     
     Description:	BitWarden Client may be able to impersonate the context of MFA in order to gain additional privilege.
     
     Justification: Authentication is required in order to gain additional privilege

  3. Spoofing the BitWarden Client Process ID:3
     
     Description:	BitWarden Client may be spoofed by an attacker and this may lead to information disclosure by MFA. Consider using a standard authentication mechanism to identify the destination process.
     
     Justification: Use of digital certificates ensures proper authentication
     
  4. Potential Lack of Input Validation for BitWarden Client ID:4
     
     Description:	Data flowing across 2fa may be tampered with by an attacker. This may lead to a denial of service attack against BitWarden Client or an elevation of privilege attack against BitWarden Client or an information disclosure by BitWarden Client.
     
     Justification: BitWarden uses a validation Service to validate input a user's input is never executed.
     
  5. Potential Data Repudiation by BitWarden Client ID:5
     
     Description:	BitWarden Client claims that it did not receive data from a source outside the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.
     
     Justification: BitWarden replaces non-existing files and any files that have been tampered with cause an error that leads to a crash.
     
  6. Data Flow Sniffing ID:6
     
     Description:	Data flowing across 2fa may be sniffed by an attacker. Depending on what type of data an attacker can read, it may be used to attack other parts of the system or simply be a disclosure of information leading to compliance violations. Consider encrypting the data flow.
     
     Justification: Sensitive data isn't stored locally and all data sent across a network is encrypted.
     
  7. Potential Process Crash or Stop for BitWarden Client ID:7
     
     Description:	BitWarden Client crashes, halts, stops or runs slowly; in all cases violating an availability metric.
     
     Justification: Currently BitWarden crashes with an error message, current coding practices dictate that this be necessary in the case of tampering.

  8. Data Flow 2fa Is Potentially Interrupted ID:8

     Description: An external agent interrupts data flowing across a trust boundary in either direction.

      Justification: The 2fa authentication is logged and encryption can be used to prevent data sniffing.
     
  9. BitWarden Client May be Subject to Elevation of Privilege Using Remote Code Execution ID:9
     
      Description: MFA may be able to remotely execute code for BitWarden Client.
     
      Justification: Input validation and sanitization is used to disallow local code execution.
     
  10. Elevation by Changing the Execution Flow in BitWarden Client ID:10
     
      Description: An attacker may pass data into BitWarden Client in order to change the flow of program execution within BitWarden Client to the attacker's choosing.
     
      Justification: Input validation and sanitization is used to ensure data is sanitized before entering the program flow.
      
  13. Spoofing of the MFA External Destination Entity ID:12
     
      Description: MFA may be spoofed by an attacker and this may lead to data being sent to the attacker's target instead of MFA.
     
      Justification: The MFA uses authentication signatures to prevent spoofing.
      
  14. External Entity MFA Potentially Denies Receiving Data ID:13
     
      Description: 	MFA claims that it did not receive data from a process on the other side of the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.
     
      Justification: Use reliable transmission protocols, acknowledge receipt with digital signatures, and implement logging to prevent denial of data receipt by external entity breach reporters.
     
 15. Data Flow 2fa confirmation Is Potentially Interrupted ID:14
     
      Description: 	An external agent interrupts data flowing across a trust boundary in either direction.
     
      Justification: The 2fa authentication is logged and encryption can be used to prevent data sniffing.

  16. Spoofing of Source Data Store Password DB ID:15
     
      Description: 	Password DB may be spoofed by an attacker and this may lead to incorrect data delivered to BitWarden Client. Consider using a standard authentication mechanism to identify the source data store.
     
      Justification: Use of digital certificates ensures proper authentication
 
  17. Weak Access Control for a Resource ID:16
     
      Description: 	Improper data protection of Password DB can allow an attacker to read information not intended for disclosure. Review authorization settings.
     
      Justification: Use ultrasonic scanners to secure information for the associated party, strengthening authentication.
 
  18. Spoofing of the Employee External Destination Entity ID:17
     
      Description: 	Employee may be spoofed by an attacker and this may lead to data being sent to the attacker's target instead of Employee. Consider using a standard authentication mechanism to identify the external entity.
     
      Justification: Use of digital certificates ensures proper authentication
 
  19. External Entity Employee Potentially Denies Receiving Data ID:18
     
      Description: 	Employee claims that it did not receive data from a process on the other side of the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.
     
      Justification: Use reliable transmission protocols, acknowledge receipt with digital signatures, and implement logging to prevent denial of data receipt by external entity breach reporters.

  20. Data Flow Key & confirmation Is Potentially Interrupted ID:19
     
      Description: 	An external agent interrupts data flowing across a trust boundary in either direction.
     
      Justification: The 2fa authentication is logged and encryption can be used to prevent data sniffing.
 
  21. Spoofing the Employee External Entity ID:20
     
      Description: 	Employee may be spoofed by an attacker and this may lead to unauthorized access to BitWarden Client. Consider using a standard authentication mechanism to identify the external entity.
     
      Justification: Use of digital certificates ensures proper authentication
 
  22. Elevation Using Impersonation ID:21
     
      Description: 	BitWarden Client may be able to impersonate the context of Employee in order to gain additional privilege.
     
      Justification: Authentication is required in order to gain additional privilege
  
  24. Potential Lack of Input Validation for BitWarden Client ID:23
     
      Description: 	Data flowing across Login Request may be tampered with by an attacker. 
     
      Justification: BitWarden uses a validation Service to validate input a user's input is never executed.
 
  25. Potential Data Repudiation by BitWarden Client ID:24
     
      Description: 	BitWarden Client claims that it did not receive data from a source outside the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.
     
      Justification: BitWarden replaces non-existing files and any files that have been tampered with cause an error that leads to a crash.
  
  26. Data Flow Sniffing ID:25
     
      Description: 	Data flowing across Login Request may be sniffed by an attacker. Depending on what type of data an attacker can read, it may be used to attack other parts of the system or simply be a disclosure of information leading to compliance violations. Consider encrypting the data flow. 
     
      Justification: Sensitive data isn't stored locally and all data sent across a network is encrypted.
 
  27. Potential Process Crash or Stop for BitWarden Client ID:26
     
      Description: 	BitWarden Client crashes, halts, stops or runs slowly; in all cases violating an availability metric.
     
      Justification: Currently BitWarden crashes with an error message, current coding practices dictate that this be necessary in the case of tampering.
 
  28.  Data Flow Login Request is Potentially Interrupted ID:27

       Description: An external agent interrupts data flow across a trust boundary in either direction.

       Justification: Use end-to-end encryption with TLS 1.3 with multi-factor authentication.

  29. Bitwarden Client May Be Subject to Elevation of Privilege Using Remote Code Execution ID:28

      Description: Employee may be able to remotely execute code for Bitwarden Client.

      Justification: Input validation and sanitization is used to disallow local code execution.

  30. Elevation of Changing the Execution Flow in Bitwarden Client ID:29

      Description: An attacker may pass data into BitWarden Client in order to change the flow of program execution within BitWarden Client to the attacker's choosing.

      Justification: Input validation and sanitization is used to ensure data is sanitized before entering the program flow.

  32. Spoofing of Destination Data Store Password DB ID:31

      Description: Password DB may be spoofed by an attacker and this may lead to data being written to the attacker's target instead of Password DB. Consider using a standard authentication mechanism to identify the destination data store.

      Justification: Use of digital certificates ensures proper authentication
      
  34. Potential Excessive Resource Consumption for BitWarden Client or Password DB ID:32

      Description: Password DB may be spoofed by an attacker and this may lead to data being written to the attacker's target instead of Password DB. Consider using a standard authentication mechanism to identify the destination data store.

      Justification: Apply rate limiting and request throttling to control the amount of requests that are proccesed in a given timeframe. Use timeouts for all resource-intensive operations to stop deadlocks.

  35. Spoofing the Account user External Entity ID:33

      Description: Account user may be spoofed by an attacker and this may lead to unauthorized access to BitWarden Client. Consider using a standard authentication mechanism to identify the external entity.

      Justification: Use of digital certificates ensures proper authentication

  36. Elevation using Impersonation ID:34

      Description: BitWarden Client may be able to impersonate the context of Account user in order to gain additional privilege.

      Justification: Authentication is required in order to gain additional privilege
      
  39. Potential Lack of Input Validation for BitWarden Client ID:36

      Description: Data flowing across Account activity may be tampered with by an attacker.

      Justification: BitWarden uses a validation Service to validate input a user's input is never executed.

  40. Potential Data Repudiation by BitWarden Client ID:37

      Description: BitWarden Client claims that it did not receive data from a source outside the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.

      Justification: BitWarden replaces non-existing files and any files that have been tampered with cause an error that leads to a crash.

  41. Data Flow Sniffing ID:38

      Description: Data flowing across Account activity may be sniffed by an attacker. Depending on what type of data an attacker can read, it may be used to attack other parts of the system or simply be a disclosure of information leading to compliance violations. Consider encrypting the data flow.

      Justification: Sensitive data isn't stored locally and all data sent across a network is encrypted.

  42. Potential Process Crash or Stop for BitWarden Client ID:39

      Description: BitWarden Client crashes, halts, stops or runs slowly; in all cases violating an availability metric.

      Justification: Currently BitWarden crashes with an error message, current coding practices dictate that this be necessary in the case of tampering.

  43. Data Flow Account activity Is Potentially Interrupted ID:40

      Description: An external agent interrupts data flowing across a trust boundary in either direction.

      Justification: The external agent is logged and encryption can be used to prevent data sniffing.

  44. Bitwarden client may be used to elevate privilege using remote code validation/execution ID:41

      Description: Account user may be able to remotely execute code using Bitwarden

      Justification: Input validation and sanitization is used to disallow local code execution.

  45. Elevation by Changing the Execution Flow in BitWarden Client  ID:42

      Description: An attacker may pass data into BitWarden Client in order to change the flow of program execution within BitWarden Client to the attacker's choosing.

      Justification: Input validation and sanitization is used to ensure data is sanitized before entering the program flow.

  46. Elevation Using Impersonation ID:44

      Description: BitWarden Client may be able to impersonate the context of Breach information processor in order to gain additional privilege.

      Justification: Authentication is required in order to gain additional privilege

  47. Spoofing of Source Data Store Database of breaches ID:45

      Description: Database of breaches may be spoofed by an attacker and this may lead to incorrect data delivered to Breach information processor. Consider using a standard authentication mechanism to identify the source data store.

      Justification:  Use of digital certificates ensures proper authentication

  48. Weak Access Control for a Resource ID:46

      Description: Improper data protection of Database of breaches can allow an attacker to read information not intended for disclosure. Review authorization settings.

      Justification:  Use ultrasonic scanners to secure information for the associated party, strengthening authentication.

  49. Spoofing of the Account user External Destination Entity ID:47

      Description: Account user may be spoofed by an attacker and this may lead to data being sent to the attacker's target instead of Account user. Consider using a standard authentication mechanism to identify the external entity.

      Justification: Use Bitwarden whitelisting to approve specific email addresses that are verified by domains to ensure verification.

  50. External Entity Account user Potentially Denies Receiving Data ID:48

      Description: Account user claims that it did not receive data from a process on the other side of the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.

      Justification: Use reliable transmission protocols, acknowledge receipt with digital signatures, and implement logging to prevent denial of data receipt by external entity breach reporters.

  51. Data Flow Breach answer Is Potentially Interrupted ID:49

      Description: An external agent interrupts data flowing across a trust boundary in either direction.

      Justification: The external agent is logged and encryption can be used to prevent data sniffing.

  52. Spoofing of Destination Data Store Database of breaches ID:50

      Description: Database of breaches may be spoofed by an attacker and this may lead to data being written to the attacker's target instead of Database of breaches. Consider using a standard authentication mechanism to identify the destination data store.

      Justification: Use HTTPS with strong TLS configs to secure data connections.

  53. Potential Excessive Resource Consumption for Breach information processor or Database of breaches ID:51

      Description: Does Breach information processor or Database of breaches take explicit steps to control resource consumption? 

      Justification: Use CDN to cache data closer to users that use them to reduce resource scaling. 

  54. Elevation Using Impersonation ID:52

      Description: Breach information processor may be able to impersonate the context of BitWarden Client in order to gain additional privilege.

      Justification: Authentication is required in order to gain additional privilege

  55. Spoofing the Breach Reporter External Entity  ID:53

      Description: Breach Reporter may be spoofed by an attacker and this may lead to unauthorized access to Breach information processor. Consider using a standard authentication mechanism to identify the external entity.

      Justification: Use TLS to ensure that data confidentiality and integrity during transmission. 

  56. Elevation Using Impersonation ID:54

       Description:	Breach information processor may be able to impersonate the context of Breach Reporter in order to gain additional privilege.

      Justification: Enable multi-factor authentication, enforce least-privilege access, and monitor for unusual account activity to prevent elevation using impersonation.
      
      
  57. Elevation by Changing the Execution Flow in Breach information processor ID:56

      Description:	An attacker may pass data into Breach information processor in order to change the flow of program execution within Breach information processor to the attacker's choosing.

      Justification:	Input validation and sanitization is used to ensure data is sanitized before entering the program flow.
      
  58. Breach information processor May be Subject to Elevation of Privilege Using Remote Code Execution  ID:57

      Description:	Breach Reporter may be able to remotely execute code for Breach information processor.

      Justification:	Apply regular security patches, use code signing, and implement strict access controls to prevent remote code execution in the breach information processor.
      
  59. Data Flow Breach update Is Potentially Interrupted   ID:58

      Description:	An external agent interrupts data flowing across a trust boundary in either direction.

      Justification:	The external agent is logged and encryption can be used to prevent data sniffing.
      
  60. Potential Process Crash or Stop for Breach information processor   ID:59

      Description:	Breach information processor crashes, halts, stops or runs slowly; in all cases violating an availability metric.

      Justification:	Currently BitWarden crashes with an error message, current coding practices dictate that this be necessary in the case of tampering.
      
  61. Data Flow Sniffing   ID:60

      Description:	Data flowing across Breach update may be sniffed by an attacker.

       Justification:	Sensitive data isn't stored locally and all data sent across a network is encrypted.
      
  62. Potential Data Repudiation by Breach information processor   ID:61

       Description:	Breach information processor claims that it did not receive data from a source outside the trust boundary.

      Justification:	BitWarden replaces non-existing files and any files that have been tampered with cause an error that leads to a crash.
      
  63. Potential Lack of Input Validation for Breach information processor   ID:62

       Description:	Data flowing across Breach update may be tampered with by an attacker.
      
      Justification:	BitWarden uses a validation Service to validate input a user's input is never executed.
      
  64. Spoofing the Breach information processor Process  ID:63

       Description:	Breach information processor may be spoofed by an attacker and this may lead to information disclosure by Breach Reporter.

      Justification:	Use of digital certificates ensures proper authentication
      
  65. Data Flow Update confirmation Is Potentially Interrupted   ID:64

       Description:	An external agent interrupts data flowing across a trust boundary in either direction.

       Justification:	The external agent is logged and encryption can be used to prevent data sniffing.
      
  66. External Entity Breach Reporter Potentially Denies Receiving Data   ID:65

      Description:	Breach Reporter claims that it did not receive data from a process on the other side of the trust boundary. 

      Justification:	Use reliable transmission protocols, acknowledge receipt with digital signatures, and implement logging to prevent denial of data receipt by external entity breach reporters.
      
  67. Spoofing of the Breach Reporter External Destination Entity  ID:66

       Description:	Breach Reporter may be spoofed by an attacker and this may lead to data being sent to the attacker's target instead of Breach Reporter. 

       Justification:	Use of digital certificates ensures proper authentication

   ## 4. Part 2
   ### 4.1 Summary

   Most of BitWarden's main functions can be summarized with the first of the DFDs where theres a external entity interacting with the BitWarden client, and that client sending data to a data store, that then sends the confirmation through the process back to the external entity. This produces vulernabilities in the data flow of the External Entity to the BitWarden client or from the BtWarden client to the data store. Nearly all the threats generated by the Threat modelling tool were marked as High Priority. 
   
   After reading through all 66 threats the team determine that the Cross-site forgery threat was unnecessary to mitigate as the BitWarden client uses API to pull data from data stores and not a browser. The threats 11, 30, 43, and 55 were removed leaving 62 threats. The Spoofing of BitWarden client process was repeated 3 times in the threat report and so 2 were removed as they all covered the same threat and mitigation, leaving 60 threats.   

   ### 4.2 Gaps
  The gaps are areas where the mitigations do not fully reduce the risk. Each threat mentioned in the gaps report is listed by their number in the list not by ID.

   1. Ensuring that data hasn't been tampered with or interupted, can lead to DoS & logs can be tampered with and thus would be untrustworthy without knowledge.
      - Threats: 8, 13, 18, 36, 44, 52, 58
   2. The input sanitization is assumed to be faultless but it could have flaws.
      - Threats: 9, 10, 26, 27, 37, 38, 50
   3. Valdiation service is assumed to be faultless but it could have flaws
      - Threats: 4, 21, 32, 56
  
  ### 4.3 Reflections
  The team worked on this early, with only 2 DFD to make most of the work was done well before the due day. We were much better than previously about 
