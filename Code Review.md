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
* Summary: The Deepscan.io scan found around 184 issues, a majority of which were issues claiming that a null value was used instead of an integer, however, on further review in all cases these null values were handled correctly and these were false positives. The second most common issue was the constant condition issue which is a result of BitWarden hiding the secrets required to maintain secure code. The rest of the issues are uncommon with only a few instances of each issue and most low priority. 


## 4. Common Weakness Enumerations

### 4.1 CWE's selected
   
* CWE-200: Exposure of Sensitive Information to an Unauthorized Actor
    * Files Manually Analyzed:

    * Automated Scan Results:
      
* [CWE-267: Privilege Defined With Unsafe Actions](https://cwe.mitre.org/data/definitions/267.html)
    * Files Manually Analyzed:
         * [web-provider.service.ts](https://github.com/bitwarden/clients/blob/main/bitwarden_license/bit-web/src/app/admin-console/providers/services/web-provider.service.ts)
         * [member-access-report.response.ts](https://github.com/bitwarden/clients/blob/main/bitwarden_license/bit-web/src/app/tools/reports/member-access-report/response/member-access-report.response.ts)
         * [provider-permissions.guard.ts](https://github.com/bitwarden/clients/blob/main/bitwarden_license/bit-web/src/app/admin-console/providers/guards/provider-permissions.guard.ts)
    * Manual Scan Results: The use case file these particular code reviews involed is insider employee abuse. The files reviewed all pertained to priviledged information. The first in the code manages organizations and providers accounts. These methods handle [adding](https://github.com/bitwarden/clients/blob/main/bitwarden_license/bit-web/src/app/admin-console/providers/services/web-provider.service.ts#L36), [creating](https://github.com/bitwarden/clients/blob/main/bitwarden_license/bit-web/src/app/admin-console/providers/services/web-provider.service.ts#L74),and [detaching](https://github.com/bitwarden/clients/blob/main/bitwarden_license/bit-web/src/app/admin-console/providers/services/web-provider.service.ts#L82). The second code refers to user access and member details. It displays [usernames](https://github.com/bitwarden/clients/blob/main/bitwarden_license/bit-web/src/app/tools/reports/member-access-report/response/member-access-report.response.ts#L42), [emails](https://github.com/bitwarden/clients/blob/main/bitwarden_license/bit-web/src/app/tools/reports/member-access-report/response/member-access-report.response.ts#L43), [two factor enabled](https://github.com/bitwarden/clients/blob/main/bitwarden_license/bit-web/src/app/tools/reports/member-access-report/response/member-access-report.response.ts#L44), [account recovery](https://github.com/bitwarden/clients/blob/main/bitwarden_license/bit-web/src/app/tools/reports/member-access-report/response/member-access-report.response.ts#L45) and more privileged information. The last code that was reviewed was a guard that checks if the logged-in user has the appropriate [permissions](https://github.com/bitwarden/clients/blob/main/bitwarden_license/bit-web/src/app/admin-console/providers/guards/provider-permissions.guard.ts#L56). 
    * Automated Scan Results: The A.I. automated scans for Aikido Security, Deepscan.io and Codacy did not give me issues relating to this CWE.
      
* CWE-269: Improper Privilege Management 
    * Files Manually Analyzed:

    * Automated Scan Results:
      
* CWE-290: Authentication Bypass by Spoofing
    * Files Manually Analyzed:
         * [login-via-auth-request-v1.component.ts](https://github.com/bitwarden/clients/blob/main/apps/desktop/src/auth/login/login-via-auth-request-v1.component.ts)
         * [desktop-login-approval-component.service.spec.ts](https://github.com/bitwarden/clients/blob/main/apps/desktop/src/auth/login/desktop-login-approval-component.service.spec.ts)
         * [auth-request.service.ts](https://github.com/bitwarden/clients/blob/main/libs/auth/src/common/services/auth-request/auth-request.service.ts)
    * Manual Scan Results: The beginning of the analysis start with the clients/apps/desktop/src/auth folder to find files related to the authentication process. The files identified were related to the auth request in relation to login, authentication approval, and the authentication request service. The use case this follows is the login use case so these files seemed most relevant to the scenario based approach we were using. The first file listed is where we find the authentication approval [Here](https://github.com/bitwarden/clients/blob/main/apps/desktop/src/auth/login/login-via-auth-request-v1.component.ts#L86). In the second file we find the parameters for authentication [Here](https://github.com/bitwarden/clients/blob/main/apps/desktop/src/auth/login/desktop-login-approval-component.service.spec.ts#L51) which shows the requirements for authentication, and in the last file we get the asyncronous approve or deny request for authentication [Here](https://github.com/bitwarden/clients/blob/main/libs/auth/src/common/services/auth-request/auth-request.service.ts#L87). These are asyncronous processes that are difficult to spoof as shown in the last file they require master key decryption from outside the client in order to validate the authentication.
    * Automated Scan Results: (1) The Akido scan did not find any issues relating to the CWE. (2) The deepscan.io scan did not find any issues relating to the CWE.
    
* [CWE-326: Inadequate Encryption Strength](https://cwe.mitre.org/data/definitions/326.html)
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
  * Manual Scan Results: Similar to the reasoning for CWE-290 we start with the authentication files in the BitWarden repo. The most important of these files for this CWE is the auth-request.service.ts file which shows [Here](https://github.com/bitwarden/clients/blob/main/apps/desktop/src/auth/login/desktop-login-approval-component.service.spec.ts#L51) and [Here](https://github.com/bitwarden/clients/blob/main/libs/auth/src/common/services/auth-request/auth-request.service.ts#L105) the service requiring a master key that comes from outside the client to approve authentication. This shows that the authentication isn't occuring client side.
  * Automated Scan Results: (1) The Akido scan did not find any issues relating to the CWE. (2) The deepscan.io scan did not find any issues relating to the CWE.



## 5. Summary

## 6. Open source contributions

## 7. Reflections
