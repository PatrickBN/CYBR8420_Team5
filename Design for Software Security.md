### 1. Data Flow Diagrams and Threat Modeling

  1. BitWarden Login Diagram
  2. BitWarden Data Breach Diagram
  3. [Threat Modeling](https://htmlpreview.github.io/?https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Software%20Security%20Engineering/DFDs/DFD%20threats.htm)

  ### 2. Introduction

  ### 3. Threat review and Mitigation

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

  8. 
     
  9. BitWarden Client May be Subject to Elevation of Privilege Using Remote Code Execution
     
      Description: MFA may be able to remotely execute code for BitWarden Client.
     
      Justification: Input validation and sanitization is used to disallow local code execution.
     
  10. Elevation by Changing the Execution Flow in BitWarden Client
     
      Description: An attacker may pass data into BitWarden Client in order to change the flow of program execution within BitWarden Client to the attacker's choosing.
     
      Justification: Input validation and sanitization is used to ensure data is sanitized before entering the program flow.

  11.
      
  12. Spoofing of the MFA External Destination Entity
     
      Description: MFA may be spoofed by an attacker and this may lead to data being sent to the attacker's target instead of MFA.
     
      Justification: The MFA uses authentication signatures to prevent spoofing.
      
  13. External Entity MFA Potentially Denies Receiving Data
     
      Description: 	MFA claims that it did not receive data from a process on the other side of the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.
     
      Justification: The BitWarden MFA and desktop client both keep logs.
     
  14. Data Flow 2fa confirmation Is Potentially Interrupted
     
      Description: 	An external agent interrupts data flowing across a trust boundary in either direction.
     
      Justification:

  15. Spoofing of Source Data Store Password DB
     
      Description: 	Password DB may be spoofed by an attacker and this may lead to incorrect data delivered to BitWarden Client. Consider using a standard authentication mechanism to identify the source data store.
     
      Justification:
 
  16. Weak Access Control for a Resource
     
      Description: 	Improper data protection of Password DB can allow an attacker to read information not intended for disclosure. Review authorization settings.
     
      Justification:
 
  17. Spoofing of the Employee External Destination Entity
     
      Description: 	Employee may be spoofed by an attacker and this may lead to data being sent to the attacker's target instead of Employee. Consider using a standard authentication mechanism to identify the external entity.
     
      Justification:
 
  18. External Entity Employee Potentially Denies Receiving Data
     
      Description: 	Employee claims that it did not receive data from a process on the other side of the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.
     
      Justification:

  19. Data Flow Key & confirmation Is Potentially Interrupted
     
      Description: 	An external agent interrupts data flowing across a trust boundary in either direction.
     
      Justification:
 
  20. Spoofing the Employee External Entity
     
      Description: 	Employee may be spoofed by an attacker and this may lead to unauthorized access to BitWarden Client. Consider using a standard authentication mechanism to identify the external entity.
     
      Justification:
 
  21. Elevation Using Impersonation
     
      Description: 	BitWarden Client may be able to impersonate the context of Employee in order to gain additional privilege.
     
      Justification:
  
  22. Spoofing the BitWarden Client Process
     
      Description: 	BitWarden Client may be spoofed by an attacker and this may lead to information disclosure by Employee. Consider using a standard authentication mechanism to identify the destination process.
     
      Justification:
  
  23. Potential Lack of Input Validation for BitWarden Client
     
      Description: 	Data flowing across Login Request may be tampered with by an attacker. This may lead to a denial of service attack against BitWarden Client or an elevation of privilege attack against BitWarden Client or an information disclosure by BitWarden Client. Failure to verify that input is as expected is a root cause of a very large number of exploitable issues. Consider all paths and the way they handle data. Verify that all input is verified for correctness using an approved list input validation approach.
     
      Justification:
 
  24. Potential Data Repudiation by BitWarden Client
     
      Description: 	BitWarden Client claims that it did not receive data from a source outside the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.
     
      Justification:
  
  25. Data Flow Sniffing
     
      Description: 	Data flowing across Login Request may be sniffed by an attacker. Depending on what type of data an attacker can read, it may be used to attack other parts of the system or simply be a disclosure of information leading to compliance violations. Consider encrypting the data flow. 
     
      Justification:
 
  26. Potential Process Crash or Stop for BitWarden Client
     
      Description: 	BitWarden Client crashes, halts, stops or runs slowly; in all cases violating an availability metric.
     
      Justification:
 
  27. 
  28. 
  29. 
  30. 
  31. 
  32. 
  33. 
  34. 
  35. 
  36. 
  37. 
  38. 
  39. 
  40. 
  41. 
  42. 
  43. 
