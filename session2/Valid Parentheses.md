```cpp
#include <bits/stdc++.h>

bool isValidParenthesis(string s) {
  stack<int> st;

  for (int i = 0; i < s.size(); i++) {
    if (s[i] == '(' || s[i] == '{' || s[i] == '[')
      st.push(s[i]);
      
    else {
      if (st.empty()) return false;
      if (s[i] == ')') {
        if (st.top() != '(') return false;
        st.pop();
      } else if (s[i] == '}') {
        if (st.top() != '{') return false;
        st.pop();
      } else if (s[i] == ']') {
        if (st.top() != '[') return false;
        st.pop();
      }
    }
  }

  if (st.size() == 0) return true;
  return false;
}
```
