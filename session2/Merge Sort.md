```cpp
void merge(vector<int> &arr, int start, int mid, int end) {
  vector<int> temp;

  int i = start;
  int j = mid + 1;

  while (i <= mid && j <= end) {
    if (arr[i] <= arr[j]) {
      temp.push_back(arr[i]);
      i++;
    } else {
      temp.push_back(arr[j]);
      j++;
    }
  }

  while (i <= mid) {
    temp.push_back(arr[i]);
    i++;
  }

  while (j <= end) {
    temp.push_back(arr[j]);
    j++;
  }

  for (int x = start; x <= end; x++) {
    arr[x] = temp[x - start];
  }
}

void sort(vector<int> &arr, int start, int end) {
  if (start >= end) return;

  int mid = (start + end) / 2;

  sort(arr, start, mid);
  sort(arr, mid + 1, end);

  merge(arr, start, mid, end);
}

void mergeSort(vector<int> &arr, int n) {
  // just helping function
  sort(arr, 0, n - 1);
}
```