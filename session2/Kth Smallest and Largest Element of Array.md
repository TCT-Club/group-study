```cpp

#include <bits/stdc++.h>

int kthsmall(vector<int> arr, int n, int k) {
    priority_queue<int> pq;

    for (int i = 0; i < n; i++) {
        pq.push(arr[i]);

        if (pq.size() > k) pq.pop();
    }

    return pq.top();
}

int kthlarg(vector<int> arr, int n, int k) {
    priority_queue<int, vector<int>, greater<int>> pq;

    for (int i = 0; i < n; i++) {
        pq.push(arr[i]);

        if (pq.size() > k) pq.pop();
    }

    return pq.top();
}

vector<int> kthSmallLarge(vector<int> &arr, int n, int k) {
    vector<int> ans;

    ans.push_back(kthsmall(arr, n, k));

    ans.push_back(kthlarg(arr, n, k));

    return ans;
}

```