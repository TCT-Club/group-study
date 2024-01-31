1. Brute force

```cpp
vector<int> rotateArray(vector<int> nums, int k) {
  int n = nums.size();

  // To handle the case where k is greater than n
  k = k % n;

  for (int step = 1; step <= k; step++) {
    // Perform one rotation step by moving the first element to the end
    int temp = nums[0];
    for (int i = 1; i < n; i++) {
      nums[i - 1] = nums[i];
    }
    nums[n - 1] = temp;
  }

  return nums;
}
```


2. Optimal

```cpp
vector<int> rotateArray(vector<int> nums, int k) {
  int n = nums.size();

  k = k % n;

  vector<int> temp = nums;

  for (int i = 0; i < n; i++) {
    nums[i] = temp[(i + k) % n];
  }

  return nums;
}
```