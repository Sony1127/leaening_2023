#include <stdio.h>
#include <stdlib.h>

int main() {
    char timeStr[100];
    int hours, minutes, seconds;
    printf("Enter time in the format hh:mm:ss: ");
    fgets(timeStr, sizeof(timeStr), stdin);
    
    sscanf(timeStr, "%d:%d:%d", &hours, &minutes, &seconds);
    
    int totalSeconds = hours * 3600 + minutes * 60 + seconds;
    
    printf("Total seconds: %d\n", totalSeconds);
    
    return 0;
}
