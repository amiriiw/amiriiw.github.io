<h2 align="center">Public Key & Private Key</h2>

<p align="center">
  <strong>Learning URLs:</strong> 
  <a href="https://youtu.be/t3mRNlt8w1c?si=UERSkQxMM80IfdNW">Jadi</a>
</p>

## What are Public and Private Keys?
Public and private keys are fundamental to cryptography and are used in many modern security systems, such as digital signatures and data encryption. These keys work as a pair, and one is incomplete without the other.
- **Public Key:** A public key is a cryptographic key that can be shared publicly. Others can use it to encrypt information or verify a digital signature.
- **Private Key:** A private key must remain confidential and is only known to the owner. It is used to decrypt information encrypted with the corresponding public key or to create a digital signature.

## How Do They Work?
1. **Encryption:**
   - If someone wants to send you secure information, they can use your public key to encrypt it.
   - When you receive the encrypted information, only you can decrypt it using your private key.
2. **Digital Signature:**
   - If you want to send a message and ensure that the recipient can verify it came from you, you use your private key to sign the message digitally.
   - The recipient can then use your public key to verify the signature and confirm that the message was sent by you and hasn't been altered.

## How to Generate a Pair of Public and Private Keys?
You can generate a pair of public and private keys using various tools available in most operating systems. One popular tool for this is OpenSSL, or you can use key management software like GPG.

### Example Using OpenSSL:
1. **Generate a Private Key:**
    ```bash
    openssl genpkey -algorithm RSA -out private_key.pem -pkeyopt rsa_keygen_bits:2048
    ```
    This command generates a 2048-bit RSA private key and stores it in a file named `private_key.pem`.
2. **Extract the Public Key from the Private Key:**
    ```bash
    openssl rsa -pubout -in private_key.pem -out public_key.pem
    ```
    This command extracts the public key associated with the private key and stores it in a file named `public_key.pem`.
#### Using the Keys:
- **Encrypting a Message:**
    To encrypt a message using the public key:
    ```bash
    echo "Hello, World!" | openssl rsautl -encrypt -pubin -inkey public_key.pem -out encrypted_message.bin
    ```
- **Decrypting a Message:**
    To decrypt the message using the private key:
    ```bash
    openssl rsautl -decrypt -inkey private_key.pem -in encrypted_message.bin
    ```
This provides a basic overview of how public and private keys work, and how to generate and use them.

---
