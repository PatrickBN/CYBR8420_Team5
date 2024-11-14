### 1. Data Flow Diagrams and Threat Modeling

  1. BitWarden Login Diagram
  2. BitWarden Data Breach Diagram
  3. [Threat Modeling](https://htmlpreview.github.io/?https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Software%20Security%20Engineering/DFDs/DFD%20threats.htm)

  ### 2. Introduction

  ### 3. Threat review and Mitigation

  1. Spoofing the MFA External Entity
     
     Description:	MFA may be spoofed by an attacker and this may lead to unauthorized access to BitWarden Client. Consider using a standard authentication mechanism to identify the external entity.
     
     Justification: 

  2. Elevation Using Impersonation
     
     Description:	BitWarden Client may be able to impersonate the context of MFA in order to gain additional privilege.
     
     Justification:

  3. Spoofing the BitWarden Client Process
     
     Description:	
     
     Justification:
     
  4. Potential Lack of Input Validation for BitWarden Client
     
     Description:	
     
     Justification:
     
  5. Potential Data Repudiation by BitWarden Client
     
     Description:	
     
     Justification:
     
  6. Data Flow Sniffing
     
     Description:	
     
     Justification:
     
  7. Potential Process Crash or Stop for BitWarden Client
     
     Description:	
     
     Justification:
     
  8. Data Flow 2fa Is Potentially Interrupted
     
     Description:	
     
     Justification:
     
  9. BitWarden Client May be Subject to Elevation of Privilege Using Remote Code Execution
     
      Description:	
     
      Justification:
     
  10. Elevation by Changing the Execution Flow in BitWarden Client
     
      Description:	
     
      Justification:
      
  11. Cross Site Request Forgery
     
      Description:	
     
      Justification:
      
  12. Spoofing of the MFA External Destination Entity
     
      Description:	
     
      Justification:
      
  13. External Entity MFA Potentially Denies Receiving Data
     
      Description: 	MFA claims that it did not receive data from a process on the other side of the trust boundary. Consider using logging or auditing to record the source, time, and summary of the received data.
     
      Justification:
     
  14. 
  15. 
  16. 
  17. 
  18. 
  19. 
  20. 
  21. 
  22. 
  23. 
  24. 
  25. 
  26. 
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
