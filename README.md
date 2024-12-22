# File Encryption and Decryption Application

## Overview
This is a Java-based desktop application for encrypting and decrypting files. The application uses AES encryption with CBC mode and supports multi-threaded file processing for better performance. A graphical user interface (GUI) built with Swing allows users to interact with the program intuitively.

---

## Features
- **Encrypt files**: Securely encrypts files using AES/CBC/PKCS5Padding.
- **Decrypt files**: Decrypt previously encrypted files.
- **Password-based encryption**: Utilizes PBKDF2 for generating secure keys from user-provided passwords.
- **Multi-threaded processing**: Enhances performance by processing files in parallel.
- **GUI Interface**: Simplified file selection and operations using Swing.

---

## Prerequisites

1. **Java Development Kit (JDK)**: Ensure JDK 8 or above is installed on your machine.
2. **Build Tool**: Optional, use Maven/Gradle for dependency management (not required in the current standalone version).

---

## How to Run

1. Compile the application using the following command:
   ```bash
   javac FileEncryptionApp.java
   ```

2. Run the application:
   ```bash
   java FileEncryptionApp
   ```

---

## Usage

### GUI Instructions

1. **Input File**:
   - Use the "Select Input File" button to choose the file you want to encrypt or decrypt.

2. **Output File**:
   - Use the "Select Output File" button to specify where the encrypted or decrypted file will be saved.

3. **Password**:
   - Enter a password. Ensure it matches the password used during encryption for decryption.

4. **Encrypt/Decrypt**:
   - Click "Encrypt" to encrypt the selected file or "Decrypt" to decrypt the selected file.

### Important Notes:
- The password must match "Raksha" in this example. You can modify this validation for custom password handling.
- Encrypted files include a salt and initialization vector (IV) stored at the beginning of the file.

---

## Code Structure

### Main Classes

1. **`FileEncryptionApp`**:
   - The main class for creating and managing the Swing-based GUI.
   - Handles user inputs and file operations.

2. **`Encryptor`**:
   - Handles AES encryption with CBC mode.
   - Writes the salt and IV to the output file.

3. **`Decryptor`**:
   - Handles AES decryption.
   - Reads the salt and IV from the encrypted file.

4. **`CryptoUtils`**:
   - Utility methods for generating a salt and deriving a secure key using PBKDF2.

5. **`MultiThreadProcessor`**:
   - Processes file operations in parallel using a thread pool for efficiency.

6. **`FileProcessor`**:
   - Abstract class to define the template for file processing tasks.

---

## Technical Details

1. **Encryption Algorithm**:
   - AES (Advanced Encryption Standard) with 256-bit key size.
   - CBC (Cipher Block Chaining) mode for strong encryption.
   - PKCS5Padding for padding.

2. **Key Derivation**:
   - PBKDF2 with HMAC-SHA256.
   - Salt and 65,536 iterations to protect against brute-force attacks.

3. **Salt**:
   - Randomly generated 16-byte salt stored in the output file.

4. **Initialization Vector (IV)**:
   - Randomly generated and stored in the output file after the salt.

---

