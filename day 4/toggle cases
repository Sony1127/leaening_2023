#include <stdio.h>
#include <string.h>
#include<ctype.h>

int main() {
    char str[100];
    int i;
    
    printf("Enter a string: ");
   // scanf("%c",&str);
    fgets(str, sizeof(str), stdin);
    
    // Toggle the case of each character
    for (i = 0; str[i] != '\0'; i++) {
        if (isupper(str[i])) {
            str[i] = tolower(str[i]);
        } else if (islower(str[i])) {
            str[i] = toupper(str[i]);
        }
    }
    
    printf("Toggled case: %s\n", str);
    
    return 0;
}