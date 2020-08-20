# [remove-outermost-parentheses](https://leetcode.com/problems/remove-outermost-parentheses/) 

# #1

```java
class Solution {
    public String removeOuterParentheses(String S) {
        StringBuilder s = new StringBuilder();
        int opened = 0;
        for (char c : S.toCharArray()) {
            if (c == '(' && opened++ > 0) s.append(c);
            if (c == ')' && opened-- > 1) s.append(c);
        }
        return s.toString();
    }
} 

```

# #2

```java
class Solution {
     public String removeOuterParentheses(String S) {
        Stack<Character> stack = new Stack<>();
        int flag = 0;
        StringBuilder stringBuilder = new StringBuilder();
        for (int i = 0;i < S.length(); ++i) {
            if ( S.charAt(i) == '(') {
                stack.push('(');
            } else {
                stack.pop();
                if (stack.isEmpty()) {
                    stringBuilder.append(S, flag + 1, i);
                    flag = i + 1;
                }
            }
        }
        return stringBuilder.toString();
    }
}
```





