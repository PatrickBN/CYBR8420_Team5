The code review main project file
# Code Review

## 1. Introduction

Code review is an essential process in verifying the security of any potential software, whether open-source or not, that a company or organization is planning on using. To accomplish this we must have a detailed plan of attack to find and mitigate these issues before we take on this new software.

## 2. Our Review Strategy

Our code review strategy began with a scenario based approach using the Use Cases we have developed previously to identify weak areas to focus on. We then presented Common Weakness Enumerations to group and collectively decided on which CWE's fit best with the use cases and the BitWarden application. These CWE's were then delegated to the team members to focus on individually through manual review of the code. Automated review using code review tools was done by each member and then the results are compared to the CWE that team member is investigating. 

## 3. Automated Scanning and Tools used

3.1 Aikdo Security
* Summary: Akido security ran an automated code review over the entire BitWarden repository, as a feature of Akido it tries to recogonize false positives and cut them out of the final view of issues to simplify reviewing the code review. The total amount of issues Akido was able to find was 89, with about 50 of those being cut out by Akido as false positives. However, it missed a lot of false positives and really that number should be closer to 70, leaving only 19 or so actual issues. Most of these issues were low level or medium level issues, and the one critical issue was an out of date component.  


3.2 Deepscan.io
* Summary: The Deepscan.io scan found around 184 issues, a majority of which were issues claiming that a null value was used instead of an integer, however, on further review in all cases these null values were handled correctly and these were false positives. 


## 4. Common Weakness Enumerations

### 4.1 CWE's selected
   
* CWE-200: Exposure of Sensitive Information to an Unauthorized Actor
    * Files Manually Analyzed:

    * Automated Scan Results:
      
* CWE-267: Privilege Defined With Unsafe Actions
    * Files Manually Analyzed:

    * Automated Scan Results:
      
* CWE-269: Improper Privilege Management
    * Files Manually Analyzed:

    * Automated Scan Results:
      
* CWE-290: Authentication Bypass by Spoofing
    * Files Manually Analyzed:
         * [login-via-auth-request-v1.component.ts](https://github.com/bitwarden/clients/blob/main/apps/desktop/src/auth/login/login-via-auth-request-v1.component.ts)
         * [desktop-login-approval-component.service.spec.ts](https://github.com/bitwarden/clients/blob/main/apps/desktop/src/auth/login/desktop-login-approval-component.service.spec.ts)
         * [auth-request.service.ts](https://github.com/bitwarden/clients/blob/main/libs/auth/src/common/services/auth-request/auth-request.service.ts)

    * Automated Scan Results:
    
* CWE-326: Inadequate Encryption Strength
    * Files Manually Analyzed:

    * Automated Scan Results:
      
* CWE-327: Use of a Broken or Risky Cryptographic Algorithm
    * Files Manually Analyzed:

    * Automated Scan Results:
      
* CWE-522: Insufficiently Protected Credentials
    * Files Manually Analyzed:

    * Automated Scan Results:
    
* CWE-603: Use of Client-Side Authentication
    * Files Manually Analyzed:
         * [login-via-auth-request-v1.component.ts](https://github.com/bitwarden/clients/blob/main/apps/desktop/src/auth/login/login-via-auth-request-v1.component.ts)
         * [desktop-login-approval-component.service.spec.ts](https://github.com/bitwarden/clients/blob/main/apps/desktop/src/auth/login/desktop-login-approval-component.service.spec.ts)
         * [auth-request.service.ts](https://github.com/bitwarden/clients/blob/main/libs/auth/src/common/services/auth-request/auth-request.service.ts)
           
    * Automated Scan Results:



## 5. Summary

## 6. Open source contributions

## 7. Reflections
