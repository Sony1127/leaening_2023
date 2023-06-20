#include <stdio.h>
int main() {
    int size, i, temp;
    printf("Enter the size of the array: ");
    scanf("%d", &size);
    int array[size]; 
    printf("Enter the elements of the array:\n");
    for (i = 0; i < size; i++) {
        scanf("%d", &array[i]);
    }  
    // Reversing the array
    for (i = 0; i < size / 2; i++) {
        temp = array[i];
        array[i] = array[size - i - 1];
        array[size - i - 1] = temp;
    }
    printf("Reversed arra is :\n");
    for (i = 0; i < size; i++) {
        printf("%d ", array[i]);
    }
    printf("\n");
    
    return 0;
}