# EX. NO: 1(A) : IMPLEMENTATION OF CAESAR CIPHER

## AIM:
To implement the simple substitution technique named Caesar cipher using C language.

## ALOGORITHM:

STEP-1: Read the plain text from the user.

STEP-2: Read the key value from the user.

STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.

STEP-4: Else subtract the key from the plain text.

STEP-5: Display the cipher text obtained above.

## PROGRAM:
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char plain[10], cipher[10];
    int key, i, length;

    // Input for plaintext
    printf("\n Enter the plain text: ");
    scanf("%9s", plain); // Limiting input to avoid overflow

    // Input for the key
    printf("\n Enter the key value: ");
    scanf("%d", &key);

    length = strlen(plain);

    printf("\n \n \t PLAIN TEXT: %s", plain);
    printf("\n \n \t ENCRYPTED TEXT: ");
    
    // Encryption process
    for (i = 0; i < length; i++) {
        cipher[i] = plain[i] + key;

        // Adjust if beyond 'Z' or 'z'
        if (isupper(plain[i]) && (cipher[i] > 'Z'))
            cipher[i] -= 26;
        if (islower(plain[i]) && (cipher[i] > 'z'))
            cipher[i] -= 26;

        printf("%c", cipher[i]);
    }
    cipher[length] = '\0'; // Null-terminating the cipher text

    // Decryption process
    printf("\n \n \t AFTER DECRYPTION: ");
    for (i = 0; i < length; i++) {
        plain[i] = cipher[i] - key;

        // Adjust if below 'A' or 'a'
        if (isupper(cipher[i]) && (plain[i] < 'A'))
            plain[i] += 26;
        if (islower(cipher[i]) && (plain[i] < 'a'))
            plain[i] += 26;

        printf("%c", plain[i]);
    }
    plain[length] = '\0'; // Null-terminating the plain text

    // getchar(); // Use this if you want to pause the program
    return 0;
}


```


## OUTPUT:
![image](https://github.com/user-attachments/assets/01af209e-ad2f-4a8f-b8b8-b98a01be6dbb)



## RESULT :
 Thus the implementation of ceasar cipher had been executed successfully.
