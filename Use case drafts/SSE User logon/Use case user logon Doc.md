## Use Case User Logon
[Link to SSE document](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Software%20Security%20Engineering.md)

Description:
Each employee has access to a password manager and secrets manager that will enable them to have assurance when they log into their accounts and submit code using their accounts that they are the only ones with access. 

### Analysis:
  
  1. Security Requirements:
      * Two Factor-Authentication - A two factor authentication method is required in the case someone has a way to access the users account or the recovery key that is sent when a master password is lost.
      * Password hasing/Salting - Hashing and salting is requirement in the event a bad actor manages to access the master key database to prevent the bad actor from reading the plaintext of the password, the salting is needed for complexity to prevent easy hashing cracking.
      * Event logging - When events occur, an admin resetting an employee password for instance, it is required that we log which employee requested it and when so we can audit an employee account if we suspect malicious aciton.
      * Input Validation - Having a source of input validation ensures that the employee who uploaded code to the BitWarden vault was the correct employee and not a malicious actor attempting to gain advantage.

  2. Security Features:
      * Two factor authentication - This is supported by BitWarden with their own two-factor authenticator. [Here](https://bitwarden.com/help/bitwarden-authenticator/)
      * Password Hashing and email salting - BitWarden uses PBKDF2 with 600,000 iteration rounds to strectch the master password along with salt of the account email address. The result is 256-bit Master Key. The Master password hash is then generated with PBKDF-SHA256 using the Master key and salt of the master password. [Here](https://bitwarden.com/help/what-encryption-is-used/)
      * Master key reset - The admin panel has access to an Account Recovery key which can be used to reset the Master Key for an employee creating a new hash for the master password that is created from the users encryption key and can only be decrypted by the organization's private key in the Admin panel. [Here](https://bitwarden.com/help/account-recovery/)
      * BitWarden secrets manager logs events - Bitwarden logs account recovery events 4 times; when a master password is reset, a user updates a password after a reset, a user opts into account recovery, and a user withdraws from account recovery. [Here](https://bitwarden.com/help/account-recovery/) and the full list of what gets logged is [Here](https://bitwarden.com/help/event-logs/)
      * BitWarden Input validation - The vault allows for employees to upload files securely and can be seperated by users and groups. [Here](https://bitwarden.com/help/managing-items/#tab-secure-notes-2VtgLfbwjcMq1V04S1pSIO)

Diagram:
![](https://github.com/PatrickBN/CYBR8420_Team5/blob/main/Use%20case%20drafts/SSE%20User%20logon/SSE%20User%20Logon%20Use%20case%203.png)
