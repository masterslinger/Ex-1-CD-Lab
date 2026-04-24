# Ex-1 IMPLEMENTATION-OF-SYMBOL-TABLE
# Register Number : 212224040346
# Date : 24-04-2026
# AIM :
## To write a C program to implement a symbol table.
# ALGORITHM :
1.	Start the program.
2.	Get the input from the user with the terminating symbol ‘$’.
3.	Allocate memory for the variable by dynamic memory allocation function.
4.	If the next character of the symbol is an operator then only the memory is allocated.
5.	While reading, the input symbol and memory address are inserted into the symbol table.
6.	The steps are repeated till ‘$’ is reached.
7.	To reach a variable, enter the variable to be searched and the symbol table has been checked for the corresponding variable, the variable along with its address is displayed as a result.
8.	Stop the program. 
# PROGRAM :
```c
#include <stdio.h>
#include <ctype.h>
#include <string.h>
#include <stdlib.h>

#define MAX_EXPRESSION_SIZE 100
#define MAX_SYMBOLS 15

int main() {
    int i = 0, j = 0, x = 0, n, flag = 0;
    int k;
    char b[MAX_EXPRESSION_SIZE], d[MAX_SYMBOLS], c, srch;
    void* addr[MAX_SYMBOLS];

    printf("Enter the Expression terminated by $: ");
    while ((c = getchar()) != '$' && i < MAX_EXPRESSION_SIZE - 1) {
        b[i++] = c;
    }
    b[i] = '\0';
    n = i - 1;

    printf("\nGiven Expression: %s\n", b);

    printf("\nSymbol Table\n");
    printf("Symbol\tType\t\tAddress\n");

    for (j = 0; j <= n; j++) {
        c = b[j];
        if (isalpha((unsigned char)c)) {
            int alreadyExists = 0;
            for (k = 0; k < x; k++) {
                if (d[k] == c) {
                    alreadyExists = 1;
                    break;
                }
            }

            if (!alreadyExists && x < MAX_SYMBOLS) {
                d[x] = c;
                addr[x] = (void*)&b[j];
                printf("%c\tidentifier\t%p\n", d[x], addr[x]);
                x++;
            }
        }
    }

    while ((c = getchar()) != '\n' && c != EOF);

    printf("\nEnter the symbol to search: ");
    srch = getchar();

    for (i = 0; i < x; i++) {
        if (srch == d[i]) {
            printf("Symbol Found\n");
            printf("Address: %p\n", addr[i]);
            flag = 1;
            break;
        }
    }

    if (flag == 0)
        printf("Symbol Not Found\n");

    return 0;
}
```
# OUTPUT :
Output 01 :
<img width="607" height="332" alt="image" src="https://github.com/user-attachments/assets/3d6137e5-5442-4a9e-a9d7-4259a6279938" />


Output 02 :
<img width="598" height="313" alt="image" src="https://github.com/user-attachments/assets/dfdc1b23-6854-447e-be13-bc5af3bf49c7" />


# RESULT
### The program to implement a symbol table is executed and the output is verified.
