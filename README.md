# EX-NO-13-MESSAGE-AUTHENTICATION-CODE-MAC
## NAME: PRIYADHARSHINI P
## REGISTER NUMBER: 212224040252
## DATE: 13-03-2026

## AIM:
To implement MESSAGE AUTHENTICATION CODE(MAC)

## ALGORITHM:

1. Message Authentication Code (MAC) is a cryptographic technique used to verify the integrity and authenticity of a message by using a secret key.

2. Initialization:
   - Choose a cryptographic hash function \( H \) (e.g., SHA-256) and a secret key \( K \).
   - The message \( M \) to be authenticated is input along with the secret key \( K \).

3. MAC Generation:
   - Compute the MAC by applying the hash function to the combination of the message \( M \) and the secret key \( K \): 
     \[
     \text{MAC}(M, K) = H(K || M)
     \]
     where \( || \) denotes concatenation of \( K \) and \( M \).

4. Verification:
   - The recipient, who knows the secret key \( K \), computes the MAC using the received message \( M \) and the same hash function.
   - The recipient compares the computed MAC with the received MAC. If they match, the message is authentic and unchanged.

5. Security: The security of the MAC relies on the secret key \( K \) and the strength of the hash function \( H \), ensuring that an attacker cannot forge a valid MAC without knowledge of the key.

## Program:
```
#include <stdio.h>
#include <string.h>

int main(){
    char k[50],m[50],mac[10]; int i;

    scanf("%s%s",k,m);

    for(i=0;i<8;i++)
        mac[i]=k[i%strlen(k)]^m[i%strlen(m)];

    printf("MAC:");
    for(i=0;i<8;i++)
        printf("%02x",(unsigned char)mac[i]);
}
```



## Output:
<img width="1271" height="508" alt="image" src="https://github.com/user-attachments/assets/82c0f844-ee4a-4564-b01f-0484b6a05b31" />



## Result:
The program is executed successfully.
