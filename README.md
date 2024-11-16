# Exercise No-1:
# Caesar Cipher Program

# Aim:
To implement Caesar Cipher encryption and decryption programs in C.

# Algorithm:

# 1. Encryption:
   - Take a plaintext message and a shift value.
   - For each character in the plaintext:
     - If the character is an uppercase letter, shift it by the given key within the range of A-Z.
     - If the character is a lowercase letter, shift it by the given key within the range of a-z.
     - Non-alphabet characters remain unchanged.
   - Display the encrypted message.

# 2. Decryption:
   - Take the ciphertext and the same shift value used for encryption.
   - For each character in the ciphertext:
     - Reverse the shift applied during encryption within the range of A-Z for uppercase letters and a-z for lowercase letters.
     - Non-alphabet characters remain unchanged.
   - Display the decrypted message.

# Encryption Code:

```
#include <stdio.h>
#include <string.h>

void encryptCaesarCipher(char* message, int shift) {
    for (int i = 0; i < strlen(message); i++) {
        char c = message[i];
        
        // Check for uppercase letters
        if (c >= 'A' && c <= 'Z') {
            message[i] = ((c - 'A' + shift) % 26) + 'A';
        }
        // Check for lowercase letters
        else if (c >= 'a' && c <= 'z') {
            message[i] = ((c - 'a' + shift) % 26) + 'a';
        }
    }
}

int main() {
    char message[100];
    int shift;

    printf("Enter a message: ");
    fgets(message, sizeof(message), stdin);
    message[strcspn(message, "\n")] = 0;  // Remove newline character

    printf("Enter shift value: ");
    scanf("%d", &shift);

    // Encrypt the message
    encryptCaesarCipher(message, shift);
    printf("Encrypted Message: %s\n", message);

    return 0;
}
```

# Decryption Code:

```
#include <stdio.h>
#include <string.h>

void decryptCaesarCipher(char* message, int shift) {
    for (int i = 0; i < strlen(message); i++) {
        char c = message[i];
        
        // Check for uppercase letters
        if (c >= 'A' && c <= 'Z') {
            message[i] = ((c - 'A' - shift + 26) % 26) + 'A';
        }
        // Check for lowercase letters
        else if (c >= 'a' && c <= 'z') {
            message[i] = ((c - 'a' - shift + 26) % 26) + 'a';
        }
    }
}

int main() {
    char message[100];
    int shift;

    printf("Enter an encrypted message: ");
    fgets(message, sizeof(message), stdin);
    message[strcspn(message, "\n")] = 0;  // Remove newline character

    printf("Enter shift value used for encryption: ");
    scanf("%d", &shift);

    // Decrypt the message
    decryptCaesarCipher(message, shift);
    printf("Decrypted Message: %s\n", message);

    return 0;
}
```

# Sample Output for Encryption:
![image](https://github.com/user-attachments/assets/db14ae12-80f0-4bd5-97fa-6b4efbb1b7fc)


# Sample Output for Decryption:
![image](https://github.com/user-attachments/assets/7782e2c2-25c5-4ff7-8c96-cde9678e71dc)


# RESULT:
The Caesar Cipher encryption and decryption programs were successfully implemented in C. The encryption code correctly converts the plaintext into ciphertext using the given shift value, and the decryption code accurately recovers the original plaintext from the ciphertext.
