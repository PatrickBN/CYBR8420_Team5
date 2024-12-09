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
   
* [CWE-200: Exposure of Sensitive Information to an Unauthorized Actor](https://cwe.mitre.org/data/definitions/200.html)
    * Files Manually Analyzed:
         * [username-randomizer.ts](https://github.com/bitwarden/clients/blob/02c65fd1b86839ec2de831488afc65b8f3efce9b/libs/tools/generator/core/src/engine/username-randomizer.ts#L10)
         * [service.spec.ts](https://github.com/bitwarden/clients/blob/02c65fd1b86839ec2de831488afc65b8f3efce9b/libs/common/src/platform/services/config/config.service.spec.ts#L112)
         * [auth-request-api.service.ts](https://github.com/bitwarden/clients/blob/main/libs/auth/src/common/services/auth-request/auth-request-api.service.ts)
    * Manual Scan Results: For this code review, the file revolves around information exploitation. The **username randomizer** allows each username to be randomly genrated using a predefined set of words. It operates using [**WordsRequest**](https://github.com/bitwarden/clients/blob/02c65fd1b86839ec2de831488afc65b8f3efce9b/libs/tools/generator/core/src/engine/username-randomizer.ts#L7) to import the './types' file, and is then declared using [**CredentialGenerator**](https://github.com/bitwarden/clients/blob/02c65fd1b86839ec2de831488afc65b8f3efce9b/libs/tools/generator/core/src/engine/username-randomizer.ts#L10). Finally [**Generated algorithms**](https://github.com/bitwarden/clients/blob/02c65fd1b86839ec2de831488afc65b8f3efce9b/libs/tools/generator/core/src/engine/username-randomizer.ts#L12) and [**randomWords**](https://github.com/bitwarden/clients/blob/02c65fd1b86839ec2de831488afc65b8f3efce9b/libs/tools/generator/core/src/engine/username-randomizer.ts#L17) are utilized to collect from a random data source for randomized data; allowing customizable options from external data sources. For the 2nd file **

    * Automated Scan Results: The scans for for Codacy, Aikido Security, and Deepscan.io gave me no issues relating to this CWE.
      
* [CWE-267: Privilege Defined With Unsafe Actions](https://cwe.mitre.org/data/definitions/267.html)
    * Files Manually Analyzed:
         * [web-provider.service.ts](https://github.com/bitwarden/clients/blob/main/bitwarden_license/bit-web/src/app/admin-console/providers/services/web-provider.service.ts)
         * [member-access-report.response.ts](https://github.com/bitwarden/clients/blob/main/bitwarden_license/bit-web/src/app/tools/reports/member-access-report/response/member-access-report.response.ts)
         * [provider-permissions.guard.ts](https://github.com/bitwarden/clients/blob/main/bitwarden_license/bit-web/src/app/admin-console/providers/guards/provider-permissions.guard.ts)
    * Manual Scan Results: The use case file these particular code reviews involed is insider employee abuse. The files reviewed all pertained to priviledged information. The first in the code manages organizations and providers accounts. These methods handle [adding](https://github.com/bitwarden/clients/blob/main/bitwarden_license/bit-web/src/app/admin-console/providers/services/web-provider.service.ts#L36), [creating](https://github.com/bitwarden/clients/blob/main/bitwarden_license/bit-web/src/app/admin-console/providers/services/web-provider.service.ts#L74),and [detaching](https://github.com/bitwarden/clients/blob/main/bitwarden_license/bit-web/src/app/admin-console/providers/services/web-provider.service.ts#L82). The second code refers to user access and member details. It displays [usernames](https://github.com/bitwarden/clients/blob/main/bitwarden_license/bit-web/src/app/tools/reports/member-access-report/response/member-access-report.response.ts#L42), [emails](https://github.com/bitwarden/clients/blob/main/bitwarden_license/bit-web/src/app/tools/reports/member-access-report/response/member-access-report.response.ts#L43), [two factor enabled](https://github.com/bitwarden/clients/blob/main/bitwarden_license/bit-web/src/app/tools/reports/member-access-report/response/member-access-report.response.ts#L44), [account recovery](https://github.com/bitwarden/clients/blob/main/bitwarden_license/bit-web/src/app/tools/reports/member-access-report/response/member-access-report.response.ts#L45) and more privileged information. The last code that was reviewed was a guard that checks if the logged-in user has the appropriate [permissions](https://github.com/bitwarden/clients/blob/main/bitwarden_license/bit-web/src/app/admin-console/providers/guards/provider-permissions.guard.ts#L56). 
    * Automated Scan Results: The A.I. automated scans for Aikido Security, Deepscan.io and Codacy did not give me issues relating to this CWE.
      
* [CWE-269: Improper Privilege Management](https://cwe.mitre.org/data/definitions/269.html) 
    * Files Manually Analyzed:
         *Files Manually Analyzed:
         * [auth-request-api.service.ts](https://github.com/bitwarden/clients/blob/main/libs/auth/src/common/services/auth-request/auth-request-api.service.ts)
         * [approve.command.ts](https://github.com/bitwarden/clients/blob/main/bitwarden_license/bit-cli/src/admin-console/device-approval/approve.command.ts)
         * [deny.command.ts](https://github.com/bitwarden/clients/blob/main/bitwarden_license/bit-cli/src/admin-console/device-approval/deny.command.ts)
     * Manual Scan Results:
         * The assurance case file this relates to is Bitwarden minimizes unauthorized access to unauthorized users. These files each deal with a way a member could elevate their privileges that they are not granted. For the first file, it is responsible for making API calls that are related to authentication requests. We are able to see that there is a difference in each request. One is [postAdminAuthRequest](https://github.com/bitwarden/clients/blob/f7b81231bccc1803ed7c1eda8dc3d6291f6f8eb2/libs/auth/src/common/services/auth-request/auth-request-api.service.ts#L38) and the other is [postAuthRequest](https://github.com/bitwarden/clients/blob/f7b81231bccc1803ed7c1eda8dc3d6291f6f8eb2/libs/auth/src/common/services/auth-request/auth-request-api.service.ts#L55). This shows that their is a difference from an admin to a standard BitWarden client. This next file is handling the approval of device authorization requests for an organization. In this file a user can manage passwords [here](https://github.com/bitwarden/clients/blob/0906c503e1f35d264d5169df178dd5a46a39a9b7/bitwarden_license/bit-cli/src/admin-console/device-approval/approve.command.ts#L34). In the last file, similar to the second file, it is checking if a user has the proper privilege to manage authorization requests [here](https://github.com/bitwarden/clients/blob/0906c503e1f35d264d5169df178dd5a46a39a9b7/bitwarden_license/bit-cli/src/admin-console/device-approval/deny.command.ts#L33).
    * Automated Scan Results: The A.I. automated scans for Aikido Security, Deepscan.io and Codacy did not give me issues relating to this CWE.

      
* [CWE-290: Authentication Bypass by Spoofing](https://cwe.mitre.org/data/definitions/290.html)
    * Files Manually Analyzed:
         * [login-via-auth-request-v1.component.ts](https://github.com/bitwarden/clients/blob/main/apps/desktop/src/auth/login/login-via-auth-request-v1.component.ts)
         * [desktop-login-approval-component.service.spec.ts](https://github.com/bitwarden/clients/blob/main/apps/desktop/src/auth/login/desktop-login-approval-component.service.spec.ts)
         * [auth-request.service.ts](https://github.com/bitwarden/clients/blob/main/libs/auth/src/common/services/auth-request/auth-request.service.ts)
    * Manual Scan Results: The beginning of the analysis start with the clients/apps/desktop/src/auth folder to find files related to the authentication process. The files identified were related to the auth request in relation to login, authentication approval, and the authentication request service. The use case this follows is the login use case so these files seemed most relevant to the scenario based approach we were using. The first file listed is where we find the authentication approval [Here](https://github.com/bitwarden/clients/blob/main/apps/desktop/src/auth/login/login-via-auth-request-v1.component.ts#L86). In the second file we find the parameters for authentication [Here](https://github.com/bitwarden/clients/blob/main/apps/desktop/src/auth/login/desktop-login-approval-component.service.spec.ts#L51) which shows the requirements for authentication, and in the last file we get the asyncronous approve or deny request for authentication [Here](https://github.com/bitwarden/clients/blob/main/libs/auth/src/common/services/auth-request/auth-request.service.ts#L87). These are asyncronous processes that are difficult to spoof as shown in the last file they require master key decryption from outside the client in order to validate the authentication.
    * Automated Scan Results: (1) The Akido scan did not find any issues relating to the CWE. (2) The deepscan.io scan did not find any issues relating to the CWE.
    
* [CWE-326: Inadequate Encryption Strength](https://cwe.mitre.org/data/definitions/326.html)
    * Files Manually Analyzed:
         * [passwordGeneration.service.ts](https://github.com/bitwarden/jslib/blob/78429aa7201989ad74a9ca36cc6832fcce0d4aee/common/src/services/passwordGeneration.service.ts)
         * [encrypted-message-handler.service.ts](https://github.com/bitwarden/clients/blob/main/apps/desktop/src/services/encrypted-message-handler.service.ts)
         * [encString.ts](https://github.com/bitwarden/directory-connector/blob/main/jslib/common/src/models/domain/encString.ts)
    * Manual Scan Results: In this code review I scanned codes that are aligned with the “encryption of sensitive data” and “network sniffer captures data” aspect of the use case that was developed prior. The first code review shows code that enforces password [policies](https://github.com/bitwarden/jslib/blob/78429aa7201989ad74a9ca36cc6832fcce0d4aee/common/src/services/passwordGeneration.service.ts#L199), [saves](https://github.com/bitwarden/jslib/blob/78429aa7201989ad74a9ca36cc6832fcce0d4aee/common/src/services/passwordGeneration.service.ts#L374,#L375), and [retrieves](https://github.com/bitwarden/jslib/blob/78429aa7201989ad74a9ca36cc6832fcce0d4aee/common/src/services/passwordGeneration.service.ts#L346,#L347) generated passwords in encrypted history, and [validates password strength](https://github.com/bitwarden/jslib/blob/78429aa7201989ad74a9ca36cc6832fcce0d4aee/common/src/services/passwordGeneration.service.ts#L393). Key functionalities include random number generation for password construction, [encryption](https://github.com/bitwarden/jslib/blob/78429aa7201989ad74a9ca36cc6832fcce0d4aee/common/src/services/passwordGeneration.service.ts#L469,#L470,#L471,#L472,#L473,#L474,#L475,#L476)/[decryption](https://github.com/bitwarden/jslib/blob/78429aa7201989ad74a9ca36cc6832fcce0d4aee/common/src/services/passwordGeneration.service.ts#L482,#L483,#L484,#L485,#L486,#L487,#L488,#L489) of password history and shuffling characters to improve randomness. The second code review handles various encrypted messages that deals with [authentication](https://github.com/bitwarden/clients/blob/main/apps/desktop/src/services/encrypted-message-handler.service.ts#L69,#L70,#L71,#L72,#L73,#L74,#L75,#L76,#L77,#L78,#L79,#L80,#L82,#L83,#L84,#L85,#L86,#L87,#L88,#L89,#L90,#L91,#L92,#L93,#L94,#L95,#L96,#L97,#L98,#L99,#L100,#L101,#L102,#L103,#L104,#L105,#L106,#L107,#L108), credential management, and password generation. This service secures measures between communicating and update throughout the system. The third code reviewed details a utility for handling encrypted strings in various formats, supporting decryption and data parsing based on encryption type. This class integrates encryption metadata management and decryption workflows for secure operations.
    * Automated Scan Results: The A.I. scans for Aikido Security, Deepscan.io and Codacy did not give me issues relating to this CWE.
      
* [CWE-327: Use of a Broken or Risky Cryptographic Algorithm](https://cwe.mitre.org/data/definitions/327.html)
    * Files Manually Analyzed:

    * Automated Scan Results:
      
* [CWE-522: Insufficiently Protected Credentials](https://cwe.mitre.org/data/definitions/522.html)
    * Files Manually Analyzed: 
         * [password-health.service.spec.ts](https://github.com/bitwarden/clients/blob/main/bitwarden_license/bit-common/src/tools/reports/risk-insights/services/password-health.service.spec.ts)
         * [login-via-auth-request-v1.components.ts](https://github.com/bitwarden/clients/blob/main/libs/angular/src/auth/components/login-via-auth-request-v1.component.ts)
         * [login-credentials-view.component.ts](https://github.com/bitwarden/clients/blob/main/libs/vault/src/cipher-view/login-credentials/login-credentials-view.component.ts#L1)
    * Manual Scan Results: These files relate closely to the user logon use case by adressing threats, and actions surrounding credential management, authentication, and security.  For the first file, it is looking at password management, strength evaluation, and security analysis. The code [PasswordStrengthServiceAbstraction](https://github.com/bitwarden/clients/blob/9c1e2ebd6779dda4bd8174722b9c3974f67dc5f9/bitwarden_license/bit-common/src/tools/reports/risk-insights/services/password-health.service.spec.ts#L4) is used for evaluating the strength of a persons password. The [findReusedPassword](https://github.com/bitwarden/clients/blob/9c1e2ebd6779dda4bd8174722b9c3974f67dc5f9/bitwarden_license/bit-common/src/tools/reports/risk-insights/services/password-health.service.spec.ts#L132) is identifying reused passowrds. Also the [findExposedPassword](https://github.com/bitwarden/clients/blob/9c1e2ebd6779dda4bd8174722b9c3974f67dc5f9/bitwarden_license/bit-common/src/tools/reports/risk-insights/services/password-health.service.spec.ts#L142) communicates with the [AuditService](https://github.com/bitwarden/clients/blob/9c1e2ebd6779dda4bd8174722b9c3974f67dc5f9/bitwarden_license/bit-common/src/tools/reports/risk-insights/services/password-health.service.spec.ts#L32) to detect leaked passwords. The next file using [loginViaRequestComponentV1](https://github.com/bitwarden/clients/blob/4daba832a2a32c347228f35593f68548746cf463/libs/angular/src/auth/components/login-via-auth-request-v1.component.ts#L48) class, which is responsible for using the login process using authentication requests in BitWarden. It retrieves the users email, and authentication status. Based on the authentication type, it builds and submits a authentication request using private and public key pairs. For the last file, it is displaying and managing user login credentials [here](https://github.com/bitwarden/clients/blob/4daba832a2a32c347228f35593f68548746cf463/libs/vault/src/cipher-view/login-credentials/login-credentials-view.component.ts#L52). It involves operations where credentials are displayed using [pwToggleValue](https://github.com/bitwarden/clients/blob/4daba832a2a32c347228f35593f68548746cf463/libs/vault/src/cipher-view/login-credentials/login-credentials-view.component.ts#L84), and it uses TOTP codes [here](https://github.com/bitwarden/clients/blob/4daba832a2a32c347228f35593f68548746cf463/libs/vault/src/cipher-view/login-credentials/login-credentials-view.component.ts#L101).
    * Automated Scan Results: The A.I. scans for Aikido Security, Deepscan.io and Codacy did not give me issues relating to this CWE.
    
* [CWE-603: Use of Client-Side Authentication](https://cwe.mitre.org/data/definitions/603.html)
    * Files Manually Analyzed:
         * [login-via-auth-request-v1.component.ts](https://github.com/bitwarden/clients/blob/main/apps/desktop/src/auth/login/login-via-auth-request-v1.component.ts)
         * [desktop-login-approval-component.service.spec.ts](https://github.com/bitwarden/clients/blob/main/apps/desktop/src/auth/login/desktop-login-approval-component.service.spec.ts)
         * [auth-request.service.ts](https://github.com/bitwarden/clients/blob/main/libs/auth/src/common/services/auth-request/auth-request.service.ts)
  * Manual Scan Results: Similar to the reasoning for CWE-290 we start with the authentication files in the BitWarden repo. The most important of these files for this CWE is the auth-request.service.ts file which shows [Here](https://github.com/bitwarden/clients/blob/main/apps/desktop/src/auth/login/desktop-login-approval-component.service.spec.ts#L51) and [Here](https://github.com/bitwarden/clients/blob/main/libs/auth/src/common/services/auth-request/auth-request.service.ts#L105) the service requiring a master key that comes from outside the client to approve authentication. This shows that the authentication isn't occuring client side.
  * Automated Scan Results: (1) The Akido scan did not find any issues relating to the CWE. (2) The deepscan.io scan did not find any issues relating to the CWE.



## 5. Summary

## 6. Open source contributions

## 7. Reflections
