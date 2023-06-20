#include <stdio.h>

int main() {
    int arr[] = {64, 84, 21, 36, 17, 90, 77, 5, 10, 48, 69};
    int evenSum = 0;
    int oddSum = 0;
    int length = sizeof(arr) / sizeof(arr[0]);

    for (int i = 0; i < length; i++) {
        if (i % 2 == 0) {
            evenSum += arr[i];
        } else {
            oddSum += arr[i];
        }
    }

    printf("Sum of even indexed elements: %d\n", evenSum);
    printf("Sum of odd indexed elements: %d\n", oddSum);

    return 0;
}