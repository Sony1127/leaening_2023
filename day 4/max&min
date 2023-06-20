#include <stdio.h>
int main() {
    int n, i;
    printf("Enter the size of the array: ");
    scanf("%d", &n);
    int array[n];
    printf("Enter the elements of the array:\n");
    for (i = 0; i < n; i++) {
        scanf("%d", &array[i]);
    }
    int min = array[0];
    int max = array[0];  
    for (i = 1; i < n; i++) {
        if (array[i] < min) {
            min = array[i];
        }
        else if (array[i] > max) {
            max = array[i];
        }
    } 
    printf("Minimum value: %d\n", min);
    printf("Maximum value: %d\n", max); 
    return 0;
}