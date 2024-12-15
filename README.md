Project Title 
**File Encryption and Decryption Utility**  

---

#### ** Overview/Introduction**  
This project provides a Java-based utility for encrypting and decrypting files securely using the AES (Advanced Encryption Standard) algorithm in CBC (Cipher Block Chaining) mode. It ensures robust security through salted key derivation and a multi-threaded processing mechanism for handling multiple files efficiently.  

---

#### ** Features**  
- **Encryption and Decryption**: Uses AES with CBC mode for secure file encryption and decryption.  
- **Key Derivation**: Derives a strong cryptographic key from a password and a unique salt.  
- **Multi-Threaded Processing**: Supports parallel encryption and decryption of multiple files for enhanced performance.  
- **IV Management**: Handles initialization vector (IV) storage and retrieval for secure encryption operations.  

---

#### ** Prerequisites**  
- **Java Development Kit (JDK)**: Version 8 or later.  
- Basic knowledge of file systems and cryptography (optional).  

---

#### ** Installation and Setup Instructions**  
1. Clone or download the repository to your local machine.  
2. Ensure the necessary JDK is installed on your system.  
3. Compile the code using `javac Main.java`.  
4. Run the program using `java Main`.  

---

#### ** Usage**  
- Place the input file (`example.txt`) in the specified directory.  
- Configure the file paths and password in the `Main` class.  
- The program will:  
  1. Encrypt the input file and generate an encrypted file (`encrypted_example.txt`).  
  2. Decrypt the encrypted file and create a decrypted file (`decrypted_example.txt`).  
  3. Perform multi-threaded encryption and decryption of additional files if specified.  

---

#### ** Code Structure/Components**  
- **`FileProcessor`**: Abstract class for processing files with encryption/decryption.  
- **`Encryptor`**: Encrypts files using AES with a secure IV.  
- **`Decryptor`**: Decrypts encrypted files back to their original form.  
- **`CryptoUtils`**: Provides utility methods for salt generation and key derivation.  
- **`MultiThreadProcessor`**: Handles concurrent processing of files using multiple threads.  
- **`Main`**: Demonstrates the program’s functionality, including encryption, decryption, and multi-threaded file processing.  

### **Limitations**  
1. **File Size**: The program may experience performance issues with very large files due to memory usage and processing time.  
2. **Key Management**: The program requires secure management of the password and salt file to ensure proper decryption.  
3. **Thread Count**: Excessive thread count in the multi-threaded processor might cause resource contention.  
4. **Algorithm Limitation**: Uses AES in CBC mode, which requires secure IV storage to prevent attacks like ciphertext manipulation.  
5. **Password Dependency**: The encryption security is tied to the strength of the password provided by the user.  
6. **Static Salt File**: A single salt file is used for all operations, making it necessary to ensure its security and availability.  
7. **Error Handling**: Limited error recovery in case of file corruption or missing IV/salt files.  

---

### **Example Usage**  

#### **1. Encryption Example:**  
Input: A file named `example.txt` containing plain text.  
Output: Encrypted file named `encrypted_example.txt`.  

**Steps:**  
- The program generates a unique salt and IV.  
- Encrypts `example.txt` using AES-CBC and writes the encrypted content to `encrypted_example.txt`.  

#### **2. Decryption Example:**  
Input: The encrypted file `encrypted_example.txt` and the salt file `salt.dat`.  
Output: Decrypted file named `decrypted_example.txt`.  

**Steps:**  
- Loads the salt and derives the key using the password.  
- Decrypts `encrypted_example.txt` and restores the original content in `decrypted_example.txt`.  

#### **3. Multi-Threaded Example:**  
Files: Multiple input files like `file1.txt`, `file2.txt`.  
Output: Encrypted files like `file1.encrypted`, `file2.encrypted`.  

**Steps:**  
- Processes the files in parallel using multiple threads for faster encryption or decryption.  
- Outputs encrypted or decrypted files simultaneously.  
