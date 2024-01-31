

leetcode 
```cpp
class Solution {
public:
    int evalRPN(vector<string>& arr) {
        
        stack<int> st;
        
        for(int i=0 ; i<arr.size() ; i++) {
            
            // check for operators
            if(arr[i] != "+" && arr[i] != "-" && arr[i] != "*" && arr[i] != "/") {
                st.push(stoi(arr[i]));
                continue;
            }
            
            int second = st.top(); st.pop();
            int first = st.top(); st.pop();
            
            if(arr[i] == "+") st.push(first + second);
            else if(arr[i] == "-") st.push(first - second);
            else if(arr[i] == "*") st.push(first * second);
            else if(arr[i] == "/") st.push(first / second);
            
        }
        
        return st.top();
    }
};
```




code studio
```cpp
#include <bits/stdc++.h>

#include <cmath>
using namespace std;

const int MOD = 1e9 + 7;

int evaluateRPN(vector<string> &exp) {
    // Write your code here.
    stack<int> st;

    for (const string &token : exp) {
        if (isdigit(token[0]) ||
            (token[0] == '-' && token.size() > 1 && isdigit(token[1]))) {
            // If the token is a number (including negative numbers)
            st.push(stoi(token));
        } else {
            // If the token is an operator
            int second = st.top();
            st.pop();
            int first = st.top();
            st.pop();

            if (token == "+") {
                st.push((first + second) % MOD);
            } else if (token == "-") {
                st.push((first - second + MOD) % MOD);
            } else if (token == "*") {
                st.push((1LL * first * second) % MOD);
            } else if (token == "/") {
                // Handle division with modulo
                int invSecond = pow(second, MOD - 2, MOD);
                st.push((1LL * first * invSecond) % MOD);
            }
        }
    }

    return st.top();
}
```