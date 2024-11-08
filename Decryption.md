# Decrypting an Encrypted Message with OpenSSL

This document guides you through the process of decrypting a message file encrypted with a symmetric key using OpenSSL. Please follow each step carefully to decrypt the message successfully.

## Prerequisites: Installing OpenSSL

If OpenSSL is not already installed on your system, use the following commands:

### For Ubuntu/Debian
```bash
sudo apt update
sudo apt install openssl
```
### Files Provided
In the shared folder, you will find the following files:

**symmetric_key.key** - This file contains the symmetric key used for encryption.
**encrypted_message.enc** - This is the encrypted file containing the message.
## Decryption
The command below will decrypt encrypted_message.enc using the symmetric_key.key file.

```
openssl enc -aes-256-cbc -d -in encrypted_message.enc -out decrypted_message.txt -pass file:./symmetric_key.key
```
### Explanation of the Command:
- **openssl enc:** Runs the OpenSSL encryption/decryption command.
- **-aes-256-cbc:** Specifies the encryption algorithm used, AES with a 256-bit key in CBC (Cipher Block Chaining) mode.
- **-d:** Tells OpenSSL to decrypt the file.
- **-in encrypted_message.enc:** Specifies the encrypted file to decrypt.
- **-out decrypted_message.txt:** Specifies the name of the output file for the decrypted message.
- **-pass file:./symmetric_key.key:** Provides the path to the symmetric key file. This file is used as a "password" to unlock the encryption.
### Step 3: View the Decrypted Message
Once the decryption process is complete, you’ll see a new file named decrypted_message.txt in your current directory. Open this file to view the original message.
```
cat decrypted_message.txt
```
