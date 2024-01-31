
1. Recursive
```cpp
/*
    Time Complexity: O( 2 ^ N )
    Space complexity: O( N )

    Where ‘N’ is the stair to reach, given in the input.
*/

int getCount(int currStep, int nStairs, const int& mod) {

    // Base case.
    if(currStep >= nStairs) {

        return (currStep == nStairs);
    }

    //  Climb one stair.
    int oneStepcount = getCount(currStep + 1, nStairs, mod);

    //  Climb two stairs
    int twoStepCount = getCount(currStep + 2, nStairs, mod);

    return (oneStepcount + twoStepCount) % mod; 

}

int countDistinctWays(int nStairs) {
    
    // Initialize the variable 'mod'.
    const int mod = 1000000007;

    // Initialize the variable 'ways'.
    int ways = getCount(0, nStairs, mod);

    return ways;
}
```


2. Dynamic Programming
```cpp
#include <bits/stdc++.h> 

#define M 1000000007;

int f(vector<int> &arr, int n) {

        if(n <= 1) {
            return 1;
        }

        if(arr[n] == -1) {
            arr[n] = (f(arr,n-1) + f(arr,n-2))%M;
            return arr[n];
        }
        else {
            return arr[n];
        }
    }

int countDistinctWays(int n) {

    //  Write your code here.
    vector<int> arr(n+1, -1);
    return f(arr,n);
}
```