
1. Simple Extra Space Method
```cpp
string reverseString(string str)

{

    string ans = "";

    int n = str.size()-1;

  

    for(int i=n ; i>=0 ; i--) {

        ans += str[i];

    }

  

    return ans;

}
```
2. Two Index Approach
```cpp
#include <bits/stdc++.h> 
string reverseString(string str)
{
	// Write your code here.
	int i = 0;
	int j = str.length()-1;

	while(i < j)
	{
		swap(str[i],str[j]);	
		i++;
		j--;
	}

	return str;
}
```
3. Pointer Approach
```cpp
string reverseString(string& str) {

    char* start = &str[0];

    char* end = &str[str.size() - 1];

    while (start < end) {
        char temp = *start;
        *start = *end;
        *end = temp;
        start++;
        end--;
    }
    
    return str;
}
```