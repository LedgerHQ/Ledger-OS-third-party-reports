# What’s the Ledger OS audit process?
With every Ledger OS release, the Ledger team of cybersecurity experts called the [Donjon](https://donjon.ledger.com/) perform a security audit before a new version enters production. The audit includes a Secure Element code review to make sure that there are no vulnerabilities to attacks such as side-channel, fault, and software attacks. 

Additionally, we have incorporated a third-party security laboratory into the Ledger OS release process. Under an NDA, the security laboratory’s consultants are granted access to the Ledger OS source code and build environment, allowing for a comprehensive and transparent review. 

For more information, please refer to [our information page](https://support.ledger.com/fr/article/Third-party-Security-Assessment-Report).

## How to verify the authenticity of the security assessment report  

### 1. Download and install GPG (GNU Privacy Guard) on your computer
  - Linux: Use your package manager to install it, for example, run `sudo apt install gnupg`.  
  - macOS: Install via Homebrew by running brew install GnuPG.  
  - Windows: Download it from GPG for Windows at https://gnupg.org/download/  

### 2. Import the PGP Public Key
Download the security laboratory’s PGP public key file from the Synacktiv website:   
https://www.synacktiv.com/synacktiv-ledger.pub.asc  (Fingerprint: `50BC FFEE 05D5 F641 BABF B486 D49D 950A 8184 F98F`)

Import the key into your GPG keyring using the following command in your terminal :  
```
gpg --import synacktiv-ledger.pub.asc
``` 
After importing, you should see confirmation that the key has been added successfully.  

### 3. Download both the document and its corresponding PGP signature file
 - Document: The Security Assessment Report you want to verify.  
 - PGP Signature: The .asc signature file associated with the document.  
  
Ensure the document and signature files are in the same directory, and take note of their file names.  
### 4. Verify the signature
To verify the signature, use the following command in your terminal:  
```
gpg --verify Synacktiv-Ledger-Security_Assessment_Report.sig.asc Synacktiv-Ledger-Security_Assessment_Report.pdf
```
After running the command, GPG will output the result of the verification. If the signature is valid, you will see a message similar to this:  
```
gpg: Good signature from "Synacktiv (key used to sign Synacktiv's reports for Ledger) <contact@synacktiv.com>"
```
