1. Brute Force
```cpp
int getPairsCount(int arr[], int n, int k) {
	int count = 0;
	
	for(int i=0 ; i<n-1 ; i++) {
		for(int j=i+1 ; j<n ; j++) {
			if(arr[i] + arr[j] == k)
				count++;
		}
	}
	
	return count;
}
```

2. Optimal
```cpp

long long pairsWithGivenSum(int arr[], int n, int k)

{

    // Write your code here

    unordered_map<int, int> freq;

    long long count = 0;

    for (int i = 0; i < n; i++) {

        // calculate the diff

        int complement = k - arr[i];

        // if that element is already encountered

        count += freq[complement];

        // update the freq of current element

        freq[arr[i]]++;

    }

    return count;

}

```
