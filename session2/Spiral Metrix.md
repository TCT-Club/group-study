```cpp
#include <bits/stdc++.h>
vector<int> spiralPathMatrix(vector<vector<int>> arr, int n, int m) {
    // Write your code here.
    int fcol = 0;
    int lcol = m - 1;

    int frow = 0;
    int lrow = n - 1;

    vector<int> ans;

    while (frow <= lrow && fcol <= lcol) {
        // Traverse top row
        for (int i = fcol; i <= lcol; i++) {
            ans.push_back(arr[frow][i]);
        }
        frow++;

        // Traverse right column
        for (int i = frow; i <= lrow; i++) {
            ans.push_back(arr[i][lcol]);
        }
        lcol--;

        // Traverse bottom row
        if (frow <= lrow) {
            for (int i = lcol; i >= fcol; i--) {
                ans.push_back(arr[lrow][i]);
            }
            lrow--;
        }

        // Traverse left column
        if (fcol <= lcol) {
            for (int i = lrow; i >= frow; i--) {
                ans.push_back(arr[i][fcol]);
            }
            fcol++;
        }
    }

    return ans;
}
```