# HILL CIPHER
HILL CIPHER
EX. NO: 3 IMPLEMENTATION OF HILL CIPHER

AIM:
 ## To write a C program to implement the hill cipher substitution techniques.

## DESCRIPTION:

Each letter is represented by a number modulo 26. Often the simple scheme A = 0, B
= 1... Z = 25, is used, but this is not an essential feature of the cipher. To encrypt a message, each block of n letters is  multiplied by an invertible n × n matrix, against modulus 26. To
decrypt the message, each block is multiplied by the inverse of the m trix used for
 
encryption. The matrix used
 
for encryption is the cipher key, and it sho
 
ld be chosen
 
randomly from the set of invertible n × n matrices (modulo 26).


## ALGORITHM:
```
STEP-1: Read the plain text and key from the user.
STEP-2: Split the plain text into groups of length three.
STEP-3: Arrange the keyword in a 3*3 matrix.
STEP-4: Multiply the two matrices to obtain the cipher text of length three.
STEP-5: Combine all these groups to get the complete cipher text.
```

## PROGRAM 
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>
int main()
{
    char msg[100];
    int key[3][3], cipher[100];
    int i, j, k, len;
    printf("Enter the plain text: ");
    scanf("%s", msg);
    printf("Enter the 3x3 key matrix:\n");
    for(i = 0; i < 3; i++)
    {
        for(j = 0; j < 3; j++)
        {
            scanf("%d", &key[i][j]);
        }
    }
    len = strlen(msg);
    while(len % 3 != 0)
    {
        msg[len++] = 'X';
    }
    msg[len] = '\0';
    printf("Cipher Text: ");
    for(i = 0; i < len; i += 3)
    {
        for(j = 0; j < 3; j++)
        {
            cipher[j] = 0;
            for(k = 0; k < 3; k++)
            {
                cipher[j] += key[j][k] *
                             (toupper(msg[i+k]) - 'A');
            }
            cipher[j] = cipher[j] % 26;
        }
        for(j = 0; j < 3; j++)
        {
            printf("%c", cipher[j] + 'A');
        }
    }
    return 0;
}
```

## OUTPUT
<img width="1837" height="685" alt="image" src="https://github.com/user-attachments/assets/65eda45d-0458-4e37-a888-c7edfa9aa73b" />


## RESULT
Thus, the C program to implement the Hill Cipher substitution technique was executed successfully.
