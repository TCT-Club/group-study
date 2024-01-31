```cpp
#include <bits/stdc++.h>
void sort012(int *arr, int n) {
    int countZeros = 0;
    int countOnes = 0;
    int countTwos = 0;

    // Count the occurrences of 0s, 1s, and 2s
    for (int i = 0; i < n; i++) {
        if (arr[i] == 0)
            countZeros++;
        else if (arr[i] == 1)
            countOnes++;
        else if (arr[i] == 2)
            countTwos++;
    }

    int i = 0;

    // Place the counted elements back into the array
    while (countZeros) {
        arr[i] = 0;
        i++;
        countZeros--;
    }
    while (countOnes) {
        arr[i] = 1;
        i++;
        countOnes--;
    }
    while (countTwos) {
        arr[i] = 2;
        i++;
        countTwos--;
    }
}
```